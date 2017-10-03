#### HDFS Lab: Replicate to another cluster
#### Crear directorios

[ec2-user@ip-172-31-19-50 ~]$ hdfs dfs -mkdir -p /labs/storage/andrescruzat
[ec2-user@ip-172-31-19-50 ~]$ hdfs dfs -mkdir -p /labs/storage/DKvothe
[ec2-user@ip-172-31-19-50 ~]$ hdfs dfs -ls /labs/storage
Found 2 items
drwxr-xr-x   - hdfs supergroup          0 2017-10-03 09:12 /labs/storage/DKvothe
drwxr-xr-x   - hdfs supergroup          0 2017-10-03 09:11 /labs/storage/andrescruzat

#### Correr TERAGEN
hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar \
teragen -Dmapred.map.tasks=20 \
-Dmapred.map.tasks.speculative.execution=false 5000000 \
/labs/storage/andrescruzat/input_teragen

[ec2-user@ip-172-31-19-50 /]$ hadoop jar  /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar \
> teragen -Dmapred.map.tasks=20 \
> -Dmapred.map.tasks.speculative.execution=false 5000000 \
> /labs/storage/andrescruzat/input_teragen
17/10/03 09:26:05 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-18-46.us-east-2.compute.internal/172.31.18.46:8032
17/10/03 09:26:05 INFO terasort.TeraGen: Generating 5000000 using 20
17/10/03 09:26:05 INFO mapreduce.JobSubmitter: number of splits:20
17/10/03 09:26:05 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/10/03 09:26:05 INFO Configuration.deprecation: mapred.map.tasks.speculative.execution is deprecated. Instead, use mapreduce.map.speculative
17/10/03 09:26:06 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507007928382_0001
17/10/03 09:26:06 INFO impl.YarnClientImpl: Submitted application application_1507007928382_0001
17/10/03 09:26:06 INFO mapreduce.Job: The url to track the job: http://ip-172-31-18-46.us-east-2.compute.internal:8088/proxy/application_1507007928382_0001/
17/10/03 09:26:06 INFO mapreduce.Job: Running job: job_1507007928382_0001
17/10/03 09:26:12 INFO mapreduce.Job: Job job_1507007928382_0001 running in uber mode : false
17/10/03 09:26:12 INFO mapreduce.Job:  map 0% reduce 0%
17/10/03 09:26:20 INFO mapreduce.Job:  map 20% reduce 0%
17/10/03 09:26:22 INFO mapreduce.Job:  map 75% reduce 0%
17/10/03 09:26:23 INFO mapreduce.Job:  map 100% reduce 0%
17/10/03 09:26:23 INFO mapreduce.Job: Job job_1507007928382_0001 completed successfully
17/10/03 09:26:23 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=2561230
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1697
                HDFS: Number of bytes written=500000000
                HDFS: Number of read operations=80
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=40
        Job Counters
                Launched map tasks=20
                Other local map tasks=20
                Total time spent by all maps in occupied slots (ms)=148411
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=148411
                Total vcore-milliseconds taken by all map tasks=148411
                Total megabyte-milliseconds taken by all map tasks=151972864
        Map-Reduce Framework
                Map input records=5000000
                Map output records=5000000
                Input split bytes=1697
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=2210
                CPU time spent (ms)=52630
                Physical memory (bytes) snapshot=5315964928
                Virtual memory (bytes) snapshot=32022372352
                Total committed heap usage (bytes)=12236881920
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=10735710707299981
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=500000000

[ec2-user@ip-172-31-19-50 /]$ hdfs dfs -ls -h /labs/storage/andrescruzat/input_teragen
Found 21 items
-rw-r--r--   3 hdfs supergroup          0 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/_SUCCESS
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00000
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00001
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00002
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00003
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00004
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00005
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00006
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00007
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00008
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00009
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00010
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00011
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00012
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00013
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00014
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00015
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00016
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00017
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00018
-rw-r--r--   3 hdfs supergroup     23.8 M 2017-10-03 09:26 /labs/storage/andrescruzat/input_teragen/part-m-00019

#### NO SE LOGRO LA REPLICACION POR QUE NO VEO EL CLUSTER DE MI PARTNER

