# Mounting the Volume

1. **Identify the Drive**:  
   List available block devices to find the drive to be mounted:

   ```bash
   lsblk -f
   ```

   Example output:  
   ```
   sdb                 
   └─sdb1
   ```
   Locate the desired partition, such as `/dev/sdb1`.

2. **Format the Drive**:  
   If the drive is blank, format it with the ext4 file system:

   ```bash
   sudo mkfs.ext4 /dev/sdb1
   ```

   - **Note**: Replace `ext4` with the desired file system if needed.

3. **Create and Mount**:  
   Create a mount point and mount the drive:

   ```bash
   sudo mkdir /mnt/backups && sudo mount /dev/sdb1 /mnt/backups
   ```

4. **Verify the Mount**:  
   Check if the drive is mounted correctly:

   ```bash
   df -h
   ```

5. **Unmount the Drive (Optional)**:  
   Unmount the drive when needed:

   ```bash
   sudo umount /dev/sdb1
   ```

   Alternative:

   ```bash
   sudo umount /mnt/backups
   ```

6. **Advanced Mount Options**:  
   Use additional options with the `mount` command if required:

   ```bash
   mount -o [options] [device] [mountfolder]
   ```

   Common options include:  
   - `ro`: Read-only  
   - `rw`: Read and write (default)  
   - `noexec`: Disable execution permissions  
   - `nosuid`: Disable set-user/group ID bits  
   - `noatime`: Prevent updating access times

7. **Make Persistent**:  
   To retain the mount after a reboot, add an entry to `/etc/fstab`

   in-progress
