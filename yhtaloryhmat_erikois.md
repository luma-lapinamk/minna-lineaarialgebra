# Yhtälöryhmien erikoistapauksia

Oletetaan, että yhtälöryhmä on esitetty edellisen luvun mukaisesti matriisiyhtälönä $AX=B$. Tämän yhtälön ratkaisu ei aina onnistu kerroinmatriisin $A$ käänteismatriisia hyödyntämällä, sillä käänteismatriisiahan ei välttämättä ole olemassa.

Käänteismatriisin olemassaolo voidaan päätellä kerroinmatriisin determinantista. Jos determinantti on nolla, niin ratkaisuja on joko nolla tai äärettömän monta. Kun tämä on todettu, tarkistetaan ensin, kumpi tilanne on kyseessä. Se tapahtuu seuraavasti:

- Muodostetaan apumatriisi $A_x$, jossa matriisin $A$ ensimmäisen sarakkeen paikalla on matriisi $B$.

- Lasketaan apumatriisin determinantti $\det{A_x}$.

- Jos $\det{A_x}=0$, ratkaisuja on äärettömän monta.

- Jos $\det{A_x} \neq 0$, ratkaisuja ei ole yhtään.

Miksi tällainen temppu toimii? Käytännössä ratkaisuja on äärettömän monta silloin, kun yhtälöryhmän yhtälöt ovat toistensa monikertoja. Kaikki yhtälöt saadaan siis muodostettua kertomalla jokin niistä eri reaaliluvuilla. Tällöin kyseessä onkin itse asiassa täysin sama yhtälö vain eri tavoilla kirjoitettuna. Ratkaisuja taas ei ole yhtään silloin, kun yhtälöiden vasemman puolet ovat toistensa monikertoja, mutta oikeat puolet eivät olekaan. Kun kerroinmatriisin yksi sarake vaihdetaan yhtälöjen ratkaisuihin, niin yhtälöiden kerrannaisuus tai sen puute nähdään nimenomaan determinanteista.

::::{admonition} Esimerkki

Onko seuraavilla yhtälöryhmillä ratkaisuja?

a) $\begin{equation}\begin{cases}3x+5y=7 \\6x+10=8 \end{cases}\end{equation}$

b) $\begin{equation}\begin{cases}2x+3y=9 \\4x+6y=18 \end{cases}\end{equation}$

:::{admonition} Ratkaisu
:class: tip, dropdown

a) Kerroinmatriisin $A=\begin{bmatrix}3 & 5 \\ 6 & 10\end{bmatrix}$ determinantti on $3\cdot 10 - 5\cdot 6 = 0$, joten ratkaisuja on nolla tai ääretön.

Apumatriisi on $A_x=\begin{bmatrix}7 & 5 \\ 8 & 10\end{bmatrix}$ ja sen determinantti on $7\cdot 10 -5\cdot 8 = 30 \neq 0$.

Yhtälöryhmällä ei ole yhtään ratkaisua. Suoraan yhtälöryhmää tarkastelemalla voi todeta, että toisen yhtälön vasen puoli on saatu kertomalla ensimmäisen yhtälön vasen puoli luvulla 2, mutta yhtälöiden oikeilla puolilla ei ole vastaavaa suhdetta.

b) Kerroinmatriisin $A=\begin{bmatrix}2 & 3 \\ 4 & 6\end{bmatrix}$ determinantti on $2\cdot 6 - 3\cdot 4 = 0$, joten ratkaisuja on nolla tai ääretön.

Apumatriisi on $A_x=\begin{bmatrix}9 & 3 \\ 18 & 6\end{bmatrix}$ ja sen determinantti on $9\cdot 6 - 18 \cdot 3 = 0$.

Ratkaisuja on siis äärettömän monta. Voitaisiinko löytää edes yksi niistä? Ratkaistaan kumpi tahansa kirjain kummasta tahansa yhtälöstä, esimerkiksi $y$ yhtälöstä $2x+3y=9$:

$2x+3y=9 \Leftrightarrow 3y=9-2x \Leftrightarrow y=3-\frac{2}{3}x$

Nyt luvun $x$ paikalle voidaan valita mikä tahansa reaaliluku, ja sitten voidaan laskea vastaava $y$ edellisestä yhtälöstä.

Esimerkiksi jos valitaan $x=0$, niin $y=3-\frac{2}{3}\cdot 0 = 3$. Jos valitaan $x=1$, niin $y=3-\frac{2}{3}\cdot 1 = \frac{7}{3}$, ja niin edelleen.

:::

::::

Seuraavissa esimerkeissä on tärkeää huomata, että tehtävässä ei ole tarkoitus ratkaista lukuja $x$ ja $y$, vaan yhtälöissä esiintyvien vakioiden arvot, joilla ratkaisuja saadaan haluttu määrä. Esimerkkejä kannattaa testailla esimerkiksi [WolframAlphassa](https://www.wolframalpha.com/). Siinä yhtälöryhmät voidaan ratkaista kirjoittamalla solve-komennon perään kaikki ratkaistavat yhtälöt pilkulla erotettuna. Kokeile, mitä tapahtuu, jos sijoitat tehtävässä kysytyn kirjaimen paikalle saamasi ratkaisun, tai vaihtoehtoisesti jonkin muun luvun!

::::{admonition} Esimerkki

Millä ehdolla yhtälöparilla $\begin{equation}\begin{cases}x+5y=4\\3x+15=a\end{cases}\end{equation}$ ei ole yhtään ratkaisua?

:::{admonition} Ratkaisu
:class: tip, dropdown

Tarkistetaan aluksi, että kerroinmatriisin determinantti on nolla:

$A=\begin{bmatrix}1 & 5 \\ 3 & 15\end{bmatrix}$, joten $\det{A}=1\cdot 15 - 3\cdot 5 = 0$.

Muodostetaan apumatriisi: $A_x=\begin{bmatrix}4 & 5 \\ a & 15\end{bmatrix}$

Apumatriisin determinantti on $4\cdot 15 - 5 \cdot a = 60-5a$.

Ratkaisuja ei ole silloin, kun $\det{A_x} \neq 0$. Tulee siis olla $60-5a\neq 0$, josta saadaan ehto $-5a\neq -60$ ja edelleen $a\neq 12$.

:::

::::

::::{admonition} Esimerkki

Millä ehdolla yhtälöparilla $\begin{equation}\begin{cases}x+5y=4\\3x+15=a\end{cases}\end{equation}$ on äärettömän monta ratkaisua? Mitä nämä ratkaisut ovat?

:::{admonition} Ratkaisu
:class: tip, dropdown

Tarkistetaan jälleen aluksi, että kerroinmatriisin determinantti on nolla:

$A=\begin{bmatrix}3 & 2 \\ 6 & 4\end{bmatrix}$, joten $\det{A}=3\cdot 4 - 2\cdot 6 = 0$.

Muodostetaan apumatriisi: $A_x=\begin{bmatrix}a & 2 \\ 7 & 4\end{bmatrix}$

Apumatriisin determinantti on $4\cdot a - 2 \cdot 7 = 4a-14$.

Ratkaisuja on äärettömän monta silloin, kun $\det{A_x} = 0$. Tulee siis olla $4a-14=0$, josta saadaan ehto $4a=14$ ja edelleen $a=\frac{14}{4}$ eli $a=\frac{7}{2}$.

Ratkaisut saadaan selville esimerkiksi ratkaisemalla $y$ alemmasta yhtälöstä:

$6x+4y=7 \Leftrightarrow 4y=7-6x \Leftrightarrow y=\frac{7}{4}-\frac{3}{2}x$.

Eräs mahdollinen ratkaisu on esimerkiksi $x=0$ ja $y=\frac{7}{4}-\frac{3}{2}\cdot 0 =\frac{7}{4}$.

:::

::::

::::{admonition} Esimerkki

Millä ehdoilla yhtälöparilla $\begin{equation}\begin{cases}2x+ay=3\\5x+7y=b\end{cases}\end{equation}$ ei ole yhtään ratkaisua?

:::{admonition} Ratkaisu
:class: tip, dropdown

Muodostetaan kerroinmatriisi ja sen determinantti:

$A=\begin{bmatrix}2&a\\5&7\end{bmatrix}, \det{A}=2\cdot 7-5\cdot a=14-5a$

Ratkaisuja on nolla tai ääretön silloin, kun $\det{A}=0$, joten pitää olla $14-5a=0 \Leftrightarrow a=\frac{14}{5}$.

Muodostetaan apumatriisi $Ax=\begin{bmatrix}3&\frac{14}{5}\\b&7\end{bmatrix}$.

Lasketaan determinantti: $\det{A_x}=3\cdot 7-\frac{14}{5}\cdot b=21-\frac{14}{5}b$

Ratkaisua ei ole, kun apumatriisin determinantti on erisuuri kuin nolla:

$21-\frac{14}{5}b \neq 0 \Leftrightarrow -\frac{14}{5}b\neq -21 \Leftrightarrow b\neq\frac{21\cdot 5}{14} \Leftrightarrow b\neq\frac{15}{2}$.

:::

::::