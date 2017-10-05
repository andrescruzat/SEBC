What is ubertask optimization?
R: Whether to enable ubertask optimization, which runs "sufficiently small" jobs sequentially within a single JVM.
"Small" is defined by the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings.

Where in CM is the Kerberos Security Realm value displayed?
R: In Administration>Settings/Kerberos

Which CDH service(s) host a property for enabling Kerberos authentication?
R: Zookeeper, Impala, HDFS, YARN, Hive, Oozie, Solr

How do you upgrade the CM agents?
R: You can use an upgrade wizard that is invoked when you connect to the Admin Console or manually install the Cloudera Manager Agent packages
Upgrade the Cloudera Manager agent software on all cluster hosts. The Cloudera Manager upgrade wizard can upgrade the agent software 
(and, optionally, the JDK), or you can install the agent and JDK software manually from tarballs. The CDH software is not upgraded 
during this process.

Give the tsquery statement used to chart Hue's CPU utilization?
R: select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName="hue"

Name all the roles that make up the Hive service
R: Hive metatstore Server, HiveServer2

What steps must be completed before integrating Cloudera Manager with Kerberos?
R: Prerequisites - These instructions assume you know how to install and configure Kerberos, you already have a working Kerberos 
key distribution center (KDC) and realm setup, and that you've installed the following Kerberos client packages on all cluster hosts 
and hosts that will be used to access the cluster, depending on the OS in use.
Furthermore, Oozie and Hue require that the realm support renewable tickets. Cloudera Manager supports setting up kerberized clusters 
with MIT KDC and Active Directory.


