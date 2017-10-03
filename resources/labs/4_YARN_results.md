---> YARN/RM Lab: Tuning for YARN

#### Ejecucion 1
[root@ip-172-31-19-50 ec2-user]# export HADOOP_USER_NAME=hdfs
[root@ip-172-31-19-50 ec2-user]# sh YARNtest.sh
Testing loop started on Tue Oct 3 15:05:08 EDT 2017

real    1m11.755s
user    0m4.625s
sys     0m0.280s

real    1m46.410s
user    0m6.600s
sys     0m0.272s
Deleted /results/tg-10GB-8-1-512
Deleted /results/ts-10GB-8-1-512

real    0m51.823s
user    0m4.592s
sys     0m0.269s

real    1m54.898s
user    0m6.649s
sys     0m0.313s
Deleted /results/tg-10GB-8-1-1024
Deleted /results/ts-10GB-8-1-1024
Testing loop ended on Tue Oct 3 15:11:02 EDT 2017

#### Ejecucion 2
[root@ip-172-31-19-50 ec2-user]# sh YARNtest.sh
Testing loop started on Tue Oct 3 15:20:26 EDT 2017
 i=  8 , j=  1 , k=  512

real    1m4.145s
user    0m4.570s
sys     0m0.255s

real    2m20.828s
user    0m5.592s
sys     0m0.270s
Deleted /results/tg-10GB-8-1-512
Deleted /results/ts-10GB-8-1-512
 i=  8 , j=  1 , k=  1024

real    0m53.664s
user    0m4.662s
sys     0m0.272s

real    2m17.680s
user    0m6.780s
sys     0m0.318s
Deleted /results/tg-10GB-8-1-1024
Deleted /results/ts-10GB-8-1-1024
Testing loop ended on Tue Oct 3 15:27:12 EDT 2017

#### Ejecucion 3 (20 mappers y 4 reducers)
[root@ip-172-31-19-50 ec2-user]# sh YARNtest.sh
Testing loop started on Tue Oct 3 15:29:31 EDT 2017
 i=  20 , j=  4 , k=  512

real    0m59.873s
user    0m4.606s
sys     0m0.254s

real    1m21.259s
user    0m6.689s
sys     0m0.286s
Deleted /results/tg-10GB-20-4-512
Deleted /results/ts-10GB-20-4-512
 i=  20 , j=  4 , k=  1024

real    0m59.978s
user    0m4.584s
sys     0m0.287s

real    1m11.349s
user    0m6.652s
sys     0m0.293s
Deleted /results/tg-10GB-20-4-1024
Deleted /results/ts-10GB-20-4-1024
Testing loop ended on Tue Oct 3 15:34:12 EDT 2017

#### Ejecucion 4 (8 mappers y 8 reducers)
[root@ip-172-31-19-50 ec2-user]# sh YARNtest.sh
Testing loop started on Tue Oct 3 15:35:40 EDT 2017
 i=  8 , j=  8 , k=  512

real    1m3.815s
user    0m4.723s
sys     0m0.270s

real    1m2.652s
user    0m6.481s
sys     0m0.291s
Deleted /results/tg-10GB-8-8-512
Deleted /results/ts-10GB-8-8-512
 i=  8 , j=  8 , k=  1024

real    0m47.082s
user    0m4.657s
sys     0m0.275s

real    1m19.685s
user    0m6.573s
sys     0m0.286s
Deleted /results/tg-10GB-8-8-1024
Deleted /results/ts-10GB-8-8-1024
Testing loop ended on Tue Oct 3 15:40:02 EDT 2017

#### Ejecucion 5 (12 mappers y 4 reducers)
[root@ip-172-31-19-50 ec2-user]# sh YARNtest.sh
Testing loop started on Tue Oct 3 15:42:46 EDT 2017
 i=  12 , j=  4 , k=  512

real    0m51.711s
user    0m4.613s
sys     0m0.258s

real    1m31.349s
user    0m6.558s
sys     0m0.276s
Deleted /results/tg-10GB-12-4-512
Deleted /results/ts-10GB-12-4-512
 i=  12 , j=  4 , k=  1024

real    0m44.689s
user    0m4.602s
sys     0m0.272s

real    1m30.416s
user    0m6.594s
sys     0m0.283s
Deleted /results/tg-10GB-12-4-1024
Deleted /results/ts-10GB-12-4-1024
Testing loop ended on Tue Oct 3 15:47:40 EDT 2017

#### Ejecucion 6 (12 mappers y 8 reducers)
[root@ip-172-31-19-50 ec2-user]# sh YARNtest.sh
Testing loop started on Tue Oct 3 16:05:54 EDT 2017
 i=  12 , j=  8 , k=  512

real    0m44.681s
user    0m4.627s
sys     0m0.241s

real    1m23.245s
user    0m6.561s
sys     0m0.298s
Deleted /results/tg-10GB-12-8-512
Deleted /results/ts-10GB-12-8-512
 i=  12 , j=  8 , k=  1024

real    1m6.987s
user    0m4.611s
sys     0m0.280s

real    1m12.350s
user    0m6.677s
sys     0m0.324s
Deleted /results/tg-10GB-12-8-1024
Deleted /results/ts-10GB-12-8-1024
Testing loop ended on Tue Oct 3 16:10:30 EDT 2017
