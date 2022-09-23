# Ominaisarvot ja -vektorit

Jos tyyppiä $n \times n$ oleva matriisi $A$ kerrotaan $n \times 1$ -tyyppisellä vektorilla $\vec{v}$ ja tulokseksi saadaan sama vektori kerrottuna jollakin luvulla $\lambda$, sanotaan että $\lambda$ on matriisin $A$ ominaisarvo ja $\vec{v}$ matriisin $A$ ominaisvektori. Yhtälönä tämä ilmaistaan seuraavasti: $A\vec{v}=\lambda\vec{v}$.

Neliömatriisilla, jonka koko on $n \times $, on $n$ ominaisarvoa. Jokaista ominaisarvoa vastaa ääretön määrä ominaisvektoreita. Ominaisarvoja ja ominaisvektoreita voidaan myöhemmin hyödyntää mm. differentiaaliyhtälöiden ratkaisuissa. Tällä sivulla esitetään, miten ominaisarvot ja -vektorit lasketaan.

## Ominaisarvoyhtälö

Matriisin ominaisarvo ja ominaisvektori löytyvät ratkaisemalla yhtälö $A\vec{v}=\lambda\vec{v}$:

$A\vec{v}-\lambda\vec{v}=\vec{0} \leftrightarrow A\vec{v}-\lambda I_n \vec{v}=\vec{0} \leftrightarrow (A-\lambda I_n)\vec{v}=\vec{0}$

Tälle yhtälölle on olemassa triviaaliratkaisu $\vec{n}=\vec{0}$, sillä nollavektori kerrottuna millä tahansa sopivan kokoisella matriisilla tuottaa nollavektorin. Tässä tapauksessa emme ole kiinnostuneita tästä ratkaisusta. Toisena vaihtoehtona on selvittää äärettömän monta ratkaisua, joilla $\vec{n} \neq \vec{0}$. Yleisesti matriisiyhtälölle $M \vec{x} = \vec{y}$, missä $M$ on $n \times n$ -tyyppinen matriisi ja $\vec{x}$ ja $\vec{y}$ ovat $n \times 1$ -tyyppisiä vektoreita, on ratkaisuja ääretön määrä silloin, kun kerroinmatriisin $M$ determinantti on nolla. Tässä tapauksessa on siis ratkaistava yhtälö $\text{det}(A-\lambda I_n)=0$. Kyseisen yhtälön vasemmasta puolesta muodostuu matriisin _karakteristinen polynomi_. Käytännössä yhtälöstä tulee $n$. asteen yhtälö, jonka tuntemattomana on ominaisarvo $\lambda$. 

**Esim.** Laske matriisin $A=\begin{bmatrix} 2 & 5 \\ 3 & 4\end{bmatrix}$ ominaisarvot.

:::{admonition} Ratkaisu
:class: tip, dropdown

Ratkaistaan yhtälö $\text{det} (A-\lambda I_2) = 0$:

$\text{det} \left(\begin{bmatrix} 2 & 5 \\ 3 & 4\end{bmatrix} - \lambda \begin{bmatrix} 1 & 0 \\ 0 & 1\end{bmatrix}\right) = 0$  

$\text{det} \left(\begin{bmatrix} 2 & 5 \\ 3 & 4\end{bmatrix} - \begin{bmatrix} \lambda & 0 \\ 0 & \lambda\end{bmatrix}\right) = 0$  

$\text{det} \begin{bmatrix} 2-\lambda & 5 \\ 3 & 4-\lambda\end{bmatrix} = 0$  

$(2-\lambda)(4-\lambda)-5\cdot 3 = 0$  

$8-2\lambda-4\lambda + \lambda^2 -15 = 0$  

$\lambda^2 - 6\lambda -7 = 0$

$\lambda = \frac{-(-6) \pm \sqrt{(-6)^2-4\cdot 1 \cdot (-7)}}{2\cdot 1}$  

$\lambda = \frac{6\pm\sqrt{64}}{2}$  

$\lambda = \frac{6\pm 8}{2}$  

$\lambda_1 = \frac{6+8}{2}=7, \lambda_2=\frac{6-8}{2}=-1$.

Matriisin $A$ ominaisarvot ovat siis $\lambda_1=7$ ja $\lambda_2=-1$.

:::

Kun matriisin ominaisarvot on löydetty, lasketaan ominaisarvoja vastaavat ominaisvektorit. Tämä onnistuu ratkaisemalla yhtälö $(A-\lambda I_n) \vec{v} = \vec{0}$. Tästä matriisiyhtälöstä muodostuu yhtälöryhmä, josta voidaan ratkaista ominaisvektorin komponentit.

**Esim.** Laske matriisin $A=\begin{bmatrix} 2 & 5 \\ 3 & 4\end{bmatrix}$ ominaisvektorit. Matriisin $A$ ominaisarvot ovat $7$ ja $-1$.

:::{admonition} Ratkaisu
:class: tip, dropdown

Merkitään ominaisarvoa $\lambda_1=7$ vastaavaa ominaisvektoria $\vec{v_1}=\begin{bmatrix} v_{11} \\ v_{12} \end{bmatrix}$. Ratkaistaan yhtälö $A-\lambda \vec{v} = \vec{0}$:

$\left(\begin{bmatrix} 2 & 5 \\ 3 & 4\end{bmatrix} - 7 \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} \right) \begin{bmatrix} v_{11 } \\ v_{12} \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$  

$\left(\begin{bmatrix} 2 & 5 \\ 3 & 4\end{bmatrix} - \begin{bmatrix} 7 & 0 \\ 0 & 7 \end{bmatrix} \right) \begin{bmatrix} v_{11}  \\ v_{12} \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$  

$\begin{bmatrix} 2-7 & 5 \\ 3 & 4-7\end{bmatrix} \begin{bmatrix} v_{11}  \\ v_{12} \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$  

$\begin{bmatrix} -5 & 5 \\ 3 & -3\end{bmatrix} \begin{bmatrix} v_{11}  \\ v_{12} \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$ 

Huomataan, että vasemmanpuoleisen matriisin determinantti on $-5\cdot (-3) - 5\cdot 3 = 15-15=0$. Tällöin yhtälöä ei voi ratkaista kyseisen matriisin käänteismatriisilla kertomalla. Ratkaisua ei löydy tällä tavalla, sillä ominaisvektoreita on ääretön määrä. Matriisitulon määritelmän avulla voidaan kuitenkin muodostaa yhtälöpari:

$\begin{equation} \begin{cases} -5 v_{11} + 5 v_{12} = 0 \\ 3 v_{11} -3 v_{12} = 0 \end{cases} \end{equation}$  

Kummasta tahansa yhtälöstä huomataan, että $v_{11}=v_{12}$. Toisin sanoen ominaisarvoa $7$ vastaavia ominaisvektoreita ovat kaikki vektorit, joissa komponenttien kertoimet ovat yhtä suuret, esimerkiksi

$\vec{v_1}=\begin{bmatrix} 1 \\ 1 \end{bmatrix}$ tai yksikkövektori $\vec{v_1}=\begin{bmatrix} 1/\sqrt{2} \\ 1\sqrt{2} \end{bmatrix}$.  

Ominaisarvoa $\lambda_2=-1$ vastaava ominaisvektori $\vec{v_2}=\begin{bmatrix} v_{21} \\ v_{22} \end{bmatrix}$ saadaan seuraavasti:

$\left(\begin{bmatrix} 2 & 5 \\ 3 & 4\end{bmatrix} - (-1) \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} \right) \begin{bmatrix} v_{21}  \\ v_{22} \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$  

$\begin{bmatrix} 3 & 5 \\ 3 & 5\end{bmatrix} \begin{bmatrix} v_{21}  \\ v_{22} \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$ 

$v_{22}=\frac{3}{5} v_{21}$

Toisin sanoen ominaisvektoreita ovat kaikki ne vektorit, joissa jälkimmäinen komponentti on suuruudeltaan $-3/5$ ensimmäisestä, esimerkiksi 

$\vec{v_2}=\begin{bmatrix} 5 \\ -3 \end{bmatrix}$ tai yksikkövektori $\vec{v_2}=\begin{bmatrix} 5/\sqrt{34} \\ -3\sqrt{34} \end{bmatrix}$.  

:::