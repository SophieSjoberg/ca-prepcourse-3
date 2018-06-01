## Windows, really?

Although there are ways to setup your windows environment for this course, it will soon become a nightmare to follow up. 

One thing you can do at this stage is setup your computer to dual boot a Linux operating system. If you're up for the challenge, a quick Google search will point you to resources on how to achieve that. 

We will take a rather simpler approach in this guide. We will use [VirtualBox](https://www.virtualbox.org/) to create and setup a Linux virtual machine. You will then use that virtual machine to go through the pre-course material.

**Note! The following walk-through is rather advanced. You should really take it slow and follow the instructions carefully.**

### Install Ubuntu 14.04 LTS on Oracle Virtual Box

1. Step 1: Download [VirtualBox Windows Installer][vbox-win-install] and Install it.

  ![Virtual Box installation](../images/virtual-box-windows/01-vb-install.png)

2. Step 2: Download a copy of [Ubuntu from here][ubuntu-download]

  Select between 32 or 64-bits version depending on your system architecture.

  ![Download Ubuntu image](../images/virtual-box-windows/02-download-ubuntu.png)

3. Step 3: Create a new VM

  Open VirtualBox
  
  ![Virtual box](../images/virtual-box-windows/03-new-vm-wizard.png)

  Click `New` to create a new VM

  ![Create Virtual Machine wizard](../images/virtual-box-windows/04-vm-name.png)

  In the 'Create Virtual Machine' window, give your VM a name.

  Select `Linux` as type

  Select the version of Ubuntu that matches the version you downloaded at step 2.

  > **Note:** In this case, i downloaded the 32-bit version of Ubuntu. If you don't have `Ubuntu (64-bit)` listed you might have to enable `intel® VT-x technology` on your computer. A quick [Google search][vt-xsearch] will help you find out how to do that for your particular computer.

  Then click 'Next'

  In the next screen, enter the memory size (minimum required 512 MB, recommended 1024 MB) then click 'Next'
  
  - Create a virtual hard disk for your VM

    ![Create virtual HDD](../images/virtual-box-windows/06-vm-create-hdd.png)

  - Select hard disk file type `VDI (VirtualBox Disk Image)`

    ![HDD file type](../images/virtual-box-windows/07-vm-hdd-type.png)

  - Hard disk mode

    ![HDD Mode](../images/virtual-box-windows/08-vm-storage-mode.png)

  - Set virtual hard disk size and file location
    
    ![HDD Size](../images/virtual-box-windows/09-vm-hdd-size.png)

  *We recommend a minimum of 20GB.*
  
  Click `create` to finalize the VM

4. Step 4: Install Ubuntu

  You should now have your newly created VM listed in the dashboard. Before we start the VM, we need to load the Ubuntu image into the virtual disk. To do that:
    - Select the VM
    - Click 'Settings'
    - Go to the 'Storage' section. You will then have the following screen

      ![Load ISO](../images/virtual-box-windows/10-vm-load-iso.png)
    - Click on the CD icon right next to the `Optical Drive` attribute dropdown list. Then select `Choose Virtual Optical Disk File...`

      ![Load ISO contd.](../images/virtual-box-windows/11-vm-load-iso-1.png)

    - In the explorer windows, navigate to the location where you saved the ubuntu ISO from [Step 2][step-2]

      ![Select ubuntu ISO image](../images/virtual-box-windows/12-vm-load-iso-2.png)

    - Click `Open`.

      ![Confirm image](../images/virtual-box-windows/13-vm-load-iso-3.png)

    - Click `OK`

  You are now ready to Install Ubuntu. Go ahead and start the Virtual Machine.

    ![Boot-up the VM](../images/virtual-box-windows/14-vm-start.png)

  The VM will boot from the Ubuntu image in our virtual optical drive and greet us with the Welcome screen

    ![Ubuntu Welcome screen](../images/virtual-box-windows/15-ubuntu-install.png)

  Click `Install Ubuntu` to start the installation process.

    ![Ubuntu welcome screen](../images/virtual-box-windows/16-ubuntu-install-1.png)

  Click `Continue`

    ![Ubuntu install step 1](../images/virtual-box-windows/17-ubuntu-install-2.png)

  Since this is a standalone installation you should be able to get away with selecting the first option `Erase disk and install Ubuntu`. But we'll go ahead and pick the last option `Something else` to partition the hard disk.

    ![Ubuntu install step 2](../images/virtual-box-windows/18-ubuntu-install-3.png)

  `/dev/sda` represents our virtual disk. In Ubuntu and `Unix` systems in general disks are often represented by the following path `/dev/sdx` where `x` is a letter from `a-z`. With multiple disks you'll then have something similar to `/dev/sda`, `/dev/sdb` etc.

  We'll go ahead and create a `New Partition Table`. Click `continue` in the warning windows that appear

    ![Ubuntu install step 3](../images/virtual-box-windows/19-ubuntu-install-4.png)

  First we'll create a [Swap area][what-is-swap]. Click the `+` sign to open the `Create partition` dialog

    ![Ubuntu install step 4](../images/virtual-box-windows/20-ubuntu-install-5.png)

  In general I like to have the swap double the size of my available RAM. In this case we set the size to 2048 since we have a RAM of 1024 MB on our VM.

    ![Ubuntu install step 5](../images/virtual-box-windows/21-ubuntu-install-6.png)

  Next we create our `root` partition, where the actual system will be installed. Don't forget to set the `Mount point` to `/`

    ![Ubuntu install step 6](../images/virtual-box-windows/22-ubuntu-install-7.png)

  You should now have something like this

    ![Ubuntu install step 6](../images/virtual-box-windows/23-ubuntu-install-8.png)

  You're now ready to install the system. Click `Install Now`. The following steps will be basic configurations for your system, namely:
    - Your location (Time zone)
    - Keyboard layout
    - User, Computer name and password
    - etc.


  **You can now grab some coffee while the installation proceeds. Once done, restart the VM.**


 ** And that's IT! Congratulations, you now have a Virtual Machine running Ubuntu. From here, you can head to our [Linux instructions](/linux.md) to complete your setup.**



[vbox-win-install]: https://www.virtualbox.org/wiki/Downloads
[ubuntu-download]: http://www.ubuntu.com/download/desktop
[vt-xsearch]: https://www.google.com/search?q=enable+intel%C2%AE+virtualization+technology
[what-is-swap]: http://askubuntu.com/questions/508870/what-is-a-swap-area