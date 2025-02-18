# CELLNOTE
**Type:** text
**Length:** Lines of 256 characters
**Multiline:** Yes

Footnote for a single cell or a group of cells. Which cell it refers to is given
by values and variables. If a value is given as * the note refers to all values
for that variable. Only one value can be given for each variable. The values
are given in the variable order indicated by [STUB](STUB.md) and [HEADING](HEADING.md), starting
with [STUB](STUB.md).

**Example**
```
CELLNOTE("*","*","Örebro", "1995")="Lekebergs kommun has been excluded from Örebro";
```
