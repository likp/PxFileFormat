# ATTRIBUTES
**Type:** text
**Length:** Lines of 256 characters
**Multiline:** Yes

This keyword specifies all attributes for as single observation value. Each
attribute value is separated with a comma sign and written within quotes. The
attribute values must appear in the same order as they appeared in the
[ATTRIBUTE-ID](ATTRIBUTE-ID.md) keyword.
The `ATTRIBUTES` keyword must be written after [ATTRIBUTE-ID](ATTRIBUTE-ID.md) and the
[CODES](CODES.md) keyword. Which observation it refers to is given by the key which is
written within parenthesis after the keyword and before the equal sign.
The format of the key is one value code for each variable in the order
indicated by [STUB](STUB.md) and [HEADING](HEADING.md) starting with the variables in the [STUB](STUB.md).
If the attribute key is missing then this will indicate the default values for the
attributes for all measures that do not have any `ATTRIBUTES` specified.
This is also referred to as the default attributes. The default attributes should
always be specified in order to save space and unnecessary repetition.

**Example**
```
ATTRIBUTES("01","A01","2005")="A","P";
ATTRIBUTES="A","F";
```
