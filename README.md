# Scala_Spark_Course

## Course "Apache Spark 2.0 with Scala- Hands on with Big Data" by Frank Kane.

### Scala
```
SparkContext
SparkConf
.broadcast()
accumulator
```
* apply Breadth-First Search(BFS) in spark
* item-based collaborative filtering (cache(), persist())

* Spark Cluster & AWS EMR(Elastic MapReducer)
* Partition
```
.partitionBy()
```
* methods benefits from partitioning
```
.join()
.cogroup()
.groupWith()
.leftOuterJoin()
.rightOuterJoin()
.groupByKey()
.reduceByKey()
.combineByKey()
.lookup()
```

* Best Practice using Cluster
1. Use an empty, default SparkConf in the your driver
   -- this way, we will use the default EMR sets up instead,
   as well as any command-line options you pass into spark-submit from your master node.
2. If executors start failing, may need to adjust memory each executor has. e.g.
```
spark-submit --executor-memory 1g MovieSimilarities1M.py 260
```
* SparkSQL/ DataFrame / DataSets
* MLLib
* Spark Streaming
* GraphX

### Packaging and deploying scala spark driver scripts to cluster
* spark-submit
```
spark-submit
 --class <class object that contains your main function>
 --jars <path to any dependencies>
 --files <files you want placed alongside your application>
 <your JAR file>
```
```
spark-submit --class main.scala.com.sundogsoftware.spark.MovieSimilarities MovieSimilarities.jar 50
```

* spark-submit parameters
```
--master
--num-executors
--executor-memory
--total-executor-cores
```
* sbt (jar file is in the target/scala-2.x)
```
sbt assembly
```
### Methods used in the course:
```
.collect()
```
```
.map()
.mapValue()
.flatMap()
```
```
.max()
.min()
```
```
.getLines()
```
```
.filter()
```
```
.reduceByKey
.sortByKey
```
