# PARTITIONED
**Type:** complex text
**Length:** N/A
**Multiline:** Yes
This is used to partition a variable into levels, for instance
```
PARTITIONED("region")="municipality",1,4;
PARTITIONED("region")="subarea",5;
```
states that the first four positions for the regional values contain the
municipality code, and that the subarea code starts in position 5. Thus the
values for the variable region after the key word [VALUES](VALUES.md) must be written in
code, not plain text. Max 3 levels can be used, each gives start position and
length except for the last level where length is implied as rest of the code.
