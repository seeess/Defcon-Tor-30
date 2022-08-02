# Defcon 30 Tor Badge / SAO Manual
![badge image](https://i.imgur.com/eSLzSpd.jpg "pile of badges")
****
[Here's a feature overview in video form](https://youtu.be/Rasb8VQQdyw)
****
I wanted to help Tor out again since they are back in person with a vendor booth. So I remade the previous onion SAO/Badge. This year's kit includes a handcuff key with the security bitting cut, and a main-badge SAO header, along with the popular accesories like the electrical outlet sticker. 

## In the box
* Tor badge
* Lanyard
* Two CR123a non-rechargeable batteries 
* Battery holder
* Sticker
* Handcuff key
* 6-pin keyed SAO 1.69bis header

### Powering the Tor SAO
This Tor board supports the [1.69bis “shitty add-on”](https://hackaday.com/2019/03/20/introducing-the-shitty-add-on-v1-69bis-standard/) (SAO) standard, there is one 2x3 male pin header that you can connect to a main badge that supports the SAO standard for power. The official defcon badge this year is supposed to have an unpopulated space a 1.69bis SAO header. So we included this SAO header in the kit, allowing you to solder this header on to the official defcon badge and power this onion badge via that SAO port. 

You can also power this board from older badges that use the 2x2 pin SAO standard. When using the older 2x2 standard verify the correct pins are connected. This board only utilizes the “3v3” and “gnd” pins of the SAO standard (other pins on the SAO header are not connected).

Alternatively, if you don’t have a main badge to plug this Tor board into for power, a battery holder and two CR123a batteries are provided so you can power this Tor board independently. Just stick the battery holder to the back of the Tor board, this was not done for you because it would prevent you from using the SAO header. The red wire on the battery holder is the postive side (and labeled on the back of the board), there isn't protection against reverse voltage so be careful. 

**Do NOT** attempt to power the Tor board from both the provided battery and a “main” badge through the SAO header simultaneously. 

### Basic Functionality
On power up the Tor SAO enters the last LED blinking mode. Pressing the button will cycle to the next LED blinking mode. 
 
1.	Very slow LED cycle (one LED at a time in order top to bottom)
2.	Slow LED cycle
3.	Fast LED cycle
4.	Very fast LED cycle
5.	Slow cylon
6.	Fast cylon
7.	Strobe
8.	Slow random
9.	Fast random
10.	Binary counter
11.	LEDs off

### Games
Having only 1 button and 5 LEDs is pretty limiting, but there’s two simple games you can play

##### Reaction Game
1. To enter this game press and hold the button for a few seconds. The top and bottom LEDs will start alternatively blinking quickly.
2. After releasing the button there is a random amount of time where all LEDs will be off. Pressing the LED during this timeframe will result in you losing the game indicated by the top two and bottom two LEDs alternatively blinking. The previous LED blinking mode will restart.
3. When you see the LEDs begin to light up, press the button as quickly as possible. The LEDs will quickly count in binary until the button is pressed. The lower score the better. If you do not press a button quickly enough all of the LEDs will light up, and the previous LED blinking mode will restart
4. If you pressed the button at the correct time a score is shown until you press the button again. At which point the Tor badge will go back to the previous LED blinking mode. 

##### Button Mashing Game
1. Pressing the button around 10 times quickly will enter the button mashing game
2. Continue to press and release the button as quickly possible. The faster the button is pressed the more LEDs will be lit up, and the brighter they will be.
3. To win, completely fill all LEDs until all LEDs flash. Or to quit the game stop pressing the button.

### Unlocks
If you score five or less on the reaction game you will unlock a new “even/odd” LED blinking mode.

If you beat the button mashing game you will unlock a new “heartbeat” LED blinking mode.

Once unlocked these new modes will available after mode 11 "LEDs off"

### EEPROM Storage
The last blinking mode you were using is stored and recovered on power up, along with any unlocks you already earned.

### Troubleshooting and Recovery
A simple reboot should solve most issues by disconnecting and reconnecting power. Be gentle with the white JST power connector if you power the board from the provided battery holder. The JST connector should be disconnected by pulling on the connector itself, and not the wires. It is also recommended that you hold onto the board-side JST connector while connecting or disconnecting the battery holder.

If the button is held while the board is powered up, and released under ~15 seconds, all LEDs will be lit and eeprom reading and writing will be disabled until the next power up. This can be used as a last resort if you have eeprom problems.

When the board is powered up the last mode and unlocks are read from eeprom. If for some reason your board is in a weird state after these values are read you can reset the eeprom values by pressing and holding the button while the board is powered up. Continue holding the button for at least 15 seconds until LEDs 2 and 4 are lit, then release the button. Your board should now act as if it was powered up for the first time. All unlocks will be lost. 

### Bill of Materials
In case something snapped off of your board, or you want to populate a bare board.

| Part Description | Part Number | Example Link |
| --- | --- | --- |
| attiny 402 MCU | ATTINY402-SSNR | [link](https://www.mouser.com/ProductDetail/Microchip-Technology/ATTINY402-SSNR?qs=%2Fha2pyFaduh21XYPei99WR3JCXj6iTo%252Bcfgu3%2Fn8qXX5qNq28IpbLA%3D%3D) |
| JST 2.0mm connector | S2B-PH-K-S(LF)(SN) | [link](https://www.digikey.com/product-detail/en/jst-sales-america-inc/S2B-PH-K-S-LF-SN/455-1719-ND/926626) |
| Button | PTS 647 SN50 SMTR2 LFS | [link](https://www.digikey.com/product-detail/en/c-k/PTS-647-SN50-SMTR2-LFS/PTS647SN50SMTR2LFSCT-ND/9649866) |
| Cap 0.1uF 0603 | C0603C104Z3VACTU | [link](https://www.mouser.com/ProductDetail/KEMET/C0603C104Z3VACTU?qs=sGAEpiMZZMs0AnBnWHyRQFqPnX0Olvco%252BYoiWDWTaEY%3D) |
| Resistor 15ohm 250mw 0603 | ERJ-PA3J150V | [link](https://www.mouser.com/ProductDetail/Panasonic/ERJ-PA3J150V?qs=sGAEpiMZZMukHu%252BjC5l7YcAVbAdukxRIYVGoqC2%252Bq%2F0%3D) |
| LED | L1SP-PRP2002800000 | [link](https://www.mouser.com/ProductDetail/Lumileds/L1SP-PRP2002800000?qs=%2Fha2pyFaduiW1qgclxjjzrnJHFvpNsBqk82fcR2oGYziUOlvP8YCZIQQaHojLBJE) |
| 2x3 SAO shrouded-keyed header |  61200621621 | [link](https://www.digikey.com/product-detail/en/wurth-electronics-inc/61200621621/732-5394-ND/4846913) |

Notes:

Pin 1 for the MCU is on the bottom right. You can test this by toning-out vcc and ground pins on the chip footprint to the SAO header or JST connector that are marked.

You will obviously need 5 LEDs and 5 resistors, all other parts you will just need one of each part.

To program the chip I used a pickit4, you will need something that supports UPDI. I used pogo pins on the top 3 vias. You could solder a 3 pin header there if you want. 

To import and compile you can use mplabx, select an attiny402, and select your pickit4 programmer, there shouldn't be a lot more to it than that. 

The CR123 battery holders were from aliexpress and I don't think you can order just one, plus I manually crimped the connectors on them. But the connector is a standard JST 2.0mm PH connector. There are many battery options to power the board using this connector. You can buy cables on amazon and connect it to your own battery, you can order small lithium-ion battery packs and charge them up, or you can avoid this need and power it via the SAO header. 

HOWEVER: I couldn't find a standard for which side the positive and negative were on for the JST connector (most of amazon had it one way, some of ebay and sparkfun had it another way). The board is marked so make sure you have the positive and negative connected correctly. It is very easy to reverse if you order a pre-made connector, just use a razorblade and lift the plastic tabs to pull out the wires. 
