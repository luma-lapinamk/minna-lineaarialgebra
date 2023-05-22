# Kerrataan yhtälöryhmiä

Tässä kappaleessa esitetään, miten yhtälöpareja ja yhtälöryhmiä ratkaistaan algebran menetelmin, ilman matriiseja. Yhtälöparissa on kaksi yhtälöä ja kaksi tuntematonta. Yhtälöryhmissä yhtälöitä ja tuntemattomia on vielä useampia. Tarkoituksena on löytää tuntemattomille sellaiset arvot, että ne toteuttavat molemmat tai kaikki yhtälöt.

Yhtälöparia, joka voidaan esittää muodossa 

$\begin{equation}
    \begin{cases}
      a_1 x + b_1 y = c_1\\
      a_2 x + b_2 y = c_2
    \end{cases}\
\end{equation}$

sanotaan lineaariseksi yhtälöpariksi. Lineaarinen yhtälöpari sisältää siis kaksi yhtälöä, jotka ovat ensimmäisen asteen yhtälöitä muuttujien $x$ ja $y$ suhteen. Lineaarinen yhtälöpari voidaan ratkaista joko sijoitusmenetelmällä tai eliminointimenetelmällä.
    
## Sijoitusmenetelmä
    
Sijoitusmenetelmässä ratkaistaan jommastakummasta yhtälöstä toinen tuntematon kirjain. Se ilmaistaan siis lukujen ja toisen kirjaimen avulla. Saatu lauseke sijoitetaan toiseen yhtälöön saman kirjaimen paikalle. Tällöin saadaan yhtälö, jossa esiintyy vain yhtä tuntematonta, ja tuntemattomalle saadaan laskettua lukuarvo. Lopuksi ratkaistaan toinen tuntematon käyttämällä jompaa kumpaa alkuperäisestä yhtälöstä, tai ensimmäisessä vaiheessa tuntemattomalle ratkaisua lauseketta.

Yhtälön ja tuntemattoman, joita käyttää ratkaisun ensimmäisessä vaiheessa, voi valita vapaasti. Lopputulos on kaikilla tavoilla laskettuna sama. Eroa voi olla välivaiheiden määrässä.

::::{admonition} Esimerkki

Ratkaise yhtälöpari $\begin{equation}
    \begin{cases}
      x - y = 2\\
      2 x + 3 y = 9
    \end{cases}\
\end{equation}$

:::{admonition} Ratkaisu
:class: tip, dropdown

Vaihtoehtoja sijoitusmenetelmällä ratkaisun ensimmäiseen vaiheeseen on neljä: ratkaistaan ensimmäisestä yhtälöstä $x$, ensimmäisestä yhtälöstä $y$, toisesta yhtälöstä $x$ tai toisesta yhtälöstä $y$.

Jos esimerkiksi ratkaistaan ylemmästä yhtälöstä ensin $x=2+y$ ja sijoitetaan se alempaan yhtälöön, saadaan 

$2(2+y)+3y=9 \Leftrightarrow  4+2y+3y=9 \Leftrightarrow 5y=5 \Leftrightarrow y=1$.

Tämän avulla voidaan ratkaista vielä ensimmäisestä yhtälöstä $x=2+y=2+1=3$.

Kaikilla muillakin esitetyillä tavoilla vastaukseksi tulee $x=3,y=1$.

:::

::::


## Eliminaatiomenetelmä

Eliminaatiomenetelmässä molemmat yhtälöt kerrotaan puolittain jollakin nollasta poikkeavalla luvulla. Kummankin yhtälön voi kertoa eri luvulla. Sen jälkeen yhtälöt lasketaan puolittain yhteen. Kertolaskussa käytettävät kertoimet on valittava siten, että yhteenlaskussa jompikumpi muuttujista häviää – käytännössä siten, että joko muuttujan $x$ tai muuttujen $y$ kertoimista tulee toistensa vastalukuja. Tuloksena on jälleen yhtälö, jossa esiintyy vain yhtä tuntematonta. Kun sille on saatu lukuarvo, voidaan lopuksi ratkaista toinenkin tuntematon.

::::{admonition} Esimerkki

Ratkaise yhtälöpari $\begin{equation} \begin{cases} 2x+5y=12 \\ 3x+2y=7\end{cases} \end{equation}$

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

$2x+5\cdot 2=12 \Leftrightarrow 2x+10=12 \Leftrightarrow 2x=2 \Leftrightarrow x=1$

tai

$3x+2\cdot 2=7 \Leftrightarrow 3x+4=7 \Leftrightarrow 3x=3 \Leftrightarrow x=1$.

:::

::::

## Ratkaisujen määrä
 
Edellisissä esimerkeissä löytyi yksi tietty lukupari $(x,y)$, joka toteuttaa annetut yhtälöt. Joskus kuitenkin yhtälöryhmällä on äärettömän paljon tai ei ollenkaan ratkaisuja. Äärettömän monta ratkaisua tunnistaa siitä, että sijoitus- tai eliminaatiomenetelmää käyttämällä päätyy yhtälöön, joka on tosi millä tahansa muuttujan arvolla tai ei riipu muuttujasta ollenkaan, esimerkiksi $0=0$. Jos taas ratkaisuja ei ole yhtään, päädytään yhtälöön, joka ei millään muuttujan arvolla voi olla totta, esimerkiksi $0=1$. Ratkaistujen määrää tarkastellan perusteellinen matriisilaskennan menetelmin luvussa "Yhtälöryhmien erikoistapauksia".

::::{admonition} Esimerkki

Ratkaise yhtälöpari $\begin{equation} \begin{cases} 2x+y=5 \\ 4x+2y=10 \end{cases} \end{equation}$  eliminaatiomenetelmällä.

:::{admonition} Ratkaisu
:class: tip, dropdown

Kertomalla ylempi yhtälö luvulla -2 saadaan $-4x-2y=-10$. 

Lasketaan yhteen tämä ja alin yhtälö, ja ratkaistaan $x$:

$-4x-2y+4x+2y=-10+10 \Leftrightarrow  0\cdot x=0$

Huomataan, että mikä tahansa $x$:n arvo toteuttaa yhtälön. Muuttujan $x$ tilalle voidaan valita ns. parametri eli vapaasti valittava lukuarvo, jota merkitään $x=t \in \Re$. Tämä voidaan sijoittaa ylempään yhtälöön, jolloin saadaan $y=5-2t$. Yhtälöparin ratkaisu on siis $x=t, y=5-2t, t \in \Re$. Yhtälöparilla on äärettömän monta ratkaisua.

:::

::::

::::{admonition} Esimerkki

Ratkaise yhtälöpari $\begin{equation} \begin{cases} 2x+y=5 \\ 4x+y=11 \end{cases} \end{equation}$ eliminaatiomenetelmällä.

:::{admonition} Ratkaisu
:class: tip, dropdown

Jälleen ylemmästä yhtälöstä saadaan luvulla kertomalla $-4x-2y=-10$. 

Kun lasketaan se yhteen alemman yhtälön kanssa, saadaan: 

$-4x-2y+4x+2y=-10+11 \Leftrightarrow  0=1$.

Yhtälö ei toteudu millään luvulla $x$. Yhtälöparilla ei ole ratkaisua.

:::

::::