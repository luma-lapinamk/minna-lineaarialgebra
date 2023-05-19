# Gaussin eliminaatio

Tässä luvussa perehdytään Gaussin eliminaatiomenetelmään, joka toimii kaikille lineaarisille yhtälöryhmille. Käytännössä tehtäviä ei toki tarvitse välttämättä ratkoa kynällä ja paperilla suoritetuilla välivaiheilla, mutta luvussa esitetyt käsitteet ovat osa insinöörin matemaattista yleissivistystä. Menetelmää käsitellään lähinnä laajan matematiikan opintojaksoilla.

Gaussin eliminaatiomenetelmässä lähtökohta on se, että yhtälöryhmä on kirjoitettu matriisimuotoon. Esimerkiksi yhtälöryhmää

$\begin{equation}\begin{cases}x+3y+4z=5\\ 3x+2y+7z=3\\ 2x-y+z=-4\end{cases}\end{equation}$  

vastaavan matriisiyhtälön $AX=B$ kerroinmatriisi $A$, tuntemattomat sisältävä vektori $X$ ja oikeat puolet sisältävä vektori $B$ olisivat  

$A=\begin{bmatrix}1 & 3 & 4\\ 3 & 2 & 7 \\ 2 & -1 & 1\end{bmatrix}, X=\begin{bmatrix}x\\y\\z\end{bmatrix}, B=\begin{bmatrix}5\\3\\-4\end{bmatrix}$.

Kerroinmatriisi $A$ muuttuu _täydennetyksi kerroinmatriisiksi_ siten, että siihen lisätään viimeiseksi sarakkeeksi vektori $B$. Esimerkin tapauksessa täydennetty kerroinmatriisi olisi  

$\begin{bmatrix}1 & 3 & 4 & 5\\ 3 & 2 & 7 & 3\\ 2 & -1 & 1 & -4\end{bmatrix}$.

## Porrasmuoto

Gaussin elimaatiomenetelmässä pyritään saattamaan täydennetty kerroinmatriisi _porrasmuotoon_. Porrasmuodossa matriisin 1. rivi sisältää kaikkien tuntemattomien (tässä esimerkissä $x$, $y$ ja $z$) nollasta poikkeavia kertoimia, mutta 2. rivillä ensimmäisen muuttujan (esimerkissä $x$) kerroin on nolla, 3. rivillä ensimmäisen ja toisen muuttujan (esimerkissä $x$ ja $y$) kertoimet ovat nollia, ja niin edelleen. Kun matriisi on porrasmuodossa, niin alimmalta riviltä voidaan helposti ratkaista viimeisen tuntemattoman arvo, ja edelleen takaisinsijoituksella ylemmille riveille saadaan muiden tuntemattomien arvot. Porrasmuodosta nähdään myös sellaiset erikoistapaukset, että yhtälöryhmällä ei ollenkaan ratkaisuja tai että ratkaisuja on ääretön määrä.

**Esim**. Porrasmuotoinen matriisi voisi näyttää vaikka tältä:

$\begin{bmatrix}2 & 3 & 1 & 7 \\ 0 & 4 & -1 & 3 \\ 0 & 0 & 8 & 6 \end{bmatrix}$

Täydennetyn kerroinmatriisin porrasmuotoon saattamiseksi voi käyttää seuraavia toimenpiteitä eli _alkeismuunnoksia_:
- matriisien rivien vaihtaminen keskenään
- matriisien rivien kertominen nollasta poikkeavilla vakioilla
- vakiolla kerrotun rivin lisääminen matriisiin riviin

Miksi tällaisia toimenpiteitä saa tehdä matriisille? Yhtälöryhmähän ei muutu miksikään, kun yhtälöiden järjestystä vaihdetaan tai kun yhtälöitä kerrotaan vakioilla. Silloinkin, kun yhtälöitä lasketaan yhteen, yhtälöryhmän ratkaisut pysyvät samoina. Kun matriisia ajatellaan esitysmuotona yhtälöryhmälle, voidaan todeta, että porrasmuotoon muokattu matriisi tuottaa yhtälöryhmälle samat ratkaisut kuin alkuperäinenkin.

Matriisit, jotka saadaan samasta matriisista edellisten toimenpiteiden avulla, ovat _yhtäpitäviä_, ja tätä yhtäpitävyyttä merkitään aaltoviivalla \~. 

Esimerkiksi $\begin{bmatrix} 2 & 7 \\ 4 & 3\end{bmatrix} \sim \begin{bmatrix} 2 & 7 \\ 0 & -11\end{bmatrix}$, 

sillä jälkimmäisen matriisin 2. rivi on saatu kertomalla 1. rivi luvulla -2 ja lisäämällä tämä rivi alkuperäisen matriisin 2. riviin.

::::{admonition} Esimerkki

Muunna porrasmuotoon edellä esitetty täydennetty kerroinmatriisi $\begin{bmatrix}1 & 3 & 4 & 5\\ 3 & 2 & 7 & 3\\ 2 & -1 & 1 & -4\end{bmatrix}$.

:::{admonition} Ratkaisu
:class: tip, dropdown

Matriisin ensimmäiselle riville ei tarvitse tehdä mitään. Toiselle riville pitäisi saada ensimmäiseksi alkioksi nolla. Tämä onnistuu esimerkiksi sillä tavalla, että kerrotaan matriisin 1. rivi luvulla -3 ja lisätään se sitten matriisin 2. riviin, ja korvataan matriisin 2. rivi tällä summalla:

- matriisin 1. rivi kerrottuna luvulla -3 on $\begin{bmatrix}-3 & -9 & -12 & -15\end{bmatrix}$

- edellisen laskun tuloksen ja matriisin 2. rivin summa on $\begin{bmatrix}-3+3 & -9+2 & -12+7 & -15+3\end{bmatrix}=\begin{bmatrix} 0 & -7 & -5 & -12\end{bmatrix}$

Matriisi on nyt siis $\begin{bmatrix}1 & 3 & 4 & 5\\ 0 & -7 & -5 & -12\\ 2 & -1 & 1 & -4\end{bmatrix}$.

Matriisin alimmasta ei suoraan yhdellä laskutoimituksella saa vaaditun muotoista, eli sellaista, että kaksi ensimmäistä alkiota olisivat nollia, mutta ainakin ensimmäinen alkio saadaan nollaksi, kun kerrotaan matriisin 1. rivi luvulla -2, lisätään se 3. riviin ja korvataan matriisin alin rivi näin saadulla rivillä:

- matriisin 1. rivi kerrottuna luvulla -2 on $\begin{bmatrix}-2 & -6 & -8 & -10\end{bmatrix}$

- edellisen laskun tuloksen ja matriisin 3. rivin summa on $\begin{bmatrix}-2+2 & -6-1 & -8+1 & -10-4\end{bmatrix}=\begin{bmatrix} 0 & -7 & -7 & -14\end{bmatrix}$

Matriisi on nyt siis $\begin{bmatrix}1 & 3 & 4 & 5\\ 0 & -7 & -5 & -12\\ 0 & -7 & -7 & -14\end{bmatrix}$.

Alimmalle riville saadaan nolla toiseksikin alkioksi, kun 2. rivi kerrotaan luvulla -1 ja lasketaan yhteen 3. rivin kanssa. Uusi alin rivi on siis

$\begin{bmatrix}0+0 & 7-7 & 5-7 & 12-14\end{bmatrix} = \begin{bmatrix} 0 & 0 & -2 & -2\end{bmatrix}$.

Porrasmuotoinen täydennetty kerroinmatriisi on siis $\begin{bmatrix}1 & 3 & 4 & 5\\ 0 & -7 & -5 & -12\\ 0 & 0 & -2 & -2\end{bmatrix}$.

:::

::::

## Ratkaisu porrasmuodosta

Kun yhtälöryhmää vastaava täydennetty kerroinmatriisi on saatu porrasmuotoon, tarvitsee enää tulkita matriisista yhtälöryhmän ratkaisut. Matriisin jokainen rivi vastaa yhtälöä, jossa viimeinen alkio on yhtälön oikea puoli, ja muut alkiot vastaavat eri muuttujien kertoimia. 

Tarkastellaan erityisesti alimmalta riviltä muodostuvaa yhtälöä, jossa mukana on vain viimeisen muuttujan (esimerkissä $z$) kerroin. Vaihtoehtoja on kolme:

**1) Yksi ratkaisu**:

Matriisin alimmalta riviltä muodostuu yhtälö, josta ratkeaa viimeinen tuntematon, ja muut tuntemattomat saadaan ylemmiltä riveiltä takaisinsijoituksella Esimerkin yhtälöryhmä 

$\begin{equation}\begin{cases}x+3y+4z=5\\ 3x+2y+7x=3\\ 2x-y+z=-4\end{cases}\end{equation}$  

saatiin seuraavanlaiseen porrasmuotoon:

$\begin{bmatrix}1 & 3 & 4 & 5\\ 0 & -7 & -5 & -12\\ 0 & 0 & -2 & -2\end{bmatrix}$

Alin rivi vastaa yhtälöä $-2z=-2$, josta ratkeaa helposti $z=1$. Matriisin 2. rivi vastaa yhtälöä $-7y-5z=-12$, joka sijoittamalla $z=1$ sievenee muotoon $-7y-5=-12$ ja edelleen antaa ratkaisun $y=1$. Tämä voidaan sijoittaa matriisin 1. riviltä saatavaan yhtälöön $x+3y+4z=5$, eli $x+3+4=5$, josta ratkeaa viimeinenkin tuntematon $x=-2$.

**2) Ei ratkaisuja**:

Matriisin alimmalta riviltä muodostuu yhtälö, jolla ei ole ratkaisua, eikä tällöin koko yhtälöryhmälläkään ole ratkaisuja. Esimerkki porrasmuotoisesta täydennetystä kerroinmatriisista, josta seuraa tällainen tilanne, on

$\begin{bmatrix}1 & 2 & 3 & -9 \\ 0 & 1 & 1 & 4 \\ 0 & 0 & 0 &1\end{bmatrix}$.

Viimeiseltä riviltä muodostuu yhtälö $0z=1$, joka ei toteudu millään $z$:n arvolla.

**3) Äärettömästi ratkaisuja**:

Matriisin alimmalta riviltä muodostuu yhtälö, jolla on äärettömän monta ratkaisua, ja tällöin koko yhtälöryhmälläkin on äärettömän monta ratkaisua. Esimerkki porrasmuotoisesta täydennetystä kerroinmatriisista, josta seuraa tällainen tilanne, on

$\begin{bmatrix}1 & 2 & -3 & 9 \\ 0 & 1 & 1 & 4 \\ 0 & 0 & 0 & 0\end{bmatrix}$.

Alimmalta riviltä saadaan yhtälö $0z=0$. Tämän yhtälön toteuttavat kaikki luvut $z$. Yleensä tällaista vapaata muuttujaa merkitään parametrina $t$. Tämä voidaan nyt sijoittaa toiselta riviltä muodostuvaan yhtälöön: $y+t=4$, josta saadaan $y=4-t$. Edelleen ylimmältä riviltä saadaan $x+2t-3t=9$ eli $x+2(4-t)-3t=9 \Leftrightarrow x+8-2t-3t=9 \Leftrightarrow x=1+5t$. Yhtälöryhmän jokainen ratkaisu vastaa tiettyä parametrin $t$ arvoa.

## Gauss-Jordan -eliminaatio

Gaussin eliminaatiossa käytettäviä laskutoimenpiteitä voidaan jatkaa vielä eteenpäin, kunnes täydennetty kerroinmatriisi muuttuu niinsanottuun _pelkistettyyn porrasmuotoon_. Tällaisessa muodossa jokaisen rivin ensimmäinen nollasta poikkeava alkio eli _porrasalkio_ on suuruudeltaan yksi, ja kaikissa paitsi viimeisessä sarakkeessa kaikki muut paitsi porrasalkio ovat nollia. Tällaisen muunnoksen jälkeen yhtälöryhmän ratkaisut ovat suoraan luettavissa muodostuneen matriisin riveiltä. Toimenpiteen nimi on Gauss-Jordan -eliminaatio.

::::{admonition} Esimerkki

Muunna pelkistettyyn porrasmuotoon yhtälöryhmän

$\begin{equation}\begin{cases}x+2y+z=4\\ 3x+8y+7z=20\\ 2x+7y+9z=23\end{cases}\end{equation}$  

täydennetty kerroinmatriisi $\begin{bmatrix}1 & 2 & 1 & 4 \\ 3 & 8 & 7 & 20 \\ 2 & 7 & 9 & 23 \end{bmatrix}$, 

ja tulkitse muodostuneesta matriisista yhtälöryhmän ratkaisu.

:::{admonition} Ratkaisu
:class: tip, dropdown

Matriisi saadaan porrasmuotoon esimerkiksi seuraavasti:

$\begin{bmatrix}1 & 2 & 1 & 4 \\ 3 & 8 & 7 & 20 \\ 2 & 7 & 9 & 23 \end{bmatrix} \sim \begin{bmatrix} 1 & 2 & 1 & 4 \\ 0 & 2 & 4 & 8 \\ 2 & 7 & 9 & 23\end{bmatrix} \sim \begin{bmatrix} 1 & 2 & 1 & 4 \\ 0 & 1 & 2 & 4 \\2 & 7 & 9 & 23\end{bmatrix} \sim $  

$\begin{bmatrix}1 & 2 & 1 & 4 \\ 0 & 1 & 2 & 4 \\0 & 3 & 7 & 15\end{bmatrix} \sim \begin{bmatrix}1 & 2 & 1 & 4 \\ 0 & 1 & 2 & 4 \\0 & 0 & 1 & 3 \end{bmatrix}$

Laskun vaiheet olivat nämä:
- kerrottiin 1. rivi luvulla -3 ja lisättiin se 2. riviin
- kerrottiin 2. rivi luvulla 1/2
- kerrottiin 1. rivi luvulla -2 ja lisättiin se 3. riviin
- kerrottiin 2. rivi luvulla -3 ja lisättiin se 3. riviin

Pelkistettyä porrasmuotoa varten pitäisi vielä saada 2. ja 3. sarakkeen alkioita nollaksi. Jatketaan alkeismuunnoksia:

$\begin{bmatrix}1 & 2 & 1 & 4 \\ 0 & 1 & 2 & 4 \\0 & 0 & 1 & 3 \end{bmatrix} \sim \begin{bmatrix}1 & 0 & -3 & -4 \\ 0 & 1 & 2 & 4 \\0 & 0 & 1 & 3 \end{bmatrix} \sim \begin{bmatrix}1 & 0 & 0 & 5 \\ 0 & 1 & 2 & 4 \\0 & 0 & 1 & 3 \end{bmatrix} \sim \begin{bmatrix}1 & 0 & 0 & 5 \\ 0 & 1 & 0 & -2 \\0 & 0 & 1 & 3 \end{bmatrix}$

Matriisista voidaan nyt lukea tuntemattomien arvot: 1. riviltä saadaan $x=5$, 2. riviltä $y=-2$ ja 3. riviltä $z=3$.

:::

::::