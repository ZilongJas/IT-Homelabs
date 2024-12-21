### Mounting a Volume

#### Objective
Mount a volume both temporarily and persistently.

#### Steps

1. Identify the drive to be mounted:

   ```bash
   lsblk -f
   ```

   Example output:
   ```
   sdb                 
   └─sdb1
   ```
   Confirm that the drive to be mounted is `sdb1` located at `/dev/sdb1`.

2. Format the drive if it is blank:

   ```bash
   sudo mkfs.ext4 /dev/sdb1
   ```

   - **Note**: Other file system options are available. Refer to the documentation for alternatives.

3. Create a mount point and mount the drive:

   ```bash
   sudo mkdir /mnt/backups && sudo mount /dev/sdb1 /mnt/backups
   ```

4. Verify the mount:

   ```bash
   df -h
   ```

5. Unmount the drive if needed:

   ```bash
   sudo umount /dev/sdb1
   ```

   or

   ```bash
   sudo umount /mnt/backups
   ```

6. For advanced mounting options, use:

   ```bash
   mount -o [options] [device] [mountfolder]
   ```

   Common options include:
   - `ro`: Read-only
   - `rw`: (default) Read and write
   - `noexec`: Disable execution permissions
   - `nosuid`: Disable set-user-identifier and set-group-identifier
   - `noatime`: Do not update access time when a file is read

7. To make the mount persistent across reboots, edit `/etc/fstab`. This ensures the volume is automatically mounted during system boot:

   - **Note**: Data in the mounted folder is not lost if this step is skipped; however, manual re-mounting will be required after each reboot.
