# Leontiefin panos-tuotos-malli

Eräs esimerkki matriisilaskennan sovelluksista on Leontiefin panos-tuotos-malli. Tämä taloustieteiden malli liittyy eri toimijoiden tuotantoon ja resurssien kulutukseen. 

## Suljettu malli

Tarkastellaan mallia seuraavan esimerkin avulla: Eräällä seudulla toimii kolme alaa $A$, $B$ ja $C$ (nämä voisivat olla esimerkiksi maatalous, teollisuus ja matkailuala). Kunkin alan tuotannosta osa menee alan omiin tarpeisiin ja osa kahden muun alan käyttöön. Alla olevan taulukon sarakkeissa on esitetty eri alojen tuotannon jakaantuminen näiden alojen kesken.

|panos/tuotos| A | B | C |
|---|-- | --| --|
|A| 0.3 | 0.1 | 0.6 |
|B| 0.2 | 0.8 | 0.2 |
|C| 0.5 | 0.1 | 0.2 |

Sarakkeita sanotaan eri alojen panoksiksi. Jokaisen sarakkeen summa on 1, sillä mallissa oletetaan, että tuotteille ei ole muita käyttäjiä kuin taulukossa mainitut toimialat. Kun tehdään tällainen oletus, puhutaan suljetusta mallista.

Taulukon vaakarivejä sanotaan tuotoksiksi. Ne kuvaavat sitä, kuinka paljon kunkin alan tuotantoa tarvitaan joko alan itsensä tai muiden alojen tuotannossa. Esimerkiksi ylimmältä riviltä nähdään, että alan $A$ tuotantoa tarvitaan yhden tuotantoyksikön tuotannossa alalla $A$ 0.3 yksikköä, alalla $B$ 0.1 yksikköä ja alalla $C$ 0.6 yksikköä.

Esimerkin taulukko voidaan esittää myös matriisina, josta käytetään nimitystä vaihtomatriisi. Tässä tapauksessa vaihtomatriisi on siis

$V=\begin{bmatrix}0.3 & 0.1 & 0.6 \\ 0.2 & 0.8 & 0.2 \\ 0.5 & 0.1 & 0.2\end{bmatrix}$.

Vaihtomatriisin avulla voidaan selvittää, kuinka suurta pitää eri alojen tuotannon olla toisiinsa verrattuna, jotta kysyntä ja tarjonta pysyvät tasapainossa. Oletetaan, että alan $A$ tuotanto on $a$ yksikköä, alan $B$ tuotanto $b$ yksikköä ja alan $C$ tuotanto $c$ yksikköä. Jotta jokainen ala saa käyttöönsä riittävästi resursseja, niin vaihtomatriisien rivien avulla voidaan muodostaa yhtälöryhmä:

$\begin{equation}\begin{cases} 0.3 a + 0.1 b + 0.6 c = a \\ 0.2 a + 0.8 b + 0.2 c = b \\ 0.5 a + 0.1 b + 0.1 c = c\end{cases}\end{equation}$

Esitetään yhtälöryhmä vielä homogeenisena eli siten, että oikealle puolelle jää vain nollia:

$\begin{equation}\begin{cases} -0.7 a + 0.1 b + 0.6 c = 0 \\ 0.2 a - 0.2 b + 0.2 c = 0 \\ 0.5 a + 0.1 b - 0.8 c = 0\end{cases}\end{equation}$

Vaihdetaan lopuksi merkit (kertomalla yhtälöt puolittain luvulla $-1$):

$\begin{equation}\begin{cases} 0.7 a - 0.1 b - 0.6 c = 0 \\ -0.2 a + 0.2 b - 0.2 c = 0 \\ -0.5 a - 0.1 b + 0.8 c = 0\end{cases}\end{equation}$

Kun yllä esitetyn yhtälöryhmän vasemman puolen kertoimet kerätään matriisiksi, todetaan että kyseinen matriisi on $I-V$. Jos eri alojen tuotantomääriä kuvataan vektorilla

$X=\begin{bmatrix} a \\ b \\ c\end{bmatrix}$,

niin ratkaistavaksi tulee yhtälö, tai oikeastaan yhtälöryhmä, $(I-V)X=0$. 

Yhtälö voidaan ratkaista esimerkiksi Gauss-Jordan -eliminaatiolla. Tällaisen ratkaisun yksityiskohdat on esitetty alla.

:::{admonition} Ratkaisu
:class: tip, dropdown

Yhtälöryhmää vastaava täydennetty kerroinmatriisi on

$A=\begin{bmatrix}0.7 & -0.1 & -0.6 & 0 \\ -0.2 & 0.1 & -0.2 & 0 \\ -0.5 & -0.1 & 0.8 & 0 \end{bmatrix}$, 

joka saadaan alkeismuunnoksilla (tai sopivalla komennolla tietokoneella, esimerkiksi Octavella rref-komennolla) pelkistettyyn porrasmuotoon

$A=\begin{bmatrix}1 & 0 & -1.1667 & 0 \\ 0 & 1 & -2.1667 & 0 \\ 0 & 0 & 0 & 0 \end{bmatrix}$.

Pelkistetystä porrasmuodosta alimmalta riviltä voidaan lukea: muuttujalle $c$ voidaan valita arvo vapaasti, siis $c=t \in \Re$. Toiselta riviltä nähdään, että $b=2.1667 t$, ja ylimmältä riviltä nähdään, että $a=1.1667 t$. Toisin sanoen mitkä tahansa luvut $a, b, c$ käyvät, kunhan niiden suhde on $a:b:c = 1.1667:2.1667:1$.

:::

## Avoin malli

Edellä esitetty malli muuttuu hieman monimutkaisemmaksi, kun sallitaan se mahdollisuus, että tuotantoa siirtyy myös järjestelmän ulkopuolelle. Toisin sanoen edellisen esimerkin tuotantoalueista esimerkiksi maatalouden tuotantoa voitaisiin myydä myös muille kuin maatalouden omaan käyttöön, teollisuuteen tai matkailualalle. Muualle, ns. avoimelle sektorille, myyty tuotanto ei enää ole minkään näiden tuotannonalojen käytettävissä.

Matemaattisesti erona suljettuun malliin on, että vaihtomatriisin pystyrivien summien ei enää tarvitse olla tasan yksi. Tällöin vaihtomatriisin nimityskin muuttuu kulutusmatriisiksi. Esimerkiksi kulutusmatriisissa

$K=\begin{bmatrix}0.5 & 0.4 & 0.2 \\ 0.2 & 0.3 & 0.1 \\ 0.1 & 0.1 & 0.3 \end{bmatrix}$  

ensimmäinen sarake esittää tilannetta, jossa tuotannonalan $A$ tuotannosta 50 % menee alan omaan käyttöön, 20 % tuotannonalalle $B$ ja 10 % tuotannonalalle $C$, ja loput 20 % myydään avoimelle sektorille.

Merkitään jälleen tuotannonalojen tuotantomääriä $a$, $b$ ja $c$ vektorina

$X=\begin{bmatrix} a \\ b \\ c\end{bmatrix}$,

jolloin tuotannon tarpeisiin riittävien resurssien määrä on $KX$. Kerätään avoimelle sektorille jäävät tuotantomäärät $a'$, $b'$ ja $c'$ vektoriin 

$Y=\begin{bmatrix} a' \\ b' \\ c'\end{bmatrix}$.

Avoimelle sektorille jää se osuus tuotannosta, jota ei tarvita alojen $A$, $B$ ja $C$ omiin tarpeisiin. Tämä voidaan kirjoittaa muodossa $Y=X-CX$ eli $Y=(I-C)X$. Oletetaan, että avoimella sektorilla on omat tarpeensa eri alojen tuotannoille. Merkitään nämä eri tuotteiden kysynnät $a''$, $b''$ ja $c''$ vektoriin

$Z=\begin{bmatrix} a'' \\ b'' \\ c''\end{bmatrix}$.

Tuotanto on tasapainossa silloin, kun eri aloilta avoimelle sektorille jäävien tuotteiden määrät ovat yhtä suuret kuin avoimen sektorin kysyntä näille tuotteille. Toisin sanoen

$(I-C)X=Z$.

Yhtälön ratkaisu onnistuu samalla tavalla kuin suljetun mallin tapauksessa.

