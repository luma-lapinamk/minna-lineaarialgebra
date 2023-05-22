# Determinantti 

Determinantti on lukuarvo, joka voidaan laskea neliömatriiseille. Jokaisella neliömatriisilla on siis olemassa determinantti. Sen arvolla on merkitystä, kun myöhemmin muodostetaan käänteismatriiseja ja ratkaistaan yhtälöryhmiä. Yleensä kuitenkin riittää tietää pelkästään se, onko determinantti nolla vai jotakin muuta kuin nolla!

Determinanttia tarvitaan myös, kun ratkaistaan eräitä erityisiä matriisiin liittyviä lukuja, ns. ominaisarvoja. Tällaistä käyttöä matriiseilla voi olla differentiaaliyhtälöissä. Näitä asioita käsitellään vain laajan matematiikan opintojaksoilla. 

## Determinantin laskeminen

Determinantti on siis yksittäiseen matriisiin liittyvä lukuarvo. Matriisin $A$ determinanttia merkitään $\det{A}$, $\det{(A)}$ tai $|A|$. Sen laskeminen onnistuu matriisin tyypistä riippuen ainakin kolmella tavalla:

**1) Jos matriisi on tyyppiä $2\times 2$, determinantille on suora laskukaava.**

Matriisin $A=\begin{bmatrix}a_{11} & a_{12} \\ a_{21} & a_{22}\end{bmatrix}$ determinantti on $\det{A} = a_{11}a_{22}-a_{21}a_{12}$.

Matriisin päälävistäjän alkioiden tulosta siis vähennetään kahden jäljelle jäävän alkion tulo.

::::{admonition} Esimerkki

Laske matriisin $M=\begin{bmatrix} 3&4 \\ 5&6\end{bmatrix}$ determinantti.

:::{admonition} Ratkaisu
:class: tip, dropdown

Determinantti on $\det{M} = 3\cdot 6-4\cdot 5=18-20=-2$.
:::

::::

::::{admonition} Esimerkki

Millä luvun $x$ arvolla matriisin $A=\begin{bmatrix}1&x\\3 &2\end{bmatrix}$ determinantti on nolla?

:::{admonition} Ratkaisu
:class: tip, dropdown

Matriisin determinantti on $\det{A}=1\cdot 2-x\cdot 3=2-3x$.

Ratkaistaan yhtälö $2-3x=0 \Leftrightarrow -3x=-2 \Leftrightarrow x=\frac{2}{3}$.

:::

::::

**2) Jos matriisi on tyyppiä $3 \times 3$, determinantti lasketaan kuten vektorien ristitulo.**

Vektorien ristitulon yhteydessä tutustuttiin jo kolmiriviseen determinanttiin. Tyyppiä $3 \times 3$ oleville matriiseille determinantti lasketaan vastaavalla tavalla kuin kahden kolmialkioisen vektorin ristitulo:

- peitetään jokin rivi ja jokin sarake

- lasketaan näkyviin jäävistä alkioista ristikkäisten alkioiden tulojen erotus

- kerrotaan kyseinen tulo peitetyn rivin ja sarakkeen risteyskohtaan jäävällä alkiolla

- tuloista muodostetaan summa siten, että merkki valitaan risteyskohtaan jäävän alkion perusteella merkkikaaviosta

Merkkikaavio on $\hspace{2cm}\begin{matrix}+ & - & + \\ - & + & - \\ + & - & + \end{matrix}$

Determinantti voidaan kehittää minkä tahansa rivin suhteen. Voidaan siis pitää mikä tahansa rivi peitettynä ja liikkua sarakkeita pitkin. Determinantin arvo on sama riippumatta siitä, minkä rivin tai sarakkeen suhteen se lasketaan. Jos valitsee peitetyksi riviksi sellainen rivin, jossa on nollia, välttyy monelta laskutoimitukselta.

Determinantti voidaan laskea myös niin, että peittääkin jonkin sarakkeen, ja sitten vuorollaan jokaisen rivin. Tällöin sanotaan, että determinantti kehitetään jonkin sarakkeen suhteen. Tällaisia laskuja ei käsitellä tässä materiaalissa.

::::{admonition} Esimerkki

Kehitetään determinantti matriisille $A=\begin{bmatrix}1&4&2\\0&0&2\\5&1&3\end{bmatrix}$

a) ensimmäisen rivin suhteen, b) toisen rivin suhteen.

:::{admonition} Ratkaisu
:class: tip, dropdown

a) $\text{det}⁡ A = 1\cdot (0\cdot 3-2\cdot 1)-4\cdot (0\cdot 3-5\cdot 2)+2\cdot (0\cdot 1-0\cdot 5) $

$\text{det}⁡ A= 1\cdot (-2)-4\cdot (-10)+2\cdot 0=38$

b) $\text{det} ⁡A = -0\cdot (4\cdot 3-2\cdot 1)+0\cdot (1\cdot 3-2\cdot 5)-2\cdot (1\cdot 1-4\cdot 5) $

$\text{det}⁡ A= -2\cdot (-19)=38$

:::

::::

:::{admonition} Huomautus vektorien ristitulosta
:class: tip, dropdown

Vektorien ristitulossa peittoon jäävät alkiot olivat kantavektoreita $\vec{i}$, $\vec{j}$ ja $\vec{k}$. Ristituloa ei kuitenkaan ole pakko laskea sillä tavalla, vaan peitettäväksi voi valita minkä tahansa muunkin rivin.

Aiemmin laskettiin esimerkkinä vektorien $\vec{a}=\vec{i}+2\vec{j}$ ja  $\vec{b}=2\vec{i}+\vec{j}+\vec{k}$ ristitulo seuraavasti:

$\vec{a}\times\vec{b} =
  \begin{vmatrix}
    \vec{i} & \vec{j} & \vec{k} \\
    1 & 2 & 0 \\
    2 & 1 & 1 \\
  \end{vmatrix}$

$=(2\cdot 1-0\cdot 1) \vec{i}-(1\cdot 1-0\cdot 2) \vec{j} + (1\cdot 1-2 \cdot 2) \vec{k}$  

$= 2 \vec{i}-\vec{j}-3\vec{k}$.

Ristitulon voi kuitenkin laskea myös siten, että peitetään keskimmäinen rivi ja suoritetaan sitten kerto- ja vähennyslaskut kuten matriisin determinanttia laskettaessa. Kertoimille pitää muistaa ottaa merkkikaaviosta oikea merkki. Keskimmäisellä rivillä viimeisenä alkiona on nolla, joten laskutoimituksia tarvitaan vähemmän:

$\vec{a}\times\vec{b} =
  \begin{vmatrix}
    \vec{i} & \vec{j} & \vec{k} \\
    1 & 2 & 0 \\
    2 & 1 & 1 \\
  \end{vmatrix}$

$=-1\cdot (1\cdot \vec{j}-1\cdot \vec{k}) + 2 \cdot (1\cdot \vec{i} -2\cdot \vec{k}) - 0 (1\cdot \vec{i}-2 \vec{j})$  

$= -1(\vec{j}-\vec{k})+2(\vec{i}-2\vec{k})$

$= -\vec{j}+\vec{k}+2\vec{i}-4\vec{k}$

$= 2 \vec{i} -\vec{j}-3\vec{k}$.

:::


**3) Minkä tahansa kokoiselle voi laskea neliömatriisin tietokoneella.**

Octavella minkä tahansa kokoisen neliömatriisin $A$ determinantti lasketaan komennolla det(A). WolframAlphassa toimii komento determinant.

Mielivaltaisen kokoisen neliömatriisin voi kyllä laskea käsinkin, jos on tarpeeksi aikaa ja paperia. Matriisin osaa, joka jää näkyviin, kun jokin rivi ja sarake on peitetty, sanotaan alideterminantiksi. Kun lasketaan determinanttia $n \times n$ –tyyppiselle matriisille, saadaan ensin $n$ kappaletta $(n-1) \times (n-1)$ –tyyppisiä alideterminantteja. Näistä jokaisesta saadaan edelleen $n-1$ kappaletta $(n-2) \times (n-2)$ –tyypin alideterminantteja. Edelleen saadaan pienempiä alideterminantteja. Lopputulos saadaan, kun alideterminantit ovat kutistuneet kokoon $2 \times 2$. Laskemalla nämä yhteen kertoimet huomioituna saadaan lopulta koko $n \times n$ –tyyppisen matriisin determinantti.