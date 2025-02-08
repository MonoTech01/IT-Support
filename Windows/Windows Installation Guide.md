# 💾 Windows Installation Guide
## 📌 Preparation
- A **USB flash drive** is required for this setup.
- Two installation methods are covered in this guide:
  - **Method 1 (USB Flash Drive):** Easier and recommended for most users, as Microsoft provides an automated setup process.
  - **Method 2 (ISO File):** Ideal for advanced users or those installing via DVD.
- If you have a USB, stick with **Method 1** since Microsoft’s tool will set up Windows automatically, eliminating the need for third-party tools like Rufus.
- If you are using a **DVD** :dvd:, select **Method 2**—no need for Rufus.
- For Linux installation, simply mount the **ISO file** in your VM. Refer to my **Ubuntu installation guide** in the Linux repository for more details.

## 💭 My Thoughts - From My Experience!
- **Windows 11 vs. Windows 10:** Although many people dislike Windows 11, I recommend upgrading since **Windows 10 support will end in October 2025** (no more security updates or Microsoft support).
- **Personal Experience:** After upgrading my **Surface Pro 7** to Windows 11, I initially experienced freezing and performance issues. However, after continuous updates, the system has improved, and I decided to stick with Windows 11.
- **Upgrade Process:** Upgrading from Windows 10 to 11 is **extremely easy**—just click **"Download and Install"** in Windows Update. If you don’t like Windows 11, Microsoft allows you to **roll back to Windows 10 within 10 days** by clicking a simple button.
- **Why This Guide?** I created this guide after being tasked at work with upgrading a **Windows 7 machine to Windows 10**. Fortunately, my coworkers provided a **USB with a Windows 10 ISO file**, but if you don’t have access to a pre-made USB, you’ll need to create one yourself—**this guide will walk you through the process!**
- **Let’s do this! 🚀** If you're ready to upgrade, follow the steps and enjoy a smooth installation process!
  
# Method 1: USB Flash Drive 
## Step 1: 
- Download the media creation tool.
Link: https://www.microsoft.com/en-us/software-download/windows10
## Step 2
- Install
  
![Win](/Images/pic0.png)
![Win](/Images/pic1.png)
![Win](/Images/pic2.png)
![Win](/Images/pic3.png)
![Win](/Images/pic4.png)
![Win](/Images/pic5.png)
![Win](/Images/pic6.png)

- What's in your USB after the installation?

![Win](/Images/pic1.1.png)

## Step 3: Upgrade Win 10 in a computer
1. Restart and Enter Setup:
   
Restart your computer.

During startup, press the key to enter BIOS/UEFI setup (often Delete, F2, F12, or Esc). Look for a message on the boot screen indicating the key.

3. Boot from USB Drive:

In BIOS/UEFI setup, change the boot order to prioritize your USB flash drive.

3. Install Windows 10:

Follow the on-screen prompts to choose language, time zone, and keyboard settings.

Enter your product key.

Choose "Custom" installation for a clean install. Delete all partitions except for "Drive 0 Unallocated Space" and format the drive if needed.

The installation process will begin.

4. Set Up Your PC

# Method 2: Using ISO file, but putting the file in a USB instead of a DVD :dvd: by using Rufus.

What is ISO file? An ISO file is a digital archive/copy of a CD, DVD, or Blu-ray disc = contents inside a CD, DVD, Blu-ray disc. It's a single file that stores everything on the disc, making it handy for things like installing programs or backing up data.

# Step 1
- Download and install Rufus. Rufus is a tool used to create bootable USB drives easily.
Link: https://rufus.ie/en/

# Step 2
- Download the media creation tool. Choose option "ISO file" instead of USB flash drive 
![Win](/Images/pic8.png)

- When you see the "Burn the ISO file to a DVD", just press "finish" because we will put the file in the USB. No need to choose "Open DVD burner".

![Win](/Images/pic9.png)

- Then, you will see this file in your chosen folder.
  
![Win](/Images/pic10.png)

# Step 3

- Select the file in Rufus. Then, choose your preferable options and "Start" the process. Make sure that your usb is empty or Rufus will delete all your data in there anyways.
  
![Win](/Images/pic11.png)

![Win](/Images/pic12.png)

![Win](/Images/pic7.png)

- Then, it should be ready!

![Win](/Images/pic13.png)


# Step 4
After finishing step 3, you should check your usb, the result should be the same as method 1. 

![Win](/Images/pic14.png)

# Step 5
Repeat Step 3 and Step 4 in method 1.

# Note: You can set up the Win on your computer without internet to speed up the process without updating extra stuffs.

