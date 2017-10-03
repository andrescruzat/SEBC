--> Revisar y setar el swapp
cat /proc/sys/vm/swappiness
cat /etc/sysctl.conf

echo "vm.swappiness = 1" >> /etc/sysctl.conf
echo 1 > /proc/sys/vm/swappiness

--> Estado de unidades montadas
[root@ip-172-31-2-104 /]# cat /etc/fstab

#
# /etc/fstab
# Created by anaconda on Sun Jul 10 13:34:52 2016
#
# Accessible filesystems, by reference, are maintained under '/dev/disk'
# See man pages fstab(5), findfs(8), mount(8) and/or blkid(8) for more info
#
/dev/mapper/centos-root /       xfs     defaults        0 0
UUID=8d6aa0ef-d963-4380-9748-2ed24a7c5c96       /boot   xfs     defaults        0 0
UUID=60262b1e-b11c-46c9-9d6b-b6c24af24ff4       /disco1   ext4     defaults        0 0
UUID=3b8d91bb-45ef-410d-8584-606bf0e7d1d2       /disco2   ext4     defaults        0 0


--> Espacio reservado
[root@ip-172-31-2-104 /]# lsblk
NAME            MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
xvda            202:0    0   40G  0 disk
├─xvda1         202:1    0  500M  0 part /boot
└─xvda2         202:2    0  7.5G  0 part
  ├─centos-root 253:0    0  6.7G  0 lvm  /
  └─centos-swap 253:1    0  820M  0 lvm
xvdb            202:16   0  120G  0 disk /disco1
xvdc            202:32   0  120G  0 disk /disco2

[root@ip-172-31-2-104 /]# df -h
Filesystem               Size  Used Avail Use% Mounted on
/dev/mapper/centos-root  6.7G  1.2G  5.5G  19% /
devtmpfs                  16G     0   16G   0% /dev
tmpfs                     16G     0   16G   0% /dev/shm
tmpfs                     16G  8.3M   16G   1% /run
tmpfs                     16G     0   16G   0% /sys/fs/cgroup
/dev/xvda1               497M  140M  357M  29% /boot
tmpfs                    3.2G     0  3.2G   0% /run/user/1000
/dev/xvdb                118G   61M  112G   1% /disco1
/dev/xvdc                118G   63M  112G   1% /disco2


--> Disabled THP
[root@ip-172-31-2-104 etc]# cat /sys/kernel/mm/transparent_hugepage/enabled
[always] madvise never
[root@ip-172-31-2-104 etc]# cat /sys/kernel/mm/transparent_hugepage/defrag
[always] madvise never
[root@ip-172-31-2-104 etc]# echo 'never' > /sys/kernel/mm/transparent_hugepage/enabled
[root@ip-172-31-2-104 etc]# echo 'never' > /sys/kernel/mm/transparent_hugepage/defrag
[root@ip-172-31-2-104 etc]# cat /sys/kernel/mm/transparent_hugepage/enabled
always madvise [never]
[root@ip-172-31-2-104 etc]# cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]

#### modificar archivo /etc/sysconfig/grub para que quede permanente

vi /etc/sysconfig/grub
modificar 
GRUB_CMDLINE_LINUX=”crashkernel=auto rd.lvm.lv=centos/root rd.lvm.lv=centos/swap rhgb quiet console=ttyS0 transparent_hugepage=never”


--> Listar configuracion de red
[root@ip-172-31-2-104 etc]# ip addr show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 02:da:fb:9b:d9:ec brd ff:ff:ff:ff:ff:ff
    inet 172.31.2.104/20 brd 172.31.15.255 scope global dynamic eth0
       valid_lft 2194sec preferred_lft 2194sec
    inet6 fe80::da:fbff:fe9b:d9ec/64 scope link
       valid_lft forever preferred_lft forever

--> Configuracion /etc/hosts
[root@ip-172-31-2-104 etc]# getent hosts
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6

--> nslookup
[root@ip-172-31-2-104 etc]# nslookup ec2-18-221-181-209.us-east-2.compute.amazonaws.com
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ec2-18-221-181-209.us-east-2.compute.amazonaws.com
Address: 172.31.1.241

[root@ip-172-31-2-104 etc]# nslookup ec2-18-221-97-251.us-east-2.compute.amazonaws.com
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ec2-18-221-97-251.us-east-2.compute.amazonaws.com
Address: 172.31.0.31

[root@ip-172-31-2-104 etc]# nslookup ec2-18-221-3-50.us-east-2.compute.amazonaws.com
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ec2-18-221-3-50.us-east-2.compute.amazonaws.com
Address: 172.31.6.155

[root@ip-172-31-2-104 etc]# nslookup ec2-13-59-16-71.us-east-2.compute.amazonaws.com
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ec2-13-59-16-71.us-east-2.compute.amazonaws.com
Address: 172.31.13.97

--> NSCD
[root@ip-172-31-2-104 etc]# service nscd status
Redirecting to /bin/systemctl status  nscd.service
? nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; disabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-02 15:25:38 EDT; 12s ago
  Process: 3646 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 3647 (nscd)
   CGroup: /system.slice/nscd.service
           +-3647 /usr/sbin/nscd

Oct 02 15:25:38 ip-172-31-2-104 nscd[3647]: 3647 monitoring file `/etc/hosts` (4)
Oct 02 15:25:38 ip-172-31-2-104 nscd[3647]: 3647 monitoring directory `/etc` (2)
Oct 02 15:25:38 ip-172-31-2-104 nscd[3647]: 3647 monitoring file `/etc/resolv.conf` (5)
Oct 02 15:25:38 ip-172-31-2-104 nscd[3647]: 3647 monitoring directory `/etc` (2)
Oct 02 15:25:38 ip-172-31-2-104 nscd[3647]: 3647 monitoring file `/etc/services` (6)
Oct 02 15:25:38 ip-172-31-2-104 nscd[3647]: 3647 monitoring directory `/etc` (2)
Oct 02 15:25:38 ip-172-31-2-104 nscd[3647]: 3647 disabled inotify-based monitoring for file `/etc/netgroup': No such file or directory
Oct 02 15:25:38 ip-172-31-2-104 nscd[3647]: 3647 stat failed for file `/etc/netgroup'; will try again later: No such file or directory
Oct 02 15:25:38 ip-172-31-2-104 nscd[3647]: 3647 Access Vector Cache (AVC) started
Oct 02 15:25:38 ip-172-31-2-104 systemd[1]: Started Name Service Cache Daemon.
Hint: Some lines were ellipsized, use -l to show in full.

--> NTPD
[root@ip-172-31-2-104 etc]# service ntpd status
Redirecting to /bin/systemctl status  ntpd.service
? ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; disabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-02 15:35:08 EDT; 6s ago
  Process: 3766 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 3767 (ntpd)
   CGroup: /system.slice/ntpd.service
           +-3767 /usr/sbin/ntpd -u ntp:ntp -g

Oct 02 15:35:08 ip-172-31-2-104 ntpd[3767]: Listen and drop on 1 v6wildcard :: UDP 123
Oct 02 15:35:08 ip-172-31-2-104 ntpd[3767]: Listen normally on 2 lo 127.0.0.1 UDP 123
Oct 02 15:35:08 ip-172-31-2-104 ntpd[3767]: Listen normally on 3 eth0 172.31.2.104 UDP 123
Oct 02 15:35:08 ip-172-31-2-104 ntpd[3767]: Listen normally on 4 lo ::1 UDP 123
Oct 02 15:35:08 ip-172-31-2-104 ntpd[3767]: Listen normally on 5 eth0 fe80::da:fbff:fe9b:d9ec UDP 123
Oct 02 15:35:08 ip-172-31-2-104 ntpd[3767]: Listening on routing socket on fd #22 for interface updates
Oct 02 15:35:08 ip-172-31-2-104 systemd[1]: Started Network Time Service.
Oct 02 15:35:08 ip-172-31-2-104 ntpd[3767]: 0.0.0.0 c016 06 restart
Oct 02 15:35:08 ip-172-31-2-104 ntpd[3767]: 0.0.0.0 c012 02 freq_set kernel 0.000 PPM
Oct 02 15:35:08 ip-172-31-2-104 ntpd[3767]: 0.0.0.0 c011 01 freq_not_set


--> Instalar MariaDB
yum install mariadb-server
### configuraciones varias... usuario root, pwd instancia de AWS
[root@ip-172-31-2-104 etc]# systemctl list-unit-files | grep mariadb
mariadb.service                             enabled

[root@ip-172-31-2-104 etc]# /usr/bin/mysql_secure_installation
...
Cleaning up...
All done!  If you've completed all of the above steps, your MariaDB
installation should now be secure.

Thanks for using MariaDB!

### crear BD

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| amon               |
| cmf                |
| hue                |
| metastore          |
| mysql              |
| nav                |
| navms              |
| oozie              |
| performance_schema |
| rman               |
| sentry             |
+--------------------+
12 rows in set (0.00 sec)

- driver descargar y despues...
mkdir -p /usr/share/java/
chmod 777 /usr/share/java/

[root@ip-172-31-2-104 /]# mkdir -p /usr/share/java/
[root@ip-172-31-2-104 /]# chmod 777 /usr/share/java/
cd /home
wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.44.tar.gz
tar zxvf mysql-connector-java-5.1.44.tar.gz
cp mysql-connector-java-5.1.44/mysql-connector-java-5.1.44-bin.jar /usr/share/java/mysql-connector-java.jar

--> Descargar repositorio Cloudera
cd /etc/yum.repos.d/
wget https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/cloudera-manager.repo
modificar archivo para la version deseada


--> Instalar Java
yum install oracle-j2sdk1.7

JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera 
JRE_HOME=/usr/java/jdk1.7.0_67-cloudera 
PATH=$PATH:$JRE_HOME/bin:$JAVA_HOME/bin 
export JAVA_HOME 
export JRE_HOME 
export PATH

--> Instalar Cloudera
	
$ sudo yum install cloudera-manager-daemons cloudera-manager-server

--> ejecutar preparacion de BD

#### /usr/share/cmf/schema/scm_prepare_database.sh database-type [options] database-name username password
/usr/share/cmf/schema/scm_prepare_database.sh mysql cmf cmf cmf_password

--> iniciar servicio

service cloudera-scm-server start
###top
tail -f /var/log/cloudera-scm-server/cloudera-scm-server.log

[root@ip-172-31-2-104 /]# service cloudera-scm-server status
/etc/init.d/cloudera-scm-server: line 109: pstree: command not found
? cloudera-scm-server.service - LSB: Cloudera SCM Server
   Loaded: loaded (/etc/rc.d/init.d/cloudera-scm-server)
   Active: active (exited) since Mon 2017-10-02 21:09:07 EDT; 12min ago
     Docs: man:systemd-sysv-generator(8)
  Process: 3862 ExecStart=/etc/rc.d/init.d/cloudera-scm-server start (code=exited, status=0/SUCCESS)

Oct 02 21:09:02 ip-172-31-2-104 systemd[1]: Starting LSB: Cloudera SCM Server...
Oct 02 21:09:02 ip-172-31-2-104 cloudera-scm-server[3862]: /etc/rc.d/init.d/cloudera-scm-server: line 109: pstree: command not found
Oct 02 21:09:02 ip-172-31-2-104 su[3889]: (to cloudera-scm) root on none
Oct 02 21:09:07 ip-172-31-2-104 cloudera-scm-server[3862]: Starting cloudera-scm-server: [  OK  ]
Oct 02 21:09:07 ip-172-31-2-104 systemd[1]: Started LSB: Cloudera SCM Server.

### Comienza instalacion de CDH en el cluster
