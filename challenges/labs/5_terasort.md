El comando terasort me dio problemas aparentemente de memoria y no hubo caso de que ejecutara bien luego de probar con distintas configuraciones, adjunto algunas salidas completas para confirmar:


[root@ip-172-31-40-99 ec2-user]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/saturn/tgen /user/saturn/tsort

17/10/06 12:55:10 INFO terasort.TeraSort: starting
17/10/06 12:55:11 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ANDRESCRUZAT.HQ, renewer=yarn, realUser=, issueDate=1507308911493, maxDate=1507913711493, sequenceNumber=12, masterKeyId=6 on 172.31.40.99:8020
17/10/06 12:55:11 INFO security.TokenCache: Got dt for hdfs://ip-172-31-40-99.us-east-2.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.40.99:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ANDRESCRUZAT.HQ, renewer=yarn, realUser=, issueDate=1507308911493, maxDate=1507913711493, sequenceNumber=12, masterKeyId=6)
17/10/06 12:55:11 INFO input.FileInputFormat: Total input paths to process : 12
Spent 300ms computing base-splits.
Spent 4ms computing TeraScheduler splits.
Computing input splits took 306ms
Sampling 10 splits of 204
Making 16 from 100000 sampled records
Computing parititions took 587ms
Spent 896ms computing partitions.
17/10/06 12:55:12 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-32-203.us-east-2.compute.internal/172.31.32.203:8032
17/10/06 12:55:12 INFO mapreduce.JobSubmitter: number of splits:204
17/10/06 12:55:12 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507307558266_0001
17/10/06 12:55:12 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.40.99:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ANDRESCRUZAT.HQ, renewer=yarn, realUser=, issueDate=1507308911493, maxDate=1507913711493, sequenceNumber=12, masterKeyId=6)
17/10/06 12:55:13 INFO impl.YarnClientImpl: Submitted application application_1507307558266_0001
17/10/06 12:55:13 INFO mapreduce.Job: The url to track the job: http://ip-172-31-32-203.us-east-2.compute.internal:8088/proxy/application_1507307558266_0001/
17/10/06 12:55:13 INFO mapreduce.Job: Running job: job_1507307558266_0001
17/10/06 12:55:21 INFO mapreduce.Job: Job job_1507307558266_0001 running in uber mode : false
17/10/06 12:55:21 INFO mapreduce.Job:  map 0% reduce 0%
17/10/06 12:55:38 INFO mapreduce.Job:  map 3% reduce 0%
17/10/06 12:55:40 INFO mapreduce.Job:  map 8% reduce 0%
17/10/06 12:55:41 INFO mapreduce.Job:  map 15% reduce 0%
17/10/06 12:55:53 INFO mapreduce.Job:  map 16% reduce 0%
17/10/06 12:55:54 INFO mapreduce.Job:  map 19% reduce 0%
17/10/06 12:55:57 INFO mapreduce.Job:  map 22% reduce 0%
17/10/06 12:55:58 INFO mapreduce.Job:  map 23% reduce 0%
17/10/06 12:55:59 INFO mapreduce.Job:  map 30% reduce 0%
17/10/06 12:56:08 INFO mapreduce.Job:  map 31% reduce 0%
17/10/06 12:56:09 INFO mapreduce.Job:  map 34% reduce 0%
17/10/06 12:56:13 INFO mapreduce.Job:  map 37% reduce 0%
17/10/06 12:56:14 INFO mapreduce.Job:  map 38% reduce 0%
17/10/06 12:56:15 INFO mapreduce.Job:  map 42% reduce 0%
17/10/06 12:56:16 INFO mapreduce.Job:  map 45% reduce 0%
17/10/06 12:56:17 INFO mapreduce.Job:  map 46% reduce 0%
17/10/06 12:56:24 INFO mapreduce.Job:  map 49% reduce 0%
17/10/06 12:56:31 INFO mapreduce.Job:  map 53% reduce 0%
17/10/06 12:56:33 INFO mapreduce.Job:  map 57% reduce 0%
17/10/06 12:56:34 INFO mapreduce.Job:  map 61% reduce 0%
17/10/06 12:56:39 INFO mapreduce.Job:  map 64% reduce 0%
17/10/06 12:56:47 INFO mapreduce.Job:  map 65% reduce 0%
17/10/06 12:56:48 INFO mapreduce.Job:  map 68% reduce 0%
17/10/06 12:56:49 INFO mapreduce.Job:  map 70% reduce 0%
17/10/06 12:56:50 INFO mapreduce.Job:  map 73% reduce 0%
17/10/06 12:56:52 INFO mapreduce.Job:  map 76% reduce 0%
17/10/06 12:56:54 INFO mapreduce.Job:  map 78% reduce 0%
17/10/06 12:56:55 INFO mapreduce.Job:  map 79% reduce 0%
17/10/06 12:57:05 INFO mapreduce.Job:  map 82% reduce 0%
17/10/06 12:57:06 INFO mapreduce.Job:  map 83% reduce 0%
17/10/06 12:57:07 INFO mapreduce.Job:  map 86% reduce 0%
17/10/06 12:57:08 INFO mapreduce.Job:  map 93% reduce 0%
17/10/06 12:57:09 INFO mapreduce.Job:  map 95% reduce 0%
17/10/06 12:57:14 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000015_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#2
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:14 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000014_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:19 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000020_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:19 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000008_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:19 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000004_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:19 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000028_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:19 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000052_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:19 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000012_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:19 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000005_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:19 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000026_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:19 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000011_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:19 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000061_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:20 INFO mapreduce.Job:  map 84% reduce 0%
17/10/06 12:57:20 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000013_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:20 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000022_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:20 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000050_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:20 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000005_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:20 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000027_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000003_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:20 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000003_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000003_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:20 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000009_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000003_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:20 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000019_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000003_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:20 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000002_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000003_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:20 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000057_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000003_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:21 INFO mapreduce.Job:  map 59% reduce 0%
17/10/06 12:57:21 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000060_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000003_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:21 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000059_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000003_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:21 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000055_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000003_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:21 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000056_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000003_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:21 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000002_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#3
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:21 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000003_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:21 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000017_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:21 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000015_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:21 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000034_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:21 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000033_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:22 INFO mapreduce.Job:  map 37% reduce 0%
17/10/06 12:57:22 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000066_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:22 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000032_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:22 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000072_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:22 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000068_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:22 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000037_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:22 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000031_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:22 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000073_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:22 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000069_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:22 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000063_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:22 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000036_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:23 INFO mapreduce.Job:  map 27% reduce 0%
17/10/06 12:57:23 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000035_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:24 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000083_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:24 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000089_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:24 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000092_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:24 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000087_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:24 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000000_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:24 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000051_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:24 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000010_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:24 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000040_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:25 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000045_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:25 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000064_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:25 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000021_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:25 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000039_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:25 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000046_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:25 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000000_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:25 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000048_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:25 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000049_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:25 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000076_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:25 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000029_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:26 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000001_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:26 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000044_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:26 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000023_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:26 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000075_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:26 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000014_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:26 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000077_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:26 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000058_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:26 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000025_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:26 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000053_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:26 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000038_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:27 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000047_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:27 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000080_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:27 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000007_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:27 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000041_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:27 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000024_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:27 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000006_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:27 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000042_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:27 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000054_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:27 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000030_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:27 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000018_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000043_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000016_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000088_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000081_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000006_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#3
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000071_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000001_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000091_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000001_0 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:57:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000001_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000004_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000090_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000011_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000074_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000011_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000098_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000011_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000097_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000011_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000096_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000011_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000094_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000011_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000093_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000011_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000099_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000011_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000011_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000078_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000009_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000082_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000009_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000086_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000084_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000079_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000085_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000122_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000121_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000111_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000112_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000115_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000124_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000116_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000123_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000009_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#8
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000007_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000067_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000070_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000062_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000065_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000102_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000013_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#2
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000146_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000152_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:34 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000151_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:34 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000150_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:34 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000149_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:34 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000148_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:34 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000154_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:34 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000147_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:34 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000125_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:34 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000132_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:34 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000127_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:34 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000164_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000120_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000126_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000156_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000128_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000129_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000103_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000107_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 12:57:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000010_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#8
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000012_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#8
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000008_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#2
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:36 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000179_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:36 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000110_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:36 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000119_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:36 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000145_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:36 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000118_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:36 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000117_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:36 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000138_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:36 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000133_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:36 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000144_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:37 INFO mapreduce.Job:  map 28% reduce 0%
17/10/06 12:57:37 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000113_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:37 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000108_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:37 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000114_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:37 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000135_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:37 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000142_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:37 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000143_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:37 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000153_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:37 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000106_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:37 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000015_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#7
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:37 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000182_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000014_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:38 INFO mapreduce.Job:  map 30% reduce 0%
17/10/06 12:57:38 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000168_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000014_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:38 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000155_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000014_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:38 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000160_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000014_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:38 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000104_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000014_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:57:38 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000014_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#2
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:57:39 INFO mapreduce.Job:  map 37% reduce 0%
17/10/06 12:57:40 INFO mapreduce.Job:  map 42% reduce 0%
17/10/06 12:57:52 INFO mapreduce.Job:  map 46% reduce 0%
17/10/06 12:57:56 INFO mapreduce.Job:  map 47% reduce 0%
17/10/06 12:57:57 INFO mapreduce.Job:  map 57% reduce 0%
17/10/06 12:58:06 INFO mapreduce.Job:  map 58% reduce 0%
17/10/06 12:58:07 INFO mapreduce.Job:  map 61% reduce 0%
17/10/06 12:58:14 INFO mapreduce.Job:  map 66% reduce 0%
17/10/06 12:58:15 INFO mapreduce.Job:  map 73% reduce 0%
17/10/06 12:58:22 INFO mapreduce.Job:  map 76% reduce 0%
17/10/06 12:58:31 INFO mapreduce.Job:  map 86% reduce 0%
17/10/06 12:58:32 INFO mapreduce.Job:  map 88% reduce 0%
17/10/06 12:58:37 INFO mapreduce.Job:  map 91% reduce 0%
17/10/06 12:58:44 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000137_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:44 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000131_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:44 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000139_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:44 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000140_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:44 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000109_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:44 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000101_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:44 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000095_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:44 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000134_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:44 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000105_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:44 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000130_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:45 INFO mapreduce.Job:  map 78% reduce 0%
17/10/06 12:58:45 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000136_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:45 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000100_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:45 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000159_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000013_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:45 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000013_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:58:45 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000183_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:45 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000185_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:45 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000180_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:45 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000187_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:45 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000184_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:45 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000141_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:46 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000157_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000007_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:46 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000011_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#8
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:58:46 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000007_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:58:46 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000009_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#8
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:58:46 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000192_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000008_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:46 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000195_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000008_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:46 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000194_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000008_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:46 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000178_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000008_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:46 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000193_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000008_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:46 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000186_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000008_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:47 INFO mapreduce.Job:  map 79% reduce 0%
17/10/06 12:58:47 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000166_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000008_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:47 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000008_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#2
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:58:48 INFO mapreduce.Job:  map 80% reduce 0%
17/10/06 12:58:48 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000188_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:48 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000181_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:48 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000202_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:48 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000158_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:49 INFO mapreduce.Job:  map 75% reduce 0%
17/10/06 12:58:49 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000161_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:49 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000169_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:49 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000162_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:49 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000165_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:49 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000163_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:49 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000167_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000006_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:49 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000006_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#7
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:58:50 INFO mapreduce.Job:  map 74% reduce 0%
17/10/06 12:58:50 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000176_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:50 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000170_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:50 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000173_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:50 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000177_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:50 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000171_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:50 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000174_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:50 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000172_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:50 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000175_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000000_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:51 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000000_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:58:51 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000199_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000015_2 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:51 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000015_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:58:51 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000019_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000001_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:51 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000056_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000001_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:51 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000001_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:58:51 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000003_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000014_2 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:51 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000066_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000014_2 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:52 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000201_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000014_2 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:53 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000014_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:58:53 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000004_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#8
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:58:53 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000009_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000003_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:53 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000055_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000003_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:53 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000032_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000003_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 12:58:53 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000003_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:58:57 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000034_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000012_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:57 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000033_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000012_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:57 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000072_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000012_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:57 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000059_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000012_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:57 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000060_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000012_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:57 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000196_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000012_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:58:57 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000012_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:58:58 INFO mapreduce.Job:  map 71% reduce 0%
17/10/06 12:59:00 INFO mapreduce.Job:  map 74% reduce 0%
17/10/06 12:59:02 INFO mapreduce.Job:  map 72% reduce 0%
17/10/06 12:59:02 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000197_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_1 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:59:02 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000198_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_1 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:59:02 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000057_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_1 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:59:02 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000022_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_1 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:59:02 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000002_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:59:04 INFO mapreduce.Job:  map 73% reduce 0%
17/10/06 12:59:05 INFO mapreduce.Job:  map 77% reduce 0%
17/10/06 12:59:06 INFO mapreduce.Job:  map 81% reduce 0%
17/10/06 12:59:07 INFO mapreduce.Job:  map 83% reduce 0%
17/10/06 12:59:15 INFO mapreduce.Job:  map 86% reduce 0%
17/10/06 12:59:16 INFO mapreduce.Job:  map 87% reduce 0%
17/10/06 12:59:20 INFO mapreduce.Job:  map 89% reduce 0%
17/10/06 12:59:21 INFO mapreduce.Job:  map 90% reduce 0%
17/10/06 12:59:22 INFO mapreduce.Job:  map 95% reduce 0%
17/10/06 12:59:23 INFO mapreduce.Job:  map 98% reduce 0%
17/10/06 12:59:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000052_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000005_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000011_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000026_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000015_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000068_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000002_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000037_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000063_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000203_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000010_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:29 INFO mapreduce.Job:  map 71% reduce 0%
17/10/06 12:59:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000077_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000040_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000083_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000044_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000097_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000021_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000046_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000084_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000096_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000065_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:30 INFO mapreduce.Job:  map 72% reduce 0%
17/10/06 12:59:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000074_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000024_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000030_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000006_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000000_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000043_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000075_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000064_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000089_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:30 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000010_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:31 INFO mapreduce.Job:  map 68% reduce 0%
17/10/06 12:59:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000051_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000090_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000039_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000017_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000054_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000048_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000087_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000012_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000081_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:31 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000092_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:32 INFO mapreduce.Job:  map 100% reduce 100%
17/10/06 12:59:32 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000200_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:32 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000191_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:32 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000190_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:32 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000025_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:32 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000047_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:32 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000053_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:32 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000038_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:32 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000031_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:32 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000041_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:32 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000007_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000073_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000036_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000080_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000069_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000112_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000035_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000005_1 from host ip-172-31-43-111.us-east-2.compute.internal
17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000010_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000005_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#2
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000008_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#4
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_r_000009_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000042_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_2 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000124_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_2 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000102_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_2 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000189_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_2 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000111_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_2 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:59:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0001_m_000115_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0001_r_000002_2 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 12:59:33 INFO mapreduce.Job: Job job_1507307558266_0001 failed with state FAILED due to: Task failed task_1507307558266_0001_r_000015
Job failed as tasks failed. failedMaps:0 failedReduces:1

17/10/06 12:59:34 INFO mapreduce.Job: Counters: 41
        File System Counters
                FILE: Number of bytes read=17325
                FILE: Number of bytes written=1438108044
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=3280310645
                HDFS: Number of bytes written=0
                HDFS: Number of read operations=315
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=0
        Job Counters
                Failed map tasks=312
                Failed reduce tasks=45
                Killed map tasks=99
                Killed reduce tasks=15
                Launched map tasks=434
                Launched reduce tasks=48
                Other local map tasks=230
                Data-local map tasks=204
                Total time spent by all maps in occupied slots (ms)=6454475
                Total time spent by all reduces in occupied slots (ms)=547989
                Total time spent by all map tasks (ms)=6454475
                Total time spent by all reduce tasks (ms)=547989
                Total vcore-milliseconds taken by all map tasks=6454475
                Total vcore-milliseconds taken by all reduce tasks=547989
                Total megabyte-milliseconds taken by all map tasks=6609382400
                Total megabyte-milliseconds taken by all reduce tasks=561140736
        Map-Reduce Framework
                Map input records=32802950
                Map output records=32802950
                Map output bytes=3345900900
                Map output materialized bytes=1424394038
                Input split bytes=15645
                Combine input records=0
                Spilled Records=32802950
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=15489
                CPU time spent (ms)=381490
                Physical memory (bytes) snapshot=54873939968
                Virtual memory (bytes) snapshot=167431790592
                Total committed heap usage (bytes)=61951967232
        File Input Format Counters
                Bytes Read=3280295000
17/10/06 12:59:34 INFO terasort.TeraSort: done

real    4m24.797s
user    0m8.130s
sys     0m0.355s


------------------------------------------
------------------------------------------

[root@ip-172-31-40-99 ec2-user]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.reduce.memory.mb=8192 /user/saturn/tgen /user/saturn/tsort

17/10/06 13:02:32 INFO terasort.TeraSort: starting
17/10/06 13:02:33 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ANDRESCRUZAT.HQ, renewer=yarn, realUser=, issueDate=1507309353428, maxDate=1507914153428, sequenceNumber=13, masterKeyId=6 on 172.31.40.99:8020
17/10/06 13:02:33 INFO security.TokenCache: Got dt for hdfs://ip-172-31-40-99.us-east-2.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.40.99:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ANDRESCRUZAT.HQ, renewer=yarn, realUser=, issueDate=1507309353428, maxDate=1507914153428, sequenceNumber=13, masterKeyId=6)
17/10/06 13:02:33 INFO input.FileInputFormat: Total input paths to process : 12
Spent 276ms computing base-splits.
Spent 5ms computing TeraScheduler splits.
Computing input splits took 282ms
Sampling 10 splits of 204
Making 16 from 100000 sampled records
Computing parititions took 553ms
Spent 838ms computing partitions.
17/10/06 13:02:34 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-32-203.us-east-2.compute.internal/172.31.32.203:8032
17/10/06 13:02:34 INFO mapreduce.JobSubmitter: number of splits:204
17/10/06 13:02:34 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507307558266_0002
17/10/06 13:02:34 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.40.99:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@ANDRESCRUZAT.HQ, renewer=yarn, realUser=, issueDate=1507309353428, maxDate=1507914153428, sequenceNumber=13, masterKeyId=6)
17/10/06 13:02:34 INFO impl.YarnClientImpl: Submitted application application_1507307558266_0002
17/10/06 13:02:35 INFO mapreduce.Job: The url to track the job: http://ip-172-31-32-203.us-east-2.compute.internal:8088/proxy/application_1507307558266_0002/
17/10/06 13:02:35 INFO mapreduce.Job: Running job: job_1507307558266_0002
17/10/06 13:02:43 INFO mapreduce.Job: Job job_1507307558266_0002 running in uber mode : false
17/10/06 13:02:43 INFO mapreduce.Job:  map 0% reduce 0%
17/10/06 13:02:59 INFO mapreduce.Job:  map 3% reduce 0%
17/10/06 13:03:00 INFO mapreduce.Job:  map 15% reduce 0%
17/10/06 13:03:14 INFO mapreduce.Job:  map 19% reduce 0%
17/10/06 13:03:17 INFO mapreduce.Job:  map 23% reduce 0%
17/10/06 13:03:18 INFO mapreduce.Job:  map 30% reduce 0%
17/10/06 13:03:30 INFO mapreduce.Job:  map 34% reduce 0%
17/10/06 13:03:34 INFO mapreduce.Job:  map 35% reduce 0%
17/10/06 13:03:35 INFO mapreduce.Job:  map 41% reduce 0%
17/10/06 13:03:36 INFO mapreduce.Job:  map 46% reduce 0%
17/10/06 13:03:44 INFO mapreduce.Job:  map 47% reduce 0%
17/10/06 13:03:45 INFO mapreduce.Job:  map 49% reduce 0%
17/10/06 13:03:50 INFO mapreduce.Job:  map 50% reduce 0%
17/10/06 13:03:51 INFO mapreduce.Job:  map 53% reduce 0%
17/10/06 13:03:52 INFO mapreduce.Job:  map 57% reduce 0%
17/10/06 13:03:53 INFO mapreduce.Job:  map 61% reduce 0%
17/10/06 13:04:00 INFO mapreduce.Job:  map 64% reduce 0%
17/10/06 13:04:08 INFO mapreduce.Job:  map 68% reduce 0%
17/10/06 13:04:09 INFO mapreduce.Job:  map 69% reduce 0%
17/10/06 13:04:10 INFO mapreduce.Job:  map 76% reduce 0%
17/10/06 13:04:15 INFO mapreduce.Job:  map 79% reduce 0%
17/10/06 13:04:24 INFO mapreduce.Job:  map 81% reduce 0%
17/10/06 13:04:25 INFO mapreduce.Job:  map 84% reduce 0%
17/10/06 13:04:26 INFO mapreduce.Job:  map 87% reduce 0%
17/10/06 13:04:28 INFO mapreduce.Job:  map 91% reduce 0%
17/10/06 13:04:30 INFO mapreduce.Job:  map 94% reduce 0%
17/10/06 13:04:31 INFO mapreduce.Job:  map 95% reduce 0%
17/10/06 13:04:32 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000000_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:04:33 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000001_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:04:36 INFO mapreduce.Job:  map 96% reduce 0%
17/10/06 13:04:38 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000022_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000003_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:04:38 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000014_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000003_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:04:38 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000001_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000003_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:04:38 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000026_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000003_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:04:38 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000015_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000003_0 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:04:38 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000003_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:04:38 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000004_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:04:39 INFO mapreduce.Job:  map 94% reduce 0%
17/10/06 13:04:39 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000005_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:04:42 INFO mapreduce.Job:  map 97% reduce 0%
17/10/06 13:04:43 INFO mapreduce.Job:  map 98% reduce 0%
17/10/06 13:04:47 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000017_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000005_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 13:04:47 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000019_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000005_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 13:04:47 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000020_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000005_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 13:04:47 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000011_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000005_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 13:04:47 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000013_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000005_1 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 13:04:47 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000005_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:04:48 INFO mapreduce.Job:  map 96% reduce 0%
17/10/06 13:04:48 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000003_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:04:48 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000002_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#6
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:04:50 INFO mapreduce.Job:  map 98% reduce 0%
17/10/06 13:04:54 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000002_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:05:00 INFO mapreduce.Job:  map 100% reduce 0%
17/10/06 13:05:00 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000000_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000004_1 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:00 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000023_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000004_1 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:00 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000021_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000004_1 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:00 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000016_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000004_1 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:01 INFO mapreduce.Job:  map 98% reduce 0%
17/10/06 13:05:05 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000027_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000008_0 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 13:05:05 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000008_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:05:12 INFO mapreduce.Job:  map 100% reduce 0%
17/10/06 13:05:20 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000029_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000003_3 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:20 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000018_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000003_3 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:20 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000010_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000003_3 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:20 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000028_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000003_3 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:21 INFO mapreduce.Job:  map 98% reduce 0%
17/10/06 13:05:28 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000002_3, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:05:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000003_4, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:05:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000044_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000007_1 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 13:05:29 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000007_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:05:31 INFO mapreduce.Job:  map 99% reduce 0%
17/10/06 13:05:32 INFO mapreduce.Job:  map 100% reduce 0%
17/10/06 13:05:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000030_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000004_3 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000024_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000004_3 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000002_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000004_3 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000004_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000004_3 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000031_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000004_3 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:35 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000004_3, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#2
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:05:36 INFO mapreduce.Job:  map 97% reduce 0%
17/10/06 13:05:37 INFO mapreduce.Job:  map 98% reduce 0%
17/10/06 13:05:41 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000005_4, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:05:45 INFO mapreduce.Job:  map 100% reduce 0%
17/10/06 13:05:47 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000005_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000001_1 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 13:05:47 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000039_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000001_1 from host ip-172-31-40-99.us-east-2.compute.internal
17/10/06 13:05:48 INFO mapreduce.Job:  map 99% reduce 0%
17/10/06 13:05:48 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000008_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:05:48 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000001_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:05:49 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000006_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#2
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:05:52 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000003_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000007_2 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:52 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000025_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000007_2 from host ip-172-31-36-168.us-east-2.compute.internal
17/10/06 13:05:53 INFO mapreduce.Job:  map 98% reduce 0%
17/10/06 13:05:53 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000007_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:05:54 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000004_4, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#8
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:05:57 INFO mapreduce.Job:  map 99% reduce 0%
17/10/06 13:06:00 INFO mapreduce.Job:  map 100% reduce 0%
17/10/06 13:06:00 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_r_000000_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1920)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:392)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:307)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 13:06:06 INFO mapreduce.Job: Task Id : attempt_1507307558266_0002_m_000040_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507307558266_0002_r_000003_5 from host ip-172-31-32-203.us-east-2.compute.internal
17/10/06 13:06:07 INFO mapreduce.Job:  map 100% reduce 100%
17/10/06 13:06:07 INFO mapreduce.Job: Job job_1507307558266_0002 failed with state FAILED due to: Task failed task_1507307558266_0002_r_000005
Job failed as tasks failed. failedMaps:0 failedReduces:1

17/10/06 13:06:08 INFO mapreduce.Job: Counters: 41
        File System Counters
                FILE: Number of bytes read=33495
                FILE: Number of bytes written=2858202527
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=6520075747
                HDFS: Number of bytes written=0
                HDFS: Number of read operations=609
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=0
        Job Counters
                Failed map tasks=30
                Failed reduce tasks=22
                Killed map tasks=1
                Killed reduce tasks=23
                Launched map tasks=233
                Launched reduce tasks=34
                Other local map tasks=29
                Data-local map tasks=204
                Total time spent by all maps in occupied slots (ms)=3352016
                Total time spent by all reduces in occupied slots (ms)=3004160
                Total time spent by all map tasks (ms)=3352016
                Total time spent by all reduce tasks (ms)=375520
                Total vcore-milliseconds taken by all map tasks=3352016
                Total vcore-milliseconds taken by all reduce tasks=375520
                Total megabyte-milliseconds taken by all map tasks=3432464384
                Total megabyte-milliseconds taken by all reduce tasks=3076259840
        Map-Reduce Framework
                Map input records=65200455
                Map output records=65200455
                Map output bytes=6650446410
                Map output materialized bytes=2831687791
                Input split bytes=30247
                Combine input records=0
                Spilled Records=65200455
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=26877
                CPU time spent (ms)=721060
                Physical memory (bytes) snapshot=106170490880
                Virtual memory (bytes) snapshot=323690565632
                Total committed heap usage (bytes)=120666980352
        File Input Format Counters
                Bytes Read=6520045500
17/10/06 13:06:08 INFO terasort.TeraSort: done

real    3m36.835s
user    0m7.502s
sys     0m0.368s




