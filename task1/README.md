


The disk file system is currently operating at full capacity, even though the reported disk usage is only 1.5 GB. This suggests that some processes are still retaining deleted files. To identify the application responsible for this, I utilized the 'lsof' command.

Upon examining the binary code within '/sbin/named,' I determined that the process associated with it can be terminated safely, as it is non-essential.

![image](https://github.com/arunsandu1/assignment/assets/31780299/df2f5ffc-fead-4dae-8f14-56bcfa70c17f)



![image](https://github.com/arunsandu1/assignment/assets/31780299/65788555-24b8-4a8c-a686-34ceef298fa6)


After killig the process the disk space is released.

```
root@ip-172-31-255-187:~# df -mh
Filesystem      Size  Used Avail Use% Mounted on
udev            224M     0  224M   0% /dev
tmpfs            48M  1.4M   47M   3% /run
/dev/xvda1      7.7G  1.2G  6.6G  15% /
tmpfs           238M     0  238M   0% /dev/shm
tmpfs           5.0M     0  5.0M   0% /run/lock
tmpfs           238M     0  238M   0% /sys/fs/cgroup
/dev/loop0       98M   98M     0 100% /snap/core/9993
/dev/loop1       29M   29M     0 100% /snap/amazon-ssm-agent/2012
tmpfs            48M     0   48M   0% /run/user/0
```

##