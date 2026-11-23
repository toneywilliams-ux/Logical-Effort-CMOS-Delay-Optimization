# Logical-Effort Hand Calculations

All values in this file are transcribed from the manual design calculations used in the project. The method is first-order and is not a substitute for PDK-based characterization.

## Reference input capacitance

\[
C_{inv}\propto W_n+W_p=0.4+0.8=1.2
\]

## Gate logical efforts

\[
g_1=1
\]

For NAND3, with three series NMOS devices and the reference sizing used in the project:

\[
g_2=\frac{1.2+0.8}{1.2}=\frac53=1.667
\]

For NOR2:

\[
g_3=\frac{0.4+1.6}{1.2}=\frac53=1.667
\]

## Path effort

\[
G=g_1g_2g_3=1\times\frac53\times\frac53=\frac{25}{9}=2.778
\]

\[
B=1,\quad H=25
\]

\[
F=GBH=2.778\times1\times25=69.444
\]

For \(N=3\):

\[
f=F^{1/3}\approx4.108
\]

Electrical efforts:

| Stage | Gate | \(g_i\) | \(h_i=f/g_i\) |
|---|---|---:|---:|
| 1 | Inverter | 1.000 | 4.108 |
| 2 | NAND3 | 1.667 | 2.465 |
| 3 | NOR2 | 1.667 | 2.465 |

## Scaling factors and dimensions

\[
X=\frac{h_1}{g_2}=\frac{4.108}{1.667}\approx2.465
\]

NAND3:

\[
W_{n}=1.2\times2.465=2.958\ \mu m
\]

\[
W_{p}=0.8\times2.465=1.972\ \mu m
\]

\[
Y=\frac{h_1h_2}{g_3}=\frac{4.108\times2.465}{1.667}\approx6.078
\]

NOR2:

\[
W_{n}=0.4\times6.078=2.431\ \mu m
\]

\[
W_{p}=1.6\times6.078=9.725\ \mu m
\]

## Parasitic and normalized delay estimate

The first-order parasitic delays used were \(p_{INV}=1\), \(p_{NAND3}=3\), and \(p_{NOR2}=2\).

\[
P=1+3+2=6
\]

\[
D_{min}=Nf+P=3(4.108)+6\approx18.324
\]

This is a dimensionless logical-effort delay estimate, not a delay in picoseconds.
