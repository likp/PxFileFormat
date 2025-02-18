# PRESTEXT
**Type:** integer
**Length:** N/A
**Multiline:** No

From PX file format version 2010 and later the definition of PRESTEXT is
changed the prior versions defines it as:
States if texts or codes are shown for the keyword [VALUES](VALUES.md). Normally a file
is created so that texts are found after the keyword [VALUES](VALUES.md) and codes after
the keyword [CODES](CODES.md). This is equivalent to `PRESTEXT("variable name")=1;`
which is the default. If a user changes presentation from texts to codes and
saves the file the value codes will be saved after the keyword [VALUES](VALUES.md) and
value texts after the keyword [CODES](CODES.md). In this case the keyword `PRESTEXT` is
written as `PRESTEXT("variable name")=0`. This enables PC-Axis to know if
it is necessary to switch to codes if aggregation is selected. The user can also
decide to show both codes and texts for a value and in this case the keyword
is saved as `PRESTEXT("variable name")=2` or `PRESTEXT("variable name")=3`. `PRESTEXT` becomes 2 if it originally was 1 and 3 if it originally
was 0.
In the new definition the `PRESTEXT` is that it is an integer value between 0-
3 that describes how the value should be presented in a user interface. The
values text should always be defined by the [VALUES](VALUES.md) keyword and the
codes should always be defined by the [CODES](CODES.md) keyword.
- 0 - Only the value code should be displayed.
- 1 - Only the value text should be displayed.
- 2 - Both code and value should be displayed and the order should be
the code and then the value text.
- 3 - Both code and value should be displayed and the order should be
the value text then the value code.

**Example**
```
VALUES("region")="Albania","Austria",…
…
CODES("region")="AL","AT",…
…
PRESTEXT("region")=2
Since the PRESTEXT is set to 2 the values would be presented as
AL Albania
AT Austria
…
```
