# ATTRIBUTE-ID
**Type:** text
**Length:** 256 characters per value
**Multiline:** Yes

This keyword list the identities of all attributes. Indirectly it also specifies the
number of attributes.
Each attribute id is separate with a comma sign and it is written within
quotes.
The `ATTRIBUTE-ID` keyword must be written before the [ATTRIBUTES](ATTRIBUTES.md)
keyword and must exist if the [ATTRIBUTES](ATTRIBUTES.md) keyword is present.
The `ATTRIBUTE-ID` keyword is multilingual, that is you do not have to
specify it for each language.

**Example**
```
ATTRIBUTE-ID="ObsStatus","ObsConf";
```
