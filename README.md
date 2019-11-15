# SATO M84-Pro EEPROM Info

## Background Story ##
We had trouble with a SATO M84-Pro-2 giving an `EEPROM ERROR` message. In troubleshooting this, I swapped the EEPROM with one from a printer that was working. Apparently, the mainboard was bad, and it corrupted the good EEPROM when powered on. Now I had two broken printers.

I ordered a replacement motherboard and an [TL866II Plus EEPROM programmer](https://smile.amazon.com/gp/product/B07CDD9PGT). After verifying the operation of the programmer, I dumped the EEPROM from the replacement motherboard to ensure we had a backup

I then experimented with some replacement EEPROMs until finding the setting that works.

## How to Use ##
  - Program the EEPROM with the contents of `M84-Pro-2.BIN`
  - The EEPROM must not be write-protected because the printer stores settings on the EEPROM.
    - If the EEPROM is write-protected, the printer will give an `EEPROM ERROR` message.


## Further Information ##
  - SATO used a [Hitachi HN58V65AP-10 8KiB EEPROM](https://datasheet.octopart.com/HN58V65AP-10-Hitachi-datasheet-109849.pdf)
  - The mentioned programmer does not list this as a supported part
    - The [Microchip/Atmel AT28C64B](http://ww1.microchip.com/downloads/en/DeviceDoc/doc0270.pdf) is pin-compatible.
    - Selecting this part in the programming software worked perfectly.
    - I did not try an actual Microchip/Atmel part in the SATO printer; I only selected this part in the programmer.
    - There are probably tens/hundreds of pin-compatible parts, but this is the first one I found.
  - This ROM image also works in the M84-Pro-3 and probably the M84-Pro-6. On startup, it asks you to confirm that the print head resolution has changed.
    - If you receive this prompt on each startup, then the EEPROM is write-protected. See above for clearing that flag.
  - No, a blank EEPROM does not work. I tried. :)

I would love to know what each of the registers mean in the ROM. If someone knows, please open a ticket.
