```
Xshell 6 (Build 0189)
Copyright (c) 2002 NetSarang Computer, Inc. All rights reserved.

Type `help' to learn how to use Xshell prompt.
[C:\~]$ 

Connecting to 13.231.41.133:22...
Connection established.
To escape to local shell, press Ctrl+Alt+].

WARNING! The remote SSH server rejected X11 forwarding request.
[centos@ip-10-112-11-85 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
devtmpfs        3.7G     0  3.7G   0% /dev
tmpfs           3.8G     0  3.8G   0% /dev/shm
tmpfs           3.8G   17M  3.7G   1% /run
tmpfs           3.8G     0  3.8G   0% /sys/fs/cgroup
/dev/nvme0n1p1  8.0G  915M  7.1G  12% /
tmpfs           761M     0  761M   0% /run/user/1000
[centos@ip-10-112-11-85 ~]$ ls /dev/
autofs         core             fd         hwrng    loop-control  net                 nvme0n1    oldmem  random  snapshot  tty    tty12  tty17  tty21  tty26  tty30  tty35  tty4   tty44  tty49  tty53  tty58  tty62  ttyS0  uinput   vcs6   vga_arbiter
block          cpu              full       initctl  mapper        network_latency     nvme0n1p1  port    raw     snd       tty0   tty13  tty18  tty22  tty27  tty31  tty36  tty40  tty45  tty5   tty54  tty59  tty63  ttyS1  urandom  vcsa   vhci
btrfs-control  cpu_dma_latency  fuse       input    mcelog        network_throughput  nvme1      ppp     rtc     stderr    tty1   tty14  tty19  tty23  tty28  tty32  tty37  tty41  tty46  tty50  tty55  tty6   tty7   ttyS2  usbmon0  vcsa1  vhost-net
char           crash            hpet       kmsg     mem           null                nvme1n1    ptmx    rtc0    stdin     tty10  tty15  tty2   tty24  tty29  tty33  tty38  tty42  tty47  tty51  tty56  tty60  tty8   ttyS3  vcs      vcsa6  zero
console        disk             hugepages  log      mqueue        nvme0               nvram      pts     shm     stdout    tty11  tty16  tty20  tty25  tty3   tty34  tty39  tty43  tty48  tty52  tty57  tty61  tty9   uhid   vcs1     vfio
[centos@ip-10-112-11-85 ~]$ ls /dev/s
ls: cannot access /dev/s: No such file or directory
[centos@ip-10-112-11-85 ~]$ ls /dev/s*
/dev/snapshot  /dev/stderr  /dev/stdin  /dev/stdout

/dev/shm:

/dev/snd:
seq  timer
[centos@ip-10-112-11-85 ~]$ ll /dev/s*
crw-------. 1 root root 10, 231 Jun 23 06:00 /dev/snapshot
lrwxrwxrwx. 1 root root      15 Jun 23 06:00 /dev/stderr -> /proc/self/fd/2
lrwxrwxrwx. 1 root root      15 Jun 23 06:00 /dev/stdin -> /proc/self/fd/0
lrwxrwxrwx. 1 root root      15 Jun 23 06:00 /dev/stdout -> /proc/self/fd/1

/dev/shm:
total 0

/dev/snd:
total 0
crw-rw----. 1 root audio 116,  1 Jun 23 06:00 seq
crw-rw----. 1 root audio 116, 33 Jun 23 06:00 timer
[centos@ip-10-112-11-85 ~]$ ll /dev/sd*
ls: cannot access /dev/sd*: No such file or directory
[centos@ip-10-112-11-85 ~]$ ll /dev/
total 0
crw-------. 1 root root     10, 235 Jun 23 06:00 autofs
drwxr-xr-x. 2 root root         100 Jun 23 06:00 block
crw-------. 1 root root     10, 234 Jun 23 06:00 btrfs-control
drwxr-xr-x. 2 root root        2300 Jun 23 06:00 char
crw-------. 1 root root      5,   1 Jun 23 06:01 console
lrwxrwxrwx. 1 root root          11 Jun 23 06:00 core -> /proc/kcore
drwxr-xr-x. 4 root root          80 Jun 23 06:00 cpu
crw-------. 1 root root     10,  61 Jun 23 06:00 cpu_dma_latency
crw-------. 1 root root     10,  62 Jun 23 06:00 crash
drwxr-xr-x. 5 root root         100 Jun 23 06:00 disk
lrwxrwxrwx. 1 root root          13 Jun 23 06:00 fd -> /proc/self/fd
crw-rw-rw-. 1 root root      1,   7 Jun 23 06:00 full
crw-rw-rw-. 1 root root     10, 229 Jun 23 06:00 fuse
crw-------. 1 root root     10, 228 Jun 23 06:00 hpet
drwxr-xr-x. 2 root root           0 Jun 23 06:00 hugepages
crw-------. 1 root root     10, 183 Jun 23 06:00 hwrng
lrwxrwxrwx. 1 root root          25 Jun 23 06:00 initctl -> /run/systemd/initctl/fifo
drwxr-xr-x. 3 root root         200 Jun 23 06:00 input
crw-r--r--. 1 root root      1,  11 Jun 23 06:00 kmsg
srw-rw-rw-. 1 root root           0 Jun 23 06:00 log
crw-rw----. 1 root disk     10, 237 Jun 23 06:00 loop-control
drwxr-xr-x. 2 root root          60 Jun 23 06:00 mapper
crw-------. 1 root root     10, 227 Jun 23 06:00 mcelog
crw-r-----. 1 root kmem      1,   1 Jun 23 06:00 mem
drwxrwxrwt. 2 root root          40 Jun 23 06:00 mqueue
drwxr-xr-x. 2 root root          60 Jun 23 06:00 net
crw-------. 1 root root     10,  60 Jun 23 06:00 network_latency
crw-------. 1 root root     10,  59 Jun 23 06:00 network_throughput
crw-rw-rw-. 1 root root      1,   3 Jun 23 06:00 null
crw-------. 1 root root    245,   0 Jun 23 06:00 nvme0
brw-rw----. 1 root disk    259,   1 Jun 23 06:00 nvme0n1
brw-rw----. 1 root disk    259,   2 Jun 23 06:00 nvme0n1p1
crw-------. 1 root root    245,   1 Jun 23 06:00 nvme1
brw-rw----. 1 root disk    259,   0 Jun 23 06:00 nvme1n1
crw-------. 1 root root     10, 144 Jun 23 06:00 nvram
crw-------. 1 root root      1,  12 Jun 23 06:00 oldmem
crw-r-----. 1 root kmem      1,   4 Jun 23 06:00 port
crw-------. 1 root root    108,   0 Jun 23 06:00 ppp
crw-rw-rw-. 1 root tty       5,   2 Jun 23 10:14 ptmx
drwxr-xr-x. 2 root root           0 Jun 23 06:00 pts
crw-rw-rw-. 1 root root      1,   8 Jun 23 06:00 random
drwxr-xr-x. 2 root root          60 Jun 23 06:00 raw
lrwxrwxrwx. 1 root root           4 Jun 23 06:00 rtc -> rtc0
crw-------. 1 root root    252,   0 Jun 23 06:00 rtc0
drwxrwxrwt. 2 root root          40 Jun 23 06:00 shm
crw-------. 1 root root     10, 231 Jun 23 06:00 snapshot
drwxr-xr-x. 2 root root          80 Jun 23 06:00 snd
lrwxrwxrwx. 1 root root          15 Jun 23 06:00 stderr -> /proc/self/fd/2
lrwxrwxrwx. 1 root root          15 Jun 23 06:00 stdin -> /proc/self/fd/0
lrwxrwxrwx. 1 root root          15 Jun 23 06:00 stdout -> /proc/self/fd/1
crw-rw-rw-. 1 root tty       5,   0 Jun 23 06:00 tty
crw--w----. 1 root tty       4,   0 Jun 23 06:00 tty0
crw--w----. 1 root tty       4,   1 Jun 23 06:01 tty1
crw--w----. 1 root tty       4,  10 Jun 23 06:00 tty10
crw--w----. 1 root tty       4,  11 Jun 23 06:00 tty11
crw--w----. 1 root tty       4,  12 Jun 23 06:00 tty12
crw--w----. 1 root tty       4,  13 Jun 23 06:00 tty13
crw--w----. 1 root tty       4,  14 Jun 23 06:00 tty14
crw--w----. 1 root tty       4,  15 Jun 23 06:00 tty15
crw--w----. 1 root tty       4,  16 Jun 23 06:00 tty16
crw--w----. 1 root tty       4,  17 Jun 23 06:00 tty17
crw--w----. 1 root tty       4,  18 Jun 23 06:00 tty18
crw--w----. 1 root tty       4,  19 Jun 23 06:00 tty19
crw--w----. 1 root tty       4,   2 Jun 23 06:00 tty2
crw--w----. 1 root tty       4,  20 Jun 23 06:00 tty20
crw--w----. 1 root tty       4,  21 Jun 23 06:00 tty21
crw--w----. 1 root tty       4,  22 Jun 23 06:00 tty22
crw--w----. 1 root tty       4,  23 Jun 23 06:00 tty23
crw--w----. 1 root tty       4,  24 Jun 23 06:00 tty24
crw--w----. 1 root tty       4,  25 Jun 23 06:00 tty25
crw--w----. 1 root tty       4,  26 Jun 23 06:00 tty26
crw--w----. 1 root tty       4,  27 Jun 23 06:00 tty27
crw--w----. 1 root tty       4,  28 Jun 23 06:00 tty28
crw--w----. 1 root tty       4,  29 Jun 23 06:00 tty29
crw--w----. 1 root tty       4,   3 Jun 23 06:00 tty3
crw--w----. 1 root tty       4,  30 Jun 23 06:00 tty30
crw--w----. 1 root tty       4,  31 Jun 23 06:00 tty31
crw--w----. 1 root tty       4,  32 Jun 23 06:00 tty32
crw--w----. 1 root tty       4,  33 Jun 23 06:00 tty33
crw--w----. 1 root tty       4,  34 Jun 23 06:00 tty34
crw--w----. 1 root tty       4,  35 Jun 23 06:00 tty35
crw--w----. 1 root tty       4,  36 Jun 23 06:00 tty36
crw--w----. 1 root tty       4,  37 Jun 23 06:00 tty37
crw--w----. 1 root tty       4,  38 Jun 23 06:00 tty38
crw--w----. 1 root tty       4,  39 Jun 23 06:00 tty39
crw--w----. 1 root tty       4,   4 Jun 23 06:00 tty4
crw--w----. 1 root tty       4,  40 Jun 23 06:00 tty40
crw--w----. 1 root tty       4,  41 Jun 23 06:00 tty41
crw--w----. 1 root tty       4,  42 Jun 23 06:00 tty42
crw--w----. 1 root tty       4,  43 Jun 23 06:00 tty43
crw--w----. 1 root tty       4,  44 Jun 23 06:00 tty44
crw--w----. 1 root tty       4,  45 Jun 23 06:00 tty45
crw--w----. 1 root tty       4,  46 Jun 23 06:00 tty46
crw--w----. 1 root tty       4,  47 Jun 23 06:00 tty47
crw--w----. 1 root tty       4,  48 Jun 23 06:00 tty48
crw--w----. 1 root tty       4,  49 Jun 23 06:00 tty49
crw--w----. 1 root tty       4,   5 Jun 23 06:00 tty5
crw--w----. 1 root tty       4,  50 Jun 23 06:00 tty50
crw--w----. 1 root tty       4,  51 Jun 23 06:00 tty51
crw--w----. 1 root tty       4,  52 Jun 23 06:00 tty52
crw--w----. 1 root tty       4,  53 Jun 23 06:00 tty53
crw--w----. 1 root tty       4,  54 Jun 23 06:00 tty54
crw--w----. 1 root tty       4,  55 Jun 23 06:00 tty55
crw--w----. 1 root tty       4,  56 Jun 23 06:00 tty56
crw--w----. 1 root tty       4,  57 Jun 23 06:00 tty57
crw--w----. 1 root tty       4,  58 Jun 23 06:00 tty58
crw--w----. 1 root tty       4,  59 Jun 23 06:00 tty59
crw--w----. 1 root tty       4,   6 Jun 23 06:00 tty6
crw--w----. 1 root tty       4,  60 Jun 23 06:00 tty60
crw--w----. 1 root tty       4,  61 Jun 23 06:00 tty61
crw--w----. 1 root tty       4,  62 Jun 23 06:00 tty62
crw--w----. 1 root tty       4,  63 Jun 23 06:00 tty63
crw--w----. 1 root tty       4,   7 Jun 23 06:00 tty7
crw--w----. 1 root tty       4,   8 Jun 23 06:00 tty8
crw--w----. 1 root tty       4,   9 Jun 23 06:00 tty9
crw--w----. 1 root tty       4,  64 Jun 23 06:01 ttyS0
crw-rw----. 1 root dialout   4,  65 Jun 23 06:00 ttyS1
crw-rw----. 1 root dialout   4,  66 Jun 23 06:00 ttyS2
crw-rw----. 1 root dialout   4,  67 Jun 23 06:00 ttyS3
crw-------. 1 root root     10, 239 Jun 23 06:00 uhid
crw-------. 1 root root     10, 223 Jun 23 06:00 uinput
crw-rw-rw-. 1 root root      1,   9 Jun 23 06:00 urandom
crw-------. 1 root root    247,   0 Jun 23 06:00 usbmon0
crw-rw----. 1 root tty       7,   0 Jun 23 06:00 vcs
crw-rw----. 1 root tty       7,   1 Jun 23 06:00 vcs1
crw-rw----. 1 root tty       7,   6 Jun 23 06:00 vcs6
crw-rw----. 1 root tty       7, 128 Jun 23 06:00 vcsa
crw-rw----. 1 root tty       7, 129 Jun 23 06:00 vcsa1
crw-rw----. 1 root tty       7, 134 Jun 23 06:00 vcsa6
drwxr-xr-x. 2 root root          60 Jun 23 06:00 vfio
crw-------. 1 root root     10,  63 Jun 23 06:00 vga_arbiter
crw-------. 1 root root     10, 137 Jun 23 06:00 vhci
crw-------. 1 root root     10, 238 Jun 23 06:00 vhost-net
crw-rw-rw-. 1 root root      1,   5 Jun 23 06:00 zero
[centos@ip-10-112-11-85 ~]$ fdisk
Usage:
 fdisk [options] <disk>    change partition table
 fdisk [options] -l <disk> list partition table(s)
 fdisk -s <partition>      give partition size(s) in blocks

Options:
 -b <size>             sector size (512, 1024, 2048 or 4096)
 -c[=<mode>]           compatible mode: 'dos' or 'nondos' (default)
 -h                    print this help text
 -u[=<unit>]           display units: 'cylinders' or 'sectors' (default)
 -v                    print program version
 -C <number>           specify the number of cylinders
 -H <number>           specify the number of heads
 -S <number>           specify the number of sectors per track

[centos@ip-10-112-11-85 ~]$ fdisk -l
fdisk: cannot open /dev/nvme1n1: Permission denied
fdisk: cannot open /dev/nvme0n1: Permission denied
[centos@ip-10-112-11-85 ~]$ sudo fdisk -l

Disk /dev/nvme1n1: 1099.5 GB, 1099511627776 bytes, 2147483648 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes


Disk /dev/nvme0n1: 8589 MB, 8589934592 bytes, 16777216 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk label type: dos
Disk identifier: 0x000b723c

        Device Boot      Start         End      Blocks   Id  System
/dev/nvme0n1p1   *        2048    16777215     8387584   83  Linux
[centos@ip-10-112-11-85 ~]$ fdisk /dev/nvme0n1
fdisk: cannot open /dev/nvme0n1: Permission denied
[centos@ip-10-112-11-85 ~]$ sudo fdisk /dev/nvme0n1
Welcome to fdisk (util-linux 2.23.2).

Changes will remain in memory only, until you decide to write them.
Be careful before using the write command.


Command (m for help): p

Disk /dev/nvme0n1: 8589 MB, 8589934592 bytes, 16777216 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk label type: dos
Disk identifier: 0x000b723c

        Device Boot      Start         End      Blocks   Id  System
/dev/nvme0n1p1   *        2048    16777215     8387584   83  Linux

Command (m for help): lsblk

 0  Empty           24  NEC DOS         81  Minix / old Lin bf  Solaris        
 1  FAT12           27  Hidden NTFS Win 82  Linux swap / So c1  DRDOS/sec (FAT-
 2  XENIX root      39  Plan 9          83  Linux           c4  DRDOS/sec (FAT-
 3  XENIX usr       3c  PartitionMagic  84  OS/2 hidden C:  c6  DRDOS/sec (FAT-
 4  FAT16 <32M      40  Venix 80286     85  Linux extended  c7  Syrinx         
 5  Extended        41  PPC PReP Boot   86  NTFS volume set da  Non-FS data    
 6  FAT16           42  SFS             87  NTFS volume set db  CP/M / CTOS / .
 7  HPFS/NTFS/exFAT 4d  QNX4.x          88  Linux plaintext de  Dell Utility   
 8  AIX             4e  QNX4.x 2nd part 8e  Linux LVM       df  BootIt         
 9  AIX bootable    4f  QNX4.x 3rd part 93  Amoeba          e1  DOS access     
 a  OS/2 Boot Manag 50  OnTrack DM      94  Amoeba BBT      e3  DOS R/O        
 b  W95 FAT32       51  OnTrack DM6 Aux 9f  BSD/OS          e4  SpeedStor      
 c  W95 FAT32 (LBA) 52  CP/M            a0  IBM Thinkpad hi eb  BeOS fs        
 e  W95 FAT16 (LBA) 53  OnTrack DM6 Aux a5  FreeBSD         ee  GPT            
 f  W95 Ext'd (LBA) 54  OnTrackDM6      a6  OpenBSD         ef  EFI (FAT-12/16/
10  OPUS            55  EZ-Drive        a7  NeXTSTEP        f0  Linux/PA-RISC b
11  Hidden FAT12    56  Golden Bow      a8  Darwin UFS      f1  SpeedStor      
12  Compaq diagnost 5c  Priam Edisk     a9  NetBSD          f4  SpeedStor      
14  Hidden FAT16 <3 61  SpeedStor       ab  Darwin boot     f2  DOS secondary  
16  Hidden FAT16    63  GNU HURD or Sys af  HFS / HFS+      fb  VMware VMFS    
17  Hidden HPFS/NTF 64  Novell Netware  b7  BSDI fs         fc  VMware VMKCORE 
18  AST SmartSleep  65  Novell Netware  b8  BSDI swap       fd  Linux raid auto
1b  Hidden W95 FAT3 70  DiskSecure Mult bb  Boot Wizard hid fe  LANstep        
1c  Hidden W95 FAT3 75  PC/IX           be  Solaris boot    ff  BBT            
1e  Hidden W95 FAT1 80  Old Minix      

Command (m for help): df -h
Selected partition 1
Partition 1 is deleted

Command (m for help): n^Hexit
Partition type:
   p   primary (0 primary, 0 extended, 4 free)
   e   extended
Select (default p): exit
Partition number (1-4, default 1): e^C
[centos@ip-10-112-11-85 ~]$ ^C
[centos@ip-10-112-11-85 ~]$ lsblk
NAME        MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
nvme0n1     259:1    0   8G  0 disk 
└─nvme0n1p1 259:2    0   8G  0 part /
nvme1n1     259:0    0   1T  0 disk 
[centos@ip-10-112-11-85 ~]$ 
[centos@ip-10-112-11-85 ~]$ fdisk /dev/nvme1n1
fdisk: cannot open /dev/nvme1n1: Permission denied
[centos@ip-10-112-11-85 ~]$ sudo fdisk /dev/nvme1n1
Welcome to fdisk (util-linux 2.23.2).

Changes will remain in memory only, until you decide to write them.
Be careful before using the write command.

Device does not contain a recognized partition table
Building a new DOS disklabel with disk identifier 0xd4babe7b.

Command (m for help): ^C
[centos@ip-10-112-11-85 ~]$ sudo fdisk -l

Disk /dev/nvme1n1: 1099.5 GB, 1099511627776 bytes, 2147483648 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes


Disk /dev/nvme0n1: 8589 MB, 8589934592 bytes, 16777216 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk label type: dos
Disk identifier: 0x000b723c

        Device Boot      Start         End      Blocks   Id  System
/dev/nvme0n1p1   *        2048    16777215     8387584   83  Linux
[centos@ip-10-112-11-85 ~]$ sudo fdisk /dev/nvme0n1p1
Welcome to fdisk (util-linux 2.23.2).

Changes will remain in memory only, until you decide to write them.
Be careful before using the write command.

Device does not contain a recognized partition table
Building a new DOS disklabel with disk identifier 0xe8c59c08.

Command (m for help): help
h: unknown command
Command action
   a   toggle a bootable flag
   b   edit bsd disklabel
   c   toggle the dos compatibility flag
   d   delete a partition
   g   create a new empty GPT partition table
   G   create an IRIX (SGI) partition table
   l   list known partition types
   m   print this menu
   n   add a new partition
   o   create a new empty DOS partition table
   p   print the partition table
   q   quit without saving changes
   s   create a new empty Sun disklabel
   t   change a partition's system id
   u   change display/entry units
   v   verify the partition table
   w   write table to disk and exit
   x   extra functionality (experts only)

Command (m for help): m
Command action
   a   toggle a bootable flag
   b   edit bsd disklabel
   c   toggle the dos compatibility flag
   d   delete a partition
   g   create a new empty GPT partition table
   G   create an IRIX (SGI) partition table
   l   list known partition types
   m   print this menu
   n   add a new partition
   o   create a new empty DOS partition table
   p   print the partition table
   q   quit without saving changes
   s   create a new empty Sun disklabel
   t   change a partition's system id
   u   change display/entry units
   v   verify the partition table
   w   write table to disk and exit
   x   extra functionality (experts only)

Command (m for help): n
Partition type:
   p   primary (0 primary, 0 extended, 4 free)
   e   extended
Select (default p): p
Partition number (1-4, default 1): 1
First sector (2048-16775167, default 2048): 
Using default value 2048
Last sector, +sectors or +size{K,M,G} (2048-16775167, default 16775167): 
Using default value 16775167
Partition 1 of type Linux and of size 8 GiB is set

Command (m for help): ^[[A^[[A^H^H^H^H^H^H^H^H^H^H^H^H^H^H
[: unknown command
Command action
   a   toggle a bootable flag
   b   edit bsd disklabel
   c   toggle the dos compatibility flag
   d   delete a partition
   g   create a new empty GPT partition table
   G   create an IRIX (SGI) partition table
   l   list known partition types
   m   print this menu
   n   add a new partition
   o   create a new empty DOS partition table
   p   print the partition table
   q   quit without saving changes
   s   create a new empty Sun disklabel
   t   change a partition's system id
   u   change display/entry units
   v   verify the partition table
   w   write table to disk and exit
   x   extra functionality (experts only)

Command (m for help): w
The partition table has been altered!

Calling ioctl() to re-read partition table.

WARNING: Re-reading the partition table failed with error 22: Invalid argument.
The kernel still uses the old table. The new table will be used at
the next reboot or after you run partprobe(8) or kpartx(8)
Syncing disks.
[centos@ip-10-112-11-85 ~]$ sudo fdisk -l

Disk /dev/nvme1n1: 1099.5 GB, 1099511627776 bytes, 2147483648 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes


Disk /dev/nvme0n1: 8589 MB, 8589934592 bytes, 16777216 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk label type: dos
Disk identifier: 0x000b723c

        Device Boot      Start         End      Blocks   Id  System
/dev/nvme0n1p1   *        2048    16777215     8387584   83  Linux
[centos@ip-10-112-11-85 ~]$ sudo mkfs -t ext4 /dev/nvme0n1p1
mke2fs 1.42.9 (28-Dec-2013)
/dev/nvme0n1p1 is mounted; will not make a filesystem here!
[centos@ip-10-112-11-85 ~]$ sudo fdisk -l

Disk /dev/nvme1n1: 1099.5 GB, 1099511627776 bytes, 2147483648 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes


Disk /dev/nvme0n1: 8589 MB, 8589934592 bytes, 16777216 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk label type: dos
Disk identifier: 0x000b723c

        Device Boot      Start         End      Blocks   Id  System
/dev/nvme0n1p1   *        2048    16777215     8387584   83  Linux
[centos@ip-10-112-11-85 ~]$ sudo mkdir /data
[centos@ip-10-112-11-85 ~]$ sudo chown centos. /data
[centos@ip-10-112-11-85 ~]$ mount -t ext4 /dev/nvme0n1p1 /data
mount: only root can use "--types" option
[centos@ip-10-112-11-85 ~]$ sudo mount -t ext4 /dev/nvme0n1p1 /data
mount: /dev/nvme0n1p1 is already mounted or /data busy
       /dev/nvme0n1p1 is already mounted on /
[centos@ip-10-112-11-85 ~]$ lsblk
NAME        MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
nvme0n1     259:1    0   8G  0 disk 
└─nvme0n1p1 259:2    0   8G  0 part /
nvme1n1     259:0    0   1T  0 disk 
[centos@ip-10-112-11-85 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
devtmpfs        3.7G     0  3.7G   0% /dev
tmpfs           3.8G     0  3.8G   0% /dev/shm
tmpfs           3.8G   17M  3.7G   1% /run
tmpfs           3.8G     0  3.8G   0% /sys/fs/cgroup
/dev/nvme0n1p1  8.0G  915M  7.1G  12% /
tmpfs           761M     0  761M   0% /run/user/1000
[centos@ip-10-112-11-85 ~]$ sudo mkfs -t ext4 /dev/nvme1n1
mke2fs 1.42.9 (28-Dec-2013)
Filesystem label=
OS type: Linux
Block size=4096 (log=2)
Fragment size=4096 (log=2)
Stride=0 blocks, Stripe width=0 blocks
67108864 inodes, 268435456 blocks
13421772 blocks (5.00%) reserved for the super user
First data block=0
Maximum filesystem blocks=2415919104
8192 block groups
32768 blocks per group, 32768 fragments per group
8192 inodes per group
Superblock backups stored on blocks: 
	32768, 98304, 163840, 229376, 294912, 819200, 884736, 1605632, 2654208, 
	4096000, 7962624, 11239424, 20480000, 23887872, 71663616, 78675968, 
	102400000, 214990848

Allocating group tables: done                            
Writing inode tables: done                            
Creating journal (32768 blocks): done
Writing superblocks and filesystem accounting information: done     

[centos@ip-10-112-11-85 ~]$ sudo mount -t ext4 /dev/nvme1n1 /data
[centos@ip-10-112-11-85 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
devtmpfs        3.7G     0  3.7G   0% /dev
tmpfs           3.8G     0  3.8G   0% /dev/shm
tmpfs           3.8G   17M  3.7G   1% /run
tmpfs           3.8G     0  3.8G   0% /sys/fs/cgroup
/dev/nvme0n1p1  8.0G  915M  7.1G  12% /
tmpfs           761M     0  761M   0% /run/user/1000
/dev/nvme1n1   1008G   77M  957G   1% /data
[centos@ip-10-112-11-85 ~]$ sudo vi /etc/fstab 
[centos@ip-10-112-11-85 ~]$ sudo reboot
Connection closing...Socket close.

Connection closed by foreign host.

Disconnected from remote host(AWS 노드) at 19:40:25.

Type `help' to learn how to use Xshell prompt.
[C:\~]$ 

```





https://zero-gravity.tistory.com/297