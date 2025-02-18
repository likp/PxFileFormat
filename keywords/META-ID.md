# META-ID
**Type:** text
**Length:** 256
**Multiline:** No

The `META-ID` keyword is used to reference a external meta information
about a table, variable or value.
I there is no subkey specified the `META-ID` refers to the cube
`META-ID="RT:12";`
If there is just one part sub key like below. Then the sub key must refer to a
variable and the data note is for that variable.
`META-ID("VARIABLE")="V:167";`
The example above states that the reference id for variable `VARIABLE` is
`V:167`.
If the sub key is divided into two parts. Then the first part of the sub key
refers to a variable and the second part refers to a value for that variable.
`META-ID("VARIABLE","VALUE")=VAL:232;`
The example above states that the reference id for value `VALUE` for variable
`VARIABLE` is `VAL:232`.
