## Meta meta
The main idea finding the flag is basic forensics technique.

#### Step-1:
After downloading `Findme.jpg`, I directly looked for Meta data.

<img src="Findme.jpg">

#### Step-2:
I tried `strings Findme.jpg | grep {`

I got the following output:

```
THM{3x1f_0r_3x17}
Q{(%
>{u],0
2=F{"
~{cg
b=+{
*qrz{
({=9
&.p{qp
Ej{L
@\{tty
_xr{
3+{y
3Na{
L^{G
(P>L{
e{@B
$Rh{
WGK{
Ggi{
A{M0>p
```

#### Step-3:
Finally the flag becomes:
`THM{ju57_d3c0d3_7h3_b453}`