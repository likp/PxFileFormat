# CONTACT
**Type:** text
**Length:** Lines of 256 characters
**Multiline:** Yes

States the person who can give information about the statistics. Is written in
the form name, organization, telephone, fax, e-mail. Several persons can be
stated in the same text string and are then divided by the #-sign. Is shown
with the footnote. If there is a contents variable the keyword is repeated for
each value `CONTACT("value")="xx"`.

**Example**
```
CONTACT="Maria Svensson, SCB, +4619176800, +4619176900,
maria.svensson@scb.se";
```
