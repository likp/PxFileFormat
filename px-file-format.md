# PX file format 2013
## Readers guide
### What this instruction covers
This manual describes how a PC-Axis PX file is constructed.
The manual is intended for people that wants to get a introduction of how to
use and to extend the Core part of the PC-Axis SDK.
The reader are not required have any type of PC-Axis experience to
understand the content but it helps. 

### How this guide is organized
The document is divided into two part. The first part defines how the PX file
structure works. The second part defined all keywords used in the PC-Axis
File Format.

### Related documents
Earlier versions of the PC-Axis file format.

## Getting started
We must first try to explain the basic structure of the PX-file. PX-files
consist of keywords that describes the contents or the data cube. Some
keywords are mandatory while some are optional.
Some keywords have an language option and some keywords have a sub key
and there is always at least one value specified for a keyword.
Some basic rules for how keywords are written
- The keyword is mandatory.
- Language is optional.
- Language is always written within square brackets.
- Language is always written immediately after the keyword.
- The sub key is optional.
- The sub key is always written within parentheses.
- The sub key is written is written after language if present otherwise it is written after the keyword.
- Value(s) are mandatory.
- Value(s) are always written after the equal sign.
- If there are multiple values each value is written within quotation marks and are separated by a comma sign.
- If there is only one value then it can be written without any quotation marks.
- Values(s) are delimited with quotation marks which means that a value itself cannot contain a quotation mark.
- The end of values (and the beginning of a new keyword) is always
marked with a semicolon.
- Longer texts are divided into several records (except for value text orvariable names which must in one line when in parentheses after a keyword).

```
KEYWORD[LANGUAGE](SUB-KEY)="VALUE_1","VALUE_2", …;
KEYWORD[LANGUAGE](SUB-KEY)=VALUE_1;
KEYWORD[LANGUAGE]="VALUE_1","VALUE_2", …;
KEYWORD (SUB-KEY)="VALUE_1","VALUE_2", …;
KEYWORD[LANGUAGE]=VALUE_1;
KEYWORD(SUB-KEY)=VALUE_1;
```
The file itself is divided into two parts one metadata part and the data part.
The data part starts after the keyword [DATA](keywords/DATA.md).
If the keyword [CHARSET](keywords/CHARSET.md) is missing it means that all texts are in DOS text
format, so that the same files can be used both in the DOS and the Windows
version of PC-Axis.
Starting with version 2005 it is possible to have more than one language in a
PX file. The second language is repeated for all necessary keywords.
`CONTENTS="Population";`, `CONTENTS[sv]=”Befolkning”;` etc. Which
languages are available are given in the keyword [LANGUAGES](keywords/LANGUAGES.md).

## Keywords
### Alphabetical list of keywords

|Keyword                                                |Mandatory|Multiplicity|Language dependent|Default value |
|-------------------------------------------------------|---------|------------|------------------|--------------|
|[AGGREGALLOWED](keywords/AGGREGALLOWED.md)             |No       |0-1         |No                |YES           |
|[ATTRIBUTE-ID](keywords/ATTRIBUTE-ID.md)               |No       |0-1         |No                |              |
|[ATTRIBUTE-TEXT](keywords/ATTRIBUTE-TEXT.md)           |No       |0-1         |Yes               |              |
|[ATTRIBUTES](keywords/ATTRIBUTES.md)                   |No       |0-?         |No                |              |
|[AUTOPEN](keywords/AUTOPEN.md)                         |No       |0-1         |No                |NO            |
|[AXIS-VERSION](keywords/AXIS-VERSION.md)               |No       |0-1         |No                |              |
|[BASEPERIOD](keywords/BASEPERIOD.md)                   |No       |0-?         |Yes               |              |
|[CELLNOTE](keywords/CELLNOTE.md)                       |No       |0-?         |Yes               |              |
|[CELLNOTEX](keywords/CELLNOTEX.md)                     |No       |0-?         |Yes               |              |
|[CFPRICES](keywords/CFPRICES.md)                       |No       |0-?         |No                |              |
|[CHARSET](keywords/CHARSET.md)                         |No       |0-1         |No                |              |
|[CODEPAGE](keywords/CODEPAGE.md)                       |No       |0-1         |No                |iso-8859-1    |
|[CODES](keywords/CODES.md)                             |Yes      |0-16        |No                |              |
|[CONFIDENTIAL](keywords/CONFIDENTIAL.md)               |No       |0-1         |No                |0             |
|[CONTACT](keywords/CONTACT.md)                         |No       |0-?         |Yes               |              |
|[CONTENTS](keywords/CONTENTS.md)                       |Yes      |1           |Yes               |              |
|[CONTVARIABLE](keywords/CONTVARIABLE.md)               |Yes      |0-1         |Yes               |              |
|[COPYRIGHT](keywords/COPYRIGHT.md)                     |No       |0-1         |No                |NO            |
|[CREATION-DATE](keywords/CREATION-DATE.md)             |Yes      |0-1         |No                |              |
|[DATA](keywords/DATA.md)                               |Yes      |1           |No                |              |
|[DATABASE](keywords/DATABASE.md)                       |No       |0-1         |Yes               |              |
|[DATANOTE](keywords/DATANOTE.md)                       |No       |0-?         |Yes               |              |
|[DATANOTECELL](keywords/DATANOTECELL.md)               |No       |0-1         |Yes               |              |
|[DATANOTESUM](keywords/DATANOTESUM.md)                 |No       |0-1         |Yes               |              |
|[DATASYMBOL1](keywords/DATASYMBOL1.md)                 |No       |0-1         |Yes               |.             |
|[DATASYMBOL2](keywords/DATASYMBOL2.md)                 |No       |0-1         |Yes               |..            |
|[DATASYMBOL3](keywords/DATASYMBOL3.md)                 |No       |0-1         |Yes               |...           |
|[DATASYMBOL4](keywords/DATASYMBOL4.md)                 |No       |0-1         |Yes               |....          |
|[DATASYMBOL5](keywords/DATASYMBOL5.md)                 |No       |0-1         |Yes               |.....         |
|[DATASYMBOL6](keywords/DATASYMBOL6.md)                 |No       |0-1         |Yes               |......        |
|[DATASYMBOLNIL](keywords/DATASYMBOLNIL.md)             |No       |0-1         |Yes               |-             |
|[DATASYMBOLSUM](keywords/DATASYMBOLSUM.md)             |No       |0-1         |Yes               |              |
|[DAYADJ](keywords/DAYADJ.md)                           |0-1      |0-?         |Yes               |NO            |
|[DECIMALS](keywords/DECIMALS.md)                       |Yes      |1           |No                |              |
|[DEFAULT-GRAPH](keywords/DEFAULT-GRAPH.md)             |No       |0-1         |No                |              |
|[DESCRIPTION](keywords/DESCRIPTION.md)                 |No       |0-1         |Yes               |              |
|[DESCRIPTIONDEFAULT](keywords/DESCRIPTIONDEFAULT.md)   |No       |0-1         |No                |              |
|[DIRECTORY-PATH](keywords/DIRECTORY-PATH.md)           |No       |0-1         |No                |              |
|[DOMAIN](keywords/DOMAIN.md)                           |No       |0-16        |No                |              |
|[DOUBLECOLUMN](keywords/DOUBLECOLUMN.md)               |No       |0-16        |Yes               |NO            |
|[ELIMINATION](keywords/ELIMINATION.md)                 |No       |0-16        |Yes               |NO            |
|[FIRST-PUBLISHED](keywords/FIRST-PUBLISHED.md)         |No       |0-1         |No                |              |
|[HEADING](keywords/HEADING.md)                         |Yes      |(0)-1       |Yes               |              |
|[HIERARCHIES](keywords/HIERARCHIES.md)                 |No       |0-1         |Yes               |              |
|[HIERARCHYLEVELS](keywords/HIERARCHYLEVELS.md)         |No       |0-1         |Yes               |              |
|[HIERARCHYLEVELSOPEN](keywords/HIERARCHYLEVELSOPEN.md) |No       |0-1         |Yes               |              |
|[HIERARCHYNAMES](keywords/HIERARCHYNAMES.md)           |No       |0-1         |Yes               |              |
|[INFO](keywords/INFO.md)                               |No       |0-1         |Yes               |              |
|[INFOFILE](keywords/INFOFILE.md)                       |No       |0-1         |Yes               |              |
|[KEYS](keywords/KEYS.md)                               |No       |0-16        |Yes               |              |
|[LANGUAGE](keywords/LANGUAGE.md)                       |Yes      |1           |No                |              |
|[LANGUAGES](keywords/LANGUAGES.md)                     |No       |0-1         |No                |              |
|[LAST-UPDATED](keywords/LAST-UPDATED.md)               |No       |0-1         |No                |              |
|[LINK](keywords/LINK.md)                               |No       |0-1         |Yes               |              |
|[MAP](keywords/MAP.md)                                 |No       |0-1         |Yes               |              |
|[MATRIX](keywords/MATRIX.md)                           |Yes      |1           |No                |              |
|[META-ID](keywords/META-ID.md)                         |No       |0-?         |Yes               |              |
|[NEXT-UPDATE](keywords/NEXT-UPDATE.md)                 |No       |0-1         |No                |              |
|[NOTE](keywords/NOTE.md)                               |No       |0-?         |Yes               |              |
|[NOTEX](keywords/NOTEX.md)                             |No       |0-?         |Yes               |              |
|[OFFICIAL-STATISTICS](keywords/OFFICIAL-STATISTICS.md) |No       |0-1         |No                |NO            |
|[PARTITIONED](keywords/PARTITIONED.md)                 |No       |0-16        |Yes               |              |
|[PRECISION](keywords/PRECISION.md)                     |No       |0-?         |Yes               |              |
|[PRESTEXT](keywords/PRESTEXT.md)                       |No       |0-16        |No                |1             |
|[PX-SERVER](keywords/PX-SERVER.md)                     |No       |0-1         |No                |              |
|[REFPERIOD](keywords/REFPERIOD.md)                     |No       |0-1/0-?     |Yes               |              |
|[ROUNDING](keywords/ROUNDING.md)                       |No       |0-1         |No                |              |
|[SEASADJ](keywords/SEASADJ.md)                         |No       |0-?         |No                |NO            |
|[SHOWDECIMALS](keywords/SHOWDECIMALS.md)               |No       |0-1         |No                |              |
|[SOURCE](keywords/SOURCE.md)                           |No       |0-1         |Yes               |              |
|[STOCKFA](keywords/STOCKFA.md)                         |No       |0-?         |Yes               |              |
|[STUB](keywords/STUB.md)                               |Yes      |0-1         |Yes               |              |
|[SUBJECT-AREA](keywords/SUBJECT-AREA.md)               |Yes      |1           |Yes               |              |
|[SUBJECT-CODE](keywords/SUBJECT-CODE.md)               |Yes      |1           |No                |              |
|[SURVEY](keywords/SURVEY.md)                           |No       |0-1         |Yes               |              |
|[SYNONYMS](keywords/SYNONYMS.md)                       |No       |0-1         |No                |              |
|[TABLEID](keywords/TABLEID.md)                         |No       |0-1         |No                |              |
|[TIMEVAL](keywords/TIMEVAL.md)                         |No       |0-1         |Yes               |              |
|[TITLE](keywords/TITLE.md)                             |Yes      |  1         |Yes               |              |
|[UNITS](keywords/UNITS.md)                             |Yes      |1-?         |Yes               |              |
|[UPDATE-FREQUENCY](keywords/UPDATE-FREQUENCY.md)       |No       |0-1         |No                |              |
|[VALUENOTE](keywords/VALUENOTE.md)                     |No       |0-?         |Yes               |              |
|[VALUENOTEX](keywords/VALUENOTEX.md)                   |No       |0-?         |Yes               |              |
|[VALUES](keywords/VALUES.md)                           |Yes      |1-16        |Yes               |              |
|[VARIABLE-TYPE](keywords/VARIABLE-TYPE.md)             |No       |0-16        |No                |              |


### Recommended order of the keywords
Some keywords must be written before some other keywords e.g. [STUB](keywords/STUB.md) and
[HEADING](keywords/HEADING.md) must precede [VALUES](keywords/VALUES.md) and [CODES](keywords/CODES.md). Here follows a list of
recommended order for how keywords should be written in PX-files though
applications should not depend on that this order is used.

- [CHARSET](keywords/CHARSET.md)
- [AXIS-VERSION](keywords/AXIS-VERSION.md)
- [CODEPAGE](keywords/CODEPAGE.md)
- [LANGUAGE](keywords/LANGUAGE.md)
- [LANGUAGES](keywords/LANGUAGES.md)
- [CREATION-DATE](keywords/CREATION-DATE.md)
- [NEXT-UPDATE](keywords/NEXT-UPDATE.md)
- [PX-SERVER](keywords/PX-SERVER.md)
- [DIRECTORY-PATH](keywords/DIRECTORY-PATH.md)
- [UPDATE-FREQUENCY](keywords/UPDATE-FREQUENCY.md)
- [TABLEID](keywords/TABLEID.md)
- [SYNONYMS](keywords/SYNONYMS.md)
- [DEFAULT-GRAPH](keywords/DEFAULT-GRAPH.md)
- [DECIMALS](keywords/DECIMALS.md)
- [SHOWDECIMALS](keywords/SHOWDECIMALS.md)
- [ROUNDING](keywords/ROUNDING.md)
- [MATRIX](keywords/MATRIX.md)
- [AGGREGALLOWED](keywords/AGGREGALLOWED.md)
- [AUTOPEN](keywords/AUTOPEN.md)
- [SUBJECT](keywords/SUBJECT.md)
- [CODE](keywords/CODE.md)
- [SUBJECT-AREA](keywords/SUBJECT-AREA.md)
- [CONFIDENTIAL](keywords/CONFIDENTIAL.md)
- [COPYRIGHT](keywords/COPYRIGHT.md)
- [DESCRIPTION](keywords/DESCRIPTION.md)
- [TITLE](keywords/TITLE.md)
- [DESCRIPTIONDEFAULT](keywords/DESCRIPTIONDEFAULT.md)
- [CONTENTS](keywords/CONTENTS.md)
- [UNITS](keywords/UNITS.md)
- [STUB](keywords/STUB.md)
- [HEADING](keywords/HEADING.md)
- [CONTVARIABLE](keywords/CONTVARIABLE.md)
- [VALUES](keywords/VALUES.md)
- [TIMEVAL](keywords/TIMEVAL.md)
- [CODES](keywords/CODES.md)
- [DOUBLECOLUMN](keywords/DOUBLECOLUMN.md)
- [PRESTEXT](keywords/PRESTEXT.md)
- [DOMAIN](keywords/DOMAIN.md)
- [VARIABLE-TYPE](keywords/VARIABLE-TYPE.md)
- [HIERARCHIES](keywords/HIERARCHIES.md)
- [HIERARCHYLEVELS](keywords/HIERARCHYLEVELS.md)
- [HIERARCHYLEVELSOPEN](keywords/HIERARCHYLEVELSOPEN.md)
- [HIERARCHYNAMES](keywords/HIERARCHYNAMES.md)
- [MAP](keywords/MAP.md)
- [PARTITIONED](keywords/PARTITIONED.md)
- [ELIMINATION](keywords/ELIMINATION.md)
- [PRECISION](keywords/PRECISION.md)
- [LAST-UPDATED](keywords/LAST-UPDATED.md)
- [STOCKFA](keywords/STOCKFA.md)
- [CFPRICES](keywords/CFPRICES.md)
- [DAYADJ](keywords/DAYADJ.md)
- [SEASADJ](keywords/SEASADJ.md)
- [UNITS](keywords/UNITS.md)
- [CONTACT](keywords/CONTACT.md)
- [REFPERIOD](keywords/REFPERIOD.md)
- [BASEPERIOD](keywords/BASEPERIOD.md)
- [DATABASE](keywords/DATABASE.md)
- [SOURCE](keywords/SOURCE.md)
- [SURVEY](keywords/SURVEY.md)
- [LINK](keywords/LINK.md)
- [INFOFILE](keywords/INFOFILE.md)
- [FIRST-PUBLISHED](keywords/FIRST-PUBLISHED.md)
- [META-ID](keywords/META-ID.md)
- [OFFICIAL-STATISTICS](keywords/OFFICIAL-STATISTICS.md)
- [INFO](keywords/INFO.md)
- [NOTEX](keywords/NOTEX.md)
- [NOTE](keywords/NOTE.md)
- [VALUENOTEX](keywords/VALUENOTEX.md)
- [VALUENOTE](keywords/VALUENOTE.md)
- [CELLNOTEX](keywords/CELLNOTEX.md)
- [CELLNOTE](keywords/CELLNOTE.md)
- [DATASYMBOL1](keywords/DATASYMBOL1.md)
- [DATASYMBOL2](keywords/DATASYMBOL2.md)
- [DATASYMBOL3](keywords/DATASYMBOL3.md)
- [DATASYMBOL4](keywords/DATASYMBOL4.md)
- [DATASYMBOL5](keywords/DATASYMBOL5.md)
- [DATASYMBOL6](keywords/DATASYMBOL6.md)
- [DATASYMBOLSUM](keywords/DATASYMBOLSUM.md)
- [DATASYMBOLNIL](keywords/DATASYMBOLNIL.md)
- [DATANOTECELL](keywords/DATANOTECELL.md)
- [DATANOTESUM](keywords/DATANOTESUM.md)
- [DATANOTE](keywords/DATANOTE.md)
- [KEYS](keywords/KEYS.md)
- [ATTRIBUTE-ID](keywords/ATTRIBUTE-ID.md)
- [ATTRIBUTE-TEXT](keywords/ATTRIBUTE-TEXT.md)
- [ATTRIBUTES](keywords/ATTRIBUTES.md)
- [PRECISION](keywords/PRECISION.md)
- [DATA](keywords/DATA.md)
