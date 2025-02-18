# ROUNDING
**Type:** integer
**Length:** 0-1
**Multiline:** Yes

If rounding is missing then rounding will be done in accordance with
information in the pcax2000.ini file. If the keyword is missing then the
decimal rule in pcax2000.ini is used.
- Rounding = `0` means that .5 is rounded up if the previous figure is odd, 1.5
becomes 2.
- Rounding = `1` means that .5 is always rounded up. 0.5 becomes 1 and 1.5
becomes 2.
