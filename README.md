 # T500-RPI-KlipperScreen
Tired of the TouchPad for the t500, here we will build our own




## Things to BUY
  * Raspberry PI 4B 4GB RAM https://chicagodist.com/products/raspberry-pi-4-model-b-4gb
  * SD Card https://chicagodist.com/products/raspberry-pi-official-noobs-microsd-card?variant=40342062268495
  * SD Card Reader (If your Laptop or COmputer Doesnt Have one)
  * 7" Touch Screen https://www.amazon.com/dp/B0B2QW89DR?ref_=ppx_hzsearch_conn_dt_b_fed_asin_title_2
  * 24v > 5V BUCK Power Adapter https://www.amazon.com/dp/B0CRVW7N2J 
  * HDMI Cord https://www.amazon.com/dp/B0CCKXH13W
  * USBA-USBC Cord https://www.amazon.com/dp/B0BGYWHG3L
  * USBA-USB Micro Cord https://www.amazon.com/dp/B0BHNVLW1Z
  * USB-C Extension https://www.amazon.com/dp/B0DKHPS1L3
  * M3 and M4 Heat Inserts
  * **Optional**  Power SUpply https://www.amazon.com/dp/B0BMGJNSVS (This just makes it easier to power your Pi and do your configurations not attached to your printer)
  * m3 bolts
  * m4x6 bolts
  * Screws https://www.amazon.com/dp/B078ZVQ7XM (Mounts the LCD Screen to case)


## Software to Download
  * Raspberry Pi Imager https://www.raspberrypi.com/software/
  * Putty https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html

## Things to Print
  Located in https://github.com/jranger615/T500-RPI-KlipperScreen/tree/main/stl
  * LCD CASE
  * LCD BACK
  * RPI TOP
  * Vertical or Horizonal Mount 

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

## Assemble the LCD Device
 * 



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
 * 




 


   


