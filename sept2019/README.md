Just starting to get things working. This folder has the same files zipped 3 ways.

I use the cli on the nrf52840 usb dongles with screen

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
