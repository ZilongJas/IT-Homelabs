### Mounting a volume

**Objectives:** Mount a volume (Both singularly and dynamically)

**Steps:**

- Get the name of the drive first
  
  ```bash
  lsblk -f
  ```
  Example output:
  
  ```
  sdb                 
  └─sdb1
  ```

  Now we confirm that the drive we need to mount is sdb1, which is in this path `/dev/sdb1`
  
- If the drive is blank you need to format the drive using:
  
  ```bash
  sudo mkfs.ext4 /dev/sdb1
  ```
- There are many other types of file systems, please check [References](#references)
- Then, let's create a folder and mount this drive into that folder.
  ```bash
  sudo mkdir /mnt/backups && sudo mount /dev/sdb1 /mnt/backups
  ```
- Verify the mount
  ```bash
  df -h
  ```
- unmount if needed
  ```bash
  sudo umount /dev/sdb1
  ```
  or
  ```bash
  sudo umount /mnt/backups
  ```

  - For advanced mounting options:
 
  `mount -o [options] [device] [mountfolder]`

  
    - `ro` read only
    - `rw` (default) read + write
    - `noexec` disables execution perms
    - `nosuid` disables set-user-identifier and set-group-identifier
    - `noatime` do not update access time when file is read


- Now, if we reboot our system, our mount is gone! So let's make it work permanently using `/etc/fstab`. It will automatically mount during boot.
- Note that, our data in the mounted file is not lost if we did not do this step, we just need to re-mount it again to access the files, but let's make it automatic:

-

[Back](README.md)  [Top](Mounting-a-Volume.md)
