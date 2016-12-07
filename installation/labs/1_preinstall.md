> operating system
[root@instance-6 adeadang]# cat /etc/redhat-release 
CentOS release 6.8 (Final)

> kernel version
[root@instance-6 adeadang]# uname -a
Linux instance-6 2.6.32-642.11.1.el6.x86_64 #1 SMP Fri Nov 18 19:25:05 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux

> ip address, hostname
[root@instance-6 adeadang]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN 
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1460 qdisc mq state UP qlen 1000
    link/ether 42:01:0a:92:00:02 brd ff:ff:ff:ff:ff:ff
    inet 10.146.0.2/32 brd 10.146.0.2 scope global eth0
    inet6 fe80::4001:aff:fe92:2/64 scope link 
       valid_lft forever preferred_lft forever
       
> hostname and dns
[root@instance-10 adeadang]# cat /etc/hosts
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
10.146.0.6 instance-10.c.api-project-778269081458.internal instance-10  # Added by Google
169.254.169.254 metadata.google.internal  # Added by Google

[root@instance-10 ~]# getent hosts
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
10.146.0.6      instance-10.c.api-project-778269081458.internal instance-10
169.254.169.254 metadata.google.internal
[root@instance-10 ~]# nslookup instance-10.c.api-project-778269081458.internal
Server:         169.254.169.254
Address:        169.254.169.254#53

Non-authoritative answer:
Name:   instance-10.c.api-project-778269081458.internal
Address: 10.146.0.6

[root@instance-10 ~]#

> memory
[root@instance-10 adeadang]# free 
             total       used       free     shared    buffers     cached
Mem:      13232688     419332   12813356        144      19212     151252
-/+ buffers/cache:     248868   12983820
Swap:            0          0          0

> storage
[root@instance-10 adeadang]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        30G  1.3G   27G   5% /
tmpfs           6.4G     0  6.4G   0% /dev/shm

> mount and partition
[root@instance-10 adeadang]# cat /etc/fstab 
UUID=eaca619d-70f4-447b-b6b3-c2faaa4aeae8 /     ext4    defaults,barrier=1 1 1
tmpfs                   /dev/shm                tmpfs   defaults        0 0
devpts                  /dev/pts                devpts  gid=5,mode=620  0 0
sysfs                   /sys                    sysfs   defaults        0 0
proc                    /proc                   proc    defaults        0 0

> vm.swappines adding  "vm.swappiness = 10" to file /etc/sysctl.conf 
[root@instance-6 adeadang]# echo 10 > /proc/sys/vm/swappiness
[root@instance-6 adeadang]# cat /proc/sys/vm/swappiness 
10

> hugepage disabled
[root@instance-10 adeadang]# cat /sys/kernel/mm/transparent_hugepage/enabled
[always] madvise never
[root@instance-10 adeadang]# cat /sys/kernel/mm/transparent_hugepage/defrag
[always] madvise never

> nscd service
[root@instance-10 adeadang]# service nscd status
nscd is stopped
[root@instance-10 adeadang]# service nscd start
Starting nscd:                                             [  OK  ]
[root@instance-10 adeadang]# chkconfig nscd on
[root@instance-10 adeadang]# service nscd status
nscd (pid 2083) is running...

> ntpd service
[root@instance-10 adeadang]# service ntpd status
ntpd (pid  1477) is running...
