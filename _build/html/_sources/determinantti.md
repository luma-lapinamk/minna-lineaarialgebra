# Determinantti 

Determinantti on eräänlainen mitta matriisin ”tilavuudelle”. Determinantin arvolla on merkitystä mm. kun myöhemmin ratkaistaan yhtälöryhmiä. Lisäksi sitä tarvitaan ainakin tietokoneohjelmoinnissa, esim. 3D-grafiikan muunnosmatriiseissa.

## Determinantin laskeminen

Matriisille $A=\begin{bmatrix}a_{11} & a_{12} \\ a_{21} & a_{22}\end{bmatrix}$, joka on tyyppiä $2 \times 2$, voidaan määritellä determinantti $\text{det} A$ seuraavasti: 

$\text{det}⁡ A = |A|= \begin{vmatrix}a_{11} & a_{12} \\ a_{21} & a_{22} \end{vmatrix}= a_{11}a_{22}-a_{21}a_{12}$.

**Esim.** Matriisin $\begin{bmatrix} 3&4 \\ 5&6\end{bmatrix}$ determinantti on $\begin{vmatrix} 3&4 \\ 5&6\end{vmatrix}=3\cdot 6-4\cdot 5=18-20=-2$.

Vektorien ristitulon yhteydessä tutustuttiin jo kolmiriviseen determinanttiin. Tyyppiä $3 \times 3$ oleville matriiseille determinantti lasketaan vastaavalla tavalla kuin kahden kolmialkioiden vektorin ristitulo:

- peitetään jokin rivi ja jokin sarake

- lasketaan näkyviin jäävistä alkioista ristikkäisten alkioiden tulojen erotus

- kerrotaan kyseinen tulo peitetyn rivin ja sarakkeen risteyskohtaan jäävällä alkiolla

- tuloista muodostetaan summa siten, että merkki valitaan risteyskohtaan jäävän alkion perusteella merkkikaaviosta.

Merkkikaavio on $\hspace{2cm}\begin{matrix}+ & - & + \\ - & + & - \\ + & - & + \end{matrix}$

Determinantti voidaan kehittää minkä tahansa rivin tai sarakkeen suhteen. Voidaan siis liikkua mitä tahansa riviä tai saraketta pitkin. Determinantin arvo on sama riippumatta siitä, minkä rivin tai sarakkeen suhteen se lasketaan.

**Esim.** Kehitetään determinantti matriisille $A=\begin{bmatrix}1&4&2\\0&0&2\\5&1&3\end{bmatrix}$

a) ensimmäisen rivin suhteen, b) toisen rivin suhteen.

:::{admonition} Ratkaisu
:class: tip, dropdown

a) $\text{det}⁡ A = 1\cdot (0\cdot 3-2\cdot 1)-4\cdot (0\cdot 3-5\cdot 2)+2\cdot (0\cdot 1-0\cdot 5) $

$\text{det}⁡ A= 1\cdot (-2)-4\cdot (-10)+2\cdot 0=38$

b) $\text{det} ⁡A = -0\cdot (4\cdot 3-2\cdot 1)+0\cdot (1\cdot 3-2\cdot 5)-2\cdot (1\cdot 1-4\cdot 5) $

$\text{det}⁡ A= -2\cdot (-19)=38$
:::

Yleisesti: Kun lasketaan determinanttia $n \times n$ –tyyppiselle matriisille, saadaan ensin $n$ kappaletta $(n-1) \times (n-1)$ –tyyppisiä alideterminantteja. Näistä jokaisesta saadaan edelleen $n-1$ kappaletta $(n-2) \times (n-2)$ –tyypin alideterminantteja. Edelleen saadaan pienempiä alideterminantteja. Lopputulos saadaan, kun alideterminantit ovat kutistuneet kokoon $2 \times 2$. Laskemalla nämä yhteen kertoimet huomioituna saadaan lopulta koko $n \times n$ –tyyppisen matriisin determinantti.

Octavella minkä tahansa kokoisen neliömatriisin $A$ determinantti lasketaan komennolla det(A).
