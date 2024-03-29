# Populaatiolaskentaa matriiseilla

[Leslien matriisin](https://en.wikipedia.org/wiki/Leslie_matrix) avulla voidaan ennustaa esimerkiksi tietyn alueen eläinmäärän kehitystä. Ennusteessa tehdään yksinkertaistettuja oletuksia populaation toiminnasta. Ennusteessa käytettävä Leslien matriisi sisältää tiedon siitä, kuinka suuri osuus tietyn ikäryhmän eläimistä säilyy hengissä seuraavaan ikäryhmään siirtymiseen asti, ja siitä, kuinka monta poikasta kyseisen ikäryhmän eläimet tuottavat.

Tarkastellaan menetelmää esimerkin avulla. Oletetaan, että kasvattamasi eläimet lisääntyvät ja pysyvät hengissä seuraavan taulukon mukaan:

|Ikä (vuosia)|Poikasia keskim.|Todennäk. selvitä seur. ikäryhmään|
|-----------|-------------------------------------------------|-------------------------------------------|
|$0 \leq x \lt 2$ |0|0.7|
|$2 \leq x \lt 4$|0.5|0.9|
|$4 \leq x \lt 6$|1.1|0.8|
|$6 \leq x \lt 8$|1.3|0.7|
|$8 \leq x \lt 10$|0.8|0.3|
|$10 \leq x \lt 12$|0.4|0|

Aloitat eläinten kasvatuksen ostamalla 40 kpl 2-vuotiaita eläimiä. Kuinka paljon ja minkä ikäisiä eläimiä sinulla on 10 vuoden päästä?

Muodostetaan Leslien matriisi $L$, johon tulee ensimmäiselle riville poikasten määrät ja 2. riviltä alkaen lävistäjälle selviytymistodennäköisyydet. Kaikki muut alkiot ovat nollia. Alkuperäistä eläinmäärää kuvaa matriisi $E$, jonka rivit vastaavat ikäryhmiä ja alkiot kertovat eläinten määrän kyseisessä ikäryhmässä.

$L=\begin{bmatrix} 0&0.5&1.1&1.3&0.8&0.4 \\ 0.7&0&0&0&0&0 \\ 0&0.9&0&0&0&0 \\ 0&0&0.8&0&0&0 \\ 0&0&0&0.7&0&0 \\ 0&0&0&0&0.3&0 \end{bmatrix}, E=\begin{bmatrix}0\\40\\0\\0\\0\\0\end{bmatrix}$

Kahden vuoden kuluttua eläimiä on

$LE=\begin{bmatrix} 0&0.5&1.1&1.3&0.8&0.4 \\ 0.7&0&0&0&0&0 \\ 0&0.9&0&0&0&0 \\ 0&0&0.8&0&0&0 \\ 0&0&0&0.7&0&0 \\ 0&0&0&0&0.3&0 \end{bmatrix} \begin{bmatrix} 0\\40\\0\\0\\0\\0 \end{bmatrix} = \begin{bmatrix} 0.5\cdot 40 \\ 0 \\ 0.9⋅40 \\ 0 \\0 \\ 0 \end{bmatrix} = \begin{bmatrix} 20\\0\\36\\0\\0\\0 \end{bmatrix}$.

Siis 40 alkuperäistä otusta on tuottanut 20 poikasta ikäryhmään 0-2 v, ja lisäksi 90 % eli 36 kpl alkuperäisistä eläimistä on siirtynyt seuraavaan ikäryhmään.

Tilanne kymmenen vuoden kuluttua saadaan laskemalla (tietokoneella)

$L^5 E \approx \begin{bmatrix} 58 \\ 31 \\ 28 \\ 20 \\ 7 \\0\end{bmatrix}$.

Tässä tietysti on oletettu, että eläimiä ei alkuhankinnan jälkeen ole ostettu tai myytykään. Huomaa myös, että tässä ikäluokkia käsitellään kahden vuoden jaksoina; siksi kymmenen vuotta vastaa viidenteen potenssiin korotusta.

::::{admonition} Esimerkki

Erästä eläinpopulaatiota kuvaavan Leslien matriisin tiedetään olevan seuraavanlainen:

$L=\begin{bmatrix}0 & 0.4 & 1.1 & 0.6 \\ 0.80 & 0 & 0 & 0 \\ 0 & 0.95 & 0 & 0 \\0 & 0 & 0.70 & 0\end{bmatrix}$

ja lisäksi tiedetään, että eri ikäluokkiin kuuluvia eläimiä kolmen ikäluokkajakson jälkeen kuvaava matriisi on

$M=\begin{bmatrix}60 \\ 50 \\ 45 \\ 15\end{bmatrix}$.

Kuinka paljon eri ikäluokkiin kuului eläimiä tarkasteluajan alussa, siis millainen matriisi $E$ kuvasi alkutilannetta?

:::{admonition} Ratkaisu
:class: tip, dropdown

Ratkaistava yhtälö on nyt $L^3E=M$. Matriisi $L$ ja siten myös matriisi $L^3$ on neliömatriisi, joten sille on mahdollista laskea käänteismatriisi (olettaen, että matriisin $L^3$ determinantti ei ole nolla). Niinpä yhtälö ratkeaa tavallisilla matriisiyhtälöiden ratkaisukeinoilla:

$L^3E=M \Leftrightarrow E=(L^3)^{-1} M$

Lasku kannattaa suorittaa tietokoneella. Octavella komento olisi: 

L=[0 0.4 1.1 0.6;0.8 0 0 0; 0 0.95 0 0; 0 0 0.7 0], M=[60;50;45;15], E=inv(L^3)\*M

Vastaukseksi tulee nuorimmasta vanhimpaan ikäryhmään noin 28, 44, 18 ja 36 yksilöä.

:::

::::