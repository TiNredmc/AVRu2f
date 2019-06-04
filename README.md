AVRu2f 
==========

U2F implementation for Teensy ++ 2.0.

I ported the code from the Teensy LC to Teensy ++ 2.0. I can't handle with the price of the real one (1,200 THB for AVR 8bit ? CRAZY !!!). So I decided to buy the clone for 220 THB. and it works just like the genuine one !. But I don't really want to do this. I want to support the PJRC but I will run into the problems like import fees, HELL-like shipping price and the too high pricetag.  

I actually replace and modified some of parts to at lease working. I tested on this site <https://akisec.com/demo/> registration and login are works well on this site. and this site works only for the registration <https://u2f.bin.coffee> .
On this github-based website also working <https://mdp.github.io/u2fdemo/#>


For the ECDSA key generation and signing this implementation uses the micro-ecc library:

<https://github.com/kmackay/micro-ecc>


License
-------

See LICENSE.txt

Setup
-----

just install teensyduino and select the Teensy++ 2.0 board. USB types is Raw HID. next navigate to the destination dir of teensy. It should /path/to/arduino/installation/path/hardware/teensy/avr/cores/usb_rawhid

in usb_private.h chage these following things 

```
#define VENDOR_ID               to 0x16C0
#define PRODUCT_ID              to 0xf1d0
#define RAWHID_USAGE_PAGE 	to 0xf1d0 // seems like this reading as fido.
#define RAWHID_USAGE	to 0x0200
```
NOTE After changed the Product ID. You won't get auto reset from teensy loader anymore. To upload code, you need to press the button manually

LED status
----------
First time after plugged in. Led will turn on .5 s and turn off.

```
Status --- ON for .5 sec --- power on
Status --- ON NO blink --- Packet received and / or sending the data
Status --- OFF --- transmission done
```
What I've Expected in the future.
--------
- fix the Authentication (Sign). It's alway failed.
- add hardware security level to generate Entropy and keep the key 
Using ATECC508A-SSHDA
