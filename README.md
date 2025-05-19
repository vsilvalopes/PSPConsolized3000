# PSPConsolized3000

This is a simple page to unite the information on how to do a PSP Consolized, using a PSP 3000 as a base.

First of all, I did not made this project.

This is the modification of the hard work of the Mexican Modder DavidXGames (https://www.youtube.com/@DAVIDXGAMESmx).

He did sometime ago the same thing, a PSP Consolized but using a PSP 2000, link to his video : https://www.youtube.com/watch?v=mVIgfFf5pms

What I did was based on his observations, improve a little the project, so, without him, nothing of this was possible.

Here his original project link, you will find some usefull information here: https://xgamesvideojuegos.blogspot.com/2023/06/psp-consolizer.html

This project intend to put a dead PSP in use again.
So if you have a PSP that turns on but with the screen busted, or a bad battery, this project is perfect for you.
You can always mod a good PSP, but in my understanding, it breaks the purpose of this project.


# Some Disclaimers

Do all the software modifications on the PSP, BEFORE consolizing it.
Some quality of life homebrews, like ChronoSwitch or even the oficial Sony updater, refuses to run in the PSP Video out.
So update anything that you need, install a permanent CFW, before removing the screen.
It is possible to use the screen with the case, but it`s a pain, trust me.

I really recomend using the ARK-4 CFW [ARK-4 Wiki](https://github.com/PSP-Archive/ARK-4/wiki), and there are some very good guides on the PSP Punk Website : [Link](https://www.pspunk.com/)

# How it Works?

The magic is on the ESP32 module that you will write software on it latter.
The ESP32 does the trick of sending the Power On Signal to the PSP and then sending the signal to enable the video out on the PSP.
So, whenever you turn on the energy, the ESP32 module is started and takes care of booting the PSP and changing the video output.

Also, the ESP32 module operates like a receiver for popular Bluetooth controllers.

It works translating all the comands of a Bluetooth controller connected to it and sending it to the PSP, so you can control the PSP using a DualShock 4 controller for example.
I reccomend using this controller (DualShock 4) , as it has the most simple pairing method (hold the SHARE + PS)

We also have two little boards (Digital Potentiometers) that does the trick of the Analog Stick inputs on the PSP.

# Bill of Materials

You will need:

- [01 ESP32-WROOM-32D Module](https://pt.aliexpress.com/item/1005004491534008.html?aff_fcid=41d82e2544ec47339c1a654e38c2d939-1745278905786-02647-_Dnpxx4h&tt=CPS_NORMAL&aff_fsk=_Dnpxx4h&aff_platform=shareComponent-detail&sk=_Dnpxx4h&aff_trace_key=41d82e2544ec47339c1a654e38c2d939-1745278905786-02647-_Dnpxx4h&terminal_id=b60c92d0c81f48f7b8e37bbf4142f48d&afSmartRedirect=y) (Buy the one without the pins soldered to the board, you will tank me latter)

- [02 Digital Potentiometers](https://pt.aliexpress.com/item/1005005669170098.html?aff_fcid=a3f2fe477a124d05906fb4d47b99376a-1745279069662-01723-_DEksNRr&tt=CPS_NORMAL&aff_fsk=_DEksNRr&aff_platform=shareComponent-detail&sk=_DEksNRr&aff_trace_key=a3f2fe477a124d05906fb4d47b99376a-1745279069662-01723-_DEksNRr&terminal_id=b60c92d0c81f48f7b8e37bbf4142f48d&afSmartRedirect=y)

- [02 FPC Connectors, with 0.5mm and 10 Pins](https://pt.aliexpress.com/item/1005004411740279.html?aff_fcid=c67a21960ecd4338b0368ce4d567d191-1745279114665-00213-_DBXDj7X&tt=CPS_NORMAL&aff_fsk=_DBXDj7X&aff_platform=shareComponent-detail&sk=_DBXDj7X&aff_trace_key=c67a21960ecd4338b0368ce4d567d191-1745279114665-00213-_DBXDj7X&terminal_id=b60c92d0c81f48f7b8e37bbf4142f48d&afSmartRedirect=y)

- [01 FPC Conector, with 0.5mm and 14 Pins](https://pt.aliexpress.com/item/1005004411740279.html?aff_fcid=c67a21960ecd4338b0368ce4d567d191-1745279114665-00213-_DBXDj7X&tt=CPS_NORMAL&aff_fsk=_DBXDj7X&aff_platform=shareComponent-detail&sk=_DBXDj7X&aff_trace_key=c67a21960ecd4338b0368ce4d567d191-1745279114665-00213-_DBXDj7X&terminal_id=b60c92d0c81f48f7b8e37bbf4142f48d&afSmartRedirect=y)

- [02 Flex Cables, 15 cm, 0,5 mm pitch and 10 Pins](https://pt.aliexpress.com/item/1005002468369055.html?spm=a2g0o.order_detail.order_detail_item.3.60974c7fMLkBF4&gatewayAdapt=glo2bra) (Forward direction)

- [01 Flex Cable, 15 cm, 0.5 mm pitch and 14 Pins](https://pt.aliexpress.com/item/1005002468369055.html?spm=a2g0o.order_detail.order_detail_item.5.60974c7fMLkBF4&gatewayAdapt=glo2bra) (Forward direction)

- [Micro Slide Switch SS12F44 3mm](https://www.aliexpress.com/item/1005003938856402.html?channel=twinner )

- [01 USB-C Conector](https://pt.aliexpress.com/item/1005006047462864.html?spm=a2g0o.order_list.order_list_main.60.3432caa4Qj0sbo&gatewayAdapt=glo2bra)

- Some kind of Super Glue

# 3D Printed Case

I've put the 3D Printed case on Cults 3D.

[PSP Consolized 3D Printable Case](https://cults3d.com/en/3d-model/gadget/psp-3000-consolized-case)

I'm charging about U$ 10,00 for the STL Files.

On the future I plan oppening the model and putting it on Thingverse for free, for now its paywalled, sorry about that!

# Materials reference

Gather all the eletronic materials, like the picture bellow : 

![IMG_20250518_120539-x](https://github.com/user-attachments/assets/ae588d7e-1822-4060-a11f-fc57961f7d2b)

# Building instructions - The Software Part

:warning: :warning: :warning: First of all, CONFIGURE EVERYTHING on your PSP, before doing anything.:warning: :warning: :warning:

I can't stress this enough, but ignoring it will give you a lot of headaches disassembling everything.
So, flash your custom firmware, edit the Recovery Menu settings BEFORE dissambling the PSP, it's much easyer doing it with the PSP on it's original form factor, you have been warned!

# Building instructions - Flashing the software on the ESP32 

1- For any of this work, you have to flash the ESP32 with the provided firmware here (Folder ESP32 Firmware) this is an essential part of the build.

2- Conect your ESP32 module via USB on your PC, it should apear on the Windows Device Manager like this :

![image](https://github.com/user-attachments/assets/dba1cc99-e9fe-429e-9937-0570bdd6b0aa)

Look for the "Silicon Labs CP210x USB to UART Bridge(COMx)" device, where X is the COM port on your PC.
Take note of the COM port number, you will use it later.

3- To Flash the firmware on the ESP32 module, grab the "Flash_download_tool_3.9.2.zip" on this repository, extract it, and open the "flash_download_tool_3.9.2.exe" (sorry but Windows only instructions)

![image](https://github.com/user-attachments/assets/dcf0d1da-46cd-4a17-8a34-8d55c9c9a23a)

3.1 When openning the "Flash_download_tool_3.9.2" set it like the picture bellow:

![image](https://github.com/user-attachments/assets/705abefc-80f4-4afc-aea9-f39a477a9fd1)

3.2 After that, you have to load the firmware .bin files, included here on the folder "ESP32 Firmware" so you can write it on the ESP32 Module, so configure it like this:

![image](https://github.com/user-attachments/assets/e9c505e0-2679-4c36-bff4-00b46ac6b166)

And this :

![image](https://github.com/user-attachments/assets/ccc2c362-0e75-48cc-b79e-40795fb22f28)

3.3 Set the respective COM port, and hit START, the flashing process will take about 1 minute, and you will be able to see some info on your chip.

![image](https://github.com/user-attachments/assets/a1357fca-2325-4554-a2ad-db45246480dc)

3.4 When the "FINISH" message appears, you can close the "Flash_download_tool_3.9.2"

And that's it, you are done, if you want to test if the module is working correctly, keep it connected to your computer USB, and try to pair it with a controller.
If everything went right, the controller should pair and give a little vibration feedback. Also, if your ESP32 board has a bluetooth LED, it should light blue, indicating that a controller is connected.

# Some warning, Soldering is needed!

:warning: :warning: :warning: You need to know HOW to solder! :warning: :warning: :warning:

Despite not that dificult and almost risk free for the PSP, you need to have some sort of soldering experience. 

There are LOTS of Youtube tutorials on it, on this guide I will only discuss the best aproach on builing that worked for ME! 

# Soldering Part 1 - The FPC connectors

0 - So in this part, you are going to solder the FPC points to the ESP32 Board. 

This part of the soldering, handles all the inputs on the PSP, like turning it on, changing the video out, and the buttons on the controller itself.

This is the basic eletronic diagram of the soldering needed, and the respective pins on the FPC boards and the ESP32 :

![Diagrama sem nome drawio](https://github.com/user-attachments/assets/335b181c-4ec4-4813-bc4e-7828998fc731)

1- Place the components on the positions bellow, Attention on the orientation of the circuits, it will make your soldering job easier:

![IMG_20250518_120443](https://github.com/user-attachments/assets/5f78bba4-c7a8-492a-b617-4bc54a04ec41)

2- For good measure, use some isolation on the back of the components, like this :

I used some Kapton tape, to isolate the botton of the components

![image](https://github.com/user-attachments/assets/902af838-ad1b-4b01-a355-b6fdcda2f1d7)

![image](https://github.com/user-attachments/assets/9cf06779-ef7f-459e-b0b5-b7a36bbfe52d)

3- After that, place some super glue on the positions, don't exagerate on it, this is just to keep the components in place:

![image](https://github.com/user-attachments/assets/5ef31a34-1886-487d-a943-f131de0b2f55)

4- Wire up the pins of the **FPC 3** to the ESP32, like this:

![image](https://github.com/user-attachments/assets/649c39fb-d14a-4d22-86c4-8fb546ee6105)

You Should have somenthing like this:

![image](https://github.com/user-attachments/assets/a9514026-98c6-4584-bcd7-43f7a2089cab)

5- Wire up the pins of the **FPC 2** to the ESP32, like this:

![image](https://github.com/user-attachments/assets/91f00150-d0bd-4c98-923c-c031f7e48d40)

5- Wire up the pins of the **FPC 1** to the ESP32, like this:

![image](https://github.com/user-attachments/assets/668930b4-83bf-4cce-befc-1cc148a96ec7)

6- At the end, everything should look like this:

![image](https://github.com/user-attachments/assets/e129ae3a-94d2-4ba7-88da-e8874974bafb)

# Soldering Part 2 - The Digital Potentiometers

0 - First of all, grab the analog stick from your PSP, even if it is busted you can use it, grab it and dissambly it carrefully, so in the end you have this little piece:

![image](https://github.com/user-attachments/assets/9719b069-d711-45bf-a387-81da0ee672f6)

1- You will need just this piece in the end: 

![image](https://github.com/user-attachments/assets/10db2e99-b177-4374-8695-1ba6ed2d753c)

2- Place a little bit of solder on the golden pads, like this :

![image](https://github.com/user-attachments/assets/5bec912f-86c7-415d-b147-70d7ab2fe6a0)

3- Solder some colored wires with about 15 cm on the pads : 

![image](https://github.com/user-attachments/assets/f8f6a5bd-7a07-4c15-95ea-cea8671850e8)

4- :warning: VERY IMPORTANT! :warning: After the soldering, insulate the analog piece with some tape, If you dont do that, you will get some ghost inputs comming from the analog stick

![image](https://github.com/user-attachments/assets/4e1d3017-73e7-4fbd-9567-f184f0d4aeca)

5- Now, you have to solder the wires of the Analog Stick Board on the Digital Potentiometers and the ESP32, like this

![Diagrama sem nomeW drawio](https://github.com/user-attachments/assets/105812e1-5496-480a-825d-49b175de1e60)

6- On the digital potetiometer boards, you have to bridge the **GND** and **CS** Points on both boards, like this :

![image](https://github.com/user-attachments/assets/104cc971-f003-4dff-a5b6-e19e7ec92cb5)

7- Also, you have to bridge the **VH** on both boards, and the **VL** Points, like this :

![image](https://github.com/user-attachments/assets/e2147a1e-9391-4fd0-b410-b6a1a4cf97da)










