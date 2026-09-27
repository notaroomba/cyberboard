<!--
  Exported from Hack Club Blueprint on 2026-09-27.
  Source: https://blueprint.hackclub.com/projects/491
-->

## 10/13/2025 - Chip Selection and Schematic Start  

_Time spent: 5.0h_  

First I'm starting to define the functionality of the board. I want it to be the size of a Raspberry Pi Pico, and I want it to have Bluetooth support as well as headers for the STM32. I also want a JST connector to charge a 1S LiPo Battery for portability so I need a battery charging IC.

Chip Selection:

- STM32WB55CG
- TPS630701RNMR (Buck-Boost Converter)
- BQ24074 (Battery Charger)

Extras:

- SPI LEDs
- USB LEDs
- Battery JST Connector
- USB-C
- Ceramic Bluetooth Antenna

![image.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjE0NiwicHVyIjoiYmxvYl9pZCJ9fQ==--56d85a1a33d10cf902e22c7f6eaffa15ef3ebc50/image.png)
  

## 10/15/2025 1 AM - Finish Schematic and PCB Routing  

_Time spent: 9.0h_  

I started looking through all of the datasheets of all of the parts that I used to get the reference designs for each of the chips and then started wiring up each component.

I then ended up with this:
![image.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjI5MCwicHVyIjoiYmxvYl9pZCJ9fQ==--7e9fd5016f1598f53da14cb4da7e65df2c8ae757/image.png)

I still have to wire out the headers but I'm planning on doing that last after I have all the passive components in place.

![image.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjI5MSwicHVyIjoiYmxvYl9pZCJ9fQ==--5c71dd018c46b06d1b4ad477c20f0dac9140fc65/image.png)
  

## 10/15/2025 11 PM - Layout and Finish Board  

_Time spent: 12.0h_  

I decided to finish the layout and during, I wanted to add an LED and also the debugging pins as test points on the bottom of the board.

![image.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjQzMiwicHVyIjoiYmxvYl9pZCJ9fQ==--112dd087281849b4809601a72c1e95b8259416ca/image.png)

I then started routing all of the GPIO's first, then the clocks and then the power stuff. I used .2mm traces for everything that wasn't power and .4mm traces for power.

![image.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjQzMywicHVyIjoiYmxvYl9pZCJ9fQ==--6b26a75ae867de93401ac9a273f6dccc0e82a911/image.png)

I also had to impedance match the antenna so basing it off this datasheet:
![image.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjQzNCwicHVyIjoiYmxvYl9pZCJ9fQ==--6fe7802ff5522970416dfaf0142bda1fe8ab5947/image.png)

I then added the traces and also put stitching vias on the side. I also added the keepout zone and made sure that the ground plane on either side had the right clearance.

![image.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjQzNSwicHVyIjoiYmxvYl9pZCJ9fQ==--ed4a1f11a4b77efb12c7438e27f2d53b7a86344c/image.png)

After that I finished adding the ground pours and ran DRC to fix the remaining errors and finally got this.

![image.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjQzNiwicHVyIjoiYmxvYl9pZCJ9fQ==--5393cd550d684cd08f26d7520e67cb55009b96d1/image.png)

After finishing the board I decided to do some renders in Blender and here are the photos.

![CyberboardLight.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjQzOSwicHVyIjoiYmxvYl9pZCJ9fQ==--0e40f0e3e02df0d3623e49b6a048985105e0a88f/CyberboardLight.png)
![Cyberboard2.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjQzNywicHVyIjoiYmxvYl9pZCJ9fQ==--0f7bcd34039d5855103f026234150fb0eac1fa59/Cyberboard2.png)
![Cyberboard.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjQzOCwicHVyIjoiYmxvYl9pZCJ9fQ==--61a0edd693f86a98079fe7fba625afcbb7b25a9d/Cyberboard.png)





  

## 10/16/2025 - Resized Keep-out zone  

_Time spent: 0.8h_  

I decided to resize the keep-out zone after some advice from my informatics teacher and looking online at the datasheet. It originally says to have a 6.5mm space but I don't have that much space horizontally as I do vertically so the most I could do was 4.3mm.

Before: 

![WhatsApp Image 2025-10-15 at 16.54.22_8be48b74.jpg](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjQ4MSwicHVyIjoiYmxvYl9pZCJ9fQ==--afbc8d7c5427cae3a0aa33655753bee44c9e9f0e/WhatsApp%20Image%202025-10-15%20at%2016.54.22_8be48b74.jpg)

After:

![image.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjQ4MywicHVyIjoiYmxvYl9pZCJ9fQ==--a7190d1decd4297d3a22a325258b947dfc716853/image.png)
  

## 10/17/2025 - Rerouted PCB on single side to save costs  

_Time spent: 6.0h_  

![Banner.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjU4OSwicHVyIjoiYmxvYl9pZCJ9fQ==--9c4125c5295b92dd5bb4bd266fb80045ed278b0c/Banner.png)

I had to reroute everything as the board was too expensive for double sided PCBA. So I decided to reduce the sizes down to 0201 for some components like the decoupling capacitors to try and save space and it worked. I then had enough space to move the battery charging IC to the other layer and I had to remove the JST connector and replaced it with 2 exposed pads on the bottom.

![image.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjU4NSwicHVyIjoiYmxvYl9pZCJ9fQ==--7ac980313a5dce8e76b065ca021ac27b7e3485aa/image.png)
![image.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjU4NiwicHVyIjoiYmxvYl9pZCJ9fQ==--afe0d03d1c7978641ad84def1e3fef29902351e9/image.png)
![image.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjU4NywicHVyIjoiYmxvYl9pZCJ9fQ==--0ea09bfaf6cad50952fa2eacc917f46d81d1a35e/image.png)
![image.png](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MjU4OCwicHVyIjoiYmxvYl9pZCJ9fQ==--d1de2e4e4c3c83d7c9e55a62eb6446f19a0313bc/image.png)  

## 11/15/2025 - Tried fixing the PCB  

_Time spent: 14.0h_  

After receiving my board I rushed to plug it in but then it wouldn't connect and turned super hot. Later that day I sent it in the KiCad discord and turns out that everything was supposedly fine. A few days later after letting my intrusive thoughts win and letting the board heat up, I revised the schematics again and noticed there's a few errors. First of all I believe that I messed up the ground plane and literally encased the STM32 in 3V3 ring:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTEyOTMsInB1ciI6ImJsb2JfaWQifX0=--5a9e5fb2c4bfa8832e220a2bb94c180f583f9212/image.png)

Then there's the other error of me not using the right decoupling capacitor values which should be 4.7uF.

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTEyOTQsInB1ciI6ImJsb2JfaWQifX0=--5c22da5b9507587a096655bcdb2983865e3fae85/image.png)

Finally another error that completely hinders me from fixing the board is that those components are 0201 and are small and also expensive to manufacture (sorry I've learned my lesson)

![WhatsApp Image 2025-11-15 at 00.44.59_852fff6f](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTEyOTUsInB1ciI6ImJsb2JfaWQifX0=--3dbaae4e562be2025d9ce564f8aee4b2699e40e5/WhatsApp%20Image%202025-11-15%20at%2000.44.59_852fff6f.jpg)

I spent the entire day trying to learn how to solder 0201 as I was trying to see if I could connect a capacitor that I took from an old wifi router to the board. I tried doing this by soldering a thin copper wire (taken from a jumper cable) to the end of a capacitor and then that capacitor to ground:

![WhatsApp Image 2025-11-15 at 00.44.59_0f044e43](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTEyOTYsInB1ciI6ImJsb2JfaWQifX0=--62d72e69163b0ca208331aa18cf4e3e7ca72a515/WhatsApp%20Image%202025-11-15%20at%2000.44.59_0f044e43.jpg)

![WhatsApp Image 2025-11-15 at 00.44.59_217dc7c0](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTEyOTcsInB1ciI6ImJsb2JfaWQifX0=--26380f3dcfe5e912714b989e970f3205975c8d0b/WhatsApp%20Image%202025-11-15%20at%2000.44.59_217dc7c0.jpg)

Although my soldering iron kept burning the flux and I had to use nail polish remover to try and clean it because I don't have isopropyl alcohol.

![WhatsApp Image 2025-11-15 at 01.02.20_5e53268a](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTEyOTksInB1ciI6ImJsb2JfaWQifX0=--9bc08252eb05f44bab18c5509172a8d7b1b00cf7/WhatsApp%20Image%202025-11-15%20at%2001.02.20_5e53268a.jpg)

After talking with @Kai Pereira, I realized that I had a lot to improve in terms of cost and component selection and that's my goal for V2, to make it as cheap as possible < 50 USD, and maybe include more features.

All this I plan to do after I finish my heatplate as I want to be able to solder everything by hand.


  

## 12/1/2025 - Banner Image  

_Time spent: 0.1h_  

Finally fixed the bug so heres a temp journal to add in the banner so that it looks cool on the blueprint website aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa

![Banner](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTcwODUsInB1ciI6ImJsb2JfaWQifX0=--941d8daf9eb96212c1932df38f1e8cce213fcc56/Banner.png)
  

