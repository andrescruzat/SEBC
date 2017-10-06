-List the cloud provider you are using (AWS, GCE, Azure, CloudCat, other)
AWS

-List your instances by IP address and DNS name (don't use /etc/hosts for this)
IP Publica
ec2-18-221-100-161.us-east-2.compute.amazonaws.com
ec2-18-221-139-65.us-east-2.compute.amazonaws.com
ec2-18-221-153-213.us-east-2.compute.amazonaws.com
ec2-18-220-53-180.us-east-2.compute.amazonaws.com
ec2-18-220-104-30.us-east-2.compute.amazonaws.com

DNS Privado
ip-172-31-40-99.us-east-2.compute.internal
ip-172-31-38-249.us-east-2.compute.internal
ip-172-31-32-203.us-east-2.compute.internal
ip-172-31-43-111.us-east-2.compute.internal
ip-172-31-36-168.us-east-2.compute.internal

-List the Linux release you are using
Centos 7.2

-List the file system capacity for the first node
[ec2-user@ip-172-31-40-99 ~]$ df -h
Filesystem               Size  Used Avail Use% Mounted on
/dev/mapper/centos-root  6.7G  1.3G  5.5G  19% /
devtmpfs                  16G     0   16G   0% /dev
tmpfs                     16G     0   16G   0% /dev/shm
tmpfs                     16G  8.4M   16G   1% /run
tmpfs                     16G     0   16G   0% /sys/fs/cgroup
/dev/xvdb                118G   61M  112G   1% /disco1
/dev/xvdc                118G  111M  112G   1% /disco2
/dev/xvda1               497M  140M  357M  29% /boot
tmpfs                    3.2G     0  3.2G   0% /run/user/1000


- List the command and output for yum repolist enabled
[ec2-user@ip-172-31-40-99 ~]$ yum repolist enabled
Loaded plugins: fastestmirror
Determining fastest mirrors
 * base: centos.mirrors.tds.net
 * extras: mirrors.cmich.edu
 * updates: mirror.trouble-free.net
repo id                                                         repo name                                                        status
!base/7/x86_64                                                  CentOS-7 - Base                                                  9,591
!extras/7/x86_64                                                CentOS-7 - Extras                                                  225
!updates/7/x86_64                                               CentOS-7 - Updates                                                 731
repolist: 10,547

