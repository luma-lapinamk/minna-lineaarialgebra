# Yhtälöryhmät

Yhtälöparissa on kaksi yhtälöä ja kaksi tuntematonta. Yhtälöryhmissä yhtälöitä ja tuntemattomia on vielä useampia. Tarkoituksena on löytää tuntemattomille sellaiset arvot, että ne toteuttavat molemmat tai kaikki yhtälöt.

Seuraavaksi esitellään perusalgebran menetelmiä yhtälöparien ratkaisuun. Sen jälkeen tutustutaan, miten yhtälöryhmiä voidaan tehokkaasti ratkoa matriisilaskennan avulla.

Yhtälöparia, joka voidaan esittää muodossa 

$\begin{equation}
    \begin{cases}
      a_1 x + b_1 y = c_1\\
      a_2 x + b_2 y = c_2
    \end{cases}\
\end{equation}$

sanotaan lineaariseksi yhtälöpariksi. Lineaarinen yhtälöpari sisältää siis kaksi yhtälöä, jotka ovat ensimmäisen asteen yhtälöitä muuttujien $x$ ja $y$ suhteen. Lineaarinen yhtälöpari voidaan ratkaista sijoitusmenetelmällä tai eliminointimenetelmällä. 
    
## Sijoitusmenetelmä
    
Sijoitusmenetelmässä ratkaistaan jommastakummasta yhtälöstä toinen tuntematon. Saatu lauseke sijoitetaan toiseen yhtälöön tuntemattoman paikalle. Lopuksi ratkaistaan toinen tuntematon.

**Esim.** Ratkaise yhtälöpari $\begin{equation}
    \begin{cases}
      x - y = 2\\
      2 x + 3 y = 9
    \end{cases}\
\end{equation}$

:::{admonition} Ratkaisu
:class: tip, dropdown

Vaihtoehtoja sijoitusmenetelmällä ratkaisun ensimmäiseen vaiheeseen on neljä: ratkaistaan ensimmäisestä yhtälöstä $x$, ensimmäisestä yhtälöstä $y$, toisesta yhtälöstä $x$ tai toisesta yhtälöstä $y$.

Jos esimerkiksi ratkaistaan ylemmästä yhtälöstä ensin $x=2+y$ ja sijoitetaan se alempaan yhtälöön, saadaan 

$2(2+y)+3y=9 \leftrightarrow  4+2y+3y=9 \leftrightarrow 5y=5 \leftrightarrow y=1$.

Tämän avulla voidaan ratkaista vielä ensimmäisestä yhtälöstä $x=2+y=2+1=3$.

Kaikilla muillakin esitetyillä tavoilla vastaukseksi tulee $x=3,y=1$. Jos et usko, kokeile.

:::


## Eliminaatiomenetelmä

Eliminaatiomenetelmässä molemmat yhtälöt kerrotaan puolittain jollakin nollasta poikkeavalla luvulla (kumpikin yhtälö eri luvulla). Sen jälkeen yhtälöt lasketaan puolittain yhteen. Kertolaskussa käytettävät kertoimet on valittava siten, että yhteenlaskussa jompikumpi muuttujista häviää – käytännössä siten, että joko muuttujan $x$ tai muuttujen $y$ kertoimista tulee toistensa vastalukuja.


**Esim.** Ratkaise yhtälöpari $\begin{equation} \begin{cases} 2x+5y=12 \\ 3x+2y=7\end{cases} \end{equation}$

:::{admonition} Ratkaisu
:class: tip, dropdown

Voidaan kertoa ylempi yhtälö luvulla 3 ja alempi yhtälö luvulla -2:

$\begin{equation} \begin{cases} 3\cdot 2x+3\cdot 5y=3\cdot 12 \\ -2\cdot 3x+ (-2)\cdot 2y=-2\cdot 7\end{cases} \end{equation}$

$\begin{equation} \begin{cases} 6x+15y=36 \\ -6x-4y=-14\end{cases} \end{equation}$

Laskemalla yhtälöt nyt yhteen (vasemmat puolet erikseen ja oikeat puolet erikseen) saadaan

$6x+15y-6x-4y=36-14$

eli sievennettynä

$11y=22$

josta ratkeaa

$y=2$.

Nyt voidaan sijoittaa saatu tulos kumpaan tahansa alkuperäisistä yhtälöistä:

$2x+5\cdot 2=12 \leftrightarrow 2x+10=12 \leftrightarrow 2x=2 \leftrightarrow x=1$

tai

$3x+2\cdot 2=7 \leftrightarrow 3x+4=7 \leftrightarrow 3x=3 \leftrightarrow x=1$.
:::

## Ratkaisujen määrä
 
Yhtälöryhmällä on joskus äärettömän paljon tai ei ollenkaan ratkaisuja.

**Esim.** Ratkaise yhtälöpari $\begin{equation} \begin{cases} 2x+y=5 \\ 4x+2y=10 \end{cases} \end{equation}$  eliminaatiomenetelmällä.

:::{admonition} Ratkaisu
:class: tip, dropdown

Kertomalla ylempi yhtälö luvulla -2 saadaan $-4x-2y=-10$. 

Lasketaan yhteen tämä ja alin yhtälö, ja ratkaistaan $x$:

$-4x-2y+4x+2y=-10+10 \leftrightarrow  0\cdot x=0$

Huomataan, että mikä tahansa $x$:n arvo toteuttaa yhtälön. Muuttujan $x$ tilalle voidaan valita ns. parametri eli vapaasti valittava lukuarvo, jota merkitään $x=t \in \Re$. Tämä voidaan sijoittaa ylempään yhtälöön, jolloin saadaan $y=5-2t$. Yhtälöparin ratkaisu on siis $x=t, y=5-2t, t \in \Re$. Yhtälöparilla on äärettömän monta ratkaisua.

:::

**Esim.** Ratkaise yhtälöpari $\begin{equation} \begin{cases} 2x+y=5 \\ 4x+y=11 \end{cases} \end{equation}$ eliminaatiomenetelmällä.

:::{admonition} Ratkaisu
:class: tip, dropdown

Jälleen ylemmästä yhtälöstä saadaan luvulla kertomalla $-4x-2y=-10$. Kun lasketaan se yhteen alemman yhtälön kanssa, saadaan: 

$-4x-2y+4x+2y=-10+11 \leftrightarrow  0\cdot x=1$.

Yhtälö ei toteudu millään luvulla $x$. Yhtälöparilla ei ole ratkaisua.

:::

## Determinanttimenetelmä (Cramerin sääntö)

Jos yhtälöpari on muotoa $\begin{equation} \begin{cases} ax+by=e \\ cx+dy=f \end{cases} \end{equation}$ niin ratkaisut saadaan $2 \times 2$ –tyyppisten determinanttien avulla. 

Tällöin yhtälöpari esitetään muodossa $\begin{bmatrix} a&b \\ c&d \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix}e \\ f\end{bmatrix}$.

Ensimmäisen muuttujan $x$ ratkaisemiseksi muokataan kerroinmatriisia korvaamalla ensimmäinen sarake yhtälöryhmän oikeat puolet sisältävällä matriisilla, jolloin saadaan $\begin{bmatrix} e&b \\ f&d \end{bmatrix}$.

Lasketaan tästä determinantti $D_x=\begin{vmatrix} e&b\\f&d\end{vmatrix}=de-bf$ ja jaetaan vielä kerroinmatriisin determinantilla $D=\begin{vmatrix}a&b\\c&d\end{vmatrix}=ad-bc$, jolloin saadaan vastaus: $x=\frac{D_x}{D}=\frac{de-bf}{ad-bc}$.

Toisen muuttujan ratkaisemiseksi muokataan kerroinmatriisia korvaamalla toinen sarake yhtälöryhmän oikeat puolet sisältävällä matriisilla, jolloin saadaan $\begin{bmatrix} a&e \\ c&f \end{bmatrix}$. 

Lasketaan tästä determinantti $D_y = \begin{vmatrix} a&e \\ c&f \end{vmatrix}=af-ec$ ja jaetaan vielä kerroinmatriisin determinantilla $D=\begin{vmatrix} a&b \\ c&d \end{vmatrix}=ad-bc$, jolloin saadaan vastaus: $y=\frac{D_y}{D}=\frac{af-ec}{ad-bc}$.

:::{admonition} Perustelu
:class: tip, dropdown
Täydentyy.
:::

**Esim.** Ratkaistaan yhtälöpari $\begin{equation} \begin{cases} 3x+2y=-1 \\ 2x+y=3\end{cases} \end{equation}$ Cramerin menetelmällä.

:::{admonition} Ratkaisu
:class: tip, dropdown

Lasketaan tarvittavat determinantit: $D_x=\begin{vmatrix}-1&2\\3&1\end{vmatrix}=-1-6=-7,  D_y=\begin{vmatrix}3&-1\\2&3\end{vmatrix}=9-(-2)=11, D=\begin{vmatrix}3&2\\2&1\end{vmatrix}=3-4=-1$.

Vastauksiksi saadaan $x=\frac{-7}{-1}=7, y=-\frac{11}{1}=-11$.

:::

## Yhtälöryhmä matriisiyhtälönä

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
a_{11}x_1+a_{12} x_2+ \ldots +a_{1n} x_n=b_1 \\ a_{21} x_1+a_{22} x_2+ \ldots +a_{2n} x_n=b_2 \\ \vdots \\ a_{m1} x_1+a_{m2} x_2+ \ldots +a_{mn} x_n=b_m \end{cases} \end{equation} \leftrightarrow AX=B$.

Jos yhtälöitä ja tuntemattomia ei ole yhtä paljon ($m\neq n$), niin yhtälöryhmällä ei yleensä ole yksikäsitteistä ratkaisua. Jos taas yhtälöitä ja tuntemattomia on yhtä paljon ($m=n$), niin yhtälöryhmällä on yksikäsitteinen ratkaisu.

Koska $A^{-1}A=I$ ja $A^{-1}AX=IX=X$, niin tuntemattomat sisältävä matriisi saadaan kertomalla yhtälö $AX=B$ puolittain vasemmalta matriisilla $A^{-1}$:

$AX=B \leftrightarrow A^{-1}AX=A^{-1}B \leftrightarrow X=A^{-1}B$.

Ratkaisu on olemassa jos ja vain jos kerroinmatriisilla $A$ on olemassa käänteismatriisi, toisin sanoen $\text{det}~A =|A| \neq 0$.

Octavella yhtälöryhmän ratkaisu $X=A^{-1}B$ saadaan komennolla: inv(A)\*B

**Esim.** Ratkaise yhtälöryhmä $\begin{equation} \begin{cases} 3x+5y=13\\x+2y=5 \end{cases} \end{equation}$ matriisimuodossa.

:::{admonition} Ratkaisu
:class: tip, dropdown

Muuttujien kertoimista muodostuu matriisi $A=\begin{bmatrix}3&5\\1&2\end{bmatrix}$ ja yhtälöiden oikeista puolista matriisi $B=\begin{bmatrix}13\\5\end{bmatrix}$. Nyt yhtälöryhmä voidaan kirjoittaa muodossa $AX=B$, missä $X=\begin{bmatrix}x\\y\end{bmatrix}$.

Matriisin $A$ determinantti on $|A|=3\cdot 2-5\cdot 1=6-5=1\neq 0$, joten on olemassa $A^{-1}$.

Muistetaan: jos matriisilla $A=\begin{bmatrix}a&b\\c&d\end{bmatrix}$ on käänteismatriisi $A^{-1}$, käänteismatriisille pätee 
$A^{-1}=\frac{1}{ad-bc} \begin{bmatrix}d&-b\\-c&a\end{bmatrix}$. 

Nyt siis $A^{-1}=\frac{1}{3\cdot 2-5 \cdot 1} \begin{bmatrix} 2&-5 \\ -1&3 \end{bmatrix}=1\cdot \begin{bmatrix} 2&-5\\-1&3\end{bmatrix}=\begin{bmatrix}2&-5\\-1&3\end{bmatrix}$

ja $X=A^{-1}B=\begin{bmatrix}2&-5\\-1&3\end{bmatrix} \begin{bmatrix} 13\\5\end{bmatrix}=\begin{bmatrix}2\cdot 13-5\cdot 5\\-1\cdot 13+3\cdot 5\end{bmatrix}=\begin{bmatrix}26-25\\-13+15\end{bmatrix}=\begin{bmatrix}1\\2\end{bmatrix}$.

Ratkaisu on siis $x=1,y=2$. 
:::