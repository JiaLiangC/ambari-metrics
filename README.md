# ambari-metrics
Apache Ambari subproject - Ambari Metrics

Ambari Metrics System ("AMS") is a system for collecting, aggregating, serving and visualizing daemon and system metrics in Ambari-managed clusters.

The original JIRA Epic for Ambari Metrics System can be found here: https://issues.apache.org/jira/browse/AMBARI-5707 
First official release of AMS was with Ambari 2.0.0. With metrics repro split, the aim is to be able to release the sub-project with separate cadence than Amabri.

 ---------------------------------------------------------------------------------------------------------
| Term                  | Definition                                                                      |
 ---------------------------------------------------------------------------------------------------------
| Metrics Collector     | The standalone server that collects metrics, aggregates metrics, serves metrics |
|                       | from the Hadoop service sinks and the Metrics Monitor.                          |
| Metrics Monitor       | Installed on each host in the cluster to collect system-level metrics and       |
|                       | forward to the Metrics Collector.                                               |
| Metrics Hadoop Sinks  | Plug-ins into the various Hadoop components sinks to send Hadoop metrics to the |
|                       | Metrics Collector.                                                              |
-----------------------------------------------------------------------------------------------------------

The Metrics Collector is daemon that receives data from registered publishers (the Monitors and Sinks). 
The Collector itself is build using Hadoop technologies such as HBase Phoenix and ATS. 
The Collector can store data on the local filesystem (referred to as "embedded mode") or use an external HDFS (referred to as "distributed mode").
It is a fully distributed collection and aggregation system starting from 2.7.0

Please refer to the wiki for more detailed info: https://cwiki.apache.org/confluence/display/AMBARI/Metrics

