# tehUberChip_Another_PSX_Modchip
Another PSX modchip made in 2021 for arduino

References for info: 

http://www.psxdev.net/forum/viewtopic.php?t=1265&start=20]

https://www.obscuregamers.com/threads/playstation-scph-7502-pu-22-pcb-modchip-question-and-modchip-diagrams-request.1311/
                        
http://www.psxdev.net/forum/viewtopic.php?t=1266 


UberChip - by Vajskids Consoles 2021

An Open Source arduino full stealth modchip developed on an SCPH5502/ PU18 with an Arduino Nano. 
Multi-disc support and a full serial monitor output which shows you exactly what's
happening as well as acting like a built in debugger.

No Audio CD delay- will boot straight to audio CD player

Currently only PAL string bits are included for PU18, the injection routine will be updated to work like the later models and
the other string characters added to the header of the INO's shortly,

Thanks to all the other open source modchip writers and especially thanks to OldCrows old articles and for
releasing the first of the mighty PSX modchips!

For stand-alone version (internal installations, no debug/ serial monitor) run a link from D4 to 3.3v pin (this will be fixed so you only need one wire and no link shortly)

A clone arduino nano will set you back a whopping 6.60AUD free post at the moment, please check compatible arduinos folder.
This will be updated when possible, but as of now I only purchase the cheap nano clones, this should work on MANY arduinos though.



Optional reset: connection 4 off MM3 diagrams to the RST on the arduino.
Without this, you can reset but you'd have to open the drive lid and close it again to get the game disc to boot again.

Just checked this connection and it has a logic high of 3.xxV and gets pulled low on reset which should trigger the arduinos reset
pin simultaneously without an issue.


How it works: Precise timing of injections on each model then either stopping the injections but keeping the gate
held low (earlier phats) or stopping the injections then reverting the DATA line to an input thus letting the original signal in without
any interference (later phats) - This is how it remains stealth. It only kicks back into an injection cycle when the drive lid is opened / closed again, or if it's reset (optional wire) or powered off/ on.

The timing isn't written in stone, but I'd suggest leaving as I've tested thorougly (I use solely Verbatim AZO these days as Taiyo Yuden (That's! CDR) have become too expensive.

Tested using 2 lasers across the board, one from a PU20 and one from a PU23 on extension cables, these were the only good lasers I had on hand at the time.
Tested with about 10 games each, 3 antimods included and a few libcrypts.

anti-mod games :

FF9, UmJammer Lammy, Spyro - Year of the Dragon - no issue with any of them.

By installing this chip YOUR DRIVE IS RESTRICTED IN WORKING within the boundaries of the chips programming!

Benefits of this:
Less wires, Discs must be in good shape! If your disc can't load within the parameters of the modchip then you've got a scratched up disc - make a fresh one. scratched
discs are only going to wear out your laser faster. Each model has slightly different timing and/ or single bit / full string injections.

Downfalls:
Your shitty scratched up discs might not load in time, thus saving your laser from unnecessary wear and tear.

Also, I'm sure you will notice how much healthier the drive sounds with the removed 100k resistor - testing has shown this signal to be nothing but detrimental to the
drives performance.
