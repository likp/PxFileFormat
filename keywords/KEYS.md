# KEYS
**Type:** {VALUES, CODES}
**Length:** N/A
**Multiline:** No

If this keyword is used it must occur as many times as there are variables in
the stub. It contains the name of the variable and whether the key is taken
from [VALUES](VALUES.md) or [CODES](CODES.md). 

**Example**
```
KEYS("age")=VALUES;
KEYS("region")=CODES;
```
When it is used all data rows start with the Value/code of the variables in the
stub. See Description of [DATA](DATA.md).
