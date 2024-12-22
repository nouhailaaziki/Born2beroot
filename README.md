# Born2beroot

## Description
**Born2beroot** is your essential companion to mastering Linux system administration, designed to guide beginners and aspiring professionals into the world of root access and system management. This resource simplifies the complexities of Linux, offering clear, practical steps to help users build confidence and expertise.

From foundational concepts like file systems, permissions, and processes to advanced topics such as security, networking, and automation, Born to be Root equips you with the tools and knowledge to excel in system administration. Its hands-on tutorials and real-world examples provide a solid framework for tackling diverse challenges, ensuring you gain both understanding and practical skills.

By adopting the mindset of the root user — the ultimate superuser — you’re encouraged to explore, experiment, and take full control of your Linux environment. This guide empowers you to unlock the system’s full potential, transforming you into a confident and capable administrator.

Whether setting up servers, troubleshooting, or optimizing performance, **Born2beroot** is your trusted guide to navigating the dynamic world of Linux with ease and proficiency.

*For more check the [subject](subject.pdf)*

`Before starting, it's important to understand that each action in every step serves a specific purpose. You should know why it's being done and how it contributes to the overall process. A solid grasp of the technical context is crucial to fully comprehend the procedure.`

## Step 1: Check for VirtualBox

To get started, ensure you have **VirtualBox** installed. If not, you can download it from [this link](https://www.virtualbox.org/). **VirtualBox** is essential for setting up the operating system we’ll be working with.

At 1337, **VirtualBox** is already available on the macOS devices, so you likely won’t need to install it. Double-check whether it’s already installed on your machine before proceeding.

### Some things you need to learn

- **VirtualBox**: Understand what VirtualBox is and how it works as a virtualization tool.
- **Virtualization**: Learn the concept of virtualization and its role in creating virtual environments.
- **Operating Systems**: Familiarize yourself with what operating systems are and their importance in managing computer hardware and software.
- **Hypervisor**: Discover the role of a hypervisor and how it enables virtualization by managing virtual machines.

## Step 2: Selecting the Operating System

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

## Step 3: Creating a New Virtual Machine in Oracle VirtualBox

1. Launch Oracle **VirtualBox**.

2. Select the "**New**" button at the top of the window.
![New button](screen_shots_guide/new_button.png)

3. In the **name** field, enter "Born2beroot" and change the **version** to Debian (64-bit).
![Name and operating system](screen_shots_guide/name_and_operating_system.png)

4. After pressing **continue** button, the **memory size** should automatically be set to **1024 MB** (1 GB), which is recommended. If it doesn’t appear as **1024 MB**, manually adjust it to that value.
![Memory size](screen_shots_guide/memory_size.png)

5. After pressing **continue** button, When prompted with three options, select the second one: **Create a virtual hard disk now**.
   ![Hard disk](screen_shots_guide/hard_disk.png)

6. After pressing **continue** button, In the **Hard disk file type** options, choose the first option: **VDI (VirtualBox Disk Image)**.
   ![Hard disk file type](screen_shots_guide/hard_disk_file_type.png)

7. After pressing **continue** button, In the **Storage on physical hard disk** options, choose the first option: **Dynamically allocated**.
   ![Storage on physical hard disk](screen_shots_guide/storage_on_physical_hard_disk.png)

8.  After pressing **continue** button, set the size of the virtual hard disk to **30 GB** if you're going to work on the **bonus part** of the project (You cannot select 30 GB exactly, but make sure the size is set to at least 30 GB). If you're only going to complete the **mandatory part**, choose **8 GB**. If you choose the **mandatory** option, you won't need the extra steps required for the **bonus part** later on. Since you're focusing on the **bonus**, you'll proceed with the 30 GB size.
![File location and size](screen_shots_guide/file_location_and_size.png)

9.  After pressing **continue** or **finished** button, you should see your new **Virtual Machine** created. To move on to the next step, go to **Settings** to start mounting an **ISO file**.
![Settings button](screen_shots_guide/settings_button.png)

10. In **Settings**, click on the **Storage** tab, then select the **Empty** option under **Storage Devices**.
![Storage button](screen_shots_guide/storage_button.png)

## Step 4: Mount the ISO File and Start the Virtual Machine

1. Once you’ve clicked on **Empty**, you should see a small disk icon similar to the one in the **screenshot below** next to the **optical drive**. Click on it.
![Disk file](screen_shots_guide/disk_file.png)

2. Choose **debian-12.8.0-amd64-netinst.iso** from the list if it appears. If it doesn't show up, click on the **Choose a disk file** button and select the **debian-12.8.0-amd64-netinst.iso** file from the folder where you downloaded **Debian**.
![Choose a disk file](screen_shots_guide/choose_a_disk_file.png)

3. Now, start the machine by clicking the **Start** button, so you can continue with the next step to install **Debian**.
![Start button](screen_shots_guide/start_button.png)

## Step 5: Installing Debian Operating System

### Configuring the Language, Time Zone, and Keyboard Layout

