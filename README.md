# Scala_Spark

## Course "Apache Spark 2.0 with Scala- Hands on with Big Data" by Frank Kane.

### Scala
```
SparkContext
SparkConf
.broadcast()
accumulator
```
#### Apply Breadth-First Search(BFS) in spark
#### Item-based collaborative filtering (cache(), persist())

#### Spark Cluster & AWS EMR(Elastic MapReducer)
##### Packaging and deploying scala spark driver scripts to cluster
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
##### Partition
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
3. Can use -master yarn to run on a YARN cluster.(EMR sets it for you)
4. Get scripts & data someplace where EMR can access easily(e.g s3 link s3n://xxx)
5. Spin up EMR cluster for Spark using AWS console to reduce billing.
6. Get external DNS name for master node, and log into it using hadoop user account and private key file.
7. Copy driver program's JAR file and any files it needs.(e.g. save in s3).
8. Run spark-submit and watch output!
9. Terminate cluster when tasks are done!


#### SparkSQL/ DataFrame / DataSets
#### MLLib
#### Spark Streaming
#### GraphX

#### Troubleshooting and managing dependencies
* Spark UI (good monitor tool). After spark-submit, go to http://127.0.0.1:4040
* If in AWS EMR, save logging in s3 and check them.
* In Yarn, collecting logging is needed because they are distributed.
```
yarn logs -applicationID <app ID>
```
* While driver scripts runs, it will log errros like executors failing to issues heartbeats. Then the following action may need:
1. too much load for each executor.
2. need more machines in your cluster.
3. executor needs more memory.
4. use partitionBy() to demand less work from individual executor by using smaller partitions.

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
