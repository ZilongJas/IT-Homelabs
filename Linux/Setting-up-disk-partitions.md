# Setting Up Disk Partitions in Linux using `parted`

#### Virtual disk added to Oracle VM: `/dev/sdb`
#### Main disk: `/dev/sda`

---

### Formatting and Partitioning the Disk

1. Start `parted` in terminal.

   ```bash
   sudo parted
   ```

2. Identify the current hard drive in use and avoid making changes to it. Example:

   ```bash
   GNU Parted 3.6
   Using /dev/sda  # This is the active drive. Do not modify it.
   Welcome to GNU Parted! Type 'help' to view a list of commands.
   (parted)
   ```

3. List all available devices:

   ```bash
   print devices
   ```

   Example output:
   ```bash
   /dev/sda (107GB)
   /dev/sdb (68.7GB)  # Note: The 64GB disk appears as 68.7GB due to measurement differences.
   ```

4. Select the newly added disk (e.g., `/dev/sdb`):

   ```bash
   select /dev/sdb
   ```

5. Create a partition table to structure the disk for data storage. This action erases all existing data on the disk:

   ```bash
   mklabel
   ```

6. When prompted, specify the label type (`gpt` for modern systems or `msdos` for older systems). Confirm any warnings about data loss.

   ```bash
   gpt
   ```

7. Create a primary partition starting at 1MiB and ending at the disk's maximum capacity:

   ```bash
   mkpart primary ext4 1MiB 68.7GB
   ```

8. Validate the partition details:

   ```bash
   print partitions
   ```

   Example output:
   ```
   Number  Start   End     Size    File system  Name     Flags
   1      1049kB  68.7GB  68.7GB  ext4         primary
   ```

9. Optionally, assign a name to the partition (e.g., `backups`):

   ```bash
   name 1 backups
   ```
