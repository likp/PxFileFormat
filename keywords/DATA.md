# DATA
**Type:** integer/text
**Length:** N/A
**Multiline:** Yes

The keyword `DATA` must be placed at the end of the file, followed by all the
data cells or if [KEYS](KEYS.md) are used the variable values and all data cells that differ
from `0`.

## File without [KEYS](KEYS.md)
After the key word follows all data cells that belong to the table.
In most cases the cells are written with one record per line in the table. The
number of records will thus be determined by the number of values in the
stub. The length of the records depends upon the number of values in the
heading, and also upon the size of figures.
Table cells that contain a dash, one, two, three, four, five or six dots should
be within quotation marks.
For data without keys it is possible to write all cells in just one record,
terminated by a semicolon.
PC-Axis accepts the delimiters comma, space, semicolon, tabulator. The
different delimiters are synonyms and can be mixed in the file.
Recommended delimiter is space.

## Files with [KEYS](KEYS.md)
For every variable in the stub is indicated the value for the variable within
quotation marks, comma separated, followed by all data cells for that row
(no quotation marks, space separated).

Whether the text from [VALUES](VALUES.md) or from [CODES](CODES.md) are used for a variable is
indicated by the keyword `KEYS(”var”)=CODES` or
`KEYS(”var”)=VALUES`. It is possible to use [VALUES](VALUES.md) from one variable
and [CODES](CODES.md) for another in the same file.
Rows that only contain 0 (zeros) are excluded from the file
One - six dots
Data that is missing is stored as one, two, three, four, five or six dots.
It is not possible to get a dot or two dots by excluding a value. Thus, you
cannot write `1,,2,3` in order to get `1,".",3,4`
For PC-Axis version prior to 2005 a dash is presented as 0 and saved as 0.
Thus, you cannot afterwards find out if the original value was - or 0. Starting
with 2005 PC-Axis keeps track on which cells are – and the keyword
[DATASYMBOLNIL](DATASYMBOLNIL.md) can be used to show something else in the table.
How the dots are shown on screen is determined by the keywords
[DATASYMBOL1](DATASYMBOL1.md), etc. If these keywords are missing the presentation is
taken from PC-Axis language files.

## Number of decimals when a file is saved
The keyword [DECIMALS](DECIMALS.md) determines the number of decimals to be saved. If
the file also contains the key word [PRECISION](PRECISION.md), PC-AXIS saves as many
decimals as corresponds to the largest number specified by [DECIMALS](DECIMALS.md) or
[PRECISION](PRECISION.md). All cells are stored with the same number of decimals.
