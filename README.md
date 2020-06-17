# TVC-Multicart-v1.1
A simple programmodule for the Videoton TVC computer that may contain multiple cartridge images

## English
This package contains the plans of a programmodule for the Videoton TV Compurer. The necessary
parts for building this cart could be obtained easily in 2018 and it costed around 2-3 USD. Cost
of the PCB depends on the manufacturer..

The cart may either contain a hex encoder switch or a 5 element DIP switch. These switches are there
for selecting the usable 16kB or area for the TVC during its startup.
The EEPROM IC has to be programmed, that each cartridge image starts at 16kB boundaries.
The populated EEPROM IC must be pin compatible with the AT29C0x0 (like AM29F0x0 or SST39SF0x0).
Using the HEX encoder one can select up to 16 images, so using an 512kB EEPROM this is not enough (16 images
are just the half of the complete eeprom). That is why there is a pin pad pair for the A18 address line. 
That pin pair must be shorted to access the upper 256kB area (ROM images from 17-32). This jumper is not required
when using the DIP switch, that contains a switch for the A18 line also.
The HEX encoder does the same as the DIP switch: it selects the proper lines on the EEPROM, just it is done by 
rotating the rotary switch.

These schematics were designed using the CADSoft Eagle 8.3.1, free software. The plans (schematics and board layout) 
can also be found, so you may change them at your own will.

You can find the edge connector's library and the cart itself in the eagle-lib directory. The 32k/64k and
the 64k+ machines have different line layout. There is no FAST line and the data lines are gated in the
64k+ machine.

Required parts:
- TVC Multicart v1.1 PCB
- DIP-32 IC socket
- eeprom (eg. SST39SF020)
- 100nF, (min) 16V, 2# ceramic capacitor
- 5+1 resistor network, 10k
- 5 DIP switch, OR
- 16 value hex-encoder

Use it wisely!

Sándor Vass, 2018-09-27



## Magyarul

Ez a csomag egy olyan nyáklap terveit tartalmazza, melyet alkatrésszekkel 
megfelelően ellátva a méltán híres Videoton TV Computerhez egy ún. multicart
cartridge készíthető. A carthoz szükséges alkatrészek 2018-ban kereskedelmi
forgalomban kaphatóak s kb 800Ft-ba kerülnek összesen. A nyáklap legyártásának
költsége gyártófüggő.

A nyáklapon egy forgatható hex enkóder és/vagy egy 5 elemű DIP kapcsolósor 
helyezhető el melyek segítségével lehet kiválasztani, hogy a TVC melyik 16kB -os 
tartományt (bankot) láthassa bekapcsoláskor/resetkor.
Az eeprom ICt úgy kell felprogramozni, hogy 16kB -onként 1-1 cartridge image
kezdődjön, így tudja az adott cartridge image-ét a TVC futtatni.
Az eepromnak lábkompatibilisnek kell lennie az AT29C040 -es ICvel (ilyenek pl.
az AM29F0x0 vagy a SST39SF0x0).
A hex enkóderrel legfeljebb 16 különböző bankot lehet kiválasztani, ez
egy 512kB -os eeprom esetében kevés lenne (pont fele a szükségesnek), ezért 
raktam a lapra egy érintkező párt az A18 lábnak. Ide egy 2x1 -es tüskesor rakható 
(egy jumperrel) vagy egy kapcsoló forrasztható: ezzel lehet kiválasztani, 
hogy az alsó, vagy a fölső 16 bank közül lehessen választani a tekerhető gombbal.
Zárva az érintkező párt az IC A18 -as lába 1-et kap, egyébként 0-át.
A hex-enkóder egy 6 kivezetéses, elforgatható kapcsoló, amely állásától
függően binárisan változtatja a kivezetéseit - 2 GND és 4 kapcsoló láb miatt
van csak 16 lehetséges állapota. Ez a forgatható kapcsoló kiválóan alkalmas az
eeprom A14-A17 lábainak állítására. Ha az eeprom mérete csak 256kB vagy
128kB, akkor nincs szükség a külső kapcsolóra, mert ilyenkor nincs A18 vonal.
A hex-enkóder mellett egy DIP kapcsolósor is beültethető a nyáklapba. Ebben az
esetben sincs szükség a külső kapcsolóra, mivel a DIP kapcsolósor tartalmazza
az A18-as vonal kapcsolóját is.

Ezeket a terveket a CADSoft Eagle 8.3.1, ingyenes verzióval terveztem, a kapcsolási 
rajz (.sch) és a nyákrajzolat (.brd) is mellékelve van, ha változtatásra van szükség.

Megtalálható az eagle-lib könyvtárban alkatrészként a cartrdige élcsatlakozója 
32k/64k és 64k+ gépekhez külön, illetve az egész cartridge, kontúrral, furatokkal
(ahol a gyári cartoknak is a furatuk található), ez szintén 32k/64k és 64k+ gépekhez.
A 64k+ gépeken nincs kivezetve a FAST jel, illetve itt az adatvonalak kapuzva vannak, 
nem közvetlenül a CPU-tól jön a jel.

Szükséges alkatrészek:
- TVC Multicart v1.1 nyáklap
- DIP-32 IC foglalat
- eeprom (pl. SST39SF020)
- 100nF, (min) 16V, 2raszteres kerámia kondenzátor
- 5+1 ellenálláshíd, 10k
- 5 elemű DIP kapcsolósor, vagy
- 16 értékű hex-enkóder



Használd egészséggel!

Vass Sándor, 2018-09-27
