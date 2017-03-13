google cloud account: adeadang@gmail.com

using google cloud env

machine type	  name		      zone			        spec		        OS		    internal    ip	external ip

n1-highmem-2	  instance-1	  asia-northeast1-b	2 vCPUs, 13 GB	CentOS-6	10.146.0.2	104.198.82.198

n1-highmem-2	  instance-2	  asia-northeast1-b	2 vCPUs, 13 GB	CentOS-6	10.146.0.3	104.198.90.255

n1-highmem-2	  instance-3	  asia-northeast1-b	2 vCPUs, 13 GB	CentOS-6	10.146.0.4	104.198.84.39 

n1-highmem-2	  instance-4	  asia-northeast1-b	2 vCPUs, 13 GB	CentOS-6	10.146.0.5	104.198.127.36

n1-highmem-2	  instance-5	  asia-northeast1-b	2 vCPUs, 13 GB	CentOS-6	10.146.0.6	104.198.82.187 


volume 

[root@instance-1 adeadang]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        30G  1.3G   27G   5% /
tmpfs           6.4G     0  6.4G   0% /dev/shm

[root@instance-2 adeadang]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        30G  1.3G   27G   5% /
tmpfs           6.4G     0  6.4G   0% /dev/shm

[root@instance-3 adeadang]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        30G  1.3G   27G   5% /
tmpfs           6.4G     0  6.4G   0% /dev/shm

[root@instance-4 adeadang]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        30G  1.3G   27G   5% /
tmpfs           6.4G     0  6.4G   0% /dev/shm

[root@instance-5 adeadang]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        30G  1.3G   27G   5% /
tmpfs           6.4G     0  6.4G   0% /dev/shm

repolist

[root@instance-1 adeadang]# yum repolist enabled
Loaded plugins: fastestmirror, security
Determining fastest mirrors
 * base: mirror.hmc.edu
 * extras: centos.sonn.com
 * updates: yum.tamu.edu
base                                                                                                                                               | 3.7 kB     00:00     
base/primary_db                                                                                                                                    | 4.7 MB     00:03     
centos-sclo-rh                                                                                                                                     | 2.9 kB     00:00     
centos-sclo-rh/primary_db                                                                                                                          | 1.4 MB     00:02     
centos-sclo-sclo                                                                                                                                   | 2.9 kB     00:00     
centos-sclo-sclo/primary_db                                                                                                                        |  84 kB     00:00     
extras                                                                                                                                             | 3.4 kB     00:00     
extras/primary_db                                                                                                                                  |  37 kB     00:00     
google-cloud-compute/signature                                                                                                                     |  454 B     00:00     
google-cloud-compute/signature                                                                                                                     | 1.4 kB     00:00 ... 
google-cloud-compute/primary                                                                                                                       | 2.0 kB     00:00     
google-cloud-compute                                                                                                                                                  4/4
updates                                                                                                                                            | 3.4 kB     00:00     
updates/primary_db                                                                                                                                 | 3.7 MB     00:02     
repo id                                                                           repo name                                                                         status
base                                                                              CentOS-6 - Base                                                                   6,696
centos-sclo-rh                                                                    CentOS-6 - SCLo rh                                                                2,905
centos-sclo-sclo                                                                  CentOS-6 - SCLo sclo                                                                227
extras                                                                            CentOS-6 - Extras                                                                    62
google-cloud-compute                                                              Google Cloud Compute                                                                  4
updates                                                                           CentOS-6 - Updates                                                                  686
repolist: 10,580


user add

[root@instance-1 adeadang]# adduser raffles
[root@instance-1 adeadang]# adduser orchard

setting uid for 2700/raffless and 2800orchard

[root@instance-1 adeadang]# usermod -u 2700 raffles
[root@instance-1 adeadang]# usermod -u 2800 orchard

group add

[root@instance-1 adeadang]# groupadd shops
[root@instance-1 adeadang]# groupadd walks

adding user to group

[root@instance-1 adeadang]# usermod -g shops raffles
[root@instance-1 adeadang]# usermod -g walks orchard

result /etc/passwd and /etc/group

[root@instance-1 adeadang]# cat /etc/passwd | grep raffles
raffles:x:2700:504::/home/raffles:/bin/bash

[root@instance-1 adeadang]# cat /etc/passwd | grep raffles
raffles:x:2700:504::/home/raffles:/bin/bash

[root@instance-1 adeadang]# cat /etc/passwd | grep orchard
orchard:x:2800:505::/home/orchard:/bin/bash

[root@instance-1 adeadang]# cat /etc/group | grep shops
shops:x:504:

[root@instance-1 adeadang]# cat /etc/group | grep walks
walks:x:505:


tes
