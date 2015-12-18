## Windows, really?
There is not much you can do with this material if you are working on a windows based computer. You can however, install Linux on your machine and follow the course using that partition. Another possibility is that you use a so called VirualBox. We have prepared a step-by-step guide for you to follow if you want to set that up.

**Note! The following walkthrough is fairly advanced so you should really take it slow and follow the instructions carefully.**
### Install Ubuntu 14.04 LTS on Oracle Virtual Box

1. Step 1: Download [VirtualBox Windows Installer][vbox-win-install] and Install it.

  ![Virtual Box installation][img-01]

2. Step 2: Download a copy of [Ubuntu from here][ubuntu-download]

  Select between 32 or 64-bits version depending on your system architecture.

    ![Ubuntu 32/64bits][img-02]

3. Step 3: Create a new VM

  Open VirtualBox

    ![virtual box][img-03]

  Click 'New' to create a new VM

    ![create virtual machine wizard][img-04]

    In the 'Create Virtual Machine' window, give your VM a name.

    Select `Linux` as type

    Select the version of ubuntu that matches the version you downloaded at step 2.

    **Note:** In this case, i downloaded the 32-bit version of Ubuntu. If you don't have `Ubuntu (64-bit)` listed you might have to enable `intel® VT-x technology` on your computer. A quick [Google search][vt-xsearch] will help you find out how to do that for your particular computer.

    Then click 'Next'

  In the next screen, enter the memory size (minimum required 512 MB, recommended 1024 MB) then click 'Next'
  - Create a virtual hard disk for your VM

    ![create virtual hdd][img-06]

  - Select hard disk file type `VDI (VirtualBox Disk Image)`

    ![hdd file type][img-07]

  - Hard disk mode

    ![hdd mode][img-08]

  - Set virtual hard disk size and file location

    ![hdd size][img-09]

    *We recommend a minimum of 20GB.*

    Click `create` to finalize the VM

4. Step 4: Install Ubuntu

  You should now have your newly created VM listed in the dashboard. Before we start the VM, we need to load the Ubuntu image into the virtual disk. To do that:
    - Select the VM
    - Click 'Settings'
    - Go to the 'Storage' section. You will then have the following screen

      ![Load ISO][img-10]

    - Click on the CD icon right next to the `Optical Drive` attribute dropdown list. Then select `Choose Virtual Optical Disk File...`

      ![load ISO cntd.][img-11]

    - In the explorer windows, navigate to the location where you saved the ubuntu ISO from [Step 2][step-2]

      ![select ubuntu iso file][img-12]

    - Click `Open`.

      ![confirm image][img-13]

    - Click `OK`

  You are now ready to Install Ubuntu. Go ahead and start the Virtual Machine.

    ![boot-up the VM][img-14]

  The VM will boot from the Ubuntu image in our virtual optical drive and greet us with the Welcome screen

    ![Ubuntu welcome screen][img-15]

  Click `Install Ubuntu` to start the installation process.

    ![Ubuntu welcome screen][img-16]

  Click `Continue`

    ![Ubuntu install step 1][img-17]

  Since this is a standalone installation you should be able to get away with selecting the first option `Erase disk and install Ubuntu`. But we'll go ahead and pick the last option `Something else` to partition the hard disk.

    ![Ubuntu install step 2][img-18]

  `/dev/sda` represents our virtual disk. In Ubuntu and `Unix` systems in general disks are often represented by the following path `/dev/sdx` where `x` is a letter from `a-z`. With multiple disks you'll then have something similar to `/dev/sda`, `/dev/sdb` etc.

  We'll go ahead and create a `New Partition Table`. Click `continue` in the warning windows that appear

    ![Ubuntu install step 3][img-19]

  First we'll create a [Swap area][what-is-swap]. Click the `+` sign to open the `Create partition` dialog

    ![Ubuntu install step 4][img-20]

  A general rule of thumb is to have swap double the size of your RAM. In this case we set the size to 2048 since we have a RAM of 1024 MB on our VM.

    ![Ubuntu install step 5][img-21]

  Next we create our `root` partition, where the actual system will be installed. Don't forget to set the `Mount point` to `/`

    ![Ubuntu install step 6][img-22]

  You should now have something simmilar to this

    ![Ubuntu install step 6][img-23]

  You're now ready to install the system. Click `Install Now`. The following steps will be basic configurations for your system, namely:
    - Your location (Time zone)
    - Keyboard layout
    - User, Computer name and password
    - etc.


  **You can now grab some coffee while the installation proceeds. Once done, restart the VM.**


 ** And that's IT! Congratulations you now have a Virtual Machine running Ubuntu.**



[vbox-win-install]: http://download.virtualbox.org/virtualbox/5.0.2/VirtualBox-5.0.2-102096-Win.exe
[ubuntu-download]: http://www.ubuntu.com/download/desktop
[vt-xsearch]: https://www.google.com/search?q=enable+intel%C2%AE+virtualization+technology
[what-is-swap]: http://askubuntu.com/questions/508870/what-is-a-swap-area
[step-2]:


[img-01]: ../images/virtual-box-windows/01-vb-install.png?raw=true
[img-02]: ../images/virtual-box-windows/02-download-ubuntu.png?raw=true
[img-03]: ../images/virtual-box-windows/03-new-vm-wizard.png?raw=true
[img-04]: ../images/virtual-box-windows/04-vm-name.png?raw=true
[img-05]: ../images/virtual-box-windows/05-vm-memory-size.png?raw=true
[img-06]: ../images/virtual-box-windows/06-vm-create-hdd.png
[img-07]: ../images/virtual-box-windows/07-vm-hdd-type.png?raw=true
[img-08]: ../images/virtual-box-windows/08-vm-storage-mode.png?raw=true
[img-09]: ../images/virtual-box-windows/09-vm-hdd-size.png?raw=true
[img-10]: ../images/virtual-box-windows/10-vm-load-iso.png?raw=true
[img-11]: ../images/virtual-box-windows/11-vm-load-iso-1.png?raw=true
[img-12]: ../images/virtual-box-windows/12-vm-load-iso-2.png?raw=true
[img-13]: ../images/virtual-box-windows/13-vm-load-iso-3.png?raw=true
[img-14]: ../images/virtual-box-windows/14-vm-start.png?raw=true
[img-15]: ../images/virtual-box-windows/15-ubuntu-install.png?raw=true
[img-16]: ../images/virtual-box-windows/16-ubuntu-install-1.png?raw=true
[img-17]: ../images/virtual-box-windows/17-ubuntu-install-2.png?raw=true
[img-18]: ../images/virtual-box-windows/18-ubuntu-install-3.png?raw=true
[img-19]: ../images/virtual-box-windows/19-ubuntu-install-4.png?raw=true
[img-20]: ../images/virtual-box-windows/20-ubuntu-install-5.png?raw=true
[img-21]: ../images/virtual-box-windows/21-ubuntu-install-6.png?raw=true
[img-22]: ../images/virtual-box-windows/22-ubuntu-install-7.png?raw=true
[img-23]: ../images/virtual-box-windows/23-ubuntu-install-8.png?raw=true

