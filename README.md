# tec-SIO-BC
Serial thru SIO by Břīåñ CHIHД 2020
- https://www.facebook.com/photo.php?fbid=10159860909909056&set=pcb.853869295122121&type=3&theater&ifg=1

I recently built a TEC-1D and got hold of a couple of Z80 SIO chips. I decided to get this chip connected to the TEC so I can transfer code to and from my computer. Also, do away with NVRam etc.. After a bit of research, I came up with this and it works great. Here are the details: 
- Using a clock speed of 3.6864 MHz which divides by 64 to get 57600 baud. Using IO Port 7 for Chip Enabled and A4,A5 for Data/Control and A/B SIO ports. Using A4-5 doesn't mess with the TEC A0-2 and I can do something similar to the LCD output for control and data. ie
```
OUT(27),a 
OUT(07),a
```
Using a USB to FTDI adaptor ($2.28 from AliExpress). Added some D-Flip Flops and jumpers to divide the clock to 28800 and 14400 baud. (Acually haven't tested this yet). Using Coolterm as my serial terminal which can send and capture files. Didn't use IM 2 but could have. I only run the code when I need to transfer, Its not like the TEC is doing something else during transfer. I use JMON's Menu to select the transfer type and the Perimeter to select start address and length. If not using JMON then code can be called directly. All pins needed are through headers on the TEC-1D except IORQ which I wire from under the board.

![](https://github.com/SteveJustin1963/tec-SIO-BC/blob/master/docs/cct.jpg)
![](https://github.com/SteveJustin1963/tec-SIO-BC/blob/master/docs/pcb.jpg)
