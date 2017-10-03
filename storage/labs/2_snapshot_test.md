---> HDFS Lab: Test HDFS Snapshots

#### Crear dierctorio y mover archivo dentro
[ec2-user@ip-172-31-19-50 home]$ export HADOOP_USER_NAME=hdfs
[ec2-user@ip-172-31-19-50 home]$ hdfs dfs -mkdir /precious
[ec2-user@ip-172-31-19-50 home]$ hdfs dfs -put /home/ec2-user/SEBC-master-students.zip /precious
[ec2-user@ip-172-31-19-50 home]$ hdfs dfs -ls /precious
Found 1 items
-rw-r--r--   3 hdfs supergroup     474831 2017-10-03 11:10 /precious/SEBC-master-students.zip

#### Borrar directorio? y archivo
[ec2-user@ip-172-31-19-50 home]$ hdfs dfs -rm -r /precious
rm: Failed to move to trash: hdfs://ip-172-31-19-50.us-east-2.compute.internal:8020/precious: The directory /precious cannot be deleted since /precious is snapshottable and already has snapshots
[ec2-user@ip-172-31-19-50 home]$ hdfs dfs -ls /precious
Found 1 items
-rw-r--r--   3 hdfs supergroup     474831 2017-10-03 11:10 /precious/SEBC-master-students.zip
[ec2-user@ip-172-31-19-50 home]$ hdfs dfs -rm -r /precious/SEBC-master-students.zip
17/10/03 11:19:02 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-19-50.us-east-2.compute.internal:8020/precious/SEBC-master-students.zip' to trash at: hdfs://ip-172-31-19-50.us-east-2.compute.internal:8020/user/hdfs/.Trash/Current/precious/SEBC-master-students.zip
[ec2-user@ip-172-31-19-50 home]$ hdfs dfs -ls /precious

#### La restauracion se hizo a travez de CM
