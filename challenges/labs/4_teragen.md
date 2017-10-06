[root@ip-172-31-40-99 ec2-user]# time hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar \
> teragen -Dmapred.map.tasks=12 \
> -Ddfs.block.size=33554432 \
> -Dmapreduce.map.memory.mb=512 \
> -Dmapred.map.tasks.speculative.execution=false 65536000 \
> /user/saturn/tgen
17/10/06 10:40:09 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-32-203.us-east-2.compute.internal/172.31.32.203:8032
17/10/06 10:40:09 INFO terasort.TeraSort: Generating 65536000 using 12
17/10/06 10:40:09 INFO mapreduce.JobSubmitter: number of splits:12
17/10/06 10:40:09 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/10/06 10:40:09 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/10/06 10:40:09 INFO Configuration.deprecation: mapred.map.tasks.speculative.execution is deprecated. Instead, use mapreduce.map.speculative
17/10/06 10:40:09 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507298747197_0001
17/10/06 10:40:10 INFO impl.YarnClientImpl: Submitted application application_1507298747197_0001
17/10/06 10:40:10 INFO mapreduce.Job: The url to track the job: http://ip-172-31-32-203.us-east-2.compute.internal:8088/proxy/application_1507298747197_0001/
17/10/06 10:40:10 INFO mapreduce.Job: Running job: job_1507298747197_0001
17/10/06 10:40:15 INFO mapreduce.Job: Job job_1507298747197_0001 running in uber mode : false
17/10/06 10:40:15 INFO mapreduce.Job:  map 0% reduce 0%
17/10/06 10:40:27 INFO mapreduce.Job:  map 6% reduce 0%
17/10/06 10:40:29 INFO mapreduce.Job:  map 21% reduce 0%
17/10/06 10:40:30 INFO mapreduce.Job:  map 22% reduce 0%
17/10/06 10:40:32 INFO mapreduce.Job:  map 29% reduce 0%
17/10/06 10:40:33 INFO mapreduce.Job:  map 31% reduce 0%
17/10/06 10:40:36 INFO mapreduce.Job:  map 37% reduce 0%
17/10/06 10:40:37 INFO mapreduce.Job:  map 38% reduce 0%
17/10/06 10:40:39 INFO mapreduce.Job:  map 44% reduce 0%
17/10/06 10:40:40 INFO mapreduce.Job:  map 47% reduce 0%
17/10/06 10:40:41 INFO mapreduce.Job:  map 48% reduce 0%
17/10/06 10:40:42 INFO mapreduce.Job:  map 57% reduce 0%
17/10/06 10:40:45 INFO mapreduce.Job:  map 62% reduce 0%
17/10/06 10:40:48 INFO mapreduce.Job:  map 67% reduce 0%
17/10/06 10:40:49 INFO mapreduce.Job:  map 68% reduce 0%
17/10/06 10:40:57 INFO mapreduce.Job:  map 72% reduce 0%
17/10/06 10:40:58 INFO mapreduce.Job:  map 73% reduce 0%
17/10/06 10:41:04 INFO mapreduce.Job:  map 74% reduce 0%
17/10/06 10:41:05 INFO mapreduce.Job:  map 75% reduce 0%
17/10/06 10:41:06 INFO mapreduce.Job:  map 87% reduce 0%
17/10/06 10:41:09 INFO mapreduce.Job:  map 93% reduce 0%
17/10/06 10:41:10 INFO mapreduce.Job:  map 94% reduce 0%
17/10/06 10:41:12 INFO mapreduce.Job:  map 98% reduce 0%
17/10/06 10:41:15 INFO mapreduce.Job:  map 99% reduce 0%
17/10/06 10:41:18 INFO mapreduce.Job:  map 100% reduce 0%
17/10/06 10:41:18 INFO mapreduce.Job: Job job_1507298747197_0001 completed successfully
17/10/06 10:41:18 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=1483850
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1025
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=48
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=24
        Job Counters
                Launched map tasks=12
                Other local map tasks=12
                Total time spent by all maps in occupied slots (ms)=624707
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=624707
                Total vcore-seconds taken by all map tasks=624707
                Total megabyte-seconds taken by all map tasks=639699968
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Input split bytes=1025
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=2658
                CPU time spent (ms)=134870
                Physical memory (bytes) snapshot=2429698048
                Virtual memory (bytes) snapshot=13750370304
                Total committed heap usage (bytes)=4454350848
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=140750829423462787
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=6553600000

real    1m11.451s
user    0m4.455s
sys     0m0.247s

[root@ip-172-31-40-99 ec2-user]# hdfs dfs -ls /user/saturn/tgen
Found 13 items
-rw-r--r--   3 saturn supergroup          0 2017-10-06 10:41 /user/saturn/tgen/_SUCCESS
-rw-r--r--   3 saturn supergroup  546133400 2017-10-06 10:41 /user/saturn/tgen/part-m-00000
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:41 /user/saturn/tgen/part-m-00001
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:41 /user/saturn/tgen/part-m-00002
-rw-r--r--   3 saturn supergroup  546133400 2017-10-06 10:41 /user/saturn/tgen/part-m-00003
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:41 /user/saturn/tgen/part-m-00004
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:41 /user/saturn/tgen/part-m-00005
-rw-r--r--   3 saturn supergroup  546133400 2017-10-06 10:41 /user/saturn/tgen/part-m-00006
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:41 /user/saturn/tgen/part-m-00007
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:41 /user/saturn/tgen/part-m-00008
-rw-r--r--   3 saturn supergroup  546133400 2017-10-06 10:41 /user/saturn/tgen/part-m-00009
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:41 /user/saturn/tgen/part-m-00010
-rw-r--r--   3 saturn supergroup  546133300 2017-10-06 10:40 /user/saturn/tgen/part-m-00011

[root@ip-172-31-40-99 ec2-user]# hadoop fsck -blocks /user/saturn
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-40-99.us-east-2.compute.internal:50070
FSCK started by saturn (auth:SIMPLE) from /172.31.40.99 for path /user/saturn at Fri Oct 06 10:42:44 EDT 2017
.............Status: HEALTHY
 Total size:    6553600000 B
 Total dirs:    3
 Total files:   13
 Total symlinks:                0
 Total blocks (validated):      204 (avg. block size 32125490 B)
 Minimally replicated blocks:   204 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          4
 Number of racks:               1
FSCK ended at Fri Oct 06 10:42:44 EDT 2017 in 9 milliseconds


The filesystem under path '/user/saturn' is HEALTHY
