# SparkDemo_PageRank
Project Goals and Outcomes
This week we learned about two different implementations of the MapReduce programming abstraction: Hadoop and Spark.

Hadoop was one of the first popular distributed MapReduce programming systems, and really paved the way for Big Data analysis at massive scales on commodity hardware. As described in lectures this week, its primary strengths are three-fold: 1) scalability, 2) programmability, and 3) fault tolerance. Hadoop allows programmers to write simple Java applications that run across thousands of networked machines and which, thanks to its MapReduce abstractions, can recover from complete hardware failure of many of those machines.

Spark, on the other hand, is a successor to Hadoop that emphasizes in-memory caching of data and a more flexible API. While Hadoop regularly persisted replicated data to disk to ensure fault tolerance, Spark instead caches information in memory and ensures that it remembers the transformations that were applied to generate a particular piece of data. Spark also offers more than simple map and reduce transformations.

You also learned about the PageRank algorithm, and how it can be used to rank inter-connected websites based on existing ranks and link counts.

In this mini-project, you will gain experience with Spark by implementing the PageRank algorithm using Spark transformations. In particular, this assignment will ask you to implement the transformations needed to complete a single iteration of the iterative PageRank algorithm given an input Spark Resilient Distributed Dataset (RDD) of websites.

Recall from lectures this week that an important concept in MapReduce frameworks is that of "key-value pairs". The key of a key-value pair is some unique identifier for some logical object, e.g. a website. The value is some metadata associated with the logical object the key identifies, e.g. information on the outbound links for a website. In Spark, a key-value pair is represented using the Tuple2 class. For example, to create a new key-value pair from some key k and some value v you can use the following code:



1
Tuple2 kvPair = new Tuple2(k, v);
Spark uses special-purpose RDD objects to store datasets containing Tuple2 objects (i.e. key-value pairs). Rather than using the standard JavaRDD class, RDDs of Tuple2 objects use the JavaPairRDD class.
