# PRECISION
**Type:** integer
**Length:** N/A
**Multiline:** No
Can occur for single values. Determines that the value shall be presented
with a number of decimals that differs from the keyword
[SHOWDECIMALS](SHOWDECIMALS.md). Is to be written as
`PRECISION("variable name","value name")=n` where n is a figure between `1`
and `6`. The number of decimals for precision must be higher than the number
of decimals for [SHOWDECIMALS](SHOWDECIMALS.md) to have any effect.
