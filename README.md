# tehUberChip_Another_PSX_Modchip
Another PSX modchip made in 2021 for arduino

References for info: 

http://www.psxdev.net/forum/viewtopic.php?t=1265&start=20]

https://www.obscuregamers.com/threads/playstation-scph-7502-pu-22-pcb-modchip-question-and-modchip-diagrams-request.1311/
                        
http://www.psxdev.net/forum/viewtopic.php?t=1266 


UberChip - by Vajskids Consoles 2021

PM41 with BIOS patch for PAL consoles Demo: https://youtu.be/Ahy8XMkAvQc 

An Open Source arduino full stealth modchip developed for each model of PS1 (so far PU18, PU22, PU23, PM41 - Assumed to work on PU20/PU8 with PU18 INO - have them on hand ...but CBF installing) with an Arduino Nano (3.3v 16mhz, running @ 8mhz). 


Multi-disc support and a full serial monitor output which shows you exactly what's
happening as well as acting like a built in debugger. There are of course stand-alone internal install versions with out a debugger.

No Audio CD delay- will boot straight to audio CD player

Thanks to all the other open source modchip writers and especially thanks to OldCrows old articles and for
releasing the first of the mighty PSX modchips!

A clone arduino nano will set you back a whopping 6.60AUD free post at the moment, please check compatible arduinos folder.
This will be updated when possible, but as of now I only purchase the cheap nano clones, this should work on MANY arduinos though.

Optional reset: connection 4 off MM3 diagrams to the RST on the arduino.
Without this, you can reset but you'd have to open the drive lid and close it again to get the game disc to boot again. 

Just checked this connection and it has a logic high of 3.xxV and gets pulled low on reset which should trigger the arduinos reset
pin simultaneously without an issue.


How it works: Precise timing of injections on each model then either stopping the injections but keeping the gate
held low (earlier phats) or stopping the injections then reverting the DATA line to an input thus letting the original signal in without
any interference (later phats) - This is how it remains stealth. It only kicks back into an injection cycle when the drive lid is opened / closed again, or if it's reset (optional wire) or powered off/ on. On the later models it's only working @ a 50% load i.e. it's only 'injecting' the low bits of the string, then releasing for the high bits. (it basically chops up the original signal to mimic the string, then disappears)

The timing isn't written in stone, but I'd suggest leaving it as is, as I've tested them thoroughly (I use solely Verbatim AZO these days as Taiyo Yuden (That's! CDR) have become too expensive.

Tested using 2 lasers across the board, one from a PU20 and one from a PU23 on extension cables, these were the only good lasers I had on hand at the time.
Tested with about 10 games each, 3 antimods included and a few libcrypts.

anti-mod games :

FF9, UmJammer Lammy, Spyro - Year of the Dragon - no issue with any of them.

By installing this chip YOUR DRIVE IS RESTRICTED IN WORKING within the boundaries of the chips programming!

Benefits of this:
Less wires, Discs must be in good shape! If your disc can't load within the parameters of the modchip then you've got a scratched up disc - make a fresh one. Scratched
discs are only going to wear out your laser faster. Each model has slightly different timing and counts either full string iterations or increments a counter per bit.

Downfalls:
Your shitty scratched up discs might not load in time, thus saving your laser from unnecessary wear and tear.

Also, I'm sure you will notice how much healthier the drive sounds with the removed 100k resistor - testing has shown this signal to be nothing but detrimental to the
drives performance.


....It may take a while, but I will eventually port this across to a PIC chip in ASM
