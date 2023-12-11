# echoShowGen1
Just some oberservations tearing down an Echo Show Gen1.
There's a ton of previous work on this: See e.g. https://de.ifixit.com/Teardown/Amazon+Echo+Show+Teardown/94625
But since I had a broken one (or so I thought, well ... now it's broken) I decided to do it myself.

# Mechanical Disassembly
Just follow the ifixit guide. Plus some additional notes:
- I found these stainless steel spudgers to be helpful whey prying open the speaker compartment.
  ![Speaker grille, Spudger inserted](https://github.com/l33tn00b/echoShowGen1/assets/28904067/6f46381f-f5ea-49f2-b12e-3da96eb740ef)
- Watch out for the digitizer cable (lower left corner of screen) when prying:
  ![Digitizer Cable](https://github.com/l33tn00b/echoShowGen1/assets/28904067/15bef5d7-4e69-4231-80c3-e0bff0431a41)

- 
# Some thoughts on the main PCB:
![Main Echo Show Gen 1 PCB](https://github.com/l33tn00b/echoShowGen1/assets/28904067/8982da69-d6fb-40e3-928b-6dfed503c8c9)

- Note how the antennas (red markings) are spaced on either side of the PCB/case: One side is Wifi (two antennas), the other side is Bluetooth so as to avoid interference.
- There's a debug connector (non-populated) (amber marking). Probably not much to get out of it (because many components around it haven't been placed, either).

# Going for the Serial Memory
Serial memory is below the largest EMI shield. 
I misjudged from the ifixit photos and openend up the power regulator shielding first. Displaced some capacitors (yellow marking) on the way...
![Serial memory, EMI shield removed](https://github.com/l33tn00b/echoShowGen1/assets/28904067/97b5b1f9-2a98-48e4-b2a7-d8435c76f359)
Not much of a deal, can be undone. More of a deal is heat damage done to the cable connectors (...let's do it, quick...use the big heat gun). So the board is broken, kinda. 
While ifixit found a W25Q16FW serial memory chip, ours had a Macronix MX25U1635F (https://www.macronix.com/Lists/Datasheet/Attachments/8669/MX25U1635F,%201.8V,%2016Mb,%20v1.6.pdf). Functionally identical.  
Package looks like a 8-land WSON 6mmx5mm. Gotta get an adapter for this one... 

Serial Memory has come off. Forgot to check the datasheet, was suprised by the amount of heat/time it took to come off. Well, there's a large (thermal) pad at the underside (yellow arrow). Had to take the BF(H)G (H is for heat, it's 30 years of Doom, yay!).
![Serial memory chip flipped from PCB](https://github.com/l33tn00b/echoShowGen1/assets/28904067/9f494dee-ff11-464b-a62d-1a441e16aedd)


# Going for the Flash:
![Flash chip marked on main PCB](https://github.com/l33tn00b/echoShowGen1/assets/28904067/e9ffc287-7e69-4c40-8244-eb14e27e107f)

Also below the largest EMI shield, right next to the CPU.
Also displaced a capacitor (yellow marking) because of the pliers I had inserted below the EMI shield to just flip it off. This one is much harder ro re-align. Board even more broken. Unsolder the flash. 
It's an 8GB NAND from Kiaoxia: THGBMJG6C1LBAIL. https://datasheet.lcsc.com/lcsc/2004271813_KIOXIA-THGBMJG6C1LBAIL_C524518.pdf
How very convienient: it's not pure flash but has an eMMC controller included which makes reading a breeze. Go for an AllIcSocket BGA 153 Reader on Aliexpres (or ebay, or Amazon, or...). 

Here's the flash. Coming off much more easily (because the PCB had already been heated and no thermal/ground pad). Still needs a bit of cleaning, but nothing broken.  
![Flash Chip, Bottom BGA Pads](https://github.com/l33tn00b/echoShowGen1/assets/28904067/19ed907c-ee6d-493f-8dbc-27a81267302d)

Except for the main PCB. Which didn't appreciate the beating (err.. heating) and started delaminating.
I sometimes long for professional tools... Well, that's part of the fun. Doing stuff you're not supposed to do using tools not made for the job. 
