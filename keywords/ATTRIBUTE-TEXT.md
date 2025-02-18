# ATTRIBUTE-TEXT
**Type:** text
**Length:** Lines of 256 characters
**Multiline:** Yes

This keyword specifies a textual representation of the attribute for
presentational purpose and it is optional.
Each attribute text is separate with a comma sign and written within quotes.
The `ATTRIBUTE-TEXT` keyword must occur after the [ATTRIBUTE-ID](ATTRIBUTE-ID.md)
and it is also language dependent. The order of the texts should be the same
as for the order of the ids.

**Example**
```
ATTRIBUTE-TEXT="Observation status","Observation confidence";
ATTRIBUTE-TEXT["sv"]="Status","Tillit";
```
