# DATANOTE
**Type:** text
**Length:** 20 characters
**Multiline:** Yes

The `DATANOTE` keyword is used to indicate that a note exists for a certain
element of the statistical cube
If no sub key is specified like below the data note * is valid for the hole
table.
`DATANOTE="*";`
If there is just one part sub key like below. Then the sub key must refer to a
variable and the data note is for that variable.
`DATANOTE("VARIABLE")="*";`
The example above states that the data note * should be displayed for
variable `VARIABLE`.
If the sub key is divided into two parts. Then the first part of the sub key
refers to a variable and the second part refers to a value for that variable.
`DATANOTE("VARIABLE","VALUE")="*";`
The example above states that the data note * should be displayed for value
`VALUE` for variable `VARIABLE`.
The keyword is multilingual so different data notes can be used for different
languages.
It is recommended to add the data note to the note text. E.g. if you have a
note on the time period 2010 it could look something like this in the PX file.

```
DATANOTE("tid","2010")="*";
VALUENOTE("tid","2010")="* Preliminary results";
```
