# Yhtälöryhmästä matriisiyhtälö

Lineaarinen yhtälöryhmä voidaan ratkaista helposti matriisilaskennan keinoin. Yhtälöryhmää 

$\begin{equation} \begin{cases}
a_{11} x_1+a_{12} x_2+ \ldots +a_{1n} x_n=b_1 \\
a_{21} x_1+a_{22} x_2+\ldots +a_{2n} x_n=b_2 \\
\vdots \\
a_{m1} x_1+a_{m2} x_2+ \ldots +a_{mn} x_n=b_m \end{cases} \end{equation}$

vastaavat kertolaskussa $AX=B$ matriisit

$A=\begin{bmatrix} a_{11}&a_{12}& \ldots &a_{1n} \\ a_{21}&a_{22}& \ldots &a_{2n}\\ \vdots & \vdots & \ddots & \vdots \\ a_{m1}&a_{m2}& \ldots &a_{mn}\end{bmatrix}, X=\begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n\end{bmatrix}$ ja $B=\begin{bmatrix} b_1 \\ b_2 \\ \vdots \\ b_m\end{bmatrix}$

sillä matriisien kertolaskun määritelmän perusteella pätee 

$\begin{equation} \begin{cases}
a_{11}x_1+a_{12} x_2+ \ldots +a_{1n} x_n=b_1 \\ a_{21} x_1+a_{22} x_2+ \ldots +a_{2n} x_n=b_2 \\ \vdots \\ a_{m1} x_1+a_{m2} x_2+ \ldots +a_{mn} x_n=b_m \end{cases} \end{equation} \Leftrightarrow AX=B$.

Usein tuntemattomia $x_1, x_2, \dots$ merkitään myös kirjaimilla $x, y, \dots$. Tämä on tietysti mahdollista vain silloin, kun kirjaimet aakkosissa eivät lopu kesken! 

Jos yhtälöitä ja tuntemattomia ei ole yhtä paljon ($m\neq n$), niin yhtälöryhmällä ei yleensä ole yksikäsitteistä ratkaisua. Tällaisia tapauksia ei käsitellä tässä materiaalissa. Jos taas yhtälöitä ja tuntemattomia on yhtä paljon ($m=n$), niin yhtälöryhmällä voi olla yksi, nolla tai äärettömän monta ratkaisua. Tarkastellaan tässä luvussa yksinkertaisinta tapausta eli sitä, jossa löytyy täsmälleen yksi ratkaisu.

Yhtälöryhmä ei välttämättä näytä samanlaiselta kuin yläreunan määritelmässä. Kirjaimia saattaa olla sekaisin eri puolilla yhtälöjä. Tällöin yhtälöjä pitää muokata. Kaikkien kirjainten pitää olla yhtälöiden vasemmalla puolella siten, että samojen kirjaimien kertoimet on yhdistetty. Jos vasemmalla puolella ei esiinny kirjainta, joka on kuitenkin muissa yhtälöissä, sen kertoimeksi voidaan kirjoittaa nolla. Vasemmalla puolella ei saa olla lukuja ilman kirjainkerrointa. Sen sijaan jokaisen yhtälön oikealla puolella tulee olla jokin luku - jos ei muuta, niin nolla.

::::{admonition} Esimerkki

Muodosta seuraavia yhtälöryhmiä vastaavat matriisiyhtälöt:

a) $\begin{equation}\begin{cases}2x+3y+4z=5\\-3x+2z=0\\x+2y+6z=0\end{cases}\end{equation}$

b) $\begin{equation}\begin{cases}2x+5=4y\\x+3y=2x+6\end{cases}\end{equation}$

:::{admonition} Ratkaisu
:class: tip, dropdown

a) Ratkaistava matriisiyhtälö on $AX=B$.

Matriisin $A$ kerätään tuntemattomien kertoimet. Toisessa yhtälössä ei esiinny kirjain $y$, mikä tarkoittaa sitä, että sen paikalle kerroinmatriisiin tulee nolla. Matriisiin $B$ kerätään yhtälöiden oikeat puolet. Yhtälöt ovat jo valmiiksi oikeassa esitysmuodossa.

Siis $A=\begin{bmatrix}2 & 3 & 4 \\ -3 & 0 & 2 \\ 1 & 2 & 6\end{bmatrix}$, $X=\begin{bmatrix}x\\y\\z\end{bmatrix}$ ja $B=\begin{bmatrix}5\\7\\0\end{bmatrix}$.

b) Muokataan kumpaakin yhtälöä erikseen oikeaan esitysmuotoon.

Ensimmäinen yhtälö: $2x+5=4y \Leftrightarrow 2x+5-4y=0 \Leftrightarrow 2x-4y=-5$

Toinen yhtälö: $x+3y=2x+6 \Leftrightarrow x-+3y-2x=6 \Leftrightarrow -x+3y=6$

Nyt yhtälöryhmä on saatu muotoon

$\begin{equation}\begin{cases}2x+-4y=-5\\-x+3y=6\end{cases}\end{equation}$

ja tätä vastaa matriisiyhtälö $AX=B$, missä

$A=\begin{bmatrix}2 & -4 \\ -1 & 3\end{bmatrix}$, $X=\begin{bmatrix}x\\y\end{bmatrix}$ ja $B=\begin{bmatrix}-5\\6\end{bmatrix}$.

:::

::::

## Ratkaisu käänteismatriisin avulla


Matriisiyhtälö $AX=B$ opittiin ratkaisemaan jo aiemmin. Koska $A^{-1}A=I$ ja $A^{-1}AX=IX=X$, niin tuntemattomat sisältävä matriisi saadaan kertomalla yhtälö $AX=B$ puolittain vasemmalta kerroinmatriisin $A$ käänteismatriisilla:

$AX=B \Leftrightarrow A^{-1}AX=A^{-1}B \Leftrightarrow X=A^{-1}B$.

Yhtälön ratkaisu tällä tavalla onnistuu, jos ja vain jos kerroinmatriisilla $A$ on olemassa käänteismatriisi, toisin sanoen $\det{A} \neq 0$.

Octavella yhtälöryhmän ratkaisu $X=A^{-1}B$ saadaan komennolla: inv(A)\*B

::::{admonition} Esimerkki 

Ratkaise yhtälöryhmä $\begin{equation} \begin{cases} 3x+5y=13\\x+2y=5 \end{cases} \end{equation}$ matriisimuodossa.

:::{admonition} Ratkaisu
:class: tip, dropdown

Muuttujien kertoimista muodostuu matriisi $A=\begin{bmatrix}3&5\\1&2\end{bmatrix}$ ja yhtälöiden oikeista puolista matriisi $B=\begin{bmatrix}13\\5\end{bmatrix}$. Nyt yhtälöryhmä voidaan kirjoittaa muodossa $AX=B$, missä $X=\begin{bmatrix}x\\y\end{bmatrix}$.

Matriisin $A$ determinantti on $\det{A}=3\cdot 2-5\cdot 1=6-5=1\neq 0$, joten käänteismatriisi $A^{-1}$ on olemassa.

Kun matriisi on tyyppiä $2\times 2$, niin käänteismatriisi on $A^{-1}=\frac{1}{ad-bc} \begin{bmatrix}d&-b\\-c&a\end{bmatrix}$. 

Nyt siis $A^{-1}=\frac{1}{3\cdot 2-5 \cdot 1} \begin{bmatrix} 2&-5 \\ -1&3 \end{bmatrix}=1\cdot \begin{bmatrix} 2&-5\\-1&3\end{bmatrix}=\begin{bmatrix}2&-5\\-1&3\end{bmatrix}$

ja $X=A^{-1}B=\begin{bmatrix}2&-5\\-1&3\end{bmatrix} \begin{bmatrix} 13\\5\end{bmatrix}=\begin{bmatrix}2\cdot 13-5\cdot 5\\-1\cdot 13+3\cdot 5\end{bmatrix}=\begin{bmatrix}26-25\\-13+15\end{bmatrix}=\begin{bmatrix}1\\2\end{bmatrix}$.

Ratkaisu on siis $x=1,y=2$. 

:::

::::

## Cramerin sääntö

Jos lineaariselle yhtälöryhmälle on olemassa yksi ratkaisu, se voidaan ratkaista myös matriisien determinanttien avulla. Menetelmää kutsutaan Cramerin säännöksi tai menetelmäksi. Tarkastellaan tässä yhtälöparia $\begin{bmatrix} a&b \\ c&d \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix}e \\ f\end{bmatrix}$.

Ensimmäisen muuttujan $x$ ratkaisemiseksi muokataan kerroinmatriisia korvaamalla ensimmäinen sarake yhtälöryhmän oikeat puolet sisältävällä matriisilla, jolloin saadaan matriisi $\begin{bmatrix} e&b \\ f&d \end{bmatrix}$.

Lasketaan tästä determinantti $D_x=de-bf$ ja jaetaan vielä kerroinmatriisin determinantilla $D=ad-bc$, jolloin saadaan vastaus: $x=\frac{D_x}{D}=\frac{de-bf}{ad-bc}$.

Toisen muuttujan ratkaisemiseksi muokataan kerroinmatriisia korvaamalla toinen sarake yhtälöryhmän oikeat puolet sisältävällä matriisilla, jolloin saadaan $\begin{bmatrix} a&e \\ c&f \end{bmatrix}$. Lasketaan tästä determinantti $D_y = af-ec$ ja jaetaan vielä kerroinmatriisin determinantilla $D=ad-bc$, jolloin saadaan vastaus: $y=\frac{D_y}{D}=\frac{af-ec}{ad-bc}$.

::::{admonition} Esimerkki

Ratkaise yhtälöpari $\begin{equation} \begin{cases} 3x+2y=-1 \\ 2x+y=3\end{cases} \end{equation}$ Cramerin menetelmällä.

:::{admonition} Ratkaisu
:class: tip, dropdown

Lasketaan tarvittavat determinantit: 

$D_x=\begin{vmatrix}-1&2\\3&1\end{vmatrix}=-1-6=-7$,

$D_y=\begin{vmatrix}3&-1\\2&3\end{vmatrix}=9-(-2)=11$,

$D=\begin{vmatrix}3&2\\2&1\end{vmatrix}=3-4=-1$.

Vastauksiksi saadaan $x=\frac{-7}{-1}=7, y=-\frac{11}{1}=-11$.

:::

::::