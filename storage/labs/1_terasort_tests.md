---> HDFS Lab: Test HDFS throughput

#### Crear usuario
[ec2-user@ip-172-31-19-50 home]$ sudo useradd -d /home/andrescruzat -m -s /bin/bash andrescruzat
[ec2-user@ip-172-31-19-50 home]$ sudo passwd andrescruzat
Changing password for user andrescruzat.
New password:
Retype new password:
passwd: all authentication tokens updated successfully.
[ec2-user@ip-172-31-19-50 home]$ cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
...
hue:x:978:974:Hue:/usr/lib/hue:/bin/false
andrescruzat:x:1001:1001::/home/andrescruzat:/bin/bash

#### Crear carpeta y cambiar usuario
[ec2-user@ip-172-31-19-50 home]$ hdfs dfs -mkdir -p /user/andrescruzat
[ec2-user@ip-172-31-19-50 home]$ hdfs dfs -chown andrescruzat /user/andrescruzat
[ec2-user@ip-172-31-19-50 home]$ hdfs dfs -ls /user
Found 3 items
drwxr-xr-x   - andrescruzat supergroup          0 2017-10-03 10:25 /user/andrescruzat
drwx------   - hdfs         supergroup          0 2017-10-03 09:53 /user/hdfs
drwxrwxrwx   - mapred       hadoop              0 2017-10-03 01:18 /user/history
[ec2-user@ip-172-31-19-50 home]$ export HADOOP_USER_NAME=andrescruzat

#### Crear archivo de 10 GB
time hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar \
teragen -Dmapred.map.tasks=4 \
-Ddfs.block.size=33554432 \
-Dmapred.map.tasks.speculative.execution=false 100000000 \
/user/andrescruzat/teragen_out

-----
$ hadoop jar hadoop-*examples*.jar teragen <number of 100-byte rows> <output dir>
$ hadoop jar hadoop-*examples*.jar teragen -D dfs.block.size=536870912
32 MB = 33554432
-----

[ec2-user@ip-172-31-19-50 home]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar \
> teragen -Dmapred.map.tasks=4 \
> -Ddfs.block.size=33554432 \
> -Dmapred.map.tasks.speculative.execution=false 100000000 \
> /user/andrescruzat/teragen_out
17/10/03 10:43:04 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-18-46.us-east-2.compute.internal/172.31.18.46:8032
17/10/03 10:43:05 INFO terasort.TeraGen: Generating 100000000 using 4
17/10/03 10:43:05 INFO mapreduce.JobSubmitter: number of splits:4
17/10/03 10:43:05 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/10/03 10:43:05 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/10/03 10:43:05 INFO Configuration.deprecation: mapred.map.tasks.speculative.execution is deprecated. Instead, use mapreduce.map.speculative
17/10/03 10:43:05 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507007928382_0002
17/10/03 10:43:05 INFO impl.YarnClientImpl: Submitted application application_1507007928382_0002
17/10/03 10:43:05 INFO mapreduce.Job: The url to track the job: http://ip-172-31-18-46.us-east-2.compute.internal:8088/proxy/application_1507007928382_0002/
17/10/03 10:43:05 INFO mapreduce.Job: Running job: job_1507007928382_0002
17/10/03 10:43:11 INFO mapreduce.Job: Job job_1507007928382_0002 running in uber mode : false
17/10/03 10:43:11 INFO mapreduce.Job:  map 0% reduce 0%
17/10/03 10:43:28 INFO mapreduce.Job:  map 4% reduce 0%
17/10/03 10:43:29 INFO mapreduce.Job:  map 15% reduce 0%
17/10/03 10:43:34 INFO mapreduce.Job:  map 17% reduce 0%
17/10/03 10:43:35 INFO mapreduce.Job:  map 23% reduce 0%
17/10/03 10:43:40 INFO mapreduce.Job:  map 28% reduce 0%
17/10/03 10:43:41 INFO mapreduce.Job:  map 30% reduce 0%
17/10/03 10:43:47 INFO mapreduce.Job:  map 38% reduce 0%
17/10/03 10:43:53 INFO mapreduce.Job:  map 43% reduce 0%
17/10/03 10:43:59 INFO mapreduce.Job:  map 51% reduce 0%
17/10/03 10:44:05 INFO mapreduce.Job:  map 58% reduce 0%
17/10/03 10:44:11 INFO mapreduce.Job:  map 65% reduce 0%
17/10/03 10:44:17 INFO mapreduce.Job:  map 73% reduce 0%
17/10/03 10:44:24 INFO mapreduce.Job:  map 80% reduce 0%
17/10/03 10:44:30 INFO mapreduce.Job:  map 87% reduce 0%
17/10/03 10:44:37 INFO mapreduce.Job:  map 95% reduce 0%
17/10/03 10:44:39 INFO mapreduce.Job:  map 96% reduce 0%
17/10/03 10:44:40 INFO mapreduce.Job:  map 100% reduce 0%
17/10/03 10:44:41 INFO mapreduce.Job: Job job_1507007928382_0002 completed successfully
17/10/03 10:44:41 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=512428
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=344
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=347771
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=347771
                Total vcore-milliseconds taken by all map tasks=347771
                Total megabyte-milliseconds taken by all map tasks=356117504
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Input split bytes=344
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1314
                CPU time spent (ms)=140320
                Physical memory (bytes) snapshot=782254080
                Virtual memory (bytes) snapshot=6385967104
                Total committed heap usage (bytes)=1694498816
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=214760662691937609
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10000000000

real    1m38.576s
user    0m4.595s
sys     0m0.248s
[ec2-user@ip-172-31-19-50 home]$ hdfs dfs -ls -h /user/andrescruzat/teragen_out
Found 5 items
-rw-r--r--   3 andrescruzat supergroup          0 2017-10-03 10:44 /user/andrescruzat/teragen_out/_SUCCESS
-rw-r--r--   3 andrescruzat supergroup      2.3 G 2017-10-03 10:44 /user/andrescruzat/teragen_out/part-m-00000
-rw-r--r--   3 andrescruzat supergroup      2.3 G 2017-10-03 10:44 /user/andrescruzat/teragen_out/part-m-00001
-rw-r--r--   3 andrescruzat supergroup      2.3 G 2017-10-03 10:44 /user/andrescruzat/teragen_out/part-m-00002
-rw-r--r--   3 andrescruzat supergroup      2.3 G 2017-10-03 10:44 /user/andrescruzat/teragen_out/part-m-00003


#### Correr TERASORT
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/andrescruzat/teragen_out /user/andrescruzat/terasort_out

[ec2-user@ip-172-31-19-50 home]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/andrescruzat/teragen_out /user/andrescruzat/terasort_out
17/10/03 10:51:20 INFO terasort.TeraSort: starting
17/10/03 10:51:22 INFO input.FileInputFormat: Total input paths to process : 4
Spent 230ms computing base-splits.
Spent 6ms computing TeraScheduler splits.
Computing input splits took 236ms
Sampling 10 splits of 300
Making 16 from 100000 sampled records
Computing parititions took 664ms
Spent 903ms computing partitions.
17/10/03 10:51:22 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-18-46.us-east-2.compute.internal/172.31.18.46:8032
17/10/03 10:51:23 INFO mapreduce.JobSubmitter: number of splits:300
17/10/03 10:51:23 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507007928382_0003
17/10/03 10:51:23 INFO impl.YarnClientImpl: Submitted application application_1507007928382_0003
17/10/03 10:51:23 INFO mapreduce.Job: The url to track the job: http://ip-172-31-18-46.us-east-2.compute.internal:8088/proxy/application_1507007928382_0003/
17/10/03 10:51:23 INFO mapreduce.Job: Running job: job_1507007928382_0003
17/10/03 10:51:28 INFO mapreduce.Job: Job job_1507007928382_0003 running in uber mode : false
17/10/03 10:51:28 INFO mapreduce.Job:  map 0% reduce 0%
17/10/03 10:51:40 INFO mapreduce.Job:  map 1% reduce 0%
17/10/03 10:51:41 INFO mapreduce.Job:  map 4% reduce 0%
17/10/03 10:51:42 INFO mapreduce.Job:  map 8% reduce 0%
17/10/03 10:51:43 INFO mapreduce.Job:  map 10% reduce 0%
17/10/03 10:51:50 INFO mapreduce.Job:  map 12% reduce 0%
17/10/03 10:51:51 INFO mapreduce.Job:  map 13% reduce 0%
17/10/03 10:51:52 INFO mapreduce.Job:  map 14% reduce 0%
17/10/03 10:51:53 INFO mapreduce.Job:  map 17% reduce 0%
17/10/03 10:51:54 INFO mapreduce.Job:  map 20% reduce 0%
17/10/03 10:51:55 INFO mapreduce.Job:  map 21% reduce 0%
17/10/03 10:52:01 INFO mapreduce.Job:  map 22% reduce 0%
17/10/03 10:52:02 INFO mapreduce.Job:  map 23% reduce 0%
17/10/03 10:52:03 INFO mapreduce.Job:  map 24% reduce 0%
17/10/03 10:52:04 INFO mapreduce.Job:  map 25% reduce 0%
17/10/03 10:52:05 INFO mapreduce.Job:  map 26% reduce 0%
17/10/03 10:52:06 INFO mapreduce.Job:  map 29% reduce 0%
17/10/03 10:52:07 INFO mapreduce.Job:  map 31% reduce 0%
17/10/03 10:52:10 INFO mapreduce.Job:  map 32% reduce 0%
17/10/03 10:52:12 INFO mapreduce.Job:  map 33% reduce 0%
17/10/03 10:52:13 INFO mapreduce.Job:  map 34% reduce 0%
17/10/03 10:52:14 INFO mapreduce.Job:  map 35% reduce 0%
17/10/03 10:52:16 INFO mapreduce.Job:  map 36% reduce 0%
17/10/03 10:52:17 INFO mapreduce.Job:  map 38% reduce 0%
17/10/03 10:52:18 INFO mapreduce.Job:  map 41% reduce 0%
17/10/03 10:52:20 INFO mapreduce.Job:  map 43% reduce 0%
17/10/03 10:52:22 INFO mapreduce.Job:  map 44% reduce 0%
17/10/03 10:52:25 INFO mapreduce.Job:  map 45% reduce 0%
17/10/03 10:52:27 INFO mapreduce.Job:  map 46% reduce 0%
17/10/03 10:52:28 INFO mapreduce.Job:  map 47% reduce 0%
17/10/03 10:52:29 INFO mapreduce.Job:  map 48% reduce 0%
17/10/03 10:52:30 INFO mapreduce.Job:  map 51% reduce 0%
17/10/03 10:52:31 INFO mapreduce.Job:  map 53% reduce 0%
17/10/03 10:52:32 INFO mapreduce.Job:  map 54% reduce 0%
17/10/03 10:52:35 INFO mapreduce.Job:  map 55% reduce 0%
17/10/03 10:52:38 INFO mapreduce.Job:  map 56% reduce 0%
17/10/03 10:52:39 INFO mapreduce.Job:  map 57% reduce 0%
17/10/03 10:52:40 INFO mapreduce.Job:  map 59% reduce 0%
17/10/03 10:52:41 INFO mapreduce.Job:  map 61% reduce 0%
17/10/03 10:52:42 INFO mapreduce.Job:  map 64% reduce 0%
17/10/03 10:52:46 INFO mapreduce.Job:  map 65% reduce 0%
17/10/03 10:52:48 INFO mapreduce.Job:  map 66% reduce 0%
17/10/03 10:52:50 INFO mapreduce.Job:  map 68% reduce 0%
17/10/03 10:52:51 INFO mapreduce.Job:  map 70% reduce 0%
17/10/03 10:52:52 INFO mapreduce.Job:  map 73% reduce 0%
17/10/03 10:52:54 INFO mapreduce.Job:  map 74% reduce 0%
17/10/03 10:52:55 INFO mapreduce.Job:  map 75% reduce 0%
17/10/03 10:52:59 INFO mapreduce.Job:  map 76% reduce 0%
17/10/03 10:53:01 INFO mapreduce.Job:  map 79% reduce 0%
17/10/03 10:53:02 INFO mapreduce.Job:  map 80% reduce 0%
17/10/03 10:53:03 INFO mapreduce.Job:  map 82% reduce 0%
17/10/03 10:53:04 INFO mapreduce.Job:  map 83% reduce 0%
17/10/03 10:53:06 INFO mapreduce.Job:  map 84% reduce 0%
17/10/03 10:53:07 INFO mapreduce.Job:  map 85% reduce 0%
17/10/03 10:53:09 INFO mapreduce.Job:  map 86% reduce 0%
17/10/03 10:53:11 INFO mapreduce.Job:  map 88% reduce 0%
17/10/03 10:53:12 INFO mapreduce.Job:  map 90% reduce 0%
17/10/03 10:53:13 INFO mapreduce.Job:  map 91% reduce 0%
17/10/03 10:53:14 INFO mapreduce.Job:  map 92% reduce 0%
17/10/03 10:53:16 INFO mapreduce.Job:  map 93% reduce 0%
17/10/03 10:53:22 INFO mapreduce.Job:  map 94% reduce 0%
17/10/03 10:53:23 INFO mapreduce.Job:  map 95% reduce 0%
17/10/03 10:53:24 INFO mapreduce.Job:  map 96% reduce 6%
17/10/03 10:53:26 INFO mapreduce.Job:  map 98% reduce 12%
17/10/03 10:53:28 INFO mapreduce.Job:  map 98% reduce 20%
17/10/03 10:53:29 INFO mapreduce.Job:  map 99% reduce 24%
17/10/03 10:53:30 INFO mapreduce.Job:  map 99% reduce 30%
17/10/03 10:53:31 INFO mapreduce.Job:  map 100% reduce 31%
17/10/03 10:53:34 INFO mapreduce.Job:  map 100% reduce 35%
17/10/03 10:53:35 INFO mapreduce.Job:  map 100% reduce 39%
17/10/03 10:53:36 INFO mapreduce.Job:  map 100% reduce 46%
17/10/03 10:53:37 INFO mapreduce.Job:  map 100% reduce 53%
17/10/03 10:53:38 INFO mapreduce.Job:  map 100% reduce 60%
17/10/03 10:53:39 INFO mapreduce.Job:  map 100% reduce 64%
17/10/03 10:53:40 INFO mapreduce.Job:  map 100% reduce 67%
17/10/03 10:53:41 INFO mapreduce.Job:  map 100% reduce 71%
17/10/03 10:53:42 INFO mapreduce.Job:  map 100% reduce 80%
17/10/03 10:53:43 INFO mapreduce.Job:  map 100% reduce 82%
17/10/03 10:53:44 INFO mapreduce.Job:  map 100% reduce 86%
17/10/03 10:53:45 INFO mapreduce.Job:  map 100% reduce 87%
17/10/03 10:53:46 INFO mapreduce.Job:  map 100% reduce 89%
17/10/03 10:53:47 INFO mapreduce.Job:  map 100% reduce 90%
17/10/03 10:53:48 INFO mapreduce.Job:  map 100% reduce 91%
17/10/03 10:53:49 INFO mapreduce.Job:  map 100% reduce 92%
17/10/03 10:53:52 INFO mapreduce.Job:  map 100% reduce 93%
17/10/03 10:53:53 INFO mapreduce.Job:  map 100% reduce 94%
17/10/03 10:53:54 INFO mapreduce.Job:  map 100% reduce 95%
17/10/03 10:53:56 INFO mapreduce.Job:  map 100% reduce 96%
17/10/03 10:53:59 INFO mapreduce.Job:  map 100% reduce 97%
17/10/03 10:54:01 INFO mapreduce.Job:  map 100% reduce 98%
17/10/03 10:54:02 INFO mapreduce.Job:  map 100% reduce 100%
17/10/03 10:54:03 INFO mapreduce.Job: Job job_1507007928382_0003 completed successfully
17/10/03 10:54:03 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=4436437787
                FILE: Number of bytes written=8820441992
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=10000048600
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=948
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=32
        Job Counters
                Launched map tasks=300
                Launched reduce tasks=16
                Data-local map tasks=300
                Total time spent by all maps in occupied slots (ms)=2931767
                Total time spent by all reduces in occupied slots (ms)=764228
                Total time spent by all map tasks (ms)=2931767
                Total time spent by all reduce tasks (ms)=764228
                Total vcore-milliseconds taken by all map tasks=2931767
                Total vcore-milliseconds taken by all reduce tasks=764228
                Total megabyte-milliseconds taken by all map tasks=3002129408
                Total megabyte-milliseconds taken by all reduce tasks=782569472
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Map output bytes=10200000000
                Map output materialized bytes=4343005233
                Input split bytes=48600
                Combine input records=0
                Combine output records=0
                Reduce input groups=100000000
                Reduce shuffle bytes=4343005233
                Reduce input records=100000000
                Reduce output records=100000000
                Spilled Records=200000000
                Shuffled Maps =4800
                Failed Shuffles=0
                Merged Map outputs=4800
                GC time elapsed (ms)=51228
                CPU time spent (ms)=1487730
                Physical memory (bytes) snapshot=171514859520
                Virtual memory (bytes) snapshot=504189251584
                Total committed heap usage (bytes)=187655258112
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=10000000000
        File Output Format Counters
                Bytes Written=10000000000
17/10/03 10:54:03 INFO terasort.TeraSort: done

real    2m43.583s
user    0m7.589s
sys     0m0.340s
[ec2-user@ip-172-31-19-50 home]$ hdfs dfs -ls -h /user/andrescruzat/terasort_out
Found 18 items
-rw-r--r--   1 andrescruzat supergroup          0 2017-10-03 10:54 /user/andrescruzat/terasort_out/_SUCCESS
-rw-r--r--  10 andrescruzat supergroup        165 2017-10-03 10:51 /user/andrescruzat/terasort_out/_partition.lst
-rw-r--r--   1 andrescruzat supergroup    600.4 M 2017-10-03 10:53 /user/andrescruzat/terasort_out/part-r-00000
-rw-r--r--   1 andrescruzat supergroup    603.5 M 2017-10-03 10:53 /user/andrescruzat/terasort_out/part-r-00001
-rw-r--r--   1 andrescruzat supergroup    578.9 M 2017-10-03 10:53 /user/andrescruzat/terasort_out/part-r-00002
-rw-r--r--   1 andrescruzat supergroup    587.0 M 2017-10-03 10:54 /user/andrescruzat/terasort_out/part-r-00003
-rw-r--r--   1 andrescruzat supergroup    592.6 M 2017-10-03 10:54 /user/andrescruzat/terasort_out/part-r-00004
-rw-r--r--   1 andrescruzat supergroup    593.3 M 2017-10-03 10:54 /user/andrescruzat/terasort_out/part-r-00005
-rw-r--r--   1 andrescruzat supergroup    599.1 M 2017-10-03 10:53 /user/andrescruzat/terasort_out/part-r-00006
-rw-r--r--   1 andrescruzat supergroup    587.9 M 2017-10-03 10:54 /user/andrescruzat/terasort_out/part-r-00007
-rw-r--r--   1 andrescruzat supergroup    597.2 M 2017-10-03 10:54 /user/andrescruzat/terasort_out/part-r-00008
-rw-r--r--   1 andrescruzat supergroup    601.5 M 2017-10-03 10:54 /user/andrescruzat/terasort_out/part-r-00009
-rw-r--r--   1 andrescruzat supergroup    601.2 M 2017-10-03 10:53 /user/andrescruzat/terasort_out/part-r-00010
-rw-r--r--   1 andrescruzat supergroup    597.2 M 2017-10-03 10:53 /user/andrescruzat/terasort_out/part-r-00011
-rw-r--r--   1 andrescruzat supergroup    585.8 M 2017-10-03 10:53 /user/andrescruzat/terasort_out/part-r-00012
-rw-r--r--   1 andrescruzat supergroup    607.9 M 2017-10-03 10:53 /user/andrescruzat/terasort_out/part-r-00013
-rw-r--r--   1 andrescruzat supergroup    597.7 M 2017-10-03 10:53 /user/andrescruzat/terasort_out/part-r-00014
-rw-r--r--   1 andrescruzat supergroup    605.6 M 2017-10-03 10:54 /user/andrescruzat/terasort_out/part-r-00015

