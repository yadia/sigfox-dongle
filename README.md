# Easy set up of Sigfox Dongle
Instruction on how to use the Sigfox SDR Dongle on a VM. You can run this VM on an MAC OS or Windows OS laptop.

## Setting up the VM
1. Download [Oracle VM VirtualBox](https://www.virtualbox.org)

2. Once downloaded creat a virtual machine with type Linux and version Ubuntu 64-bit.
   Add around 1024 MB for memory size.
![VM Setup](https://github.com/yadia/sigfox-dongle/blob/master/RSA/img_1.png)

3. In the hard disk part select "Create a virtual har disk now". 
![VM Setup3](https://github.com/yadia/sigfox-dongle/blob/master/RSA/img_2.png)

4. Select VDI for hard disk type, as it will be stored within out system.
![VM Setup4](https://github.com/yadia/sigfox-dongle/blob/master/RSA/img_3.png)

5. Select fixed sized for the hard disk. This way in case you need to deleted anything it will take less time.
*You may pick dynamically allocated if you want. It will not affect the performance of the VM*
![VM Setu5](https://github.com/yadia/sigfox-dongle/blob/master/RSA/img_4.png)

6. File location and size, provide the VM the desired virtual hardisk size.
for RSA software you need at least 5GB for running the dongle in SNEK (Sigfox Network Emulator Kit) go for 10 GB. 
*The Network Emulator Kit require more space as it will be running a virtual image of Ubuntu.*
![VM Setu6](https://github.com/yadia/sigfox-dongle/blob/master/RSA/img_5.png)

7. Once all the steps are completed you will have your virtual box ready to use.
Click on your virtual machine name and select what image you would like for it to read from (for RSA select the location of where you download the Sigfox Dongle [RSA software](https://build.sigfox.com/sdr-dongle#compatibility)
![VM Setu7](https://github.com/yadia/sigfox-dongle/blob/master/RSA/vm_setup.png)

8. If you are succesfuly running the RSA software (Sigfox Radio Signal Analyzer) you will see the image bellow:
![VM Setu8](https://github.com/yadia/sigfox-dongle/blob/master/RSA/iso.png)

## Running the Radio Signal Analyzer

### Requirements
* Sigfox Dongle 2 *If I am not mistaken only this version can work with the RSA software*
* VM running the Sigfox Radio Analyser ISO

### 1. Open RSA Software
*Check on Ubuntu Mate's Settings if your dongle is detected. The name of it is*  **SIGFOX NED** 


