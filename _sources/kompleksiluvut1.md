# Kompleksiluvut

yleistä

Kompleksikonjugaatti

Kompleksiluvun itseisarvo

## Laskusääntöjä

Kompleksilukuja voidaan laskea yhteen, vähentää toisistaan, kertoa vakiolla ja kertoa toisillaan samoilla laskusäännöillä kuin polynomeja. Laskujen sievennyksessä on huomioitava, että $i^2=-1$. Lopputulos esitetään reaali- ja imaginaariosan summana.

::::{admonition} Esimerkki

Laske luvuilla $a=3+2i$ ja $b=4-5i$ laskut:

a) $a+b$, b) $a-b$, c) $2a+3b$, d) $ab$

:::{admonition} Ratkaisu
:class: tip, dropdown

a) $a+b = 3+2i + 4-5i = (3+4)+(2-5)i = 7-3i$

b) $a-b= 3+2i - (4-5i) = 3+2i-4+5i=(3-4)+(2+5)i = -1+7i$

c) $2a+3b=2(3+2i)+3(4-5i)=6+4i+12-15i = (6+12)+(4-15)i=18-11i$

d) $(3+2i)(4-5i)=3\cdot 4 +3\cdot (-5i)+2i\cdot 4 + 2i \cdot (-5i) $

$=12-15i+8i-10i^2 = 12-15i+8i-10\cdot (-1) $

$= 12-15i+8i+10 = (12+10)+(-15+8)i = 22-7i $

:::

::::

Kompleksilukujen osamääränkin $\frac{z_1}{z_2}$ laskussa tavoittaa on esitysmuoto $x+yi$. Tähän esitysmuotoon päästään laventamalla jakolasku nimittäjän $z_2$ kompleksikonjugaatilla $z_2^\*$. Tällöin nimittäjästi tulee reaaliluku, jolla voidaan jakaa osoittajan reaaliosa ja imaginaariosa erikseen.

::::{admonition} Esimerkki

Laske jakolasku $\frac{z_1}{z_2}$, kun $z_1=3+2i$ ja $z_2=1+4i$.

:::{admonition} Ratkaisu
:class: tip, dropdown

$\frac{z_1}{z_2}=\frac{z_1z_2^\*}{z_2 z_2^\*} $  

$\frac{z_1}{z_2}=\frac{(3+2i)(1+4i)}{(1+4i)(1-4i)} $

$\frac{z_1}{z_2}=\frac{3\cdot 1 + 3 \cdot 4i+2i\cdot 1 + 2i\cdot 4i}{1\cdot 1 + 1 \cdot (-4i)+4i\cdot 1 + 4i\cdot (-4i)}$

$\frac{z_1}{z_2}=\frac{3\cdot 1 + 3 \cdot 4i+2i\cdot 1 + 2i\cdot 4i}{1\cdot 1 + 1 \cdot (-4i)+4i\cdot 1 + 4i\cdot (-4i)}$

$\frac{z_1}{z_2}=\frac{3 + 12i+2i + 8i^2}{1-4i+4i 16i^2}$

$\frac{z_1}{z_2}=\frac{3 + 14i + 8i^2}{1-16i^2}$

$\frac{z_1}{z_2}=\frac{3 + 14i - 8}{1+16}$

$\frac{z_1}{z_2}=\frac{-11 + 14i}{17}$

$\frac{z_1}{z_2}=\frac{-11}{17} + \frac{14}{17}i$

Reaaliosien jakaminen keskenään ja imaginaariosien jakaminen keskenään ei ole kompleksilukujen jakolaskua. Laske huviksesi $\frac{\Re{z_1}}{\Re{z_2}}$ ja $\frac{\Im{z_1}}{\Im{z_2}}$. Sen jälkeen unohda, että olet koskaan tällaisen laskun laskenut.

:::

::::