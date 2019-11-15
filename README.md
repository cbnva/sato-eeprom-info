# SATO M84-Pro EEPROM Info

## Background Story ##
We had trouble with a SATO M84-Pro-2 giving an `EEPROM ERROR` message. In troubleshooting this, I swapped the EEPROM with one from a printer that was working. Apparently, the mainboard was bad, and it corrupted the good EEPROM when powered on. Now I had two broken printers.

I ordered a replacement motherboard and an [EEPROM programmer](https://smile.amazon.com/gp/product/B07CDD9PGT). After verifying the operation of the programmer, I dumped the EEPROM from the replacement motherboard to ensure we had a backup

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
    - I did not try one in the SATO printer.
    - There are probably hundreds of pin-compatible parts, but this is the first one I found.

I would love to know what each of the registers mean in the ROM. If someone knows, please open a ticket.
