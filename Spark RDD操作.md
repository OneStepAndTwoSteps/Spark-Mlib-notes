## RDD操作

### fileter操作：

__案例：FP-growth得到的关联数据__

model.freqItemsets().collect()

__部分数据展示：__

    [FreqItemset(items=['E'], freq=8),
    FreqItemset(items=['E', 'C'], freq=6),
    FreqItemset(items=['E', 'C', 'A'], freq=6),
    FreqItemset(items=['E', 'A'], freq=6),
    FreqItemset(items=['B'], freq=2),
    FreqItemset(items=['B', 'E'], freq=2),
    FreqItemset(items=['B', 'E', 'C'], freq=2),
    FreqItemset(items=['B', 'E', 'C', 'A'], freq=2),
    FreqItemset(items=['B', 'E', 'A'], freq=2),
    FreqItemset(items=['B', 'C'], freq=2),
    FreqItemset(items=['B', 'C', 'A'], freq=2),
    FreqItemset(items=['B', 'A'], freq=2),
    FreqItemset(items=['A'], freq=8),
    FreqItemset(items=['D'], freq=2),
    FreqItemset(items=['D', 'C'], freq=2),

type(model.freqItemsets())   
    
    PythonRDD[40] at RDD at PythonRDD.scala:52

__得到freq=2的数据__

model.freqItemsets().filter(lambda x:2 in x).collect()

    FreqItemset(items=['B'], freq=2),
    FreqItemset(items=['B', 'E'], freq=2),
    FreqItemset(items=['B', 'E', 'C'], freq=2),
    FreqItemset(items=['B', 'E', 'C', 'A'], freq=2),
    FreqItemset(items=['B', 'E', 'A'], freq=2),
    FreqItemset(items=['B', 'C'], freq=2),
    FreqItemset(items=['B', 'C', 'A'], freq=2),
    FreqItemset(items=['B', 'A'], freq=2),
    FreqItemset(items=['D'], freq=2),
    FreqItemset(items=['D', 'C'], freq=2),
    FreqItemset(items=['D', 'C', 'A'], freq=2),
    FreqItemset(items=['D', 'A'], freq=2),
    FreqItemset(items=['F'], freq=2),
    FreqItemset(items=['F', 'E'], freq=2),
    FreqItemset(items=['F', 'E', 'C'], freq=2),
    FreqItemset(items=['F', 'E', 'C', 'A'], freq=2),
    FreqItemset(items=['F', 'E', 'A'], freq=2)

__得到频繁2项集的数据：__

model.freqItemsets().filter(lambda x: len(x.items)== 2 ).collect()

    [FreqItemset(items=['E', 'C'], freq=6),
    FreqItemset(items=['E', 'A'], freq=6),
    FreqItemset(items=['B', 'E'], freq=2),
    FreqItemset(items=['B', 'C'], freq=2),
    FreqItemset(items=['B', 'A'], freq=2),
    FreqItemset(items=['D', 'C'], freq=2),
    FreqItemset(items=['D', 'A'], freq=2),
    FreqItemset(items=['F', 'E'], freq=2),
    FreqItemset(items=['F', 'B'], freq=2),
    FreqItemset(items=['F', 'C'], freq=2),
    FreqItemset(items=['F', 'A'], freq=2),
    FreqItemset(items=['C', 'A'], freq=8),
    FreqItemset(items=['G', 'E'], freq=4),
    FreqItemset(items=['G', 'C'], freq=5),
    FreqItemset(items=['G', 'A'], freq=5)]

