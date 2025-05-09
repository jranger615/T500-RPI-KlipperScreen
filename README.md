 # T500-RPI-KlipperScreen
Tired of the TouchPad for the t500, here we will build our own
This Klipper screen should work for other klipper machines but may require other conifguration changes and a new mount

![mail google](https://github.com/user-attachments/assets/79d49e21-df40-43d1-9392-eec835ce35d7)




> [!IMPORTANT]
>### RPI5 Version
> * Added RPI5 version of STLs.
> * It however may require different usb/pwr wires/buck converter.
> * Uses official RPI5 FAN

> ### If you wish to tip and help continue my work on mods please use:
>* Paypal: Jeff.b.ranger@gmail.com
>* Venmo: @Jeff-Ranger-1



## Things to BUY
  * Raspberry PI 4B 4GB RAM https://chicagodist.com/products/raspberry-pi-4-model-b-4gb  (I will remodel this for RPi5 as well)
  * SD Card https://chicagodist.com/products/raspberry-pi-official-noobs-microsd-card?variant=40342062268495
  * SD Card Reader (If your Laptop or COmputer Doesnt Have one)
  * 7" Touch Screen https://www.amazon.com/dp/B0B2QW89DR?ref_=ppx_hzsearch_conn_dt_b_fed_asin_title_2
  * 24v > 5V BUCK Power Adapter https://www.amazon.com/dp/B0CRVW7N2J 
  * HDMI Cord https://www.amazon.com/dp/B0CCKXH13W
  * USBA-USBC Cord https://www.amazon.com/dp/B0BRQY1FLG
  * USBA-USB Micro Cord https://www.amazon.com/dp/B0BHNVLW1Z
  * USB-C Extension https://www.amazon.com/dp/B0DKHPS1L3
  * M3 and M4 Heat Inserts
  * **Optional**  Power Supply https://www.amazon.com/dp/B0BMGJNSVS (This just makes it easier to power your Pi and do your configurations not attached to your printer)
  * m3 bolts
  * m4x6 bolts (Attatchment to Printer)
  * Screws https://www.amazon.com/dp/B078ZVQ7XM (Mounts the LCD Screen to case)
  * RPI4 Fan https://www.amazon.com/dp/B091L1XKL6


## Software to Download
  * Raspberry Pi Imager https://www.raspberrypi.com/software/
  * Putty https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html

## Things to Print
Located: https://github.com/jranger615/T500-RPI-KlipperScreen/tree/main/stl
  * LCD_FRONT.stl
  * RPI4_LCD_BACK.stl
  * RPI4-TOP.stl
  * Vertical-LCD-Mount.stl or Horizon-LCD-Mount.stl
    
 ![image](https://github.com/user-attachments/assets/480fdf53-5f8e-4c9c-993d-95e3de02b68e)


## Install Mainsail on SD CARD
  * First, take the MicroSD you’ll use for your Raspberry Pi and connect it to your computer. 
  * $Download and install the Pi Imager tool and launch it.
  * Click Choose Device, and select Raspberry PI 4
  * Click “Choose OS”, scroll down to “Other specific-purpose OS”, choose “3D printing”, and then select Mainsail OS.
  * Choose Storage, and make sure to select the SD card.
  * Click Next
  * Click Edit Setting
    
    ![image](https://github.com/user-attachments/assets/f59d0560-0c07-4107-8b2e-08a6b104cc03)
  * Set a Host name of your choice
  * set MKS as the user  (***This is important so we dont have to edit many configs on the t500)
    
    ![image](https://github.com/user-attachments/assets/cd456ae6-c1b2-49e8-939e-fece0c0c93ed)
  * Set makerbase as the password
  * Enable and SET your WIFI Settings
  * Click Save
  * Click Yes
  * Click Yes to write to SD Card
  * Once Complete put the SD Card in your Raspberry PI


## Install Kiauh
 * Attach your Raspberry PI to the power cord and turn it on
 * Open Putty.exe and add host name you used in the Mainsial install  EX: mkspiB.local  (May need to attach network cord if wifi doesnt work after a couple minutes)
   
 ![image](https://github.com/user-attachments/assets/6cca23de-22d2-457e-92bb-478fb9638cb3)
 * Click Open
 * Click Accept
  
  ![image](https://github.com/user-attachments/assets/664f3b0c-ea94-425e-92ca-70f4fc7a1aee)

 * Enter user: MKS 
 * Click enter
 * Enter password: makerbase
 * Click Enter
 * Type: sudo apt-get update && sudo apt-get install git -y
 * click enter
 * Enter password: makerbase
 * Click enter
 * type: cd ~ && git clone https://github.com/dw-0/kiauh.git
 * click enter
 * type: ./kiauh/kiauh.sh
 * click enter
 
 ![image](https://github.com/user-attachments/assets/7f48f7c9-8262-43e3-a071-174bd17cc7c9)
 * type: 1 and click enter
 * type: 1 and click enter to install
 * type 7 and click enter
   
  ![image](https://github.com/user-attachments/assets/fdeb06e4-3a3c-41ca-82fb-3e0a1524ce27)

 * When Prompted "Press enter for default (Yes) [Y/n]" Click Enter
 * When Prompted "Press enter for default (Xserver) Backend Xserver or Wayland (cage)? x/w" Click Enter  (This will take awhile to complete)
 * When Prompted "Install NetworkMangher for the network panel [Y/n]" Type Y
 * Click enter


 ## Install Kamp 
  If you are not currently using KAMP you can skip this step 

 * Reconnect to putty like above
 * Browse to https://github.com/kyleisah/Klipper-Adaptive-Meshing-Purging and follow the installation commands


## Fix Wifi Configurations (This is only needed if all WIFI options arent showing up)
When you first set up a Raspberry Pi, sometimes you'll need to manually set the timezone/location to allow you to make a WiFi connection (even though the initial setup screens appear to set this for you). 
* Putty into your device
* type: sudo raspi-config
  
 ![image](https://github.com/user-attachments/assets/05004e32-d1ab-4b4f-a787-ec6f7d8db1bf)
* Select Localization Options again and Selec WLAN Country
* Set TimeZone
* Select Localization Options again and Selec WLAN Country
* Press the Right Direction button and Click Finish
* type: Sudo reboot
* Click Enter
May Also Require Disabling Network Manager and Re-Enabling it in Advanced Options

## Horizonal Orientation Configs
 * Putty into device as before
 * type: sudo nano /boot/config.txt
 * Add the below...Some can be uncommented in other sections but you can add this to the bottom.
  ```ruby
framebuffer_width=1024
framebuffer_height=600
hdmi_force_hotplug=1
hdmi_cvt=1024 600 60 3 0 0 0
hdmi_group=2
hdmi_mode=87
 ```
* Ctrl+X to save
* Type Y to save
  
## For Vertical orientation ONLY 
 Note: This orientation appears a bit stretched to me
 * Putty into device as before
 * type: sudo nano /boot/config.txt
 * find "dtoverlay=vc4-fkms-v3d" and comment it out by putting a # in front of it (This is RPI4 SPecific)
 * Goto the end of the file 
 * add: display_rotate=3
 * Ctrl-X to exit
 * Y to Save
 * type: cd /usr/share/X11/xorg.conf.d/
 * type: sudo nano 40-libinput.conf
 * find one that has a section that has "Identifier ... touchscreen catchall".
 * Add: Option "TransformationMatrix" "0 -1 1 1 0 0 0 0 1"
 * Ctrl-X to exit
 * Y to Save


## Backup Klipper Configs
 * Open your browser and goto your current IP or name for your t500
 * Click the Machine Tab on the Left
 * Click the Check box for your config files and then click download (More files may apply depending on your configuration)
 * Stock Files:
  ```ruby
   printer.cfg
   plr.cfg
   moonracker.cfg
   fluidd.cfg
  ```
 * They will be download as a zip so you will have to extract them before uploading them later 


## Update Klipper
 * open your browser and goto your host name EX: mkspiB.local
 * Click the machine tab in Klipper
 * On the right side File Manager, Click Update on all the sections. (I prefer to do one at a time over the Update All Function at the bottom)
  ![image](https://github.com/user-attachments/assets/a1cea5a1-014b-456b-a263-60ca90ff440d)
 * This may disconnect and require you to refresh your browser to get back in
 * Click the upload button in the config files section and upload all your files you backedup from Klipper
   
   ![image](https://github.com/user-attachments/assets/6beb0823-5ee8-47f6-a8dc-015c385ddfc6)
 * open printer.cfg
 * comment out the following:
```ruby
#[mcu rpi]
#serial: /tmp/klipper_host_mcu

#[adxl345]
#cs_pin: rpi:None
#spi_bus: spidev0.0

#[resonance_tester]
#accel_chip: adxl345
#probe_points:230, 230, 20  # an example
#accel_per_hz:50
#min_freq:1
##max_smoothing:0.2
#hz_per_sec:0.5
```
* Commet out max_accel_to decel replace
```ruby
#max_accel_to_decel: 1500 
minimum_cruise_ratio: .5
```


## Assemble the LCD Device
 * Add 4 - M3x4 Heater inserts into the LCD Case

  ![image](https://github.com/user-attachments/assets/5ede8c89-a91d-4ca6-978f-2eaeed7d19bc)
 * Insert the LCD into the Front Case and Attach the 4 small screws in each corner to hold in firmly in place
 * Add 6 - M3x4 Heater inserts into the RPI4 LCD Case Back. 

  ![image](https://github.com/user-attachments/assets/0f5a40a9-b023-4ef4-b964-5b85a3afd00f)
 * Take your RPI4 and insert it to the RPI4 TOP.
 * Install RPI4 Fan per instructions included
 * Place the TOP on the LCD Backing plateon RPI4
 * Insert 4 m3x12 bolts in the 4 corners to hold them in place
 * Attach the back to the LCD front and install 4-m3x6 bolts to attach all together
 * Install 3 - m4x6 into the Mounting Bracket
 * Install the mounting bracket onto the backing plate using 4 - m3x6 bolts
 * Attach all the wires from the RPI4 to the LCD
 * HDMI to HDMI Micro
 * USB-A to USB-C (Closest to the HDMI enabled the touch screen)
 * Make sure the on switch is on, this is easy to see through the large hole in the mesh backing


## Remove Touch PAD
 * Remove the Power Cord from the Tablet
 * Remove the USB Cord from the Tablet
 * Remove the 3 Allen Screws from the back of the Touch Pad
 * Push the bed to the back
 * Remove the 4 Screws from the t500 Cover
 * Pull the bed forward
 * Remove the back 3 screws
 * Push the bed back again
 * Pull the cover off the t500
 * Remove the USB and Power Cord

   ![image](https://github.com/user-attachments/assets/c4e7aa67-8965-4485-9f60-0e9561f8c26b)
 * Cut the zip tie holding the wires in place and remove the wires from your t500 
 * Cut the END off the Power Cord and Solder the wires to your Buck Connector.
 * Plug the Buck Connector into the board and run the wires to out towards the LCD Mount (You may want to use self tap screws or double sided tape to mount the buck connector)
 * Attach the USB-C Extension to the power cord
 * Run the USB-C wire to USB-A wire from the board out towards the Touch PAD


## Attach new RPI Touch screen
 * Attach the New LCD to the Mounting bracket using 3 - m4-6 screws
 * Attach the USB C power cord
 * Attach the USB C to USB A to the PI
 * Power on printer and make sure everything attaches
 * Re-Install the t500 top plate with the 6 screws
 * ENJOY




 


   


