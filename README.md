# echoShowGen1
Just some oberservations tearing down an Echo Show Gen1.
There's a ton of previous work on this: See e.g. https://de.ifixit.com/Teardown/Amazon+Echo+Show+Teardown/94625
But since I had a broken one (or so I thought, well ... now it's broken) I decided to do it myself.

# Mechanical Disassembly
Just follow the ifixit guide. Plus some additional notes:
- I found these stainless steel spudgers to be helpful whey prying open the speaker compartment.
  ![PXL_20231211_074135713](https://github.com/l33tn00b/echoShowGen1/assets/28904067/6f46381f-f5ea-49f2-b12e-3da96eb740ef)
- Watch out for the digitizer cable (lower left corner of screen) when prying:
  ![PXL_20231211_074944904](https://github.com/l33tn00b/echoShowGen1/assets/28904067/15bef5d7-4e69-4231-80c3-e0bff0431a41)

- 
# Some thoughts on the main PCB:
![PXL_20231211_075842942](https://github.com/l33tn00b/echoShowGen1/assets/28904067/8982da69-d6fb-40e3-928b-6dfed503c8c9)

- Note how the antennas (red markings) are spaced on either side of the PCB/case: One side is Wifi (two antennas), the other side is Bluetooth so as to avoid interference.
- There's a debug connector (non-populated) (amber marking). Probably not much to get out of it (because many components around it haven't been placed, either).

# Going for the Serial Memory
Serial memory is below the largest EMI shield. 
I misjudged from the ifixit photos and openend up the power regulator shielding first. Displaced some capacitors (yellow marking) on the way...
![PXL_20231211_085445772](https://github.com/l33tn00b/echoShowGen1/assets/28904067/97b5b1f9-2a98-48e4-b2a7-d8435c76f359)
Not much of a deal, can be undone. 


