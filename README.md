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

[01 ESP32-WROOM-32D Module](https://pt.aliexpress.com/item/1005004491534008.html?aff_fcid=41d82e2544ec47339c1a654e38c2d939-1745278905786-02647-_Dnpxx4h&tt=CPS_NORMAL&aff_fsk=_Dnpxx4h&aff_platform=shareComponent-detail&sk=_Dnpxx4h&aff_trace_key=41d82e2544ec47339c1a654e38c2d939-1745278905786-02647-_Dnpxx4h&terminal_id=b60c92d0c81f48f7b8e37bbf4142f48d&afSmartRedirect=y) (Buy the one without the pins soldered to the board, you will tank me latter)

[02 Digital Potentiometers](https://pt.aliexpress.com/item/1005005669170098.html?aff_fcid=a3f2fe477a124d05906fb4d47b99376a-1745279069662-01723-_DEksNRr&tt=CPS_NORMAL&aff_fsk=_DEksNRr&aff_platform=shareComponent-detail&sk=_DEksNRr&aff_trace_key=a3f2fe477a124d05906fb4d47b99376a-1745279069662-01723-_DEksNRr&terminal_id=b60c92d0c81f48f7b8e37bbf4142f48d&afSmartRedirect=y)

[02 FPC Connectors, with 0.5mm and 10 Pins](https://pt.aliexpress.com/item/1005004411740279.html?aff_fcid=c67a21960ecd4338b0368ce4d567d191-1745279114665-00213-_DBXDj7X&tt=CPS_NORMAL&aff_fsk=_DBXDj7X&aff_platform=shareComponent-detail&sk=_DBXDj7X&aff_trace_key=c67a21960ecd4338b0368ce4d567d191-1745279114665-00213-_DBXDj7X&terminal_id=b60c92d0c81f48f7b8e37bbf4142f48d&afSmartRedirect=y)

[01 FPC Conector, with 0.5mm and 14 Pins](https://pt.aliexpress.com/item/1005004411740279.html?aff_fcid=c67a21960ecd4338b0368ce4d567d191-1745279114665-00213-_DBXDj7X&tt=CPS_NORMAL&aff_fsk=_DBXDj7X&aff_platform=shareComponent-detail&sk=_DBXDj7X&aff_trace_key=c67a21960ecd4338b0368ce4d567d191-1745279114665-00213-_DBXDj7X&terminal_id=b60c92d0c81f48f7b8e37bbf4142f48d&afSmartRedirect=y)

[02 Flex Cables, 15 cm, 0,5 mm pitch and 10 Pins](https://pt.aliexpress.com/item/1005002468369055.html?spm=a2g0o.order_detail.order_detail_item.3.60974c7fMLkBF4&gatewayAdapt=glo2bra) (Forward direction)

[01 Flex Cable, 15 cm, 0.5 mm pitch and 14 Pins](https://pt.aliexpress.com/item/1005002468369055.html?spm=a2g0o.order_detail.order_detail_item.5.60974c7fMLkBF4&gatewayAdapt=glo2bra) (Forward direction)

[01 USB-C Conector](https://pt.aliexpress.com/item/1005006047462864.html?spm=a2g0o.order_list.order_list_main.60.3432caa4Qj0sbo&gatewayAdapt=glo2bra)

# 3D Printed Case

I've put the 3D Printed case on Cults 3D.

[PSP Consolized 3D Printable Case](https://cults3d.com/en/3d-model/gadget/psp-3000-consolized-case)

I'm charging about U$ 10,00 for the STL Files.

On the future I plan oppening the model and putting it on Thingverse for free, for now its paywalled, sorry about that!

# Building Instructions



