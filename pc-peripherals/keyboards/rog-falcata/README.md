# ASUS ROG Falcata

I bought this keyboard in december 2025 and have almost exclusively used in 
Linux, though with some issues. I have mostly been using the keyboard on PCs
running CachyOS so far and my experience migth be limited. 

I mainly use this keyboard for coding and productivity and not so much gaming. 
Yes it's expensive but I'm quite picky with my keyboards and I could have found
cheaper, even more custom, ones. I didn't want to spend loads of money on a 
completely custom one that I couldn't return.

My previous favourite, that was good enough, was Microsofts Natural Keyboard
but mine is staring to break down and they are getting harder and harder to 
get new ones since they stoped making them.



## Link cable

The two halves of the keyboard is connected with what looks like an USB-C
cable but according to ASUS and various people on the interwebs it's a 
custom pinout. The connectors are USB-C but thats the only thing certain.

I'v plugged my cable into a cheap USB Cable checker and I got this image 
that might help someone. I thought it could help someone. 

![image of cable checker with cable connected](falcata-extension-cable-checker.jpg "Cable with checker")



Using simple USB-C Breakout boards and checking connections with a multimeter I got a 
more complete view of it.

![image of breakout board for usb-c](breakout.png "breakout board")


![image of usb-c pinout](USB_Type-C_receptacle_pinout.svg.png "USB-C Pinout")

(Image of usb-c pinout CC-BY-SA Chindi.ap)

__Measuring from A to A__

`x` indicates connection

|     | A1  | A2  | A3  | A4  | A5  | A6  | A7  | A8  | A9  | A10 | A11 | A12 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A1  | x   |     |     |     |     |     |     |     |     |     |     | x   |
| A2  |     |     |     |     |     |     |     |     |     |     |     |     |
| A3  |     |     |     |     |     |     |     |     |     |     |     |     |
| A4  |     |     |     | x   |     |     |     |     | x   |     |     |     |
| A5  |     |     |     |     | x   |     |     |     |     |     |     |     |
| A6  |     |     |     |     |     | x   |     |     |     |     |     |     |
| A7  |     |     |     |     |     |     | x   |     |     |     |     |     |
| A8  |     |     |     |     |     |     |     |     |     |     |     |     |
| A9  |     |     |     | x   |     |     |     |     | x   |     |     |     |
| A10 |     |     |     |     |     |     |     |     |     | x   |     |     |
| A11 |     |     |     |     |     |     |     |     |     |     | x   |     |
| A12 | x   |     |     |     |     |     |     |     |     |     |     | x   |

__Measuring from A to B__

`x` indicates connection

|     | B1  | B2  | B3  | B4  | B5  | B6  | B7  | B8  | B9  | B10 | B11 | B12 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A1  | x   |     |     |     |     |     |     |     |     |     |     | x   |
| A2  |     |     |     |     |     |     |     |     |     |     |     |     |
| A3  |     |     |     |     |     |     |     |     |     |     |     |     |
| A4  |     |     |     | x   |     |     |     |     | x   |     |     |     |
| A5  |     |     |     |     | x   |     |     |     |     |     |     |     |
| A6  |     |     |     |     |     | x   |     |     |     |     |     |     |
| A7  |     |     |     |     |     |     | x   |     |     |     |     |     |
| A8  |     |     |     |     |     |     |     |     |     |     |     |     |
| A9  |     |     |     | x   |     |     |     |     | x   |     |     |     |
| A10 |     |     |     |     |     |     |     |     |     | x   |     |     |
| A11 |     |     |     |     |     |     |     |     |     |     | x   |     |
| A12 | x   |     |     |     |     |     |     |     |     |     |     | x   |

## Firmware

Delivered with `8.00.01` but I had some issues getting configuration changes to
stick so I upgraded to `8.00.19` and after that it works.


## Linux experience

Out of the box, the keyboard works but changing settings were impossible.
Chrome, Chromium and Opera all found the keyboard using 
https://gearlink.asus.com but there were issues as soon as I tried to get
any further. And yes, it's access related.

The quick and dirty way of enabling access is to run 
`sudo chmod a+rw /dev/hidraw*` before trying to access the keyboard using
the web application. A more permanent solution is to create udev rules.

I will add more information here about how I did it finally but I basically
followed this https://github.com/thyazide/70-asus.rules


### Stuff that I haven't got to work

I have not been able to find a way to do firmware updates using Linux
but it worked without any issues in Windows 11.
