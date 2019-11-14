# SATO M84-Pro EEPROM Info

## Background Story ##
We had trouble with a SATO M84-Pro-2 giving an `EEPROM ERROR` message. One obvious step of troubleshooting this is to swap the EEPROM with a printer that's working. Apparently, the mainboard was bad, and it corrupted the good EEPROM when powered on.

I ordered a replacement motherboard and an [EEPROM programmer](https://smile.amazon.com/gp/product/B07CDD9PGT). After verifying the operation of the programmer, I dumped the EEPROM from the replacement motherboard to ensure we had a backup

I then experimented with some replacement EEPROMs until finding the setting that works.
