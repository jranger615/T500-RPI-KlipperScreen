# T500-RPI-KlipperScreen
Tired of the TouchPad for the t500, here we will build our own




*** Things to BUY
  * Raspberry PI 4B 4GB RAM https://chicagodist.com/products/raspberry-pi-4-model-b-4gb
  * SD Card https://chicagodist.com/products/raspberry-pi-official-noobs-microsd-card?variant=40342062268495
  * SD Card Reader (If your Laptop or COmputer Doesnt Have one)
  * 7" Touch Screen https://www.amazon.com/dp/B0B2QW89DR?ref_=ppx_hzsearch_conn_dt_b_fed_asin_title_2
  * 24v > 5V BUCK Power Adapter https://www.amazon.com/dp/B0CRVW7N2J 
  * HDMI Cord https://www.amazon.com/dp/B0CCKXH13W
  * USB Cord https://www.amazon.com/dp/B0BGYWHG3L
  * M3 and M4 Heat Inserts


***Software to Download
  * Raspberry Pi Imager https://www.raspberrypi.com/software/

***Things to Print
  *LCD CASE
  *LCD BACK
  *RPI BACK
  *Vertical or Horizonal Mount 

  ***Install Mainsail on SD CARD
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

  * 
    

  * Here, we recommend setting the hostname value to something you can recognize (we’ll use “printer.local” for the rest of this guide) and that won’t conflict with other Raspberry Pi on your network. Also, enable SSH using a password authenticator. Set a username and password, with the user being “pi”. If desired, set the Wi-Fi connection settings as well. Finally, click “Save”, and then you can press “Write” in the main window. Wait until the process is complete before pulling out the SD card.
Insert the SD card into your Raspberry Pi and power it on.
