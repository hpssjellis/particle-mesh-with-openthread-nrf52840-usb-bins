Just starting to get things working. This folder has the same files zipped 3 ways.



### warning getting the Argon and Xenon back to normal needs:

To get thngs back to normal you may have to flash the Argon binaries back onto your Argon

https://github.com/particle-iot/device-os/releases/download/v1.4.1-rc.1/particle_device-os@1.4.1-rc.1.zip

Look to the bottom of this thread 

https://community.particle.io/t/particle-device-os-updates-thread/14378/97



.



I use the cli on the nrf52840 usb dongles with the "screen" app.

I use the nrf-connect util to install the .hex files onto the dongles. 

download at https://www.nordicsemi.com/Software-and-Tools/Development-Tools/nRF-Connect-for-desktop/Download#infotabs

with some info https://www.nordicsemi.com/Software-and-Tools/Development-Tools/nRF-Connect-for-desktop

This program actually works fine on windows. The screen command I think only works on linux though.

The button on the dongles s a bit hidden and is pushed sideways. Button must be held down while inserting the dongle into your computer. 


For the particle mesh devices. Put the device into dfu mode touch both buttons then keep holding the mode (left side of usb cable) first it flashes cyan then yellow, release on yellow.

Then in the folder with the argon or xenon bin enter this

```
particle flash --usb  myProjectName-argon.bin


```

If you power up 2 or more argons with wifi working they should find each other as their mesh credentials have been set to be the same. 

If you connect D0 to 3v3 then all Argons should flash every 5 seconds. If you set any Argon D6 to 3V3 it shuts off wifi but the Argons should still flash every 5 seconds, suggesting that the Argons are communicating useing the Mesh network and not wifi.



With the nrf52840 usb dongles

Connect one dongle to your laptop with OTBR (openthread border router) working.

To see what it is called type or some other method

```ls /dev/ttyA*```

Then type 

```screen /dev/ttyACM0 115200```

then hit a key

then type

```state```


Now is not a bad time to power up your argons and xenons

```scan```

```ping ff02::1 ```


``` ping (local ipv4 address, see console for argons at startup) ```


Please reply if you can do anything else. I would really like to use screen to get the nrf52840 sending a udp message to the argons and xenons but unfortunately I think I will have to do it in software.
