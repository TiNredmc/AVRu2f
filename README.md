teensy-u2f
==========

U2F implementation for Teensy ++ 2.0.

I ported the code from the Teensy LC to Teensy ++ 2.0. I can't handle with the price of the real one (1,200 THB for AVR 8bit ? CRAZY !!!). So I decided to buy the clone for 220 THB. and it works just like the genuine one !. But I don't really want to do this. I want to support the PJRC but I will run into the problems like import fees, HELL-like shipping price and the too high pricetag.  

I actually replace and modified some of parts to at lease working. I tested on this site <https://akisec.com/demo/> registration and login are works well on this site. and this site works only for the registration <https://u2f.bin.coffee>



For the ECDSA key generation and signing this implementation uses the micro-ecc library:

<https://github.com/kmackay/micro-ecc>


License
-------

See LICENSE.txt
