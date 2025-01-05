# Born2beroot

## Description
---

**Born2beroot** is your essential companion to mastering Linux system administration, designed to guide beginners and aspiring professionals into the world of root access and system management. This resource simplifies the complexities of Linux, offering clear, practical steps to help users build confidence and expertise.

From foundational concepts like file systems, permissions, and processes to advanced topics such as security, networking, and automation, Born to be Root equips you with the tools and knowledge to excel in system administration. Its hands-on tutorials and real-world examples provide a solid framework for tackling diverse challenges, ensuring you gain both understanding and practical skills.

By adopting the mindset of the root user — the ultimate superuser — you’re encouraged to explore, experiment, and take full control of your Linux environment. This guide empowers you to unlock the system’s full potential, transforming you into a confident and capable administrator.

Whether setting up servers, troubleshooting, or optimizing performance, **Born2beroot** is your trusted guide to navigating the dynamic world of Linux with ease and proficiency.

*For more check the [subject](subject.pdf)*

`Before starting, it's important to understand that each action in every step serves a specific purpose. You should know why it's being done and how it contributes to the overall process. A solid grasp of the technical context is crucial to fully comprehend the procedure.`

## Step 1: Check for VirtualBox
---

To get started, ensure you have **VirtualBox** installed. If not, you can download it from [this link](https://www.virtualbox.org/). **VirtualBox** is essential for setting up the operating system we’ll be working with.

At 1337, **VirtualBox** is already available on the macOS devices, so you likely won’t need to install it. Double-check whether it’s already installed on your machine before proceeding.

### Some things you need to learn

- **VirtualBox**: Understand what VirtualBox is and how it works as a virtualization tool.
- **Virtualization**: Learn the concept of virtualization and its role in creating virtual environments.
- **Operating Systems**: Familiarize yourself with what operating systems are and their importance in managing computer hardware and software.
- **Hypervisor**: Discover the role of a hypervisor and how it enables virtualization by managing virtual machines.

❗❗For more details, check the [Guide for Virtual Machine and Linux Administration](Guide%20for%20Virtual%20Machine%20and%20Linux%20Administration.md), where you'll find explanations on all the concepts you'll need to learn.

## Step 2: Selecting the Operating System
---

### Debian vs Rocky Linux

When considering the operating system for the "**Born2beroot**" project, **Debian** stands out as the top recommendation. Here’s why:

1. **Stability and Reliability**: Debian is renowned for its robust stability, making it an ideal choice for server environments. With its established release cycle and thorough documentation, it offers a smooth experience for both beginners and advanced users alike.

2. **Extensive Community Support**: Debian is supported by a vibrant and engaged community, with a wealth of online resources to assist you. This active support network is especially valuable if you’re just starting out in system administration.

3. **Ideal for System Administration**: As specifically recommended for newcomers to system administration, Debian’s user-friendly package management (apt) and comprehensive documentation simplify the learning process. It’s a great choice for implementing essential tasks required by the project.

4. **Robust Security**: Debian comes with solid security features, including SELinux, which should be enabled at startup and configured as per the project requirements. AppArmor is also necessary to run at startup, adding another layer of security to the system.

5. **Project Compatibility**: Debian’s capabilities align perfectly with the project’s needs. From setting up encrypted partitions with LVM to implementing a strict password policy, configuring sudo, managing SSH access, and setting up a firewall with UFW, Debian supports all these requirements.

6. **Bonus Features**: Should you opt for the bonus section of the project, Debian provides a stable environment for additional services, like setting up WordPress or any custom service you prefer.

7. **Current Version**: The most recent stable version of Debian, as of this guide’s writing, is Debian 12.5. You can download the image from [this link](https://www.debian.org/download).

In conclusion, Debian offers a dependable, secure, and well-documented platform that fits perfectly with the project’s needs. It’s an excellent choice for gaining hands-on experience in system administration while ensuring your environment is well-supported and aligned with the project’s goals.

❗❗For more details, check the [Guide for Virtual Machine and Linux Administration](Guide%20for%20Virtual%20Machine%20and%20Linux%20Administration.md), where you'll find explanations on all the concepts you'll need to learn.

## Step 3: Creating a New Virtual Machine in Oracle VirtualBox
---

1. Launch Oracle **VirtualBox**.

2. Select the "**New**" button at the top of the window.
![New button](screen_shots_guide/new_button.png)

3.  In the name field, enter **'Born2beroot'** and change the version to **Debian (64-bit)**. Also, make sure to select the machine folder path as `Goinfre/home` if you are working on a computer of the school.
![Name and operating system](screen_shots_guide/goinfre.png)

4. After pressing **continue** button, the **memory size** should automatically be set to **1024 MB** (1 GB), which is recommended. If it doesn’t appear as **1024 MB**, manually adjust it to that value.
![Memory size](screen_shots_guide/memory_size.png)

5. After pressing **continue** button, When prompted with three options, select the second one: **Create a virtual hard disk now**.
   ![Hard disk](screen_shots_guide/hard_disk.png)

6. After pressing **continue** button, In the **Hard disk file type** options, choose the first option: **VDI (VirtualBox Disk Image)**.
   ![Hard disk file type](screen_shots_guide/hard_disk_file_type.png)

7. After pressing **continue** button, In the **Storage on physical hard disk** options, choose the first option: **Dynamically allocated**.
   ![Storage on physical hard disk](screen_shots_guide/storage_on_physical_hard_disk.png)

8.  After pressing **continue** button, set the size of the virtual hard disk to **30.80 GB** if you're going to work on the **bonus part** of the project. If you're only going to complete the **mandatory part**, choose **8 GB**. If you choose the **mandatory** option, you won't need the extra steps required for the **bonus part** later on. Since you're focusing on the **bonus**, you'll proceed with the 30.80 GB size.
![File location and size](screen_shots_guide/set_the%20_size_of_vm.png)

9.  After pressing **continue** or **finished** button, you should see your new **Virtual Machine** created. To move on to the next step, go to **Settings** to start mounting an **ISO file**.
![Settings button](screen_shots_guide/settings_button.png)

10. In **Settings**, click on the **Storage** tab, then select the **Empty** option under **Storage Devices**.
![Storage button](screen_shots_guide/storage_button.png)

## Step 4: Mount the ISO File and Start the Virtual Machine
---

1. Once you’ve clicked on **Empty**, you should see a small disk icon similar to the one in the **screenshot below** next to the **optical drive**. Click on it.
![Disk file](screen_shots_guide/disk_file.png)

2. Choose **debian-12.8.0-amd64-netinst.iso** from the list if it appears. If it doesn't show up, click on the **Choose a disk file** button and select the **debian-12.8.0-amd64-netinst.iso** file from the folder where you downloaded **Debian**.
![Choose a disk file](screen_shots_guide/choose_a_disk_file.png)

3. Now, start the machine by clicking the **Start** button, so you can continue with the next step to install **Debian**.
![Start button](screen_shots_guide/start_button.png)

## Step 5: Installing Debian Operating System

### Configuring the Language, Time Zone, and Keyboard Layout

1. The screen will appear as shown below. For a better viewing experience, right-click with your mouse, select the **Virtual Screen 1** option, and scale it to **200%**. After that, choose the **Install** option, as we will proceed without using a graphical interface.
![Better viewing](screen_shots_guide/better_viewing.png)
![install button](screen_shots_guide/install_button.png)

2. Next, you’ll be prompted to select a language. I’m choosing English.
![Language](screen_shots_guide/language.png)

3. Enter your Country, Territory, or Area. Since I’m in Morocco 🇲🇦 I’ll select Other.
![Country](screen_shots_guide/country.png)

4. Choose your continent or region. In my case, it's Morocco 🇲🇦. I will start by selecting Africa.
![Continent](screen_shots_guide/continent.png)

5. Choose your Country, Territory, or Area. Since I’m Moroccan, I’ll select Morocco 🇲🇦.
![Morocco](screen_shots_guide/morocco.png)

6. For configuring locales, I’ll choose United States.
![Configuring local](screen_shots_guide/default_locale.png)

7. In keyboard configuration, Select American English to ensure the keys are correctly mapped; otherwise, the keyboard layout may not function as expected.
![Keyboard](screen_shots_guide/keyboard.png)

8. Once this steps is completed, you should see a window similar to the one below.
![Loading](screen_shots_guide/loading.png)

### Configuring the Network

1. The system will first ask for the **hostname**. As per the instructions, you should enter your **intra name** followed by **42**. In my case, it’s **noaziki42**.
![Hostname](screen_shots_guide/hostname.png)

2. For domain name, We'll leave this section blank, as the instructions do not specify any requirements for a domain name.
![Domain name](screen_shots_guide/domian_name.png)

3. You’ll be prompted to enter a password for the system administrator account. It's important to write it down or take a photo for reference, as you will need it later. If you want to confirm that you've entered the password correctly, tab until you reach the **Show Password in Clear** option. Press the space bar, and the password will be displayed.
![Root password](screen_shots_guide/root_password.png)

4. Now, you'll be asked to re-enter the password to confirm it. Make sure it matches the one you entered previously.
![Re-enter password](screen_shots_guide/re_enter_password.png)

5. To avoid using the root account for non-administrative tasks, you'll be prompted to create a normal user account. I’ll enter my full name, **Nouhaila Aziki**, as the full name for the new user.
![Full name](screen_shots_guide/full_name.png)

6. Now, you’ll be asked to provide a nickname or username for the non-root user. I’ll proceed with my intra username, **noaziki**, as the username for the new user.
![Username](screen_shots_guide/username.png)

7. You’ll need to choose a password for the non-root user. I’m proceeding with a new one, but if you think you might forget it, it's better to use the same password as the one for the Root User.
![User password](screen_shots_guide/user_password.png)

8. You’ll need to confirm the password for the non-root user. As I showed when setting the root password, you can use the arrows to navigate to the **Show Password** option and press the space bar to display it, ensuring it’s correct.
![Re-enter user password](screen_shots_guide/re_enter_user_password.png)

### Organizing Disk Partitions

Partitioning is an essential step in structuring disk space on your server. It helps to allocate different areas of the disk for specific functions.

1. Choose "Use Entire Disk and Set Up Encrypted LVM": This guided option automatically partitions your disk and configures encrypted Logical Volume Manager (LVM), which is mandatory as per the project's requirements.

However!!! If you're planning to tackle the bonus section of the project, you should select "Manual" and proceed with custom partitioning. This serves as a heads-up for those interested in the bonus. Otherwise, feel free to stick with the default guided partitioning method and skip this step.

I will continue with the custom partitioning for the bonus task, but you're free to opt for the guided approach if you prefer.
![Partition disk](screen_shots_guide/partition_disks_manual.png)

2. In this section, you’ll see a general description of your partitions and mount points. Since we haven’t created any partitions yet, we need to create a  new partition table. To do this, choose the device where you want to create the partitions. In my case, I’ll select the only available device: SCSI2 (0, 0, 0) (sda) - 33.1 GB ATA VBOX HARDDISK.

Don’t be confused if you see SCSI3 instead, as the SCSI controller number is assigned automatically by VirtualBox and may vary between installations or configurations. This number is just a virtual representation of the disk controller used by the virtual machine. As long as you choose the correct disk (sda) with the correct capacity (33.1 GB ATA VBOX HARDDISK), you should be good to go.
![Partition disk](screen_shots_guide/partition_disks_scsi2.png)

3. Click **Yes** to confirm the device selection.
![Yes button](screen_shots_guide/new_empty_partition.png)

4. After completing the previous step, you’ll see an empty partition table. To configure it, select the **FREE SPACE** in order to create the partitions.
![Empty partition](screen_shots_guide/free_space.png)

5. Create a new partition.
![Create a partition](screen_shots_guide/create_a_partition.png)

6. Following the image provided in the subject, we will create the partitions one by one (this image from the bonus part).
![Partition size](screen_shots_guide/partition_size.png)

7. As indicated in the subject, the size of the first partition should be **500.99 megabytes**.
![First partition size](screen_shots_guide/the_max_size_for_it.png)

8. I will briefly explain the different types of sections:

`Primary Partition: This is the only type of partition that can hold an operating system. A hard drive can have up to four primary partitions, or three primary partitions and one extended partition.`

`Extended Partition: Designed to overcome the limit of four primary partitions on a single disk, only one extended partition can exist per disk. It serves as a container for logical partitions.`

`Logical Partition: This partition exists within an extended partition and is formatted with a specific file system, like ext4. Once formatted, it is recognized by the operating system as a separate drive. While you can have up to 23 logical partitions in theory, Linux limits this to 15 logical partitions for practical use, which is more than enough for the scope of this project.`

For this step, we will choose Primary because it will be the partition where the Operating System will be installed.
![First partition](screen_shots_guide/type_for_the_first_partition.png)

9. We will select **Beginning** because we want the new partition to be created at the start of the available space on the disk.
![Location for the first partition](screen_shots_guide/location_for_the_first_partition.png)

10. The following screenshot displays the partition details. We will modify the mount point according to the specifications provided in the project instructions.
![Following screenshot](screen_shots_guide/first_partition_settings.png)

11. We will choose **/boot** as the mount point for our partition, as specified in the project instructions.
![Following screenshot](screen_shots_guide/mount_point_for_first_partition.png)

12. We have finished configuring the current partition.
![Following screenshot](screen_shots_guide/first_partition_setting_done.png)

13. Once we have completed the previous step, the partition should appear. Next, we need to create a logical partition using all the remaining available disk space. This partition will have no mount point and will be encrypted. To do this, we select the free space where we want to create the logical partition.![Following screenshot](screen_shots_guide/second_free_space.png)

14. Create a new partition
![Following screenshot](screen_shots_guide/creat_second_partition.png)

15. We will follow the example provided in the subject for creating the logical partition.
![Following screenshot](screen_shots_guide/partition_size.png)

16. We will select max for this partition to utilize all the remaining available disk space.
![Following screenshot](screen_shots_guide/second_partition_size.png)

17. Since we need to create the LVM, we must select Logical for this partition type.
![Following screenshot](screen_shots_guide/type_for_the_second_partition.png)

18. For this partition, we will not assign a mount point, as it is meant to be encrypted and used for LVM (Logical Volume Management).
![Following screenshot](screen_shots_guide/second_partition_setting.png)

19. In the context of virtual machines (VMs) and disk management, logical partitions are typically not mounted directly because they are part of a larger virtual disk image or disk file. Instead, they are used as components of LVM (Logical Volume Management), where they are combined into logical volumes that are then mounted for use by the system.
![Following screenshot](screen_shots_guide/mount_point_for_second_partition.png)

20. Now that we have selected Logical for the partition type and left it without a mount point, we can finish the partitioning process by confirming and applying the changes. Once done, the logical partition will be created, and we'll proceed to the next steps in the setup process.
![Following screenshot](screen_shots_guide/second_partition_setting_done.png)

21. Let's configure the encrypted volumes now
![configure](screen_shots_guide/configure_encrypted_volumes.png)

22. Accept the confirmation message to proceed with configuring the encrypted volume. This step finalizes the encryption setup and applies the necessary changes to the partition.
![Accept](screen_shots_guide/write_the_changes.png)

 23. Waiting for upload.
![Waiting](screen_shots_guide/waiting_for_upload.png)

 24. Now, we proceed to create the encrypted volumes. This step involves setting up the partition for encryption to ensure data security.
![Create it](screen_shots_guide/create_the_encrypted_volume.png)

25. We select the partition we want to encrypt. Use the arrow keys to navigate to /dev/sda5, and press the space bar to select it.
![Create it](screen_shots_guide/dev:sda5.png)

26. We have completed the configuration of the current partition and can now proceed to the next step.
![Completed](screen_shots_guide/the_current_partition_finished.png)

27. We are done with this step, as we do not need to create any additional encrypted volumes.
![done](screen_shots_guide/finish.png)

28. We accept the confirmation message, which informs us that everything within the selected partition will be encrypted. The process should complete quickly.
![done](screen_shots_guide/click_yes.png)

29. We don't mind whether it takes a long time or a short time; we simply click 'Cancel' because there is nothing to encrypt, as the partition is empty.
![Click cancel](screen_shots_guide/Screen_Shot_1.png)

30. Once again, we will need to enter a password, but this time it will be the encryption phrase. As I mentioned earlier, you must repeat the process and write it down, as it will be important in the future.
![Password](screen_shots_guide/Screen_Shot_2.png)

31. Confirm the password.
![Password](screen_shots_guide/Screen_Shot_3.png)

32. Now we'll configure the Logical Volume Manager.
![Logical Volume Manager](screen_shots_guide/Screen%20Shot%202024-12-24%20at%2011.24.02%20AM.png)

33. We will accept the confirmation message, as we agree that the changes will be saved to the disk.
![Accept](screen_shots_guide/Screen%20Shot%202024-12-24%20at%2011.24.40%20AM.png)

34. Let's create a new volume group. A volume group combines multiple partitions.
![Volume Group](screen_shots_guide/Screen%20Shot%202024-12-24%20at%2011.25.41%20AM.png)

35. We need to assign the name as specified in the instructions: LVMGroup.
![LVMGroup](screen_shots_guide/Screen%20Shot%202024-12-24%20at%2011.26.31%20AM.png)

36. Select the partition where the group should be created.
![group's partition](screen_shots_guide/Screen%20Shot%202024-12-24%20at%2011.38.37%20AM.png)

37. We need to create them according to the example provided in the instructions.
![subject's instructions](screen_shots_guide/partition_size.png)

38. We'll begin by selecting the group where we want them to be created. Choose the only available group (the one we just created).
![Create logical volume](screen_shots_guide/Screen%20Shot%202024-12-24%20at%2011.39.30%20AM.png)

39. We'll follow the sequence outlined in the subject for creating the logical volume, beginning with the root and finishing with var-log. After that, we’ll choose a name for each logical volume accordingly.
![root](screen_shots_guide/Screen%20Shot%202024-12-24%20at%2011.40.11%20AM%20copy.png)

40. As specified in the subject, the size will be set to 10GB.
![size](screen_shots_guide/Screen%20Shot%202024-12-24%20at%2011.40.59%20AM%20copy.png)

41. To avoid repetition, proceed by applying the same process to all partitions in the volume group. Assign each one the same name and size as outlined in the example above.
![subject's instructions](screen_shots_guide/partition_size.png)

42. Once you’ve created all the logical volumes as specified, your window should match the one shown below. At this point, simply type `"finish"` to complete the process.
![size](screen_shots_guide/Screen%20Shot%202024-12-31%20at%2010.14.28%20AM.png)

43. Now, in the section displaying all the partitions and available free space, you should see all the logical partitions we just created. Our next step is to configure each one by selecting the desired file system and the corresponding mount point as specified in the subject. We’ll proceed in order, starting with the first partition that appears, which is "home," by pressing Enter.
![cofigure](screen_shots_guide/Screen%20Shot%202024-12-26%20at%204.38.28%20PM.png)
   
44. It will display the partition configuration. Since the partition currently lacks a file system, we need to assign one. To do this, press Enter on the `"Use as"` option, which is currently set to `"Do not use."`
![cofigure](screen_shots_guide/Screen%20Shot%202024-12-26%20at%204.39.07%20PM.png)

45. Select the Ext4 file system, as it is the most commonly used file system in Linux distributions.
![cofigure](screen_shots_guide/Screen%20Shot%202024-12-26%20at%204.40.03%20PM.png)

46. Next, we need to select the mount point by pressing Enter on the "Mount point" option.
![cofigure](screen_shots_guide/Screen%20Shot%202024-12-26%20at%204.40.46%20PM.png)

47. For the "home" partition, select "home" as the mount point. For future partitions, choose the appropriate mount points specific to each one to avoid repetition.
![cofigure](screen_shots_guide/Screen%20Shot%202024-12-26%20at%204.41.27%20PM.png)

48. The partition setup is complete.
![cofigure](screen_shots_guide/Screen%20Shot%202024-12-26%20at%204.42.28%20PM.png)

49. Now, proceed with the same steps for all the partitions. For the var/log partition, manually enter the mount point. For the swap partition, instead of choosing a file system, select "swap area" after you click `"Use as: Do not use."`, Once all the partitions are configured, click "Finish partitioning" and confirm to write the changes to the disk.
![Finish partitioning](screen_shots_guide/Screen%20Shot%202024-12-26%20at%205.04.02%20PM.png)

50. Confirm the changes, and after that, you will see the installation progress bar.
![Finish partitioning](screen_shots_guide/Screen%20Shot%202024-12-31%20at%201.46.41%20PM.png)
![Finish partitioning](screen_shots_guide/Screen%20Shot%202024-12-26%20at%205.05.09%20PM.png)

51. It will prompt us to install additional packages. However, select "No" since they are not needed for this setup.
![Finish partitioning](screen_shots_guide/Screen%20Shot%202024-12-31%20at%2010.44.40%20AM.png)

52. Choose the country that is specific to your location. This will set the appropriate time zone and regional settings for your system.
![Morocco](screen_shots_guide/Screen%20Shot%202024-12-31%20at%2010.45.07%20AM.png)

53. Choosing `deb.debian.org` ensures faster, reliable, and secure package downloads by automatically selecting the best mirror based on your location.
![deb](screen_shots_guide/Screen%20Shot%202024-12-31%20at%2010.48.18%20AM.png)

54. Leave this field empty and press `continue`
![continue](screen_shots_guide/Screen%20Shot%202024-12-31%20at%2010.49.10%20AM.png)

55. Since we do not want developers to see our statistics, select `"No"`
![continue](screen_shots_guide/Screen%20Shot%202024-12-31%20at%2010.50.24%20AM.png)

56. Remove all software options by pressing the space bar and then click "Continue," as these options are forbidden according to the subject.
![continue](screen_shots_guide/Screen%20Shot%202024-12-31%20at%2010.51.45%20AM.png)

57. Select "Yes" to install the GRUB bootloader on the hard drive. GRUB is essential in the boot process of Linux-based operating systems, providing a flexible and customizable bootloader that manages system booting, kernel loading, and system recovery.
![continue](screen_shots_guide/Screen%20Shot%202024-12-31%20at%2010.52.39%20AM.png)

58. Next, choose the device for the bootloader installation. Select /dev/sda (ata_VBOX_HARDDISK) as the target for the GRUB bootloader. This ensures that your system will boot from the correct hard drive.
![continue](screen_shots_guide/Screen%20Shot%202024-12-31%20at%201.55.25%20PM.png)

59. Type `"Continue"` to complete the installation and finish setting up your system.
![continue](screen_shots_guide/Screen%20Shot%202024-12-31%20at%201.57.23%20PM.png)

## Step 6: Virtual Machine Configuration
---

1. The first step is to enter the encryption password that you previously set up during the installation process. This will unlock the encrypted disk and allow the system to boot successfully.
![continue](screen_shots_guide/Screen%20Shot%202024-12-31%20at%201.59.11%20PM.png)

2. Next, enter the username and password for the non-root user that you created during the installation process. This will log you into the system with regular user privileges.
![continue](screen_shots_guide/Screen%20Shot%202024-12-31%20at%202.18.28%20PM.png)
Great! 🎉 Now that everything is set up, you're ready to begin configuring your Debian virtual machine. You can now proceed with installing any necessary software, setting up your development environment, or customizing the system to suit your needs. Enjoy exploring your virtual machine!

## Step 7: Install sudo and configure users and groups
---

1. To install **sudo**, we first need to switch to the root user. Open the terminal, type `su` or `su -`, and enter the root password when prompted. Once logged in as root, run the command `apt install sudo` to install the required package. After installation, restart the machine to apply the changes. Use the command `sudo reboot` to reboot the system and wait for it to restart.
![continue](screen_shots_guide/Screen%20Shot%202024-12-31%20at%202.19.55%20PM.png)

2. After rebooting, re-enter the encryption and user passwords. To ensure sudo was installed correctly, log in as the root user again and run the command `sudo -V`, this will show the sudo version, along with the configuration arguments and available plugins that provide additional details. Next, switch to the root user using `su` or `su -`. Then, attempt to create a user with the same name as the non-root user currently logged in using `sudo adduser your_login`. Since the user was already created during the installation, you should receive a message indicating that the user already exists.
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%209.49.37%20AM.png)

 3. Next, we need to create a new group called user42. To do this, run the following command `sudo addgroup user42`, this will add the new group to the system.
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2010.01.05%20AM.png)

4. ```Have you heard of **GID**? It stands for **Group Identifier**—essentially the unique ID assigned to each group in Unix-like systems. Similar to how users are given a **UID** (User ID), groups are identified by their **GID**. This identifier is key for managing permissions and access control, allowing users in the same group to collaborate and share resources seamlessly. Think of the **GID** as the group’s digital signature, ensuring efficient organization and coordination within the system.```

❗❗For more details, check the [Guide for Virtual Machine and Linux Administration](Guide%20for%20Virtual%20Machine%20and%20Linux%20Administration.md), where you'll find explanations on all the concepts you'll need to learn.

 Was the group created successfully? Yes, since no error message appeared, the group has been created properly. To confirm, you can use the command `getent group group_name`.
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2010.02.46%20AM.png)
Running the command `cat /etc/group` will display the contents of the **/etc/group** file, which includes a list of all groups on your system, along with their **GID** and members. The output will look something like this:
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2010.05.06%20AM.png)

5. To add a user to a group, you can use the command `sudo adduser username group_name`, this command will include the user in the specified group. In this case, we need to add the user to both the sudo and user42 groups. To do this, run `sudo adduser username sudo` and `sudo adduser username user42`. After adding the user to the groups, you can verify that everything is set up correctly by using the command `getent group group_name`. Alternatively, you can open and edit the `/etc/group` file using `sudo vim /etc/group`. In this file, you should see the username listed under both the sudo and user42 groups. This confirms that the user is correctly added to the groups.
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2010.08.07%20AM.png)

## Step 8: Install and configure the SSH
---

```🔒 **SSH**, or **Secure Shell**, serves as both a protocol and a tool for securely accessing remote servers. It establishes an encrypted communication channel, ensuring that all data exchanged between the client and the server remains confidential and intact. This strong encryption makes SSH indispensable for secure remote management and file transfers.```

❗❗For more details, check the [Guide for Virtual Machine and Linux Administration](Guide%20for%20Virtual%20Machine%20and%20Linux%20Administration.md), where you'll find explanations on all the concepts you'll need to learn.

1. The first step is to update the package repositories we defined in the /etc/apt/sources.list file. To do this, run the following command in your terminal: `sudo apt update`. This command refreshes the list of available packages from the repositories, ensuring that the system is aware of the latest versions and updates.
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%201.05.48%20PM.png)

2. Next, we’ll install the primary connectivity tool for remote login using the SSH protocol: OpenSSH. To install it, we’ll enter the following command `sudo apt install openssh-server`. When prompted with a confirmation message, type Y to proceed, and then wait for the installation to complete.
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2010.23.27%20AM.png)
After running the installation command, you should see an output similar to the following:
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2010.24.21%20AM.png)
To verify that OpenSSH has been installed correctly, we’ll run the following command `sudo service ssh status`. If the installation was successful, you should see an output indicating that the SSH service is active and running, similar to this:
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2010.25.23%20AM.png)
This confirms that SSH is up and running.

2. After completing the installation, there are configuration files that we need to adjust. For this, we’ll use vim(to install vim use the command `apt install vim`), or any other preferred text editor. The first file to modify is located at `/etc/ssh/sshd_config`. If you're not logged in as the root user, you might not have the necessary write permissions. In such cases, you can either. Switch to the root user by running `su -`, followed by entering the root password. Or, simply prepend sudo to the command to temporarily gain root privileges, like this `sudo vim /etc/ssh/sshd_config`. This allows you to edit the configuration file with the proper permissions.

The following image illustrates the vim installation stage.
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2010.37.44%20AM.png)
This command below is to open /etc/ssh/sshd_config
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%201.10.30%20PM.png)
You have to see as in the picture
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2011.20.12%20AM.png)

In the SSH configuration file (/etc/ssh/sshd_config), lines that begin with a # are commented out, meaning they are inactive. To modify these lines, we will need to remove the comment (the #) and then update the values. Once you're editing the file, locate the following lines and modify them as shown. Change the port number:
`#Port 22`
Remove the # and change the port to 4242, so the line should look like this:
`Port 4242`
Disable root login:
`#PermitRootLogin prohibit-password`
Remove the # and set root login to no:
`PermitRootLogin no`
After making these changes, save the file and exit the editor with `ESC` and `:wq!` .
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2011.22.05%20AM.png)

3. Next, we need to edit the file located at: `/etc/ssh/ssh_config`
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%201.12.04%20PM.png)
Uncoment the Port 22 and change it to 4242
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2011.33.13%20AM.png)

4. Finally, to apply the changes we’ve made, we need to restart the SSH service. To do this, run the following command: `sudo service ssh restart`. Once the service has been restarted, you can check its status to confirm that the changes have been applied correctly. Use the following command: `sudo service ssh status`. Look for the Port 4242 line in the output to verify that the server is now listening on the new port. It should look similar to this:
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2011.36.02%20AM.png)
This confirms that SSH is now operating on Port 4242 as intended.

## Step 9: Install and configure the UFW
---


```🔒 **UFW** (Uncomplicated Firewall) is a user-friendly front-end for managing **iptables**, the default firewall configuration tool used by many Linux distributions. It simplifies the process of configuring firewall rules through an intuitive command-line interface. This makes it easy for users to control network traffic and strengthen system security with just a few commands.```
```With UFW, even users with limited experience in firewall management can quickly set up and maintain strong firewall policies, protecting their systems from unauthorized access and potential threats.```

❗❗For more details, check the [Guide for Virtual Machine and Linux Administration](Guide%20for%20Virtual%20Machine%20and%20Linux%20Administration.md), where you'll find explanations on all the concepts you'll need to learn.

1.  To get started, the first step is to install UFW. Open your terminal and run the following command: `sudo apt install ufw`
When prompted, type 'y' to confirm that you want to install the package, and then wait for the installation to complete. This will prepare your system for configuring the firewall and enhancing its security.
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%201.14.46%20PM.png)

2- After installing UFW, the next crucial step is to enable it. To do so, run the following command in your terminal: `sudo ufw enable`
Upon execution, you should receive a confirmation message indicating that the firewall is now active. This ensures your system is better protected against unauthorized access, enhancing its overall security.
Now, let’s configure the firewall to allow connections through port 4242. Run the following command in your terminal: `sudo ufw allow 4242`
This will allow traffic on port 4242, ensuring your desired services or applications can communicate freely.
Finally, let’s verify that everything is set up correctly by checking the status of the firewall. To do this, execute the command: `sudo ufw status`
You should see a list of allowed connections, with port 4242 listed as allowed. This confirms that your firewall is effectively protecting your system while allowing the necessary communication.
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2011.41.21%20AM.png)

## Step 10: set a strong password for your sudo privileges

1. Next, we’ll create a file at the path /etc/sudoers.d/ to store our password configuration. For clarity, we’ll name the file sudo_config.

Execute the following command in your terminal to create the file: `touch /etc/sudoers.d/sudo_config`
This file will be important for securely managing your sudo password settings.
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2011.44.54%20AM.png)

2. To fulfill the requirement of storing all sudo commands' input and output, we need to create a directory named sudo within the /var/log path.
Run the following command in your terminal to create this directory: `mkdir /var/log/sudo`
This ensures that all sudo activities are logged centrally, which is essential for system administration and security monitoring.
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2011.45.47%20AM.png)

3. Now, let's edit the file we created in the previous step. As mentioned, you can use any text editor, but for simplicity, we'll use Nano.
Execute the following command in your terminal to open the file for editing: `vim /etc/sudoers.d/sudo_config`
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2011.47.19%20AM.png)
This step allows you to securely and effectively configure password policies within the sudo_config file.
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%201.26.35%20PM.png)

## Step 11: Strong Password Policy Settings 

1. The first step will be to edit the login.defs file.
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%201.28.50%20PM.png)

2. In the sudo_config file, we'll set the password expiration policies. To do this, modify the following lines:
Change: `PASS_MAX_DAYS 99999` To: `PASS_MAX_DAYS 30`
And change: `PASS_MIN_DAYS 0` To: `PASS_MIN_DAYS 2`
These changes ensure that the maximum password age is set to 30 days, requiring users to change their passwords periodically, and the minimum password age is set to 2 days, preventing users from changing their password too quickly after a reset.
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2012.18.33%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-01%20at%2012.19.56%20PM.png)

Now, let’s delve into configuring password policies:

- **PASS_MAX_DAYS**: This parameter sets the maximum number of days a password can be used before it expires. After this period, the user will be required to change their password. For example `PASS_MAX_DAYS 30`. This means the password will expire after 30 days.

- **PASS_MIN_DAYS**: This parameter defines the minimum number of days a password must be used before it can be changed again. It prevents users from changing their passwords too frequently. For example `PASS_MIN_DAYS 2`. This means the user must wait at least 2 days before changing their password again.

- **PASS_WARN_AGE**: This setting triggers a warning message to users, notifying them of their password’s impending expiration within the specified number of days. For example `PASS_WARN_AGE 7`. This means users will be warned 7 days before their password expires.

By configuring these parameters, you ensure better control over password management and security in your system.

3. To continue with the configuration and enhance password security, we need to install the necessary packages. Run the following command in your terminal `apt install libpam-pwquality`. When prompted, type 'Y' to confirm the installation and wait for the process to complete.
These packages provide additional password quality checking capabilities, allowing you to enforce stronger password policies and improve your system's security.
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%201.31.05%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%201.31.50%20PM.png)

4. To proceed with configuring password policies, we need to modify the common-password file. This file controls how the system handles password settings. Use the following command to open the file for editing `vim /etc/pam.d/common-password`. Once the file is open, you can make the necessary changes to configure password policies effectively. This step will help ensure that the system enforces the appropriate password quality and security settings.
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%201.33.11%20PM.png)

5. After the retry=3 option in the /etc/pam.d/common-password file, we need to add the following commands to enforce stronger password policies:

```bash
minlen=10
ucredit=-1
dcredit=-1
lcredit=-1
maxrepeat=3
reject_username
difok=7
enforce_for_root
```
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%201.33.38%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%201.38.08%20PM.png)
Here’s what each parameter does:

- `minlen=10`: Sets the minimum password length to 10 characters.
- `ucredit=-1`: Requires at least 1 uppercase letter in the password.
- `dcredit=-1`: Requires at least 1 digit (number) in the password.
- `lcredit=-1`: Requires at least 1 lowercase letter in the password.
- `maxrepeat=3`: Limits the maximum number of consecutive identical characters to 3.
- `reject_username`: Ensures that the password does not contain the username.
- `difok=7`: Requires at least 7 characters to be different from the previous password.
- `enforce_for_root`: Enforces these password rules even for the root user.
These settings help to enforce robust password policies that enhance the overall security of your system.

## Step 12: Connect from SSH
---

1. Before closing the virtual machine, it’s important to save a snapshot through VirtualBox’s configuration settings. This will allow you to easily revert to the current state of the machine if needed.

To do this, navigate to the Snapshot Manager in VirtualBox and create a new snapshot with a descriptive name. This step ensures that your progress and configurations are preserved.

🔒 Next, to establish SSH connectivity, start by closing the virtual machine. Then, reopen VirtualBox and navigate to the machine's configuration settings. From there, we will adjust the network settings to enable SSH access for the virtual machine.

This step prepares the virtual machine for remote administration through SSH.

Once you're in the virtual machine's configuration settings in VirtualBox, navigate to the Network tab. Here, you'll need to configure the port for SSH connectivity:

Under Adapter 1, ensure the network is set to NAT.

Click on Advanced and then Port Forwarding.
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%201.44.36%20PM.png)
In the Port Forwarding rules window, add a new rule:

Protocol: TCP
Host IP: Leave this blank.
Host Port: Choose a port number on your host machine, in our case we will choose 4242.
Guest IP: Leave this blank.
Guest Port: Set this to 4242.
This will forward traffic from port 4242 on your host machine to port 4242 on the virtual machine, enabling SSH connectivity.

Once this is set, click OK to save the changes, and you’ll be ready to connect to your virtual machine via SSH using the specified port.
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%201.49.04%20PM.png)

2. To connect to the virtual machine from the host machine, open a terminal on the host and type the following command:
```bash
ssh your_login@localhost -p 4242
```
This command initiates an SSH connection to the virtual machine, specifying the username and port 4242. You will be prompted to enter the password for the user. Once authenticated, you should see the login prompt, which typically appears in green, indicating a successful connection.
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%207.23.18%20PM.png)
Ensure your virtual machine is running while you attempt to connect via SSH.

## Step 13: Writing the Bash Monitoring Script
---

Entering this section requires close attention to detail. It's essential to fully understand everything presented here. Don't try to take shortcuts! During the evaluation, you'll most likely be asked about the script's functionality or how it operates.

### What is a script?
A script is a file containing a sequence of commands. When executed, these commands perform specific tasks outlined in the script.

### 1- System Architecture
To display the system's architecture, use the `uname -a` command. This command provides comprehensive information about the system, except in cases where the CPU or platform is unknown.

### 2- Physical Cores
To find out the number of physical cores, access the `/proc/cpuinfo` file, which contains information about the CPU, such as type, brand, model, and performance. You can count the physical cores using the command:
```grep "physical id" /proc/cpuinfo | wc -l```

### 3- Virtual Cores
Similarly, to determine the number of virtual cores, use the `/proc/cpuinfo` file again. This time, run the command:
```grep processor /proc/cpuinfo | wc -l```
to count the number of virtual cores.

### 4- RAM
To view details about the RAM, use the `free` command, which provides real-time data about RAM usage, available space, and reserved resources. For more detailed information, run `free --help`. To display RAM in megabytes, use:
`free --mega`

After running the command, filter the output to show only relevant data. To get the used memory, run:
```free --mega | awk '$1 == "Mem:" {print $3}'```

To get the total memory, run a similar command but print the second word instead of the third:
```free --mega | awk '$1 == "Mem:" {print $2}'```

Finally, to calculate the percentage of used memory, run this command, which formats the output to two decimal places:
```free --mega | awk '$1 == "Mem:" {printf("(%.2f%%)\n", $3/$2*100)}'```

### 5- Disk Memory
To view the disk memory usage, use the `df` command. Running `df -m` displays the memory in megabytes. Filter the output using `grep` and `awk` to show only relevant information. To calculate the used disk space, use:
```df -m | grep "/dev/" | grep -v "/boot" | awk '{memory_use += $3} END {print memory_use}'```

To get the total disk space, sum the values in the second column and convert the result to gigabytes if needed:
```df -m | grep "/dev/" | grep -v "/boot" | awk '{total_size += $2} END {print total_size/1024}'```

To calculate the percentage of used disk memory, combine the previous commands:
```df -m | grep "/dev/" | grep -v "/boot" | awk '{use += $3} {total += $2} END {printf("(%.2f%%)\n", use/total*100)}'```

### 6- CPU Usage Percentage
To find the CPU usage percentage, use the vmstat command to gather system statistics. Specify an interval and use tail and awk to extract the relevant data. For example:
```vmstat 1 4 | tail -1 | awk '{print $15}'```
This gives you the available CPU percentage.

Subtract this value from 100 to get the CPU usage percentage, then format the result to one decimal place and append a `%` symbol.

### 7- Last Reboot
To check the date and time of the last system reboot, use the ```who -b``` command. Filter the output to show only the relevant information using `awk`:
```who -b | awk '$1 == "system" {print $3 " " $4}'```

### 8- LVM Active
To determine if LVM (Logical Volume Manager) is active, use the `lsblk `command to display block device information. Filter the output to search for LVM and print "Yes" or "No" accordingly. The command is:
```if [ $(lsblk | grep "lvm" | wc -l) -gt 0 ]; then echo yes; else echo no; fi```

### 9- TCP Connections
To determine the number of established TCP connections, use the ```ss``` command, which replaces the obsolete `netstat`. Run the command with the `-ta` flag to display only TCP connections. Then filter with `grep` to find established connections, and use `wc -l` to count them:
```ss -ta | grep ESTAB | wc -l```

### 10- Number of Users
To count the number of active `users`, use the users command, which lists logged-in users. Then use ```wc -w``` to count the words:
```users | wc -w```

### 11- IP Address & MAC Address
To get the IP address of the host, use the ```hostname -I``` command. For the MAC address, use the ```ip link``` command to show network interfaces. Filter the output to display only the MAC address:
```ip link | grep "link/ether" | awk '{print $2}'```

### 12- Number of Commands Executed with sudo
To count the number of commands executed with `sudo`, use the `journalctl` command, which collects system logs. Filter the results with `_COMM=sudo` and refine them with grep COMMAND. Finally, count the entries with `wc -l`:
```journalctl _COMM=sudo | grep COMMAND | wc -l```

Verify this command by executing it, running a sudo command, and checking if the count increases.

⚠️ Reminder: Do not copy and paste these commands without fully understanding them! ⚠️

To create the Bash file for the monitoring script, connect via SSH, switch to superuser mode, and use `vim monitoring.sh`.
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%207.38.48%20PM.png)

Once you’re in the vim editor, press i to enter insert mode and then start writing the script.
!!Ensure you understand every command and section of the script, as you’ll likely need to explain it during evaluation.!!

And write the script inside like below

```bash
#!/bin/bash

while true;
do
	sleep 599

# ARCHITECTURE
architecture=$(uname -a)

# CPU PHYSICAL
cpu_physical=$(grep "physical id" /proc/cpuinfo | wc -l)

# CPU VIRTUAL
cpu_virtual=$(grep "processor" /proc/cpuinfo | wc -l)

# MEMORY USAGE
ram_total=$(free --mega | awk '$1 == "Mem:" {print $2}')
ram_use=$(free --mega | awk '$1 == "Mem:" {print $3}')
ram_percent=$(free --mega | awk '$1 == "Mem:" {printf("%.2f"), $3/$2*100}')

# DISK USAGE
disk_total=$(df -h | grep /dev/ | grep -v "/boot" | awk '{disk_t += $2} END {printf ("%.1fGb\n"), disk_t/1024}')
disk_use=$(df -h | grep /dev/ | grep -v "/boot" | awk '{disk_u += $3} END {printf "%d", disk_u}')
disk_percent=$(df -h | grep /dev/ | grep -v "/boot" | awk '{disk_u += $3} {disk_t+=$2} END {printf("%d"), disk_u/disk_t*100}')

# CPU LOAD
cpu1=$(vmstat 1 2 | tail -1 | awk '{print $15}')
cpu_op=$(expr 100 - $cpu1)
cpu_fin=$(printf "%.1f" $cpu_op)

# LAST BOOT
last_boot=$(who -b | awk '$1 == "system" {print $3 " " $4}')

# LVM USE
lvm_use=$(if [ $(lsblk | grep "lvm" | wc -l) -gt 0 ]; then echo yes; else echo no; fi)

# CONNECTIONS TCP
connections_tcp=$(ss -ta | grep ESTAB | wc -l)

# USER LOG
user_log=$(users | wc -w)

# NETWORK
ip=$(hostname -I)
mac=$(ip link | grep "link/ether" | awk '{print $2}')

# SUDO
sudo_count=$(journalctl _COMM=sudo | grep COMMAND | wc -l)

wall "
	#Architecture: $architecture
	#CPU physical: $cpu_physical
	#vCPU: $cpu_virtual
	#Memory Usage: $ram_use/${ram_total}MB ($ram_percent%)
	#Disk Usage: $disk_use/$disk_total ($disk_percent%)
	#CPU load: $cpu_fin%
	#Last boot: $last_boot
	#LVM use: $lvm_use
	#Connections TCP: $connections_tcp ESTABLISHED
	#User log: $user_log
	#Network: IP $ip($mac)
	#Sudo: $sudo_count cmd
"
done
```
![continue](screen_shots_guide/Screen%20Shot%202025-01-04%20at%2010.39.29%20AM.png)

After successfully running the script, you should see output that gives you a detailed summary of your system's performance and configuration. The following is an example of what you might see after executing the monitoring script:
![continue](screen_shots_guide/Screen%20Shot%202025-01-04%20at%2010.55.32%20AM.png)

## Step 14: 📅 Crontab Setup for Monitoring Script
---

1. What is Crontab?
Crontab (Cron Table) is a configuration file that schedules jobs (commands or scripts) to run at specific times or intervals. Each line in the crontab file represents a task that will be executed automatically at the designated time.

2. Open Crontab for Editing
To schedule the monitoring script to run at regular intervals, you'll need to edit the crontab file. Use the following command:

```bash
crontab -e
```
or
```bash
crontab -u root -e
```
This opens the crontab configuration file in your default text editor.
you will be prompted to select an editor, choose the first one as it is the easiest.
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%207.49.07%20PM.png)

3. Define the Frequency of Execution
Crontab uses a specific format to schedule tasks. The format consists of five fields:

Crontab Syntax:
```bash
m h dom mon dow command
```
### Fields Explained:
- m (Minute):
The minute when the command should run.
	- Valid values: 0-59
	- Example: 5 means the task will run at the 5th minute of the hour.
- h (Hour):
The hour when the command should run (24-hour format).
	- Valid values: 0-23
	- Example: 14 means the task will run at 2:00 PM.
- dom (Day of Month):
The specific day of the month when the command should run.
	- Valid values: 1-31
	- Example: 15 means the task will run on the 15th day of the month.
- mon (Month):
The specific month when the command should run.
	- Valid values: 1-12 or abbreviated names (jan, feb, etc.)
	- Example: 7 means the task will run in July.
- dow (Day of Week):
The day of the week when the command should run.
	- Valid values: 0-7 (where 0 and 7 both represent Sunday), or abbreviated names (sun, mon, etc.)
	- Example: 5 or fri means the task will run on Friday.
- command:
The actual script or command you want to execute.

### Example
```scss
*    *    *    *    *  command_to_be_executed
-    -    -    -    -
|    |    |    |    |
|    |    |    |    |  
|    |    |    |    ----- Day of the week (0 - 7) (Sunday is both 0 and 7)
|    |    |    --------- Month (1 - 12)
|    |    --------------- Day of the month (1 - 31)
|    -------------------- Hour (0 - 23)
------------------------- Minute (0 - 59)
```
Example:
If you want the script to run every 10 minutes, add the following line to the crontab file:
```bash
*/10 * * * * /path/to/your/script/monitoring.sh
```
In this example:
*/10: Runs the script every 10 minutes.

Inside the file, you will add the following command: 
```@reboot sh /home/your_login/monitoring.sh```
This will ensure that the script runs once every 10 minutes after a reboot.
![continue](screen_shots_guide/Screen%20Shot%202025-01-04%20at%2011.12.43%20AM.png)
In this case, the command `@reboot sh /home/your_login/monitoring.sh` added to your crontab makes your script run automatically at system startup. Here's how crontab works in this context:

- `@reboot`: This is a special time specification in crontab that schedules your script to run every time the system starts or reboots. It ensures your monitoring script starts as soon as the system is up and running.

- `sh /home/noaziki/monitoring.sh`: This part of the crontab entry specifies the command to be executed. In this case, it's telling the system to run your Bash script (monitoring.sh) using sh.

- `Script Execution`: When your system boots, crontab triggers the script located at /home/noaziki/monitoring.sh.

Do you remember this part of the script?
```bash
while true;
do
	sleep 599
done
```
Let's analyze it now.

- `while true;`: This creates an infinite loop. The condition true always evaluates as "true," meaning the loop will never exit on its own. It's used when you want a section of code to run repeatedly without stopping until the program is manually terminated or the system shuts down.

- `do`: This marks the beginning of the commands that will be executed inside the loop. In your case, everything between do and done will repeat.

- `sleep 599`: The sleep command pauses the execution of the script for 599 seconds (about 10 minutes) each time the loop iterates. After this 10-minute pause, the script continues to gather system metrics and then broadcasts the results.

How It Works:

- Loop Cycle: The script enters the loop (while true) and then sleeps for 599 seconds. After the sleep period ends, it collects the system metrics and displays them using the wall command.

- Repeat: After displaying the metrics, the loop starts again, waits for another 599 seconds, and repeats the process indefinitely.
In essence, this part of the script ensures that the system monitoring task is executed approximately every 10 minutes.

- Script Output: Each time the script runs, it gathers various system metrics (architecture, CPU, memory, disk usage, etc.) and uses the wall command to broadcast the information to all logged-in users on the terminal.

In short, every time your system reboots, this script runs in the background and continuously monitors your system's status, updating every 10 minutes.

## Step 14: Wordpress & services configuration


![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.01.58%20PM.png)

![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.03.54%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.05.10%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.06.37%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.31.40%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.35.23%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.40.03%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.41.52%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.44.40%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.46.13%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-38%20at%208.48.11%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.49.47%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.51.41%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.56.34%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.57.05%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%208.58.26%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%209.04.32%20PM.png)
![continue](screen_shots_guide/Screen%20Shot%202025-01-02%20at%209.05.23%20PM.png)

