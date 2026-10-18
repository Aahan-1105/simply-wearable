# simply-wearable

## Overview
simply_wearable was created for the Half-Life program by hackclub for week 1: PCB Week.

I recently got a G-SHOCK and love it, but miss step counting from my old watch, so I decided to create a simple wearable with step tracking and a few buttons. I also decided to add a screen as a simple way to make it cooler without significant complexity. 

## Features
- BLE to phone
- Step counting
- oled screen with images and info
- 2 buttons for control
- Remote shutter for group photos
- Battery voltage monitoring
- 110maH battery with usb-c charging
- Built for under $30 USD

## Notes
Having made a keyboard in KiCAD before, I chose to use KiCAD to design the Schematic and PCB for this project. I started off with research on how to accomplish my goals. For step-counting, the GY-BMI160 Module integrates I2C communication with easy power management and an efficient hardware-based pedometer unit. The module will count and store steps up to a certain number, before syncing with the microcontroller to update the information. This approach lets me keep the microcontroller asleep over 90% of the time and results in an incredibly efficient device.

The Nice!Nano microcontroller is based on the nRF52840 and is compact with built-in battery management, while being very efficient. While it is designed for and used in wireless keyboards, I chose to use it for this project due to its capabilities and the fact that I have an extra one at home already. 

The 0.91" oled will be prett simple and connect to the nice!nano over I2C, and will wake from a button press to show step count, battery voltage and some other basic info. it was chosen for easy packaging right above the nice!nano. 

Undeniably the hardest part of this project was the packaging. I wanted to fit all the functionality into the smallest package that wouldn't be noticed on my wrist, and ended up cutting some important functionality to make this happen, such as the haptic system for quiet alerts and extra buttons and battery capacity. Maybe in a future version, I'll have a custom/built-in controller and IC instead of devboards.

## Photos

<img width="354" height="569" alt="image" src="https://github.com/user-attachments/assets/537d02c7-bf04-48cd-9947-ecbb1a275924" />

Finished PCB Excluding Ground Fill

<img width="732" height="613" alt="image" src="https://github.com/user-attachments/assets/ff5d23fd-cfcb-4b5e-9048-8e5e2c937655" />

Finished Schematic

Renders of the PCB and CAD will be added as completed!

## Reflection
Designing this was an awesome experience and I hope I get to build it!

My biggest learning from this project is that for compact projects like this, I will need to learn to use ICs directly and move away from devboards. Given this, my next dedicated project will definitely be either a custom MC devboard, flight controller, or similar project.

Thanks again to Hack Club and their program, Half-Life, for making this possible!

## BOM
|Purchase Status|Part              |Qty|Price (USD)|Total |Link                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |Shipping/Tax|Notes                           |
|---------------|------------------|---|-----------|------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|--------------------------------|
|               |301230 Battery    |1  |$10.05     |$10.05|https://www.aliexpress.com/item/1005005348368664.html?spm=a2g0o.cart.0.0.21be38dafBGUUp&mp=1&pdp_npi=6%40dis!CAD!CAD+15.74!CAD+8.22!!CAD+7.73!!!%402101c4b817914249992426203e0e42!12000032707728288!ct!CA!6705116064!!1!0!                                                                                                                                                                                                                                                                                                                                                                        |            |Powers the wearable             |
|               |Passive components|1  |$4.92      |$4.92 |https://www.aliexpress.com/item/1005012364450156.html?spm=a2g0o.cart.0.0.d93b38da2l9jbS&mp=1&pdp_npi=6%40dis!USD!USD+2.83!USD+2.83!!USD+2.69!!!%402101c4b817914251483713919e0e42!12000058305516207!ct!CA!6705116064!!1!0!                                                                                                                                                                                                                                                                                                                                                                         |            |Capacitor and buttons           |
|               |0.91" oled screen |1  |$3.58      |$3.58 |https://www.aliexpress.com/item/1005012327947468.html?spm=a2g0o.cart.0.0.21be38dafBGUUp&mp=1&pdp_npi=6%40dis!CAD!CAD+15.25!CAD+5.19!!CAD+5.14!!!%402101c4b817914249992426203e0e42!12000059297375602!ct!CA!6705116064!!1!0!                                                                                                                                                                                                                                                                                                                                                                        |            |displaying info and cat gifs    |
|               |GY-BMI160         |1  |$1.62      |$1.62 |https://www.aliexpress.com/item/1005007137336558.html?spm=a2g0o.cart.0.0.7b0e38daxFEVi0&mp=1&pdp_npi=6%40dis!USD!USD+1.61!USD+1.61!!USD+1.61!!!%402103128917922644849797739e0ffa!12000051162992792!ct!CA!6705116064!!1!0!                                                                                                                                                                                                                                                                                                                                                                         |            |step counting!                  |
|               |PCB               |1  |$10.85     |$10.85|https://github.com/Aahan-1105/simply-wearable/blob/main/Images/JLCPCB_Cart.png                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |            |Hold components and connect them|
|X              |Nice!Nano         |1  |$4.18      |$4.18 |https://www.aliexpress.com/item/1005009026511947.html?spm=a2g0o.productlist.main.3.5471422107m4xT&algo_pvid=e24ab648-8f51-4fb5-8646-e05f5afd7a02&algo_exp_id=e24ab648-8f51-4fb5-8646-e05f5afd7a02-2&pdp_ext_f={%22order%22%3A%221861%22%2C%22eval%22%3A%221%22%2C%22fromPage%22%3A%22search%22}&pdp_npi=6%40dis!USD!4.18!4.18!!!27.86!27.86!%40210303cd17922849321912959e0b8d!12000047645063314!sea!CA!6705116064!X!1!0!n_tag%3A-29919%3Bd%3Aac0a92ca%3Bm03_new_user%3A-29895&curPageLogUid=UxK5qiU7Y3iq&utparam-url=scene%3Asearch&#124;query_from%3A&#124;x_object_id%3A1005009026511947&#124;_p_origin_prod%3A|            |micro controller                |
|               |                  |   |           |      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |            |                                |
|               |TOTAL (USD)       |   |$35.20     |$0.00 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |            |                                |
