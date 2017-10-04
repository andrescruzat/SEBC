[root@ip-172-31-19-50 ec2-user]# beeline
Beeline version 1.1.0-cdh5.11.2 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-18-122.us-east-2.compute.internal:10000/default;principal=hive/_HOST@ACRUZATCDH.COM
scan complete in 1ms
Connecting to jdbc:hive2://ip-172-31-18-122.us-east-2.compute.internal:10000/default;principal=hive/_HOST@ACRUZATCDH.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.2)
Driver: Hive JDBC (version 1.1.0-cdh5.11.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-18-122.us-east-2.co> show tables;
INFO  : Compiling command(queryId=hive_20171004184747_fd51ce34-2f59-43a7-b4f4-e6ae2e964aaf): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171004184747_fd51ce34-2f59-43a7-b4f4-e6ae2e964aaf); Time taken: 0.605 seconds
INFO  : Executing command(queryId=hive_20171004184747_fd51ce34-2f59-43a7-b4f4-e6ae2e964aaf): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004184747_fd51ce34-2f59-43a7-b4f4-e6ae2e964aaf); Time taken: 0.252 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.177 seconds)


#### Autenticar george en kerberos

[root@ip-172-31-19-50 ec2-user]# kinit george
Password for george@ACRUZATCDH.COM:
[root@ip-172-31-19-50 ec2-user]# beeline
Beeline version 1.1.0-cdh5.11.2 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-18-122.us-east-2.compute.internal:10000/default;principal=hive/_HOST@ACRUZATCDH.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-18-122.us-east-2.compute.internal:10000/default;principal=hive/_HOST@ACRUZATCDH.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.2)
Driver: Hive JDBC (version 1.1.0-cdh5.11.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-18-122.us-east-2.co> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171004190606_613d019e-9a8e-4ca7-90ff-566b70fce8e3): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171004190606_613d019e-9a8e-4ca7-90ff-566b70fce8e3); Time taken: 0.072 seconds
INFO  : Executing command(queryId=hive_20171004190606_613d019e-9a8e-4ca7-90ff-566b70fce8e3): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004190606_613d019e-9a8e-4ca7-90ff-566b70fce8e3); Time taken: 0.137 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.301 seconds)

#### Autenticar ferdinand en kerberos

[root@ip-172-31-19-50 ec2-user]# kinit ferdinand
Password for ferdinand@ACRUZATCDH.COM:
[root@ip-172-31-19-50 ec2-user]# beeline
Beeline version 1.1.0-cdh5.11.2 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-18-122.us-east-2.compute.internal:10000/default;principal=hive/_HOST@ACRUZATCDH.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-18-122.us-east-2.compute.internal:10000/default;principal=hive/_HOST@ACRUZATCDH.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.2)
Driver: Hive JDBC (version 1.1.0-cdh5.11.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-18-122.us-east-2.co> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171004190808_d30e1dbb-9e42-4325-8836-6a26529c4a26): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171004190808_d30e1dbb-9e42-4325-8836-6a26529c4a26); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20171004190808_d30e1dbb-9e42-4325-8836-6a26529c4a26): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004190808_d30e1dbb-9e42-4325-8836-6a26529c4a26); Time taken: 0.124 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.286 seconds)


