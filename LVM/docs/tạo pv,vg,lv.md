# tạo physical volume , volume group và logical volume
## 1. tạo physical volume
- để tạo physical volume trên /dev/sdb
```
root@hailh13:/home/vagrant# pvcreate /dev/sdb
  Physical volume "/dev/sdb" successfully created
  ```
- liệt kê các physical volume vừa tạo ta dùng `pvs`
```
root@hailh13:/home/vagrant# pvs
  PV         VG   Fmt  Attr PSize  PFree 
  /dev/sdb   kl1  lvm2 a--  10.00g 10.00g
  ```

ý nghĩa trong `pvs`
 - `pv`: đĩa sử dụng
 - `vg`: volume group
 - `psize`: kích thước đĩa vật lý 
 - `pfree`: kích thước còn trống của đĩa vật lý 

- để xem thông tin chi tiết physical volume ta dùng `pvdisplay`
```
root@hailh13:/home/vagrant# pvdisplay /dev/sdb
  "/dev/sdb" is a new physical volume of "10.00 GiB"
  --- NEW Physical volume ---
  PV Name               /dev/sdb
  VG Name
  PV Size               10.00 GiB
  Allocatable           NO
  PE Size               0
  Total PE              0
  Free PE               0
  Allocated PE          0
  PV UUID               lfjusy-Qf0I-9BBM-fIVL-ebHb-4Wic-pLtTEG
  ```
## 2. tạo volume group 
```
root@hailh13:/home/vagrant# vgcreate kl1 /dev/sdb
  Volume group "kl1" successfully created
```
- để tạo volume group với tên `kl1` bằng cách sử dụng `/dev/sdb`
- đê xem thông tin chi tiết volume group:
```
root@hailh13:/home/vagrant# vgdisplay kl1
  --- Volume group ---
  VG Name               kl1
  System ID
  Format                lvm2
  Metadata Areas        1
  Metadata Sequence No  1
  VG Access             read/write
  VG Status             resizable
  MAX LV                0
  Cur LV                0
  Open LV               0
  Max PV                0
  Cur PV                1
  Act PV                1
  VG Size               10.00 GiB
  PE Size               4.00 MiB
  Total PE              2559
  Alloc PE / Size       0 / 0
  Free  PE / Size       2559 / 10.00 GiB
  VG UUID               NFXZDa-HF1G-w6Ii-CRm5-Ucv0-RusG-7mSP8K
```
- ý nghĩa của các trường thông tin của volume group khi chạy lệnh `vgdisplay`
  - `vg name`: tên group
  - `format`: kiến trúc được sử dụng 
  - `vg access`: volume group có thể đọc , viết và sẵn sàng sử dụng 
  - `vg status`: volume group có thể được thay đổi kích cỡ , chúng ta có thể mở rộng thêm nếu cần thêm dung lượng
  - `pe size` : mở rộng physical , kích thước cho đĩa có thể được xác định bằng kích thước Pe hoặc gb, 4mb là kích thước mặc định của lvm 
  - `vg size` : kích thước của ổ 
  - `total PE`: dung lượng volume group 
  - `alloc pe`: tổng pe đã sử dụng 
  - `free pe` : tổng pe chưa sử dụng 
- để kiểm tra số lượng physical volume dùng để tao volume group:
```
root@hailh13:/home/vagrant# vgs
  VG   #PV #LV #SN Attr   VSize  VFree 
  kl1    1   0   0 wz--n- 10.00g 10.00g
  ```

- `vg` tên volume group
- `#pv` physical volume sử dụng trong volume group
- `vfree` hiển thị không gian trống có sẵn trong volume group 
- `vsize` tổng kích thước của volume group
- `#LV` logical volume nằm trong volume group 
- `#SN` số lượng snapshot volume group
- `attr` trạng thái của volume group có thể ghi có thể đọc , có thể thay đổi 

## 3. tạo logical volume 
```
root@hailh13:/home/vagrant# lvcreate -n projects -L 5G kl1
  Logical volume "projects" created

root@hailh13:/home/vagrant# lvcreate -n backups -l 100%FREE kl1
  Logical volume "backups" created
```

- trong đó 
 - `-n` sử dụng chỉ ra tên của logical volume cần tạo \
 - `-L` sử dụng chỉ một kích thước cố định 
 - `-l` sủ dụng chỉ phần trăm của không gian còn lại trong volume group

- chạy lệnh `lvs` để xem danh sách logical volume 
```
root@hailh13:/home/vagrant# lvs
  LV       VG   Attr      LSize Pool Origin Data%  Move Log Copy%  Convert
  backups  kl1  -wi-a---- 5.00g
  projects kl1  -wi-a---- 5.00g
```
- ý nghĩa của `lvs`
 - `lV` tên logical volume 
 - `%data` phần trăm dung lượng logical volume được sử dụng 
 - `Lsize` kích thước của volume

- sử dụng lệnh `lvdisplay` để hiển thị thông tin chi tiết của các volume
```
root@hailh13:/home/vagrant# lvdisplay kl1/projects
  --- Logical volume ---
  LV Path                /dev/kl1/projects
  LV Name                projects
  VG Name                kl1
  LV UUID                33q1Jj-62mV-e5DK-drGv-tJfd-c40C-Q4uLex
  LV Write Access        read/write
  LV Creation host, time hailh13, 2025-11-04 02:11:59 +0000
  LV Status              available
  # open                 0
  LV Size                5.00 GiB
  Current LE             1280
  Segments               1
  Allocation             inherit
  Read ahead sectors     auto
  - currently set to     256
  Block device           252:0
```

```
root@hailh13:/home/vagrant# lvdisplay kl1/backups
  --- Logical volume ---
  LV Path                /dev/kl1/backups
  LV Name                backups
  VG Name                kl1
  LV UUID                cR9E4f-YTHH-yVqd-APzH-PkTC-23Ur-lBCtIQ
  LV Write Access        read/write
  LV Creation host, time hailh13, 2025-11-04 02:12:49 +0000
  LV Status              available
  # open                 0
  LV Size                5.00 GiB
  Current LE             1279
  Segments               1
  Allocation             inherit
  Read ahead sectors     auto
  - currently set to     256
  Block device           252:1
```

- ta sử dụng file system `ext4` vì nó cho phép chúng ta tăng và giảm kích thước của mỗi logical volume
```
root@hailh13:/home/vagrant# mkfs.ext4 /dev/kl1/projects
mke2fs 1.42.9 (4-Feb-2014)
Filesystem label=
OS type: Linux
Block size=4096 (log=2)
Fragment size=4096 (log=2)
Stride=0 blocks, Stripe width=0 blocks
327680 inodes, 1310720 blocks
65536 blocks (5.00%) reserved for the super user
First data block=0
Maximum filesystem blocks=1342177280
40 block groups
32768 blocks per group, 32768 fragments per group
8192 inodes per group
Superblock backups stored on blocks:
        32768, 98304, 163840, 229376, 294912, 819200, 884736

Allocating group tables: done
Writing inode tables: done
Creating journal (32768 blocks): done
Writing superblocks and filesystem accounting information: done 
```

```
root@hailh13:/home/vagrant# mkfs.ext4 /dev/kl1/backups
mke2fs 1.42.9 (4-Feb-2014)
Filesystem label=
OS type: Linux
Block size=4096 (log=2)
Fragment size=4096 (log=2)
Stride=0 blocks, Stripe width=0 blocks
327680 inodes, 1309696 blocks
65484 blocks (5.00%) reserved for the super user
First data block=0
Maximum filesystem blocks=1342177280
40 block groups
32768 blocks per group, 32768 fragments per group
8192 inodes per group
Superblock backups stored on blocks:
        32768, 98304, 163840, 229376, 294912, 819200, 884736

Allocating group tables: done
Writing inode tables: done
Creating journal (32768 blocks): done
Writing superblocks and filesystem accounting information: done 
```

## 4. giảm kích cỡ logical volume
- liểm tra dung lượng của logical volume 
``` 
root@hailh13:/home/vagrant# lvs
  LV       VG   Attr      LSize Pool Origin Data%  Move Log Copy%  Convert
  backups  kl1  -wi-a---- 5.00g
  projects kl1  -wi-a---- 5.00g
  ```
- bước 1 ngắt kết nối 
 
 sử dụng lệnh Unmount
```
root@hailh13:/home/vagrant# umount /vagrant
root@hailh13:/home/vagrant# df -TH
Filesystem     Type      Size  Used Avail Use% Mounted on
udev           devtmpfs  516M   13k  516M   1% /dev
tmpfs          tmpfs     105M  390k  104M   1% /run
/dev/sda1      ext4       43G  1.6G   39G   4% /
none           tmpfs     4.1k     0  4.1k   0% /sys/fs/cgroup
none           tmpfs     5.3M     0  5.3M   0% /run/lock
none           tmpfs     521M     0  521M   0% /run/shm
none           tmpfs     105M     0  105M   0% /run/user
none           vboxsf    226G  221G  5.3G  98% /vagrant
```
- bước 2 kiểm tra lỗi file system bằng lệnh `e2fsck`
```
root@hailh13:/home/vagrant# e2fsck -f /dev/kl1/projects
e2fsck 1.42.9 (4-Feb-2014)
Pass 1: Checking inodes, blocks, and sizes
Pass 2: Checking directory structure
Pass 3: Checking directory connectivity
Pass 4: Checking reference counts
Pass 5: Checking group summary information
/dev/kl1/projects: 11/327680 files (0.0% non-contiguous), 55902/1310720 blocks
```
- `-f` để kiểm tra 

- bước 3 giảm kích thước 
- giảm logical volume tên projects vs kích thước 5G giảm xuống còn 4G 
```
root@hailh13:/home/vagrant# resize2fs /dev/kl1/projects 4G
resize2fs 1.42.9 (4-Feb-2014)
Resizing the filesystem on /dev/kl1/projects to 1048576 (4k) blocks.
The filesystem on /dev/kl1/projects is now 1048576 blocks long.
```
- bước 4 kiểm tra lỗi file system đã giảm 
```
root@hailh13:/home/vagrant# e2fsck -f /dev/kl1/projects
e2fsck 1.42.9 (4-Feb-2014)
Pass 1: Checking inodes, blocks, and sizes
Pass 2: Checking directory structure
Pass 3: Checking directory connectivity
Pass 4: Checking reference counts
Pass 5: Checking group summary information
/dev/kl1/projects: 11/262144 files (0.0% non-contiguous), 51790/1048576 blocks
```
- bước 5 kiểm tra kích thước 
``` 
root@hailh13:/home/vagrant# lvs
  LV       VG   Attr      LSize Pool Origin Data%  Move Log Copy%  Convert
  backups  kl1  -wi-a---- 5.00g
  projects kl1  -wi-a---- 4.00g
```