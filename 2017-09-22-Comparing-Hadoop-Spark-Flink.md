---

layout: post
title: Hadoop vs Spark vs Flink
author: Sivan Sasidharan
tags: 'bigdata, hadoop, apache spark, flink, hortonworks'
categories: blog
excerpt: Comparing the Three Frameworks - Hadoop/Spark/Flink
date: '2017-09-22'
comments = true

---

<h3 id="hadoop-vs-spark-vs-flink">Hadoop vs Spark vs Flink</h3>
<blockquote>
<p><strong>Data Processing</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Hadoop was designed for batch processing, that means it takes large dataset in input, all at once, processes it and produces the result. Batch processing is very efficient in processing in high volume data. Depending on the size of the data being processed and the computational power of the system, output can be delayed significantly</code></td>
<td><code>Apache Spark is also a part of Hadoop Ecosystem, it is a batch processing System at heart too but it also supports stream processing</code></td>
<td><code>Flink provides single runtime for the streaming and as well batch processing so one common runtime is utilized for data streaming application and batch processing application</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Streaming Engine</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Map-reduce is batch- oriented processing tool. It takes large dataset in input, all at once, processes it and produces the result</code></td>
<td><code>Spark Streaming processes data streams in micro-batches, where each batch contains a collection of events that arrived over the batch period. But it is not sufficient for use cases where we need to process large streams of live data and provide results in real time</code></td>
<td><code>Apache Flink is the true streaming engine that uses streams for workloads: streaming, SQL, micro-batch and batch. Batch is a finite set of streamed data</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Data Flow</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>MapReduce computation dataflow does not have any loops, it is a chain of stages; at each stage you progress forward using output of previous stage and producing input for the next stage.</code></td>
<td><code>Though Machine Learning algorithm is a cyclic data flow, it is represented as direct acyclic graph inside the spark.</code></td>
<td><code>Flink takes a different approach than others. It supports controlled cyclic dependency graph in run time. This helps it in representing the Machine Learning algorithms in a very efficient way</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Computation Model</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>MapReduce adopted batch-oriented model. Batch is essentially processing data at rest, taking a large amount of data at once, processing it and then writing out the output</code></td>
<td><code>Spark has adopted micro-batching. Micro-batches are an essentially “collect and then process” kind of computational model</code></td>
<td><code>Flink has adopted a continuous flow, operator-based streaming model. A continuous flow operator processes data when it arrives, without any delay in collecting the data or processing the data</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Performance</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Hadoop supports batch processing only. It doesn’t process streamed data hence overall performance is slower when compared</code></td>
<td><code>Though Apache Spark has an excellent community background and now It is considered as most matured community. But Its stream processing is not much efficient than Apache Flink as it uses micro-batch processing</code></td>
<td><code>Overall performance of Apache Flink is excellent as compared to any other data processing system. Apache Flink uses native closed loop iteration operators which makes machine learning and graph processing more faster when we compare Flink and Spark and Hadoop</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Memory management</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Hadoop provides configurable Memory management. You can do it dynamically or statically</code></td>
<td><code>Spark provides configurable memory management. The latest release of Spark has moved towards automating memory management</code></td>
<td><code>Flink provides automatic memory management. It has its own memory management system, separate from Java’s garbage collector</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Fault tolerance</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>MapReduce is highly fault tolerant. There is no need to restart the application from scratch in case of any failure in Hadoop</code></td>
<td><code>Spark Streaming recovers lost work and with no extra code or configuration, it delivers exactly-once semantics out of the box</code></td>
<td>’<code>The fault tolerance mechanism followed by Apache Flink is based on Chandy-Lamport distributed snapshots. The mechanism is lightweight, which results in maintaining high throughput rates and provide strong consistency guarantees at the same time</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Scalability</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>MapReduce has incredible scalability potential and has been used in production on tens of thousands of Nodes</code></td>
<td><code>Spark is highly scalable, we can keep adding n number of nodes in the cluster. A large known spark cluster is of 8000 nodes</code></td>
<td><code>Flink is also highly scalable, we can keep adding n number of nodes in the cluster A large known Flink cluster is of thousands of nodes</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Iterative Processing</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Does not support iterative processing</code></td>
<td><code>Spark iterates its data in batches In Spark, each iteration has to be scheduled and executed separately</code></td>
<td><code>Flink iterates data by using its streaming architecture. Flink can be instructed to only process the parts of the data that have actually changed, thus significantly increasing the performance of the job</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Language Support</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Hadoop Supports Primarily Java, other languages supported are c, c++, ruby, groovy, Perl, python</code></td>
<td><code>Spark supports java, Scala, python and R. Spark is implemented in scala, it provides API in other languages like Java, Python, and R.</code></td>
<td>`Flink Supports java, Scala, python and R. Flink is implemented in java. It does provide Scala API too.</td>
</tr>
<tr>
<td>`</td>
<td></td>
<td></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Optimization</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>In MapReduce, jobs have to be manually optimized. There are several ways to optimize the MapReduce Jobs: Configure your cluster correctly, use a combiner , use LZO compression, tune the number of MapReduce Task appropriately and use the most appropriate and compact writable type for your data</code></td>
<td><code>In Apache Spark, jobs have to be manually optimized. There is a new extensible optimizer, Catalyst, based on functional programming construct in scala. Catalyst’s extensible design had two purposes: First, easy to add new optimization techniques. Second, enable external developers to extend the optimizer catalyst</code></td>
<td><code>Flink comes with an optimizer that is independent with actual programming interface. The Flink optimizer works similarly to a relational Database Optimizer, but applies these optimizations to the Flink programs, rather than SQL queries</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p>Latency</p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>The MapReduce framework of Hadoop is relatively slower since it is designed to support different format, structure and huge volume of data. That’s why Hadoop has higher latency than both spark and Flink</code></td>
<td><code>Apache Spark is yet another batch processing system but it is relatively faster than Hadoop MapReduce since it caches much of the input data on memory by RDD and keeps intermediate data in memory itself, eventually writes the data to disk upon completion or whenever required.</code></td>
<td><code>With minimum efforts in configuration, Apache Flink’s data streaming runtime achieves low latency and high throughput</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Processing Speed</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>MapReduce processes slower than spark and flink. The slowness occurs only because of the nature of the MapReduce based execution, where it produces lots of intermediate data, much data exchanged between nodes, thus causes huge disk IO latency. Furthermore, it has to persist much data in disk for synchronization between phases so that it can support Job recovery from failures. Also, there are no ways in MapReduce to cache all subset of the data in memory</code></td>
<td><code>Spark processes faster than MapReduce because it caches much of the input data on memory by RDD and keeps intermediate data in memory itself, eventually writes the data to disk upon completion or whenever required. Spark is 10x times faster than mapreduce and this shows how spark is better than Hadoop MapReduce</code></td>
<td><code>Flink processes faster than Spark because of its streaming architecture. Flink can be instructed to only process the parts of the data that have actually changed, thus significantly increasing the performance of job</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Visualization</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Hadoop data visualization tool is zoomdata that can connect directly to HDFS as well as to SQL-on-Hadoop technologies such as Impala, Hive, Spark SQL, Presto and more</code></td>
<td><code>Spark offers a web interface for submitting and executing jobs on which the resulting execution plan can be visualized. Flink and Spark both are integrated to Apache zeppelin It provides data analytics, ingestion, as well as discovery, visualization, and collaboration</code></td>
<td><code>Flink also offers a web interface for submitting and executing jobs. The resulting execution plan can be visualized on this interface</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Recovery</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>MapReduce is naturally resilient to system faults or failures. It is highly fault tolerant system</code></td>
<td><code>Spark RDDs allow recovery of partitions on failed nodes by re-computation of the DAG while also supporting a more similar recovery style to Hadoop by way of checkpointing, to reduce the dependencies of RDDs</code></td>
<td><code>Flink supports checkpointing mechanism that stores the program in the data sources and data sink, the state of window, as well as user-defined state that recovers streaming job after failure</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Security</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Hadoop supports Kerberos authentication, which is somewhat painful to manage. However, third party vendors have enabled organizations to leverage Active Directory Kerberos and LDAP for authentication.</code></td>
<td><code>Spark’s security is a bit sparse by currently only supporting authentication via shared secret (password authentication). The security bonus that Spark can enjoy is that if you run Spark on HDFS, it can use HDFS ACLs and file-level permissions. Additionally, Spark can run on YARN to use Kerberos authentication</code></td>
<td><code>There is user-authentication support in Flink via the Hadoop / Kerberos infrastructure. If you run Flink on YARN, Flink acquires the Kerberos tokens of the user that submits programs, and authenticate itself at YARN, HDFS, and HBase with that.Flink’s upcoming connector, streaming programs can authenticate themselves as stream brokers via SSL</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Cost</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>MapReduce can typically run on less expensive hardware than some alternatives since it does not attempt to store everything in memory</code></td>
<td><code>As spark requires a lot of RAM to run in-memory, increasing it in cluster, gradually increases its cost.</code></td>
<td><code>Flink also requires a lot of RAM to run in-memory, so it will increase its cost gradually.</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Compatibility</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Hadoop MapReduce and Apache Spark are compatible with each other and Spark shares all MapReduce’s compatibilities for data sources, file formats and business intelligence tools via JDBC and ODBC</code></td>
<td><code>Spark and hadoop are compatible to each other. Spark is compatible with Hadoop data. It can run in Hadoop clusters through YARN or Spark’s standalone mode, and it can process data in HDFS, HBase, Cassandra, Hive, and any Hadoop InputFormat</code></td>
<td><code>Flink is a scalable data analytics framework that is fully compatible to Hadoop. It provides a Hadoop Compatibility package to wrap functions implemented against Hadoop’s MapReduce interfaces and embed them in Flink programs</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Interactive Mode</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>MapReduce does not have interactive Mode</code></td>
<td><code>Spark has an interactive shell to learn how to make the most out of Apache Spark. This is a Spark application written in Scala to offer a command-line environment with auto-completion where you can run ad-hoc queries and get familiar with the features of Spark</code></td>
<td><code>Flink comes with an integrated interactive Scala Shell. It can be used in a local setup as well as in a cluster setup</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Real time Analysis</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>MapReduce fails when it comes to real-time data processing as it was designed to perform batch processing on voluminous amounts of data</code></td>
<td><code>It can process real time data ie data coming from the real-time event streams at the rate of millions of events per second</code></td>
<td><code>It is mainly used for real-time data Analysis Although it also provides fast batch data Processing</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Abstraction</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>In Mapreduce, we don’t have any type of abstraction.</code></td>
<td><code>In Spark, for batch we have Spark RDD abstraction and DStream for streaming which is internally RDD itself.</code></td>
<td><code>In flink, we have Dataset abstraction for batch and DataStreams for the streaming application</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Machine Learning</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Hadoop requires machine learning tool like Apache Mahout</code></td>
<td><code>Spark has its own set of machine learning MLlib. Within memory caching and other implementation details, it’s really powerful platform to implement ML algorithms</code></td>
<td><code>Flink has FlinkML which is Machine Learning library for Flink. It supports controlled cyclic dependency graph in runtime. This makes them represent the ML algorithms in a very efficient way compared to DAG representation.</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Scheduler</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Scheduler in Hadoop becomes the pluggable component. There are two schedulers for multi user workload: fair Scheduler and capacity Scheduler. To schedule complex flows, MapReduce needs an external job scheduler like Oozie.</code></td>
<td><code>Due to in-memory computation, spark acts its own flow scheduler. Can be configured with YARN Scheduler</code></td>
<td><code>Flink can use YARN Scheduler but Flink also has its own Scheduler</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>SQL support</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>It enables users to run SQL queries using Apache Hive</code></td>
<td><code>It enables users to run SQL queries using Spark-SQL. Spark provides both Hive like query language and Dataframe like DSL for querying structured data</code></td>
<td><code>In Flink, Table API is an SQL-like expression language that supports data frame like DSL and it’s still in beta. There are plans to add the SQL interface but not sure when it will land in the framework</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Caching</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>MapReduce cannot cache the data in memory for future requirements</code></td>
<td><code>Spark can cache data in memory for further iterations which enhance its performance</code></td>
<td><code>Flink can cache data in memory for further iterations to enhance its performance</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Deployment</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>In Standalone mode, Hadoop is configured to run in a single-node, non-distributed mode. In pseudo Distributed mode, Hadoop runs in a pseudo distributed mode. The difference is that each Hadoop daemon runs in a separate java process in pseudo-distributed mode. Whereas in local mode each Hadoop daemon runs as a single java process. In a fully-distributed mode, all daemons are executed in separate nodes forming a multi-node cluster</code></td>
<td><code>In addition to running on the Mesos or YARN cluster managers, Spark also provides a simple standalone deploy mode. It can be launched either manually, by starting a master and workers by hand or use our provided launch scripts. It is also possible to run these daemons on a single machine for testing</code></td>
<td><code>In addition to running on YARN cluster Managers, Flink also provides standalone deploy mode</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Duplication elimination</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>There is no duplication elimination in Hadoop</code></td>
<td><code>Spark also process every record exactly one time hence eliminates duplication.</code></td>
<td><code>Apache Flink processes every record exactly one time hence eliminates duplication. Streaming applications can maintain custom state during their computation. Flink’s checkpointing mechanism ensures exactly once semantics for the state in the presence of failures</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Window criteria</strong></p>
</blockquote>
<p>A data stream needs to be grouped into multiple logical streams on each of which a window operator can be applied.</p>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Hadoop doesn’t support streaming so there is no need of window criteria</code></td>
<td><code>Spark has time-based window criteria</code></td>
<td><code>Flink has record-based or any custom user-defined Flink Window criteria</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Back pressure Handing</strong></p>
</blockquote>
<p>BackPressure refers to the buildup of data at an I/O switch when buffers are full and not able to receive additional data. No additional data packets are transferred until the bottleneck of data has been eliminated or the buffer has been emptied.</p>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Hadoop handles back pressure through Manual Configuration</code></td>
<td><code>Spark also handles back pressure through Manual Configuration</code></td>
<td><code>Flink handles back pressure Implicitly through System Architecture</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Hardware Requirements</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>MapReduce runs very well on commodity Hardware</code></td>
<td><code>Spark needs mid to high-level hardware because Spark cache data in memory for further iterations which enhance its performance</code></td>
<td><code>Flink also needs mid to High-level Hardware. Flink can also cache data in memory for further iterations which enhance its performance.</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>High Availability</strong></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Configurable in High Availability Mode</code></td>
<td><code>Configurable in High Availability Mode</code></td>
<td><code>Configurable in High Availability Mode</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Amazon S3 connector</strong><br>
<em>Amazon Simple Storage Service (Amazon S3) is object storage with a simple web service interface to store and retrieve any amount of data from anywhere on the web</em></p>
</blockquote>

<table>
<thead>
<tr>
<th>Hadoop</th>
<th>Spark</th>
<th>Flink</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Provides Supports for Amazon S3 Connector</code></td>
<td><code>Provides Supports for Amazon S3 Connector</code></td>
<td><code>Provides Supports for Amazon S3 Connector</code></td>
</tr>
</tbody>
</table><hr>
<blockquote>
<p><strong>Apache License</strong></p>
</blockquote>
<p>All the three are Apache Licensed.<br>
The Apache License, Version 2.0 (ALv2) is a permissive free software license written by the Apache Software Foundation (ASF). The Apache License requires preservation of the copyright notice and disclaimer.</p>
<hr>
<h5 id="references">References</h5>
<p><a href="http://flink.apache.org">Apache Flink</a><br>
<a href="https://spark.apache.org/">Apache Spark</a><br>
<a href="http://hadoop.apache.org/">Apache Hadoop</a><br>
<a href="http://blog.cloudera.com/blog">Cloudera Blog</a><br>
<a href="https://hortonworks.com/blog/">Hortonworks Blog</a></p>

