# Assignment-3.3

Q1.Components of hadoop 2.x
Hadoop 2.x Architecture has mainly 2 set of daemons

1.HDFS 2.x Daemons:  Name Node, Secondary Name Node (not required in HA) and Data Nodes
2.MapReduce 2.x Daemons (YARN):  Resource Manager, Node Manager

1.HDFS 2.x Daemons
The working methodology of HDFS 2.x daemons is same as it was in Hadoop 1.x Architecture with following differences.
Hadoop 2.x allows Multiple Name Nodes for HDFS Federation
New Architecture allows HDFS High Availability mode in which it can have Active and StandBy Name Nodes (No Need of Secondary Name Node in this case)
Hadoop 2.x Non HA mode has same Name Node and Secondary Name Node working same as in Hadoop 1.x architecture

2.MapReduce 2.x Daemons (YARN)
MapReduce2 has replace old daemon process Job Tracker and Task Tracker with YARN(Yet Another Resource Negotiator) components Resource Manager and Node Manager respectively. These two components are responsible for executing distributed data computation jobs in Hadoop 2.

a.Resource Manager
This daemon process runs on master node (may run on the same machine as name node for smaller clusters)
It is responsible for getting job submitted from client and schedule it on cluster, monitoring running jobs on cluster and allocating proper resources on the slave node
It communicates with Node Manager daemon process on the slave node to track the resource utilization
It uses two other processes named Application Manager and Scheduler for MapReduce task and resource management

b.Node Manager
This daemon process runs on slave nodes (normally on HDFS Data node machines)
It is responsible for coordinating with Resource Manager for task scheduling and tracking the resource utilization on the slave node
It also reports the resource utilization back to the Resource Manager
It uses other daemon process like Application Master and Container for MapReduce task scheduling and execution on the slave node
