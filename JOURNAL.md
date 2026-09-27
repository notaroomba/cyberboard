<!--
  Exported from Hack Club Blueprint on 2026-09-27.
  Source: https://blueprint.hackclub.com/projects/2195
  V1 source: https://blueprint.hackclub.com/projects/491
-->

# Cyberboard V1

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

# Cyberboard V2

## 11/28/2025 - Fixed Schematic and Add Sensors  

_Time spent: 6.0h_  

So after the first iteration of the Cyberboard, there were a lot of issues, mainly me being stupid and not using the right values but also in the design of the PCB (not using 4 layers) so in this version I am going to fix that and upgrade it by adding an IMU/Barometer to make it the ultimate devboard for small projects!

Ah and I also plan on hand soldering it / reflow it using my custom hotplate (lol making tools to make tools) so it will be way cheaper and make up for my past mistakes.

I will be adding on the ICM-42688 and BMP580 and also I was thinking about reducing the size of the buck-boost converter as it was one of the biggest contributors to price/complexity on the board. So like any good engineer, I went on LCSC and searched for the most used DC DC converter to implement and found TPS631000 and it's perfect looking at the application implementation:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUxNDEsInB1ciI6ImJsb2JfaWQifX0=--b0fa0ebded6ffdd10a3fd0899f6f457d492f2cb7/image.png)

I think with this I can rewire the board completely and add in more functionality. So I thought about what other cool functionality and I decided on adding in a current sensor for the battery

 ![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUxNDMsInB1ciI6ImJsb2JfaWQifX0=--b4a511edd6004db9aba7949ed06dfd1286dffe36/image.png)

I also found a cheaper battery charging IC: BQ24072RGTR instead of the BQ24074RGT

The only thing they have differently is one pin that instead of ITERM it's TD:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUxNjEsInB1ciI6ImJsb2JfaWQifX0=--8ec58df8ee816c50f3fe19733c76d4bef6bf53f5/image.png)

AND IT'S WAY CHEAPER AND COSTS ONLY 0.8 USD INSTEAD OF 3 USD

AND IT's LITERALLY A DROP IN REPLACEMENT FOR THAT CHIP:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUxNjIsInB1ciI6ImJsb2JfaWQifX0=--f2face34fdeb268f8c1ef716fd9b9e77d1cd557a/image.png)

I just had to change the value for TD to a more standarized value but it should work the same as a pull down resistor:
![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUxOTcsInB1ciI6ImJsb2JfaWQifX0=--927cadef47eb2a087ae7249c741a0fdd9e08740d/image.png)

Reading through the datasheet I also saw that the example application was using a custom timer and to reduce cost even more I decided to use the default timer as that will suffice.

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUyMDUsInB1ciI6ImJsb2JfaWQifX0=--5f76a7b933da7922d9eac48e09d91c11bf0dacf3/image.png)


After I got the battery fixed I went on and fixed the decoupling capacitors for the STM32:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUyMDYsInB1ciI6ImJsb2JfaWQifX0=--ce8fa220837e32c4d3389376ea8b26809b103f1d/image.png)

After that I imported the new buck converter and looked at the datasheet:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUyMTEsInB1ciI6ImJsb2JfaWQifX0=--524059b9c29aa333ad10da1302530977c10a1e6e/image.png)

I had to import this inductor `DFE252012P-1R0M=P2` as it was specified in the datasheet:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUyMTMsInB1ciI6ImJsb2JfaWQifX0=--aaa8ec76d899ff0f7802f8069c748bfe5836de64/image.png)

After setting up the rest of the pins, I came up with this: 

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUyMTksInB1ciI6ImJsb2JfaWQifX0=--39028d8021e22523a3d8429432992d79f7dbe1d4/image.png)

Now it's time to set up the sensors that I'll be using (ICM-42688-PC and BMP580):

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUyMjUsInB1ciI6ImJsb2JfaWQifX0=--7eb23a58b397c7f1d4a56360fc977c7c4d218efd/image.png)

Thankfully I have enough pins free on my devboard, and you can't say that a devboard is a devboard if you aren't using all of the pins lol.

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUyMjYsInB1ciI6ImJsb2JfaWQifX0=--b606f0fef005ae7b2857611cec0d003083600722/image.png)

but before deciding on which communication interface I'm going to use, I'll have to edit the pins on STM32CubeMX:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUyMzYsInB1ciI6ImJsb2JfaWQifX0=--4d5aa59d803e2331e86585b5314be8558a99df41/image.png)

I originally had some EVENTOUT pins that labeled which pins weren't going to be used but this time, I am going to try and use all of them. In total I have 11 pins free to play around with, I plan on using LED's with the extra pins to at least have 3 status ones.  

## 11/30/2025 12:04 AM - PCB Layout and Routing  

_Time spent: 5.0h_  

I started the layout of the PCB and noticed a few errors in my schematic and fixed them (I2C lines strike again) and then had something like this:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTU5NzYsInB1ciI6ImJsb2JfaWQifX0=--88765b214df30fff1f27facecbc231806ef9ebc7/image.png)

I found out that I can compact the board alot and make room for the antenna as I plan to use the bottom layer mainly for the GPIO's as the top layer is kind of busy with all of the passive components.

I organized it a bit more and got this layout, but I wasn't satisfied with the way that there was a squareish hole off center so I redid it again

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTYwMDMsInB1ciI6ImJsb2JfaWQifX0=--b552d8295e25a45f441da30f320318c4005eb48d/image.png)
(before)

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTYwMTYsInB1ciI6ImJsb2JfaWQifX0=--9dbae78b173b0005665515d212be16253a4e5933/image.png)
(after)

And after that I didn't liked how it looked so I went back to the original and planned on putting a V2 in the squareish hole.

I then started routing up the design and also making minor changes here and there to not cover some silkscreen, I also enjoyed routing this section as I find that it looks cool the stripe effect:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTYwNzUsInB1ciI6ImJsb2JfaWQifX0=--fb9d8a25014b0040081b2a8cfcd7a4e85465cc04/image.png)
  

## 11/30/2025 12:27 AM - Pin Selection (BEFORE PREVIOUS JOURNAL)  

_Time spent: 4.0h_  

I started selecting the pins on STM3CubeMX and wanted to use I2C for the BMP580 and then SPI for the IMU. Another design requirement is that I wanted it as far away from the Bluetooth antenna as possible, which is why I decided on this pinout:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUzOTUsInB1ciI6ImJsb2JfaWQifX0=--7a6c8487e60e39353090c1ac80c7d52cad2e9025/image.png)

I might interchange the CS and interrupt pins as to better route it later but that's a good starting point. I then finished wiring the ICM:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUzOTYsInB1ciI6ImJsb2JfaWQifX0=--6847fde5bf5657c9e0c09da5fd3c867b05ff3c1e/image.png)

AND I REMEMBERED TO ADD PULL UP RESISTORS TO THE I2C LINES

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTUzOTksInB1ciI6ImJsb2JfaWQifX0=--3416f2259a59eb247b71c7c91b5728300530b0bb/image.png)

then I had to organize the schematic a bit as there wasn't any space for the new sensors lol

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTU0MDgsInB1ciI6ImJsb2JfaWQifX0=--0f32063afec01051f2e593528b450d78ca1986b1/image.png)

I then edited the footprints and made sure that all of them were at least 0402 (ptsd soldering 0201).


I forgot that I had this draft saved on one laptop so when I used another I pushed a journal from there and I forgot about these changes so aja, this journal comes before `PCB Layout and Routing`  

## 11/30/2025 2 AM - Finished Routing and Antenna  

_Time spent: 2.0h_  

I spent a bit of time finishing up the routing and also making sure that everything looks neat including the silkscreen:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTYyMzQsInB1ciI6ImJsb2JfaWQifX0=--a731d878d47edb8a278cfa9770b3f33d010700ac/image.png)


I somehow did it and managed to fit an IMU and Barometer in such a tiny 1 SIDED BOARD

I had fun routing the antenna as I had a crisis and thought I had my antenna for Ember wrong but I just recalculated the impedance badly

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTYyMzUsInB1ciI6ImJsb2JfaWQifX0=--76610fa6257903a2f3b7df826664ade13971dc6a/image.png)

It's a 4 layer board so SIG/GND/PWR/SIG and I had some stitching vias for 3v3:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTYyMzcsInB1ciI6ImJsb2JfaWQifX0=--a269de86bb98a22045eab9b58f08378680d2dbb9/image.png)

Aside from that I just finished routing and tmrw I'll start work on the renders and also getting feedback from the KiCad Discord.

  

## 11/30/2025 1 PM - Blender Render, Panelization, and LCSC  

_Time spent: 4.0h_  

After fixing some pins that were out of order due to routing, I started rendering the PCB in Blender based on the last file. 

![Banner](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTY0NDIsInB1ciI6ImJsb2JfaWQifX0=--0b2be51714e3598fedfcc99d4d58514309788f89/Banner.png)


![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTY0MDUsInB1ciI6ImJsb2JfaWQifX0=--bd799a2a8fdc73bca47d1bbd4727d5fdcb592414/image.png)

It looks a bit drab so I am going to add in more lights like in Trace and see if that helps out a bit.

Meanwhile, I decided to panelize the PCB because in V1, there was a lot of extra space that I could use to make more copies and not have to pay extra.

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTY0NDMsInB1ciI6ImJsb2JfaWQifX0=--a611d3e8a20deafb0567b2c71758b0a8f631e0ef/image.png)

After that I also exported the BOM and went to LCSC to check out how much it cost and it was surprisingly cheap at (taking advantage of the MOQ for most).

I also had to specify the stackup (which I kinda forgot to do for Ember but I sent an email requesting to change it). This also meant that I had to change the width of the traces and also the width of the board.

  

## 3/7/2026 - IT WORKS!!!  

_Time spent: 39.0h_  

ookay so its been a while since I've worked on this since getting a gap year so I finally finished it and it works!

basically I had all of the components and saw the stencil and it was a bit hard to get right

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTE3NTkyLCJwdXIiOiJibG9iX2lkIn19--920d49f2da39b3ec71757612801b3cd3a99e5ceb/image.png)

and then decided to try and hotplate it with Ember in a hotel lobby (actually)

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTE3NTkzLCJwdXIiOiJibG9iX2lkIn19--edbc52852cd9924b1705ea42f74e7e59d129042b/image.png)

and it worked kinda! although at first it turned on but didn't connect to my laptop so I was wondering why that was, but I hadn't had time to debug it until I stopped moving around.

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTE3NTk5LCJwdXIiOiJibG9iX2lkIn19--9e4558f329bc02418f72c1fd50b44131d1fa2569/image.png)

it was then until I finally got to HQ and found a lovely soldering station but I kinda wanted to make more PCB's to try and test them so I did a thing in my room and reflowed another one:

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTE3NjAxLCJwdXIiOiJibG9iX2lkIn19--8aef2cba4f69f32b122f824b4876d91004fea206/image.png)

but it faced the same problem that the usb wouldnt enumerate so I figured that it was a problem with the STM32

I wouldn't give up tho so I went to HQ and found that they had a wonderful hot air machine and hot plate so I tried reflowing the STM32 again to try and fix it

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTE3NjAyLCJwdXIiOiJibG9iX2lkIn19--81d04d6f9b832ceec1f2c8eea6232dabb0d35406/image.png)

but after a few tries of soldering it on and off it still hadn't worked but it was then that it started connecting to my PC but when I tried making a test program for the yellow light it wouldn't turn it on, and I tested with a multimeter and it should have worked but then i took a look at the side and apparently the stm wasn't totally connected so I had to retry again until it worked

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTE3NjAzLCJwdXIiOiJibG9iX2lkIn19--d0b199ca5e5bdab58ec459b28269bb60c23f0718/image.png)

now I could connect to it but I still had a few problems with the barometer so I tried to resolder it and actually had to cut a trace because it wasn't supposed to be connected to ground (CSB)

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTE3NjEzLCJwdXIiOiJibG9iX2lkIn19--b536eb45cd39ef019f746c89cb515c8ae0ccfd45/image.png)

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTE3NjEyLCJwdXIiOiJibG9iX2lkIn19--a5fbbe297fdbeebe6901cb4ce691693ca3a293b3/image.png)

and that worked because initially it wasnt detecting any chips on the i2c line that the bmp580 was on so yea...

after I got that working it was time for the IMU and heres where it got crazy, so I first got some drivers for it and tried to connect to the IMU and get its WHOAMI register but it kept giving me 0x00 (nothing) so that was kinda suspicious so then I reflowed it varios times until I noticed that it might be a different imu because the chip symbols were different and IT WAS!

looking through the LCSC part number on the package it was different from the one that I had originally wanted

 ![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTE3NjE0LCJwdXIiOiJibG9iX2lkIn19--a285de2049775c9345e1736fb560ce6e0bb1cd59/image.png)

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTE3NjE1LCJwdXIiOiJibG9iX2lkIn19--5df719f002ea897bce287c0cc0fcf425f3f30ecb/image.png)

in any case I still fixed and started up a demo that showcased all of the features of the board!

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTE3NjI1LCJwdXIiOiJibG9iX2lkIn19--ec42d92a601faa597bc9f2521dd824520a167698/image.png)

![IMG_3614](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MTE3NjI2LCJwdXIiOiJibG9iX2lkIn19--cc1e4b6f1e2b546d1d412f3fbb74f233924eaa5c/IMG_3614.jpeg)





  

