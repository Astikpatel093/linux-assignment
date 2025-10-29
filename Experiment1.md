## [Experiment 1:installing some useful tools for programming for linux]
### Name: Astik Patel, Roll No.: 590029070 Date: 2025-09-04

### AIM:
* install wsl virtualbox,create virtual machine with linux os like ubuntu,linuxmint,or debian

### Requirements:
* internet,terminal,websites

### Theory:
* installing ubuntu,linuxmint,or debian

## part 1: Installing and Enabling WSL (Ubuntu) on Windows

## procedure & observations
install wsl - go to the terminal type sudo apt instal wslor wsl --install -d ubuntu observation1
Enables the required "virtual machine platform" and "windows subsystem for linux" optional components.
Downloads and installs the latest ubuntu linux distribution by default
requests a reboot.
reboot your computer when prompted.

step 2: set your ubuntu Distribution

1. After rebooting , a terminal window open for ubuntu.if it doesn't,open your start menu and launch "ubuntu".

2. wait for the installation to finish.you will be asked to create a new UNIX username and **password**.
this is separate from your windows login.

Troubleshioting WSL installation:

 if wsl --install -d ubuntu fails or the command is not recognised:

       Enable features manually:open "Turn windows features on or off" in the start menu.check the boxes for "Virtual machine Platform" and **"Windows subsystem for linux"**. click OK,reboot,and then run  wsl --install again.


Error: "THe virtual machine could not be started because a requird feature is not installed."

             this almost always mean **hardware virtualization is disabled in your BIOS/UEFI**.    

step 3: Enable virtualization in Bios/UEFI

     1. check if it's enabled:
            press ctrl + shift + Esc to open task manager.
            Go to the "performence" tab.
            look at the bottom right. "virtualization" dhould say **Enabled**.

     2. if it's Disabled:       

            Reboot your computer and enter the BIOS/UEFI setup.the  key to press is usually Delete , F2,F10,F12,or Esc. it flashes on the screen during boot.
             
            Navigate the BIOS menus (often under Advanced**,**CPU comfiguration**, or **security setting).

            Find the setting for **virtualization technology**. it might be called:

            intel virtualization Technology (**Intel VT-x**)

            AMD-V (for AMD CPUs)

            SVM Mode 

            Enable the setting.

            save and Exit (usually   F10  ). Your computer will reboot.

After enabling virtualization,Windows should automatically enable the Hypervisor (Windows HYpervisor Platfrom).
WSL will now work.

Verify WSL is Working: Open a new powerShell or
Command prompt and type:


     wsl -l -v

     this should list yoour installed ubuntu distibution and its version.

## part 2:     
virtualBox is a traditional Type 2 hypervisor for running full fledged virtual machines.

step 1:Download and install virtualBox

1. Go to the official VirtualBox download page.
2. Under "VirtualBox platform packages",click "Windows hosts" to download the installer.
3. Run the downloaded  .exe  file.
4. Follow the installation wizard.You can accept all default settings.it's safe to install all features (network interfaces,etc.).
5. You will likely get a warning about installing device software.click "install" to proceed.


step 2:(Optional)install the microsoft visual c++ Redistributable

1. this is sometimes reqiured for vitualBox to funtion correctly,especially if you see related errors.

2. Download the latest Visual stdio 2019
redistributable from the official microsoft site.

3. Download and run the  vc_redist.x64.exe  file.

4. Follow the prompts to install it.A reboot is recommended afterward.

## part 3: creating a virtual machine with linux mint 

step 1. Download linux Mint 

1. Go to the Linux Mint (cinnamon) download page.

2. choose the edition you prefer (Cinnamon is the most feature-complete).choose **64-bit**.

3. Download the ISO file.This is a disk image that VirtualBox Will use as the installation source.

step 2: create a New Virtual Machine in virtualBox

1. Open **Oracle VM VirtualBOX**.
2. Click the "New" button (blue star).
3. Name and Operating system :

        Name:  Linux Mint (this Will auto-fill other fields).

        ISO Image:Click the folder icon and browse to select the Linux Mint ISO you downloaded.

        Type: Linux

        Version: Ubuntu (64-bit) (Linux Mint is Ubuntu-based, so this is the best match).

        Click **Next**.
1. Hardware Resources:

          Memory (RAM): Allocate at least 4096 MB
          (4 GB) if you have 8+ GB of physical RAM.
          Do not give it all your RAM.

          processors: Allocate 2 or more CPUs if your system has multiple cores.

          Click **Next**.

1. Hard Disk:
      "Create a virtual hard disk now" should be selected. Click **create**.

      Hard disk file type: **VDI(VirtualBOX Disk Image)**.

      Storage on physical hard disk:
      Dynamically allocated(uses space only as needed).

      file location and size: The default location is fine.Allocate at least 25 GB for the Disk.
      Click **Create**.


step 3: Install Linux Mint on the Virtual MAchine 

1. With your new "Linux Mint" VM selected in the Virtual Manager,click the "Start" (Green arrow)
button.
2. The VM will boot from the ISO into the linux mint live enviroment.

3. Double - click "Install Linux Mint" on the desktop.

4. Follow the installation wizad:

      Select your language and Keyboard layout.
      Connect to a Wifi network if desired.

      Installation type : You can choose the default *"Erase disk and install Linux mint"**.*This only erases the Virtual hard disk you created, not your actual physical drive.
       
      select your time zone.

      Create your user account(name,computer name,username,password).

5. The installation will run. once finished,you will be 
prompted to **restart the computer**.

6. when it asks you to "Please remove the installation medium", you can press  Enter  .VirtualBOX will automatically eject the ISO on shutdown.

7. The VM Will reboot into your freshly installed linux mint OS.

Step 4. install Guest Additons (Highly Recommended)

Guest Additions provide better screen resolution, shared clipboard,file sharing,and much better overall performance. 

1. Inside your running linux mint VM,go to the virtualBOX menu: Devices > Insert Guest Addition CD image...

2. A CD icon will appear on the desktop. Open it.

3. Right-click in the folder and select **"Open in terminal"**.

4. In the terminal that opens Run:

  sudo ./VBoxLinuxAdditions.run

  1. Enter your password and wait for the installtion to complete.
  2. Reboot the VM from the linux mint menu for the changes to take full effect.



## RESULT:

installation complete.
