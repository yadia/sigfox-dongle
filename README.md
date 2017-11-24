# Easy set up of Sigfox Dongle
Instruction on how to use the Sigfox SDR Dongle on a VM. You can run this VM on an MAC OS or Windows OS laptop.

This tutorial consists of the following sections:
* Intro to SDR Dongle
* Setting up the VM
* Using the Radio Signal Analyzer Software
* Using the Sigfox Network Emulator Software

## SDR Dongle Charateristics
   |    | 
------------ | -------------
Operating frequency | 865-870 MHz, 902-928 MHz software configurable
Monitored spectrum| 192kHz
Receiver Sensitivity | -64dBm @ 100bps
Transmit Power | 14dBm

The SDR dongle kit comes with a 40 dB attenuator provided which should be used for class 0U device.

### Software 
* Radio Signal Analyzer
* Sigfox Network Emulator


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
Radio Signal Analyzer is a user-friendly software to analyse in real time Sigfox’ signals.

### Requirements
* Sigfox Dongle 2 *If I am not mistaken only this version can work with the RSA software*
* VM running the Sigfox Radio Analyser ISO

### 1.Check if the SDR Dongle is detected
Check on Ubuntu Mate's Settings if your dongle is detected. The name of it is  **SIGFOX NED** .
If it is not detected try pluging and unplugging (depending on your computer this may take a few tries).

### 2. Open RSA Software and set Device Static Configuration
Click on the RSA application and acept the Licence Agreement. Next, click in the "Device Configuration"

   * Modem Type --> This depends on your Sigfox Modem  most Modem have Uplink and Downlink capabilities. *Kindly consult with your device's Sifox Modem datasheet*
   * Device ID. --> The ID of the device you are testing. (Currently RSA supports only one device at a time)
   * Key Selection ---> Check if your device is configured in Public Key or Private Key. *If you have previously done SNE your device might be in private key*
   * Device Private Key ----> Only required if enter if you have set it up ortherwise leave it as it is
   * Radio Configuration ---> Depends on your device pick from RC1, RC2, RC3a, RC4
   
Radio Configuration Zone | Frequency |  EIRP  | Countries
 ------------ | ------------- | ------------- | -------------
1 | 868-878 MHz |  16dBm | Europe, Middle East
2 | 902.1375-904.665 MHz | 24dBm |USA, Mexico, and Brazil
3a | 920.5-929.7 MHs | 16dBm | Japan Only
4| 920.1385-922.66251 MHz | 24dBm | South america, South East Asia, HK, NZ, TW

Once you have set up those parameters you are ready to start device calibration

### 3. Device Calibration
This allows you to evaluate your device's power emission. The best conditions the power band should be green (-40 and -15 dBFs)
![RSA1](https://github.com/yadia/sigfox-dongle/blob/master/RSA/rsa_1.png)


### 4. Sigfox Verified Tests
You can run different test modes to evaulate your device. However, you can only run one test mode at a time.
Available test modes
    Test Mode   |  Mode Number |   Covers  | Notes |
   ------------ | ------------- | ------------- | ------------- |
   TX-BSPK  | Mode 0  | Normal, minimum, and maximum voltage. Spectrum measurement, Datarate measurement, Dynamic Drift measurement, Phase measurement, Envelope measurement, Static Drift measurement, Power measurement. | **For UPLINK RF**
   TX-PROTOCOL | Mode 1 | Uplink Protocol, Timings, Frequency Distribution  | **UPLINK Protocol is tested on all type frames Bit, 1-12Byte, Out of Band**
   RX-PROTOCOL | Mode 2 |Downlink Protocol, Timings, GFSK Response. | **DOWNLINK Protocol **
   RX-GFSK | Mode 3 | GFSK demodulation, approximate sensitivity
   RX-SENSITIVITY | Mode 4 | Device Sensitivity with Sigfox Protocol.| ** Can't be tested with SDR Dongle** 
   TX-SYNTH | Mode 5 | Device Synthesis Step | N/A
   
### 5. Veredicts
Depending on the test mode run the Veredicts window will tell you whether the item is NOT TESTED, PASSED or FAILED.
You can export this results and save it as images in the folder you select.


## Sigfox Network Emulation
Ever needed to test a device, but found yourself with no Sigfox Network? Fear not, the SNE is exactly what you need to test your device.

Supported browsers:
- Chrome
- Firefox
- Edge

### Requirements 
1. Create a VM running on the latest [Ubuntu](https://www.ubuntu.com/download/desktop) 
2. Start up your VM and download the Sigfox Network Emulator for Ubuntu Linux software at (support.sigfox.com/products/SDR-dongle) using your browser.
3. In Home > Download   you will find the SNE software labeled as " snek.deb". Double click it to get the instalation process started.

4. Ubuntu software will ask for confirmation on the instalation.

5. Once installed, you can find the software in your Applications > *Sigfox Network Emulator"

6. Connect the SDR dongle and  open the application and if the SDR dongle is detected the application will open in your broweser (seen below ).

If the SDR dongle is not connected or detected, you will get the following error:


## Using the SNE
####Emulation Configuration
The SNE has 3 menus which can be configured:
1. The radio zone to emulate -> RC1,2,3,4,5
2. The declared devices : devices the that will connect with the SDR
3. The callbacks triggered on message reception or network events.

### Radio configuration ###
Set up the desired values for Uplunk bit rate, Uplink and Downlink frequences. 
You can refer to the table (#)

### Device Registration Page
You can add up to 5 devices to the SNE. The <NAME> field is optional but convenient for identifying your devices. The device ID is the Hexadecimal characters which identify the Sigfox Module. It can be enter in lowercase or uppercase.

**Important**
*Only devices registered in this page will be able to transmit their packets to the network emulator, all other devices will be ignored*
If you want to authenticate your device's messages then the device must be running in "emulator mode"/"public key".

**Warning**: If authentication is disabled, messages from declared devices will be
displayed on the network emulator and callbacks will be activated, but, in case of
bidirectional transactions, the device under test will not be able to authenticate the
downlink message sent by the emulator.


### Messages 
The messages will be displayed in the "Message page". They are listed from newest to oldest. There is  a maximum capacity for 100 mesages, oldest messages get delted when the limit is reached.




