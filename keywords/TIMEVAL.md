# TIMEVAL
**Type:** text
**Length:** N/A
**Multiline:** Yes

New keyword in version 1.5 to enable the use of time series. After the
keyword is the name of the time variable given, e.g. `TIMEVAL(”time”)`.
`TLIST` gives information on timescale and timeperiods. The time periods
must be consecutive.
If the table contains the time periods `1994`, `1995`, `1996` `TIMEVAL` can be
written in this way:
```
TIMEVAL(”time”)=TLIST(A1, ”1994”-”1996”);
```
or
```
TIMEVAL(”time”)=TLIST(A1), ”1994”, ”1995”,"1996”;
```
The following formats are used:
- `A1` for annual statistics written as `CCYY` (`C` for century, `Y` for year)
- `H1` for halfyear in format `CCYYH`, where `H` is 1 or 2
- `Q1` for quarterly data written `CCYYQ`, where `Q` is 1 - 4.
- `M1` for monthly statistics written `CCYYMM`
- `W1` for weekly data written `CCYYWW`

`TIMEVAL` is used in PC-AXIS version 1.7 when converting to Aremos and
Gesmes/Ecoser format. It is also used for start and stop time in list of
contents in HTML-format.
The variable time can be used both after the keyword [VALUES](VALUES.md) and after
`TIMEVAL`. If both exist `TIMEVAL` must be placed after [VALUES](VALUES.md). If only
`TIMEVAL` exists [VALUES](VALUES.md) for time are created as follows:
Time scale time periods shown as
```
A1 1995, 1996, 1997
H1 1995H1, 1995H2, 1996H1
Q1 1995Q1, 1995Q2, 1995Q3
M1 1995M01, 1995M02, 1995M03
W1 1995W01, 1995W02, 1005W03
```
