---
layout: post
category: blog
title: "Hadoop vs Spark vs Flink"
excerpt: "Comparing the Three Frameworks - Hadoop/Spark/Flink"
tags: [bigdata, hadoop, apache spark, flink, hortonworks]
Hortonworks: http://hortonworks.com/products/hortonworks-sandbox/
comments: true
---

#### Hadoop vs Spark vs Flink

> Data Processing

__Hadoop:__ Hadoop was designed for batch processing, that means it takes large dataset in input, all at once, processes it and produces the result. Batch processing is very efficient in processing in high volume data. Depending on the size of the data being processed and the computational power of the system, output can be delayed significantly.

__Spark:__ Apache Spark is also a part of Hadoop Ecosystem, it is a batch processing System at heart too but it also supports stream processing.

__Flink:__ Flink provides single runtime for the streaming and as well batch processing so one common runtime is utilized for data streaming application and batch processing application.

---

> Streaming Engine

__Hadoop:__ Map-reduce is batch- oriented processing tool. It takes large dataset in input, all at once, processes it and produces the result.

__Spark:__ Spark Streaming processes data streams in micro-batches, where each batch contains a collection of events that arrived over the batch period. But it is not sufficient for use cases where we need to process large streams of live data and provide results in real time.

__Flink:__ Apache Flink is the true streaming engine that uses streams for workloads: streaming, SQL, micro-batch and batch. Batch is a finite set of streamed data.

---

>  Data Flow

__Hadoop:__ MapReduce computation dataflow does not have any loops, it is a chain of stages; at each stage you progress forward using output of previous stage and producing input for the next stage.

__Spark:__ Though Machine Learning algorithm is a cyclic data flow, it is represented as direct acyclic graph inside the spark.

__Flink:__ Flink takes a different approach than others. It supports controlled cyclic dependency graph in run time. This helps it in representing the Machine Learning algorithms in a very efficient way.

---

>  Computation Model

__Hadoop:__ MapReduce adopted batch-oriented model. Batch is essentially processing data at rest, taking a large amount of data at once, processing it and then writing out the output.

__Spark:__ Spark has adopted micro-batching. Micro-batches are an essentially “collect and then process” kind of computational model.

__Flink:__ Flink has adopted a continuous flow, operator-based streaming model. A continuous flow operator processes data when it arrives, without any delay in collecting the data or processing the data.

---

>  Performance

__Hadoop:__ Hadoop supports batch processing only. It doesn’t process streamed data hence overall performance is slower when compared Hadoop vs Spark vs flink.

__Spark:__ Though Apache Spark has an excellent community background and now It is considered as most matured community. But Its stream processing is not much efficient than Apache Flink as it uses micro-batch processing.

__Flink:__ Overall performance of Apache Flink is excellent as compared to any other data processing system. Apache Flink uses native closed loop iteration operators which makes machine learning and graph processing more faster when we compare Flink and Spark and Hadoop.

---

>  Memory management

__Hadoop:__ Hadoop provides configurable Memory management. You can do it dynamically or statically.

__Spark:__ Spark provides configurable memory management. The latest release of Spark has moved towards automating memory management.

__Flink:__ Flink provides automatic memory management. It has its own memory management system, separate from Java’s garbage collector.

---

>  Fault tolerance

__Hadoop:__ MapReduce is highly fault tolerant. There is no need to restart the application from scratch in case of any failure in Hadoop.

__Spark:__ Spark Streaming recovers lost work and with no extra code or configuration, it delivers exactly-once semantics out of the box.

__Flink:__ The fault tolerance mechanism followed by Apache Flink is based on Chandy-Lamport distributed snapshots. The mechanism is lightweight, which results in maintaining high throughput rates and provide strong consistency guarantees at the same time.

---

>  Scalability

__Hadoop:__ MapReduce has incredible scalability potential and has been used in production on tens of thousands of Nodes.

__Spark:__ Spark is highly scalable, we can keep adding n number of nodes in the cluster. A large known spark cluster is of 8000 nodes.

__Flink:__ Flink is also highly scalable, we can keep adding n number of nodes in the cluster A large known Flink cluster is of thousands of nodes.

---
>  Iterative Processing

__Hadoop:__ It does not support iterative processing

__Spark:__ Spark iterates its data in batches In Spark, each iteration has to be scheduled and executed separately.

__Flink:__ Flink iterates data by using its streaming architecture. Flink can be instructed to only process the parts of the data that have actually changed, thus significantly increasing the performance of the job.

---

>  Language Support

__Hadoop:__ Hadoop Supports Primarily Java, other languages supported are c, c++, ruby, groovy, Perl, python.

__Spark:__ Spark supports java, Scala, python and R. Spark is implemented in scala, it provides API in other languages like Java, Python, and R.

__Flink:__ Flink Supports java, Scala, python and R. Flink is implemented in java. It does provide Scala API too.

---

>  Optimization

__Hadoop:__ In MapReduce, jobs have to be manually optimized. There are several ways to optimize the MapReduce Jobs: Configure your cluster correctly, use a combiner , use LZO compression, tune the number of MapReduce Task appropriately and use the most appropriate and compact writable type for your data.

__Spark:__ In Apache Spark, jobs have to be manually optimized. There is a new extensible optimizer, Catalyst, based on functional programming construct in scala. Catalyst’s extensible design had two purposes: First, easy to add new optimization techniques. Second, enable external developers to extend the optimizer catalyst.

__Flink:__ Flink comes with an optimizer that is independent with actual programming interface. The Flink optimizer works similarly to a relational Database Optimizer, but applies these optimizations to the Flink programs, rather than SQL queries.

---


>  Latency

__Hadoop:__ The MapReduce framework of Hadoop is relatively slower since it is designed to support different format, structure and huge volume of data. That’s why Hadoop has higher latency than both spark and Flink.

__Spark:__ Apache Spark is yet another batch processing system but it is relatively faster than Hadoop MapReduce since it caches much of the input data on memory by RDD and keeps intermediate data in memory itself, eventually writes the data to disk upon completion or whenever required.

__Flink:__ With minimum efforts in configuration, Apache Flink’s data streaming runtime achieves low latency and high throughput.

---

>  Processing Speed

__Hadoop:__ MapReduce processes slower than spark and flink. The slowness occurs only because of the nature of the MapReduce based execution, where it produces lots of intermediate data, much data exchanged between nodes, thus causes huge disk IO latency. Furthermore, it has to persist much data in disk for synchronization between phases so that it can support Job recovery from failures. Also, there are no ways in MapReduce to cache all subset of the data in memory.

__Spark:__ Spark processes faster than MapReduce because it caches much of the input data on memory by RDD and keeps intermediate data in memory itself, eventually writes the data to disk upon completion or whenever required. Spark is 10x times faster than mapreduce and this shows how spark is better than Hadoop MapReduce.

__Flink:__ Flink processes faster than Spark because of its streaming architecture. Flink can be instructed to only process the parts of the data that have actually changed, thus significantly increasing the performance of job.

---

> Visualization

__Hadoop:__ Hadoop data visualization tool is zoomdata that can connect directly to HDFS as well as to SQL-on-Hadoop technologies such as Impala, Hive, Spark SQL, Presto and more.

__Spark:__ Spark offers a web interface for submitting and executing jobs on which the resulting execution plan can be visualized. Flink and Spark both are integrated to Apache zeppelin It provides data analytics, ingestion, as well as discovery, visualization, and collaboration.

__Flink:__ Flink also offers a web interface for submitting and executing jobs. The resulting execution plan can be visualized on this interface.

---

> Recovery

__Hadoop:__ MapReduce is naturally resilient to system faults or failures. It is highly fault tolerant system.

__Spark:__ Spark RDDs allow recovery of partitions on failed nodes by re-computation of the DAG while also supporting a more similar recovery style to Hadoop by way of checkpointing, to reduce the dependencies of RDDs.

__Flink:__ Flink supports checkpointing mechanism that stores the program in the data sources and data sink, the state of window, as well as user-defined state that recovers streaming job after failure.

---

> Security

__Hadoop:__ Hadoop supports Kerberos authentication, which is somewhat painful to manage. However, third party vendors have enabled organizations to leverage Active Directory Kerberos and LDAP for authentication.

__Spark:__ Spark’s security is a bit sparse by currently only supporting authentication via shared secret (password authentication). The security bonus that Spark can enjoy is that if you run Spark on HDFS, it can use HDFS ACLs and file-level permissions. Additionally, Spark can run on YARN to use Kerberos authentication.

__Flink:__ There is user-authentication support in Flink via the Hadoop / Kerberos infrastructure. If you run Flink on YARN, Flink acquires the Kerberos tokens of the user that submits programs, and authenticate itself at YARN, HDFS, and HBase with that.Flink’s upcoming connector, streaming programs can authenticate themselves as stream brokers via SSL.

---

> Cost

__Hadoop:__ MapReduce can typically run on less expensive hardware than some alternatives since it does not attempt to store everything in memory.

__Spark:__ As spark requires a lot of RAM to run in-memory, increasing it in cluster, gradually increases its cost.

__Flink:__ Flink also requires a lot of RAM to run in-memory, so it will increase its cost gradually.

---

> Compatibility

__Hadoop:__ Hadoop MapReduce and Apache Spark are compatible with each other and Spark shares all MapReduce’s compatibilities for data sources, file formats and business intelligence tools via JDBC and ODBC.

__Spark:__  Spark and hadoop are compatible to each other. Spark is compatible with Hadoop data. It can run in Hadoop clusters through YARN or Spark’s standalone mode, and it can process data in HDFS, HBase, Cassandra, Hive, and any Hadoop InputFormat.

__Flink:__ Flink is a scalable data analytics framework that is fully compatible to Hadoop. It provides a Hadoop Compatibility package to wrap functions implemented against Hadoop’s MapReduce interfaces and embed them in Flink programs.

---

> Interactive Mode

__Hadoop:__ MapReduce does not have interactive Mode.

__Spark:__  Spark has an interactive shell to learn how to make the most out of Apache Spark. This is a Spark application written in Scala to offer a command-line environment with auto-completion where you can run ad-hoc queries and get familiar with the features of Spark.

__Flink:__ Flink comes with an integrated interactive Scala Shell. It can be used in a local setup as well as in a cluster setup

---

> Real time Analysis

__Hadoop:__ MapReduce fails when it comes to real-time data processing as it was designed to perform batch processing on voluminous amounts of data.

__Spark:__  It can process real time data ie data coming from the real-time event streams at the rate of millions of events per second.

__Flink:__ It is mainly used for real-time data Analysis Although it also provides fast batch data Processing.

---

> Abstraction

__Hadoop:__ In Mapreduce, we don’t have any type of abstraction.

__Spark:__  In Spark, for batch we have Spark RDD abstraction and DStream for streaming which is internally RDD itself.

__Flink:__ In flink, we have Dataset abstraction for batch and DataStreams for the streaming application.

---

> Machine Learning

__Hadoop:__ Hadoop requires machine learning tool like Apache Mahout.

__Spark:__  Spark has its own set of machine learning MLlib. Within memory caching and other implementation details, it’s really powerful platform to implement ML algorithms.

__Flink:__ Flink has FlinkML which is Machine Learning library for Flink. It supports controlled cyclic dependency graph in runtime. This makes them represent the ML algorithms in a very efficient way compared to DAG representation.

---

> Scheduler

__Hadoop:__ Scheduler in Hadoop becomes the pluggable component. There are two schedulers for multi user workload: fair Scheduler and capacity Scheduler. To schedule complex flows, MapReduce needs an external job scheduler like Oozie.

__Spark:__  Due to in-memory computation, spark acts its own flow scheduler.

__Flink:__ Flink can use YARN Scheduler but Flink also has its own Scheduler.

---

> SQL support

__Hadoop:__ It enables users to run SQL queries using Apache Hive.

__Spark:__  It enables users to run SQL queries using Spark-SQL. Spark provides both Hive like query language and Dataframe like DSL for querying structured data.

__Flink:__ In Flink, Table API is an SQL-like expression language that supports data frame like DSL and it’s still in beta. There are plans to add the SQL interface but not sure when it will land in the framework.

---

> Caching

__Hadoop:__ MapReduce cannot cache the data in memory for future requirements

__Spark:__  Spark can cache data in memory for further iterations which enhance its performance.

__Flink:__ Flink can cache data in memory for further iterations to enhance its performance.

---

> Deployment

__Hadoop:__ In Standalone mode, Hadoop is configured to run in a single-node, non-distributed mode. In pseudo Distributed mode, Hadoop runs in a pseudo distributed mode. The difference is that each Hadoop daemon runs in a separate java process in pseudo-distributed mode. Whereas in local mode each Hadoop daemon runs as a single java process. In a fully-distributed mode, all daemons are executed in separate nodes forming a multi-node cluster.

__Spark:__  In addition to running on the Mesos or YARN cluster managers, Spark also provides a simple standalone deploy mode. It can be launched either manually, by starting a master and workers by hand or use our provided launch scripts. It is also possible to run these daemons on a single machine for testing

__Flink:__ In addition to running on YARN cluster Managers, Flink also provides standalone deploy mode.

---


> Duplication elimination

__Hadoop:__ There is no duplication elimination in Hadoop.

__Spark:__  Spark also process every record exactly one time hence eliminates duplication.

__Flink:__ Apache Flink processes every record exactly one time hence eliminates duplication. Streaming applications can maintain custom state during their computation. Flink’s checkpointing mechanism ensures exactly once semantics for the state in the presence of failures.

---

> Window criteria

A data stream needs to be grouped into multiple logical streams on each of which a window operator can be applied.

__Hadoop:__ Hadoop doesn’t support streaming so there is no need of window criteria.

__Spark:__  Spark has time-based window criteria.

__Flink:__ Flink has record-based or any custom user-defined Flink Window criteria.

---

> Back pressure Handing

BackPressure refers to the buildup of data at an I/O switch when buffers are full and not able to receive additional data. No additional data packets are transferred until the bottleneck of data has been eliminated or the buffer has been emptied.

__Hadoop:__ Hadoop handles back pressure through Manual Configuration.

__Spark:__  Spark also handles back pressure through Manual Configuration.

__Flink:__ Flink handles back pressure Implicitly through System Architecture.

---

> Hardware Requirements

__Hadoop:__ MapReduce runs very well on commodity Hardware

__Spark:__  Spark needs mid to high-level hardware because Spark cache data in memory for further iterations which enhance its performance.

__Flink:__ Flink also needs mid to High-level Hardware. Flink can also cache data in memory for further iterations which enhance its performance.

---

> High Availability

__Hadoop:__ Configurable in High Availability Mode

__Spark:__  Configurable in High Availability Mode

__Flink:__ Configurable in High Availability Mode

---

> Amazon S3 connector 
_Amazon Simple Storage Service (Amazon S3) is object storage with a simple web service interface to store and retrieve any amount of data from anywhere on the web_

__Hadoop:__ Provides Supports for Amazon S3 Connector

__Spark:__  Provides Supports for Amazon S3 Connector

__Flink:__ Provides Supports for Amazon S3 Connector

---

> Apache License

All the three are Apache Licensed. 
The Apache License, Version 2.0 (ALv2) is a permissive free software license written by the Apache Software Foundation (ASF). The Apache License requires preservation of the copyright notice and disclaimer.

---

##### References 

[Apache Flink](http://flink.apache.org)
[Apache Spark](https://spark.apache.org/)
[Apache Hadoop](http://hadoop.apache.org/)
[Cloudera Blog](http://blog.cloudera.com/blog)
[Hortonworks Blog](https://hortonworks.com/blog/)