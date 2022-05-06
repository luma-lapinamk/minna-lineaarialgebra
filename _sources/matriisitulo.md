# Matriisitulo

Matriisien $A$ ja $B$ kertolasku eli matriisitulo $AB$ voidaan laskea vain, jos matriisi $A$ on tyyppiä $m \times n$ ja matriisi $B$ tyyppiä $n \times p$; siis matriisin $A$ sarakkeiden määrän on oltava yhtä suuri kuin matriisin $B$ rivien määrän. Kertolaskun tuloksena on matriisi $C=AB$, jonka tyyppi on $m \times p$.

![Matriisien tyypit](matriisitulo_koko.png "Matriisien tyypit matriisitulossa")

Matriisin $C=AB$ alkio $c_{ij}$ saadaan kertomalla matriisin $A$ rivin $i$ alkiot matriisin $B$ sarakkeen $j$ alkioilla ja laskemalla tulojen summa. 

![Matriisitulon periaate](matriisitulo_resepti.png "Matriisitulon periaate")

Matriisien kertolasku ei ole vaihdannainen: yleensä $AB \neq BA$. Octavella matriisitulo lasketaan kertomerkillä, lasku $AB$ suoritetaan siis komennolla A\*B.

:::{admonition} Huomautus
:class: tip, dropdown

Matriisin rivejä ja sarakkeita voidaan ajatella vektoreina. Matriisitulon alkiot ovat siis pistetuloja vektoreista, jotka muodostavat matriisin $A$ rivit ja matriisin $B$ sarakkeet!

Toisaalta vektoreitakin voidaan ajatella matriiseina. Jos vektorissa on $n$ komponenttia, niin vektorin komponenteista voidaan muodostaa tyypin $n \times 1$ tai $1 \times n$ matriisi.

:::
 
**Esim.** Laske tulo $AB$, kun $A=\begin{bmatrix}2&3&1\\0&4&2\end{bmatrix}$ ja $B=\begin{bmatrix}0&2&1\\3&1&2\\1&0&2\end{bmatrix}$.

:::{admonition} Ratkaisu
:class: tip, dropdown

Matriisi $A$ on tyyppiä $2\times3$ ja matriisi $B$ on tyyppiä $3 \times 3$, joten matriisi voidaan laskea. Lopputuloksen tyypin pitäisi olla $2 \times 3$.

$AB=\begin{bmatrix}2\cdot 0+3\cdot 3+1\cdot 1 & 2\cdot 2+3\cdot 1+1\cdot 0 & 2\cdot 1+3\cdot 2+1\cdot 2 \\ 0\cdot 0+4\cdot 3+2\cdot 1 & 0\cdot 2+4\cdot 1+2\cdot 0 & 0\cdot 1+4\cdot 2+2\cdot 2\end{bmatrix}=\begin{bmatrix}10&7&10\\14&4&12\end{bmatrix}$.

:::

**Esim.** Artun kaupassa maito maksaa 1 €/litra, vehnäjauhot 0.60 €/kg ja munat 2.50 €/kenno. Bertan kaupassa maito maksaa 1.29 €/litra, vehnäjauhot 0.35 €/kg ja munat 2.19 €/kenno. Kummasta kaupasta on halvempaa ostaa ainekset lettutaikinaan, johon tulee 2 litraa maitoa, 0.4 kg jauhoja ja puoli kennoa munia? Muotoile ongelma matriisien kertolaskuksi!


:::{admonition} Ratkaisu
:class: tip, dropdown

Muodostetaan matriisi $H$ tuotteiden hinnoille eri kaupoissa. Ensimmäinen rivi kuvaa maidon, jauhojen ja munien hintaa Artun kaupassa. Toinen rivi kuvaa maidon, jauhojen ja munien hintaa Bertan kaupassa.
         
$H=\begin{bmatrix}1 &0.60 &2.50 \\ 1.29 &0.35 &2.19\end{bmatrix}$

Muodostetaan matriisi $K$ tuotteiden kulutuksille lettutaikinassa. Alkiot vastaavat maidon, jauhojen ja munien kulutusta (yksiköinä litra, kilogramma ja kenno).

$K=\begin{bmatrix}2 \\ 0.4 \\0.5\end{bmatrix}$.

Lasketaan matriisi $HK$. Matriisin $H$ tyyppi on $2 \times 3$ ja matriisin $K$ tyyppi on $3 \times 1$, joten matriisitulo $HK$ voidaan laskea, ja tuloksena olevan matriisin tyyppi on $2 \times 1$. Matriisit alkiot kuvaavat taikinan aineksien hintaa: ylärivilla hinta Artun kaupasta ostettuna, ja alarivillä hinta Bertan kaupasta ostettuna.

$HK=\begin{bmatrix}1\cdot2+0.60\cdot0.4+2.50\cdot0.5\\ 1.29\cdot 2+0.35\cdot 0.4+2.19\cdot 0.5\end{bmatrix}=\begin{bmatrix}2+0.24+1.25 \\2.58+0.14+1.095\end{bmatrix}=\begin{bmatrix} 3.49 \\ 3.815\end{bmatrix}$.

Tällaisen ongelman toki ratkaisee helpommin ilman matriiseja kuin matriiseja hyödyntämällä. Toivottavasti kuitenkin matriisilaskennalle aukenee myöhemmin jotain hyötykäyttöä!

:::

## Matriisitulon laskusääntöjä

Jos matriisit $A$, $B$ ja $C$ ovat keskenään sopivan kokoisia, niin niille ja reaaliluvulle $p$ pätevät seuraavat laskusäännöt:

- $(AB)C=A(BC)$

- $A(B+C)=AB+BC$

- $(A+B)C=AC+BC$

- $p(AB)=(pA)B=A(pB)$

- $(AB)^T=B^TA^T$

- $(B^TA^T)^T=AB$

Osa laskusäännöistä näyttää hyvin samanlaisilta kuin reaalilukujen laskusäännöt, esimerkiksi osittelulaki. Laskusääntöjen perustelu jää harjoitustehtäväksi.