# Scala_Spark_Course

## Course "Apache Spark 2.0 with Scala- Hands on with Big Data" by Frank Kane.

### Scala
```
sparkContext
.broadcast()
accumulator
```
* apply Breadth-First Search(BFS) in spark
* item-based collaborative filtering (cache(), persist())

* Spark Cluster
* SparkSQL/ DataFrame / DataSets
* MLLib
* Spark Streaming
* GraphX

### Packaging and deploying scala spark driver scripts to cluster
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
