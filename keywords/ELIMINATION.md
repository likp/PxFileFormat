# ELIMINATION
**Type:** {YES, NO, text}
**Length:** 256 characters
**Multiline:** Yes

States if and how a variable may be eliminated in a table. If the key word is
written as `ELIMINATION("variable name")="value name"` this value will be
used as an elimination value if the user does not select the variable to the
table. If the key word is written `ELIMINATION("variable name")=YES` this
means that the variable will be eliminated by the summing up of all the
values for that variable in the file.
