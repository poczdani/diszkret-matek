
**2.3. Permutációk (Sorbarendezések)**

*Alapfogalom (Faktoriális):* $n! := 1 \cdot 2 \cdot \dots \cdot n$, azaz az első $n$ darab pozitív egész szám szorzata. Alapszabályként kikötjük, hogy $0! := 1$. Hasznos azonosság: $(n+1)! = (n+1) \cdot n!$.

**1. Ismétlés nélküli permutáció ($P_n$)**
* *Mit jelent?* $n$ darab **különböző** elem összes lehetséges sorbarendezését.
* *Képlet:* $P_n = n!$
* *Logikája:* Az első helyre $n$-félét választhatunk, a másodikra már csak $(n-1)$-et, és így tovább. A független választásokat összeszorozzuk ($n \cdot (n-1) \cdot \dots \cdot 1$).

**2. Ismétléses permutáció ($P_n^{k_1, \dots, k_s \text{ (ism)}}$)**
* *Mit jelent?* Összesen $n$ darab elem sorbarendezését, de úgy, hogy vannak köztük teljesen **egyforma (megkülönböztethetetlen)** típusok. Legyen $s$-féle típus, amikből rendre $k_1, k_2, \dots, k_s$ darab van ($k_1 + \dots + k_s = n$).
* *Képlet:* $P_n^{k_1, \dots, k_s \text{ (ism)}} = \frac{n!}{k_1! \cdot \dots \cdot k_s!}$
* *Logikája:* Ha minden elem különböző lenne, $n!$-féleképpen rendezhetnénk őket sorba. Azonban az azonos típusú (pl. $k_1$ db) elemek egymás közötti cseréje ($k_1!$-féle csere) nem hoz létre új mintát. Így a teljes $n!$ lehetőséget le kell osztanunk minden egyes azonos csoport belső cseréinek számával ($k_i!$-okkal).

**Polinomiális együttható (2.14. Definíció)**
A fenti ismétléses permutáció képletét egy speciális zárójeles formában is fel szokták írni, ezt nevezzük polinomiális együtthatónak:
$$\binom{n}{k_1, \dots, k_s} := \frac{n!}{k_1! \cdot \dots \cdot k_s!}$$

**2.3.2. Variációk és kombinációk (Kiválasztások)**

A feladatok megoldásánál az a legfontosabb, hogy tisztázzuk: *számít-e a kiválasztás sorrendje* (variáció vs. kombináció), illetve *visszatehetjük-e* a már kihúzott elemet (ismétléses vs. ismétlés nélküli).

**1. Ismétlés nélküli variáció ($V_n^k$)**
* *Jellemzők:* Nincs visszatevés, a sorrend **számít** (pl. dobogós helyezések).
* *Logika:* Az első húzásnál $n$ lehetőségünk van, a másodiknál $n-1$, és így tovább, összesen $k$ alkalommal.
* *Képlet:* $n \cdot (n-1) \cdot \dots \cdot (n - k + 1)$

**2. Ismétléses variáció ($V_n^{k(ism)}$)**
* *Jellemzők:* Van visszatevés, a sorrend **számít** (pl. PIN kód, totó).
* *Logika:* Minden egyes húzásnál (összesen $k$-szor) ugyanúgy az összes $n$ elem rendelkezésünkre áll.
* *Képlet:* $V_n^{k(ism)} = n^k$

**3. Ismétlés nélküli kombináció ($C_n^k$)**
* *Jellemzők:* Nincs visszatevés, a sorrend **NEM számít** (pl. Lottósorsolás, kártyaosztás).
* *Logika:* Fogjuk az ismétlés nélküli variációk számát (ahol még számít a sorrend), és elosztjuk a kiválasztott $k$ elem egymás közötti, számunkra érdektelen sorbarendezéseinek számával ($k!$).
* *Képlet:* $C_n^k = \frac{n \cdot (n-1) \cdot \dots \cdot (n-k+1)}{k!}$ -> Amit $$\binom{n}{k}$$ -nak hívnak


**A Binomiális Együttható ("n alatt a k")**

Az ismétlés nélküli kombinációt hivatalosan így jelöljük és számoljuk:
$$\binom{n}{k} := C_n^k = \frac{n!}{k! \cdot (n-k)!}$$

**4. Ismétléses kombináció ($C_n^{k(ism)}$)**

* *Jellemzők:* Van visszatevés (többször is választhatjuk ugyanazt az elemet), és a sorrend **NEM számít** (pl. egyforma golyók elosztása dobozokba, fagyigombócok kelyhe).
* *A bizonyítás logikája (Strigulák és Válaszfalak / "Stars and Bars" módszer):*
  Képzeljük el, hogy az $n$ féle kategóriát $n-1$ darab "válaszfallal" (0-val) választjuk el egymástól. A $k$ darab kiválasztott elemet "strigulákkal" (1-esekkel) jelöljük. Egy kiválasztás így egy pontosan $n+k-1$ hosszúságú (0 és 1 számjegyekből álló) sorozatot alkot. A feladat innentől az, hogy az $n+k-1$ helyből kiválasszuk azt az $n-1$ helyet, ahová a válaszfalak (0-k) kerülnek. Ez egy sima ismétlés nélküli kombinációra vezeti vissza a problémát.
* *Képlet:*
  $$C_n^{k(ism)} = \binom{n+k-1}{n-1}$$
  *(Megjegyzés: A szimmetria miatt ez pontosan egyenlő a $\binom{n+k-1}{k}$ értékkel is.)*


összegző táblázat 

**A Kombinatorika Alapesetei ("Puska" a képletekhez)**

**1. KIVÁLASZTÁSOK (Variációk és Kombinációk)**
Amikor $n$ darab dologból választunk ki (vagy húzunk ki) $k$ darabot.

| | **Ismétlés nélküli (NINCS visszatevés)** <br> *(Minden elem csak egyszer választható)* | **Ismétléses (VAN visszatevés)** <br> *(Egy elem többször is választható)* |
| :--- | :--- | :--- |
| **SZÁMÍT a sorrend** <br> *(pl. futóverseny helyezettjei, PIN kód)* | **Ismétlés nélküli variáció** <br> $V_n^k = \frac{n!}{(n-k)!}$ <br> $= n \cdot (n-1) \cdot \dots \cdot (n-k+1)$ | **Ismétléses variáció** <br> $V_n^{k(ism)} = n^k$ <br> *(Minden helyre $n$-félét tehetünk)* |
| **NEM számít a sorrend** <br> *(pl. lottósorsolás, kártyaosztás, fagyikehely)* | **Ismétlés nélküli kombináció** <br> $C_n^k = \binom{n}{k} = \frac{n!}{k!(n-k)!}$ <br> *(A variáció leosztva a felesleges $k!$ cserével)* | **Ismétléses kombináció** <br> $C_n^{k(ism)} = \binom{n+k-1}{n-1} = \binom{n+k-1}{k}$ <br> *(A "Strigulák és Válaszfalak" trükk)* |


**A 2x2-es Táblázat Navigátora**

**1. Kérdés a SOROKHOZ: A "Helycsere" teszt (Számít a sorrend?)**
*Képzeld el, hogy már kihúztad a nyerteseket. Cseréld meg két nyertes helyét! Változott valami a feladat szempontjából?*
* **IGEN (új eredményt kaptunk):** Akkor ez a táblázat **FELSŐ SORA** (Variáció / Permutáció).
* **NEM (ugyanaz a csapat maradt):** Akkor ez a táblázat **ALSÓ SORA** (Kombináció).

**2. Kérdés az OSZLOPOKHOZ: Az "Elfogyás" teszt (Van ismétlés?)**
*Képzeld el a húzás pillanatát. Amit kihúztál, azt rögtön utána kihúzhatod újra?*
* **IGEN (nem fogy el / visszateszem):** Akkor ez a táblázat **JOBB OSZLOPA** (Ismétléses).
* **NEM (elfogyott / zsebre raktam):** Akkor ez a táblázat **BAL OSZLOPA** (Ismétlés nélküli).

---
*Bónusz kérdés a felső sorhoz:* **3. A "Mindenki játszik?" teszt (Variáció vs. Permutáció)**
*Ha a Felső Sorban (Variáció) vagy, kérdezd meg: Az összes rendelkezésre álló elemet sorba kell raknom, vagy maradnak kimaradók?*
* **Mindenkit sorba rakok:** Permutáció.
* **Maradnak kimaradók:** Variáció.

---

**2. SORBARENDEZÉSEK (Permutációk)**
Amikor mind az $n$ darab elemet felhasználjuk és sorba rakjuk ($k=n$).

* **Ismétlés nélküli permutáció ($P_n$):**
  * *Jellemző:* Minden elem **különböző** (pl. 5 különböző ember sorbaállítása).
  * *Képlet:* $P_n = n!$
* **Ismétléses permutáció ($P_n^{ism}$):**
  * *Jellemző:* Vannak teljesen **egyforma** elemek (pl. azonos színű biliárdgolyók sorbarendezése).
  * *Képlet:* $P_n^{ism} = \frac{n!}{k_1! \cdot k_2! \cdot \dots \cdot k_s!}$ *(Az összes elem faktoriálisa leosztva az egyforma csoportok faktoriálisaival).*


**2.25. Tétel: Kapcsolat a kombinatorikai alapműveletek között**

A tétel megmutatja, hogy a kiválasztások (variáció, kombináció) bizonyos esetekben visszavezethetők a teljes sorbarendezésekre (permutációkra).

**1. $V_n^n = P_n$**
* *Logika:* Ha egy $n$ elemű halmazból mind az $n$ elemet kiválasztjuk úgy, hogy számít a sorrend (nincs ismétlés), az logikailag és számszakilag is megegyezik a halmaz összes elemének sorbarendezésével (permutációjával). 
* *Bizonyítás:* $V_n^n = n \cdot (n-1) \cdot \dots \cdot (n - n + 1) = n \cdot (n-1) \cdot \dots \cdot 1 = n! = P_n$

**2. $C_n^k = P_n^{k, n-k \text{ (ism)}}$** (illetve $\binom{n}{k} = \binom{n}{k, n-k}$)
* *Logika:* Az ismétlés nélküli kombináció (kiválasztás) modellezhető egy ismétléses permutációval. Képzeljük el, hogy az $n$ elemhez $k$ darab "kiválasztott" (egyforma) és $n-k$ darab "nem kiválasztott" (egyforma) státuszt/pozíciót rendelünk. Ezeknek a státuszoknak az összes lehetséges sorbarendezése pontosan kiadja a kombinációk számát.
* *Bizonyítás:* Mindkét oldal képlete ugyanazt az algebrai alakot adja: $\frac{n!}{k! \cdot (n-k)!}$.

**2.4. A Stirling-formula (Nagy faktoriálisok becslése)**

*Probléma:* Az $n!$ (faktoriális) értéke hatalmas sebességgel nő, így nagy $n$ értékek esetén a pontos kiszámolása (vagy akár a számológépen való ábrázolása) lehetetlenné válik. Szükségünk van egy eszközre, amivel a nagyságrendjét becsülni tudjuk.

**2.26. Tétel (Stirling-formula):**
Elég nagy $n \in \mathbb{N}$ természetes számok esetén az $n!$ értéke nagyon jó közelítéssel megadható az alábbi formulával:
$$n! \approx \left(\frac{n}{e}\right)^n \cdot \sqrt{2\pi n}$$

**A becslés pontossága (Korlátok):**
Ha matematikai pontossággal akarjuk "közrefogni" (alsó és felső becslést adni) az $n!$ értékét, a következő szigorú egyenlőtlenséget használhatjuk:
$$\left(\frac{n}{e}\right)^n \cdot \sqrt{2\pi n} \cdot e^{\frac{1}{12n+1}} \le n! \le \left(\frac{n}{e}\right)^n \cdot \sqrt{2\pi n} \cdot e^{\frac{1}{12n}}$$

**Alkalmazás az informatikában:**
A formulát elsősorban nagy binomiális együtthatók értékének becslésére, illetve az algoritmusok elméletében a különböző futásidők (pl. $\mathcal{O}(2^n)$ exponenciális és $\mathcal{O}(n!)$ faktoriális algoritmusok) összehasonlítására használjuk.

**3. Fejezet: A Binomiális Tétel (Newton-tétel)**

A tétel arra ad egy gyors, általános képletet, hogy hogyan emeljünk tetszőleges $(a+b)$ kéttagú összeget $n$-edik hatványra, anélkül, hogy a zárójeleket végig kéne szoroznunk.

**3.1. Tétel (Binomiális Tétel):**
Tetszőleges $a, b \in \mathbb{C}$ számok és $n \in \mathbb{N}$ természetes szám esetén:
$$(a+b)^n = \sum_{i=0}^n \binom{n}{i} \cdot a^i \cdot b^{n-i}$$

*Konyhanyelven a formula működése:*
1. A szumma ($\sum$) azt jelenti, hogy $i$-t elindítjuk 0-tól egészen $n$-ig, és a kapott tagokat összeadjuk.
2. Minden egyes tagnál az $a$ hatványkitevője "nő" (vagy csökken), a $b$ hatványkitevője pedig ellentétesen mozog, de a két kitevő összege mindig pontosan $n$ marad.
3. A tagok előtt álló szorzószámok (a binomiális együtthatók) pedig megadják, hogy az adott betűkombináció hányféleképpen jöhetett létre a zárójelek összeszorzásakor.

**A Szumma ($\sum$) és az index ($i$) szerepe a Binomiális Tételben**

A képlet: $(a+b)^n = \sum_{i=0}^n \binom{n}{i} \cdot a^i \cdot b^{n-i}$

* **Az $n$ jelentése:** A hatványkitevő, ami egy **fix** szám marad végig (pl. hány darab zárójelünk van összesen).
* **Az $i$ jelentése:** Egy **iteratív lépésszámláló**. Nem egy fix szám, hanem folyamatosan lépked 0-tól egészen $n$-ig. Azt mutatja meg, hogy az adott lépésben hány darab "a" betűt választottunk ki.
* **A $\binom{n}{i}$ jelentése:** Teljesen megegyezik a kombinatorikából ismert "n alatt a k" ($\binom{n}{k}$) ismétlés nélküli kombinációval. Csak itt a $k$ helyett a lépésszámláló ($i$) aktuális értékét helyettesítjük be.

**Példa kibontva: $(a+b)^3$ esetén ($n=3$)**
A szumma jel miatt az $i$ értéke elindul 0-ról, és egyesével fellép 3-ig. Minden lépésben kiszámoljuk a tagot, és a végén összeadjuk őket (+):

* **Amikor $i = 0$:** $\binom{3}{0} \cdot a^0 \cdot b^3$
* **+ (Amikor $i = 1$):** $\binom{3}{1} \cdot a^1 \cdot b^2$
* **+ (Amikor $i = 2$):** $\binom{3}{2} \cdot a^2 \cdot b^1$
* **+ (Amikor $i = 3$):** $\binom{3}{3} \cdot a^3 \cdot b^0$

*Látható a szabály:* Az $n$ (a felső 3-as) végig fix maradt. Az $i$ pörgött 0-tól 3-ig. Az "a" kitevője az $i$-vel együtt nőtt, a "b" kitevője pedig csökkent, de a két kitevő összege mindig pontosan $n$ (azaz 3) maradt.


**3. Fejezet Kiegészítés: A Tört és Negatív Hatványok Titka**

**3.3. Definíció: Általánosított binomiális együttható**
Ha a felső szám egy tetszőleges (nem feltétlenül egész) $\alpha$ szám, az $\binom{\alpha}{n}$ értékét a törtes "kiejtős" szabállyal számoljuk ki:
$$\binom{\alpha}{n} := \frac{\alpha \cdot (\alpha - 1) \cdot \dots \cdot (\alpha - n + 1)}{n!}$$

**3.4. Tétel: Newton binomiális sora**
Ha egy kéttagú összeget nem egész számra (hanem pl. törtre, ami gyökvonást jelent) emelünk hatványra, a Binomiális Tétel továbbra is működik, de a kifejtés **végtelen sok tagból** fog állni:
$$(a+x)^\alpha = \sum_{i=0}^{\infty} a^{\alpha-i} \cdot \binom{\alpha}{i} \cdot x^i$$
*(Fontos kikötés: Ez csak akkor ad értelmes, véges eredményt, ha $|x| < |a|$ teljesül. Ezzel az analízis tantárgy foglalkozik részletesebben.)*


**3.2. A binomiális együtthatók tulajdonságai (Bevezető)**

**A számolás gyakorlati szabályai:**
Bár az elméleti levezetéseknél a faktoriális alakot ($\frac{n!}{k!(n-k)!}$) használjuk, a gyakorlati feladatoknál a számológépek kapacitáskorlátai miatt a törtes, "kiejtős" formát kell alkalmazni:
$$\binom{n}{k} = \frac{n \cdot (n-1) \cdot \dots \cdot (n-k+1)}{k!}$$

*Tipp extrém nagy számokhoz:* Ha nagyon sok tényezőt kellene összeszorozni, a törtet érdemes tényezőnkénti párokra bontani, hogy elkerüljük a túlcsordulást (pl. $\frac{200}{100} \cdot \frac{199}{99} \dots$).

**Az aranyszabály:** Rengeteg algebrai azonosság létezik (több száz). A mechanikus algebrai átalakítások helyett mindig a **kombinatorikai okoskodást** (logikai esetbontást, szituáció elképzelését) érdemes előnyben részesíteni.


**3.2. A binomiális együtthatók legfontosabb tulajdonságai**

A képletek magolása helyett érdemes a **kombinatorikai jelentésüket** (sztorijukat) megjegyezni!

1. **Szimmetria (3.9. Állítás, iii):** $\binom{n}{k} = \binom{n}{n-k}$
   *Logika:* Kiválasztani $k$ elemet ugyanaz, mint kiválasztani az $n-k$ darab "maradékot". (Nagy számoknál számításkönnyítő trükk!).
2. **Pascal-szabály (3.10. Állítás):** $\binom{n}{k-1} + \binom{n}{k} = \binom{n+1}{k}$
   *Logika:* Egy elemet kipécézünk. Vagy betesszük a kiválasztottak közé (ekkor a többiekből $k-1$ kell), VAGY kizárjuk (ekkor a többiekből kell mind a $k$). Erre az összeadási szabályra épül a **Pascal-háromszög**.
3. **Vandermonde-konvolúció (3.11. Állítás):** $\sum_{i=0}^k \binom{n}{i} \binom{\ell}{k-i} = \binom{n+\ell}{k}$
   *Logika:* Két különböző halmazból ($n$ és $\ell$) választunk összesen $k$ elemet úgy, hogy végigpörgetjük az összes lehetséges "felosztást" a két halmaz között.


**4. Fejezet: A Logikai Szitaformula (Tartalmazás és kizárás elve)**

Akkor használjuk, ha több halmaz (vagy tulajdonság) uniójának (összesített elemszámának) a kiszámítása a feladat, de a halmazoknak vannak közös elemei (átfedései), amiket nem akarunk többször beleszámolni.

**Alapképlet (2 halmazra):**
$|A \cup B| = |A| + |B| - |A \cap B|$
*(Összeadom az egyeseket, kivonom a közös részt).*

**Általános képlet (Több halmazra - 4.2. Tétel):**
A számolás egy váltakozó előjelű (plusz-mínusz) sorozat:
1. **(+)** Összeadjuk az egyes halmazok méretét.
2. **(-)** Kivonjuk az összes lehetséges páros metszet méretét.
3. **(+)** Hozzáadjuk az összes lehetséges hármas metszet méretét.
4. **(-)** Kivonjuk a négyes metszeteket... és így tovább, felváltva.

*Miért működik?* A bizonyítás logikája szerint így érjük el, hogy egy olyan elem, ami pontosan $r$ darab halmazban van benne, a plusz-mínusz kompenzációk végén pontosan **1-szer** legyen beleszámolva a végeredménybe.

**4.2. Fejezet: Az Elcserélt Levelek (Derangement / Hatcheck probléma)**

**A Sztori (A Részeg Postás):** Képzeljük el, hogy van $n$ darab megírt levelünk és $n$ darab megcímzett borítékunk. A postás annyira részeg, hogy teljesen vakon, véletlenszerűen dugdossa be a leveleket a borítékokba. (Ugyanez a klasszikus "Kalapellenőrzési probléma": $n$ úriember leadja a kalapját, majd a végén mindenki kap egy random kalapot).
*A kérdés:* Hányféleképpen történhet meg a teljes katasztrófa, vagyis hogy **egyetlen egy levél (vagy kalap) sem a saját (eredeti) helyére kerül?** (Ezt jelöli a könyv $|N|$-nel).

**A Megoldás Logikája (A "Kifordított" Szita):**
Közvetlenül összeszámolni a teljes káoszt szinte lehetetlen. Ehelyett a matematikusok **fordítva gondolkodnak**: 
1. **Az Alaphalmaz:** Veszik az összes lehetséges elrendezést (ez $n!$, azaz $n$ faktoriális).
2. **A Szita bedobása:** Ebből az összesből akarják kivonni azokat a "rossz" eseteket, amikor *legalább egyvalaki* a saját levelét kapja.
3. **A Plusz-Mínusz Tánc:** * Ha rögzítjük, hogy 1 ember jó levelet kap, a maradék $(n-1)!$-féleképpen keveredhet. Ezeket levonjuk.
   * De ekkor többször vontuk le azokat az eseteket, amikor 2 ember is jót kapott! Így rögzítünk 2 embert, akiknek a maradéka $(n-2)!$-féleképpen keveredhet. Ezeket visszadjuk.
   * Aztán levonjuk a 3 emberes egyezéseket, hozzáadjuk a 4 embereseket, és így tovább (Logikai szitaformula).

**A Képlet (4.5. egyenlet):**
Amikor ezt a hatalmas szitaformulát kivonjuk az összes $n!$ esetből, a rengeteg tag csodálatosan leegyszerűsödik erre az elegáns végeredményre:
$$|N| = n! \cdot \sum_{i=2}^n \frac{(-1)^i}{i!}$$

*Konyhanyelven kifejtve:*
$|N| = n! \cdot \left( \frac{1}{2!} - \frac{1}{3!} + \frac{1}{4!} - \dots \pm \frac{1}{n!} \right)$

*Miért $i=2$-től indul a szumma?*
Mert ha elindítanád 0-tól, az első két tag így nézne ki: $\frac{1}{0!} - \frac{1}{1!} = 1 - 1 = 0$. Mivel ezek nullázzák egymást, a könyv praktikusan egyből a 2-es számmal indítja a számolást.

**4.2. Fejezet Folytatás: Derangement és Szubfaktoriális**

* **Definíció:** Azt a permutációt, amelyiknek egyetlen eleme sincs az eredeti (saját) helyén, **fixpont nélküli permutációnak** vagy **derangementnek** hívjuk.
* **Jelölése:** $D_n$ (ahol $n$ az elemek száma).
* **Kiszámítási trükkök a vizsgára:** A nagy szitaformula helyett két gyors módszer is létezik:
    1.  **Rekurzió (4.10. Állítás):** $D_n = n \cdot D_{n-1} + (-1)^n$. (Ahol $(-1)^n$ páros $n$-nél $+1$, páratlannál $-1$).
    2.  **Szubfaktoriális közelítés (4.9. Állítás):** $D_n \approx \frac{n!}{e}$. A pontos $D_n$ érték mindig a kapott tört legközelebbi egész száma.
* **A "Nagy Szabály":** Bármilyen nagy is az $n$, annak a valószínűsége, hogy teljes a káosz, egy idő után állandósul $1/e$ (kb. 36,78%) értéken.


# 5. fejezet

**5. Fejezet Bevezető: Alapfogalmak**

**5. Fejezet Kiegészítés: A Rekurzió logikája és a "Szent Grál" (Az Explicit Képlet)**

**1. Hogyan működik a rekurzív képlet a gyakorlatban? (A Hanói-példa)**
A képlet: $h_n = 2 \cdot h_{n-1} + 1$
*Fontos szabály:* A képletben szereplő $n$ a korongok száma, a $h$ pedig a hozzájuk tartozó lépésszám!
* Ha 3 korongunk van ($n=3$), a képlet így néz ki: $h_3 = 2 \cdot h_2 + 1$
* Mivel tudjuk, hogy 2 korong átrakása 3 lépés ($h_2 = 3$), ezt behelyettesítjük: 
  $h_3 = 2 \cdot 3 + 1 = 7$ lépés.

**2. Mitől "rekurzív" ez a szabály?**
A rekurzió lényege: **a szabály önmagát hívja meg**. Az egyenlőségjel mindkét oldalán ott van a $h$ betű! Ha meg akarjuk tudni a 4 korongos megoldást ($h_4$), ahhoz előbb meg kell kérdeznünk a saját szabályunkat a 3 korongra ($h_3$), ahhoz pedig a 2 korongra ($h_2$), egészen nulláig.

**3. Mi a baj a rekurzióval? (A "Szívás-faktor")**
Ha egy vizsgán megkérdezik, mennyi a $h_{100}$ (100 korong lépésszáma), a rekurzív képlettel visszafelé kéne lépkednünk egészen 1-ig, majd onnan egyesével, 99-szer elvégezni a szorzást és összeadást. Ez emberileg kiszámolhatatlan.

**4. A Cél: Az Explicit Képlet (A Táblakép lényege)**
A matematika (és az órai táblakép) fő célja, hogy ezt a "visszautalós" rekurziót átalakítsa egy **Explicit Képletté** ($a_n = \dots$). 
* Az explicit képletben a jobb oldalon már *nincs ott* a visszautalós betű, csak maga az $n$ szám!
* (A Hanói tornyok explicit képlete pl. $h_n = 2^n - 1$). Ebbe elég csak beütni a 100-ast a számológépbe ($2^{100} - 1$), és azonnal megkapjuk a végeredményt, a korábbi 99 lépés kiszámolása nélkül!
* **Az eszköz:** Hogy hogyan csinálunk a rekurzióból explicit képletet? Erre való a tanár által tanított **Karakterisztikus egyenlet**!

**5. Rekurzió (5.0. Def):** Olyan szabály, ahol az $n$-edik elemet ($a_n$) az előző elemek (pl. $a_{n-1}, a_{n-2}$) segítségével számoljuk ki.
**6. Rendszám ($k$):** Azt mutatja meg, hogy hány lépést kell visszanéznünk a kiszámításhoz (k-adrendű).
**7. K.É.P. (Kezdeti érték probléma):** Egy $k$-adrendű sorozat elindításához pontosan $k$ darab fix kezdőértéket kell megadni a legelején (pl. $a_0, a_1$).
**8. Fibonacci-sorozat (5.2. Példa):** Klasszikus másodrendű rekurzió ($f_n = f_{n-1} + f_{n-2}$), amihez a *Binet-formula* adja meg a bonyolult, gyökös explicit megoldást.


**5.2. Előzetes: A Karakterisztikus Egyenlet logikája (A rekurzió "megölése")**

**A Probléma:** A rekurzív (visszautalós) egyenletekből (pl. $a_n = 3a_{n-1} - 7a_{n-2}$) képtelenség gyorsan kiszámolni a 100. tagot. Olyan "explicit" képletet akarunk ($a_n = \dots$), amiben csak az $n$ szerepel, és azonnal számolható.

**A Megoldás (A "Mágikus Tipp"):**
A matematikusok észrevették, hogy ezek a sorozatok a végén mindig valamilyen hatványozásra (mértani sorozatra) vezethetők vissza. Ezért bevetik az alábbi trükköt:

1. **A Tipp (Helyettesítés):** Feltételezzük, hogy a keresett explicit képlet valamilyen ismeretlen $q$ számnak az $n$-edik hatványa. Tehát bevezetjük, hogy: **$a_n = q^n$**.
2. **A Beírás:** Ezt a $q^n$-t kíméletlenül beírjuk a rekurzív egyenletbe minden $a$ betű helyére. (Például az $a_{n-1}$ helyére $q^{n-1}$ kerül, az $a_{n-2}$ helyére $q^{n-2}$).
3. **Az Átalakulás (A Karakterisztikus Egyenlet):** Ha az így kapott egyenletet leosztjuk a legkisebb $q$ hatvánnyal, a végtelen rekurzió hirtelen eltűnik! Helyette kapunk egy sima, középiskolás (pl. másodfokú) egyenletet (pl. $q^2 = 3q - 7$). 

Ezt a sima egyenletet hívjuk **Karakterisztikus Egyenletnek**. Ha ennek kiszámoljuk a megoldásait (a $q_1$ és $q_2$ gyököket), abból már gyerekjáték összerakni a végső explicit képletet!

**5.2. Alapfogalmak: A Rekurziók "Személyleírása" (5.4. Definíció)**

A vizsgán és az órán leggyakrabban a következő típusú egyenletekkel dolgozunk:
**"Állandó együtthatójú homogén lineáris k-adrendű rekurzió"**

Mit jelentenek a kifejezések konyhanyelven?
* **Lineáris:** A korábbi elemeket ($a_{n-1}, a_{n-2}$) csak egyszerű számokkal szorozzuk és összeadjuk (nincs négyzetre emelés, gyökvonás stb.).
* **k-adrendű:** Pontosan $k$ lépést (elemet) kell visszanéznünk a múltba a kiszámításhoz.
* **Állandó együtthatójú:** A korábbi elemeket szorzó számok ($d_1, \dots, d_k$) fix konstansok, nem függnek az $n$-től.
* **Homogén:** Az egyenletben *csak* a múltbeli tagok (és szorzataik) szerepelnek. Az egyenlet végén lévő "független", maradék tag (a $b_n$) pontosan **0**. (Ha $b_n \neq 0$, pl. lóg ott egy $+1$, akkor Inhomogénnek hívjuk).

**5.2.2. A Karakterisztikus Egyenlet (A "Klasszikus Módszer" receptje)**

Ezzel a 4 lépéssel csinálunk a rekurzív "visszautalós" szabályból explicit ($a_n = \dots$) képletet a vizsgán!

**1. Lépés: A Karakterisztikus egyenlet felírása**
Cseréld ki a sorozat elemeit $q$ megfelelő hatványaira. Egy másodrendű egyenletnél (pl. $a_n = A \cdot a_{n-1} + B \cdot a_{n-2}$):
* $a_n$ helyére írj **$q^2$**-et.
* $a_{n-1}$ helyére írj **$q$**-t.
* $a_{n-2}$ helyére írj **1**-et (a $q$ eltűnik, csak a konstans marad).
Eredmény: Egy sima másodfokú egyenlet ($q^2 = A \cdot q + B$).

**2. Lépés: A Gyökök kiszámolása**
Rendezd nullára az egyenletet ($q^2 - Aq - B = 0$), és oldd meg a másodfokú megoldóképlettel! Kapsz két gyököt: $q_1$ és $q_2$.

**3. Lépés: Az általános explicit képlet felírása (Két eset van!)**
* **A) Ha a két gyök különböző ($q_1 \neq q_2$):** (5.11. Tétel)
  A képlet: **$a_n = c_1 \cdot q_1^n + c_2 \cdot q_2^n$**
* **B) Ha a két gyök megegyezik ($D=0$, tehát $q_1 = q_2 = q$):** (5.13. Állítás)
  A második tagot "fel kell ütni" egy $n$ szorzóval!
  A képlet: **$a_n = c_1 \cdot q^n + c_2 \cdot n \cdot q^n$**

**4. Lépés: A $c_1$ és $c_2$ konkrét kiszámolása (K.É.P. behelyettesítés)**
Az előző lépésben kapott egyenlet még "általános" (benne vannak a $c$ betűk). Hogy pontos számokat kapjunk, használjuk a feladatban megadott Kezdeti Értékeket (pl. $a_0 = 1, a_1 = 3$)!
* Írjuk be az $n$ helyére a 0-t, és egyenltsük ki az $a_0$ értékével (Kapunk egy egyenletet).
* Írjuk be az $n$ helyére az 1-et, és egyenltsük ki az $a_1$ értékével (Kapunk még egy egyenletet).
Ebből a kétismeretlenes egyenletrendszerből kiszámoljuk $c_1$-et és $c_2$-t, visszarakjuk a 3. lépés képletébe, és kész a végső Explicit Képlet!


**5.3. A Fibonacci-sorozat levezetése**

**A Feladat:** Keressük meg az $f_n = f_{n-1} + f_{n-2}$ rekurzió explicit képletét, ha a kezdőértékek (K.É.P.) $f_0 = 0$ és $f_1 = 1$.
*(Nullára rendezve: $f_n - f_{n-1} - f_{n-2} = 0$)*

**A 4 lépéses "Svájci Bicska" módszer a gyakorlatban:**

**1. Lépés: A Karakterisztikus egyenlet**
Kicseréljük az $f$ betűket a $q$ megfelelő hatványaira:
* $f_n \rightarrow q^2$
* $f_{n-1} \rightarrow q^1$ (azaz $q$)
* $f_{n-2} \rightarrow 1$
Kapott egyenlet: **$q^2 - q - 1 = 0$**

**2. Lépés: A Gyökök kiszámolása**
A másodfokú megoldóképletből két különböző, "csúnya" gyököt kapunk:
$$q_{1,2} = \frac{1 \pm \sqrt{5}}{2}$$

**3. Lépés: Az általános képlet felírása (1. Eset: Különböző gyökök)**
Mivel a két gyök nem egyenlő, simán csak beírjuk őket a képletbe:
$$f_n = c_1 \cdot \left(\frac{1+\sqrt{5}}{2}\right)^n + c_2 \cdot \left(\frac{1-\sqrt{5}}{2}\right)^n$$

**4. Lépés: A $c_1$ és $c_2$ kiszámolása (K.É.P. alapján)**
Behelyettesítjük az $n = 0$ és $n = 1$ értékeket az egyenletbe:
* $n=0$ esetén: $0 = c_1 + c_2$ (amiből következik, hogy $c_1 = -c_2$).
* $n=1$ esetén: $1 = c_1 \cdot \frac{1+\sqrt{5}}{2} + c_2 \cdot \frac{1-\sqrt{5}}{2}$.

A kétismeretlenes egyenletrendszer megoldása: $c_1 = \frac{1}{\sqrt{5}}$ és $c_2 = -\frac{1}{\sqrt{5}}$.

**Végeredmény (A Binet-formula):**
Ezeket a "c" értékeket visszaírva a 3. lépésbe megkapjuk a tökéletes, azonnal számolható explicit képletet!
$$f_n = \frac{1}{\sqrt{5}} \cdot \left( \left(\frac{1+\sqrt{5}}{2}\right)^n - \left(\frac{1-\sqrt{5}}{2}\right)^n \right)$$

**5.3. A Fibonacci-sorozat levezetése**

A tankönyvi levezetés sok lépést átugrik, ezért itt van lépésről lépésre, hogy megértsük a matematikáját!
**A Feladat:** Készítsünk explicit képletet az $f_n = f_{n-1} + f_{n-2}$ szabályból, ahol a kezdőértékek: $f_0 = 0$ és $f_1 = 1$.

**1. Lépés: Hogyan lesz az $f$-ből $q$-s egyenlet?**
* Először rendezzünk mindent egy oldalra, hogy a jobb oldal 0 legyen: 
  $f_n - f_{n-1} - f_{n-2} = 0$
* Alkalmazzuk a "Mágikus Tippet" (a cserét):
  * Az $f_n$ (legújabb) kapja a legnagyobb hatványt: **$q^2$**
  * Az $f_{n-1}$ (eggyel régebbi) kapja a **$q^1$**-et (azaz sima $q$)
  * Az $f_{n-2}$ (legrégebbi) elveszti a $q$-t, csak a szorzószáma marad (ami itt $-1$).
* Eredmény: **$q^2 - q - 1 = 0$**

**2. Lépés: Honnan jön a $\sqrt{5}$? (A gyökök kiszámolása)**
* Beütjük az egyenletet a középiskolás másodfokú megoldóképletbe: $q_{1,2} = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$
* Nálunk $a=1, b=-1, c=-1$. A gyökjel alatt ez történik: $\sqrt{(-1)^2 - 4 \cdot 1 \cdot (-1)} = \sqrt{1 + 4} = \sqrt{5}$.
* Eredmény a két gyök: **$q_1 = \frac{1 + \sqrt{5}}{2}$** és **$q_2 = \frac{1 - \sqrt{5}}{2}$**

**3. Lépés: A sablon képlet felírása**
Mivel a két gyök különböző, a sablonunk így néz ki:
$$f_n = c_1 \cdot \left(\frac{1+\sqrt{5}}{2}\right)^n + c_2 \cdot \left(\frac{1-\sqrt{5}}{2}\right)^n$$

**4. Lépés: Hogyan számoljuk ki a $c_1$ és $c_2$ értékét?**
Használjuk a K.É.P.-t ($f_0 = 0, f_1 = 1$), és írjuk be az $n$ helyére a 0-t és az 1-et!
* **Ha $n=0$ (A 0. hónap):** Bárminek a nulladik hatványa 1. Tehát a sablonból ez marad: $0 = c_1 \cdot 1 + c_2 \cdot 1$. Ebből kiderül, hogy a két szám egymás ellentéte: **$c_1 = -c_2$**.
* **Ha $n=1$ (Az 1. hónap):** Bárminek az első hatványa önmaga marad. $1 = c_1 \cdot \frac{1+\sqrt{5}}{2} + c_2 \cdot \frac{1-\sqrt{5}}{2}$.
* Mivel tudjuk, hogy $c_2$ az ellentéte $c_1$-nek, behelyettesítve és átrendezve kijön a két "c" érték:
  $c_1 = \frac{1}{\sqrt{5}}$ és $c_2 = -\frac{1}{\sqrt{5}}$

**A Végeredmény (Binet-formula):**
Ha ezeket a tört értékeket visszaírjuk a sablonunk (3. lépés) elejére, megkapjuk a "Szent Grált":
$$f_n = \frac{1}{\sqrt{5}} \cdot \left( \left(\frac{1+\sqrt{5}}{2}\right)^n - \left(\frac{1-\sqrt{5}}{2}\right)^n \right)$$


# 6. fejezet

**6. Fejezet: Generátorfüggvények**

**A módszer lényege (A "Végtelen Vonat" hasonlat):** Egy nehezen kezelhető $(a_n)$ végtelen számsorozatot felültetünk egy matematikai vonatra. 
* **A vagonok:** Az $x$ növekvő hatványai ($x^0, x^1, x^2 \dots$). Az $x$-nek nincs konkrét számszerű értéke, csak egy helyjelölő "címke" (pl. az $x^2$ jelenti a 2-es számú vagont).
* **Az utasok:** A sorozatunk elemei ($a_0, a_1, a_2 \dots$), amiket "beültetünk" az egyre növekvő számú vagonokba, mint szorzószámok (együtthatók).

**6.0. Definíció (Generátorfüggvény):**
Egy tetszőleges $(a_n)$ számsorozat generátorfüggvénye az a végtelen hosszú "polinom" (hivatalos nevén: hatványsor), ahol a sorozat elemei adják az $x$ hatványainak együtthatóit:
$$F(x) := \sum_{n=0}^{\infty} a_n x^n = a_0 \cdot x^0 + a_1 \cdot x^1 + a_2 \cdot x^2 + a_3 \cdot x^3 + \dots$$

*Miért zseniális ez?*
Mert a végtelen számlistákkal nehéz számolni, de egy "barátságos" $x$-es függvénnyel könnyű! 
Például egy fontos trükk (6.1. iii megjegyzés): ha a teljes $F(x)$ vonatot megszorzod $x$-szel, akkor minden utas automatikusan átszáll egy vagonnal feljebb (pl. az $a_1$ az $x^1$-ből átkerül az $x^2$-be). Ezzel a sorozat bonyolult "eltolása" egy pofonegyszerű algebrai szorzássá válik!


**6.4. Példa: A Hanói Tornyok és a Generátorfüggvény**

**A Probléma:** A Hanói tornyok lépésszámát egy rekurzív (előző tagra visszautalós) képlet adja meg: $h_{n+1} = 2 \cdot h_n + 1$. Ha a 100. lépést akarjuk tudni, végig kéne számolni az előző 99-et. Ezt a végtelen számolást akarjuk "betömöríteni" egyetlen függvénybe!

**A Megoldás (Konyhanyelven és Matekul):**

**1. Lépés: A "Nulladik utas" meghatározása**
Mivel a generátorfüggvényünk (a Végtelen Vonat) a 0. vagonnal ($x^0$) indul, szükségünk van egy kezdőértékre. Logikusan gondolkodva: 0 darab korong átrakásához 0 darab lépés szükséges. Tehát: $h_0 := 0$.

**2. Lépés: Felültetés a vonatra (A Nagy Trükk)**
Vesszük az eredeti rekurzív képletünket, megszorozzuk az $x$ megfelelő hatványával ($x^{n+1}$), és mindkét oldal elé odarakunk egy végtelen szummát ($\sum_{n=0}^{\infty}$). Ezzel a lépéssorozatunk hivatalosan is "felszállt a vonatra".
A kapott egyenlet: 
$$\sum_{n=0}^{\infty} h_{n+1} \cdot x^{n+1} = 2x \cdot \sum_{n=0}^{\infty} h_n x^n + x \cdot \sum_{n=0}^{\infty} x^n$$

**3. Lépés: A "Zip fájl" létrehozása ($H(x)$ bevezetése)**
A sok ijesztő szummát (a teljes vonatot) elnevezzük egyetlen betűnek: **$H(x)$**. 
* A bal oldal maga a $H(x)$ vonat, amiről hiányzik a nulladik utas: $H(x) - h_0$.
* A jobb oldalon az első szumma a sima vonat megszorozva $2x$-szel: $2x \cdot H(x)$.
* A jobb oldal végén lógó "simlis" végtelen $x$-összeget ($\sum x^n$) pedig a mértani sorozat képletével egyszerűsítjük: $\frac{1}{1-x}$.

**4. Lépés: A Végeredmény (A 6.6-os képlet)**
Ha a fenti "becsomagolt" betűket behelyettesítjük az egyenletbe, és átrendezzük azt $H(x)$-re (tudva, hogy $h_0 = 0$), megkapjuk a tömörített végeredményt:
$$H(x) = \frac{x}{(1-x)(1-2x)}$$

**Konklúzió:** Ez az apró, barátságos tört a Hanói tornyok generátorfüggvénye. Ebbe az egyetlen törtbe bele van kódolva a játék összes létező lépésszáma a végtelenségig! 
*(Megjegyzés: A 6.5. Módszer ugyanezt a folyamatot írja le általánosan, bármilyen hasonló "visszautalós + 1" típusú problémára).*

**6.6. Tétel: A Generátorfüggvények "Rosette-i köve"**

Ez a tétel megteremti a tökéletes, oda-vissza kapcsolatot a rekurzív sorozatok és az algebrai törtek között.

**A Tétel kimondja:**
Egy $(a_n)$ sorozat generátorfüggvénye **pontosan akkor** írható fel egy racionális törtfüggvény (két polinom hányadosa, $\frac{p(x)}{q(x)}$) alakjában, **ha** az $(a_n)$ sorozat elemei egy állandó együtthatójú homogén lineáris rekurziót (egy fix "visszautalós" szabályt) elégítenek ki. 
*Kikötés:* A tört nevezője nem lehet 0, ha az $x$ helyére 0-t helyettesítünk (hogy elkerüljük a nullával való osztást a visszafejtésnél).

**Konyhanyelven (A "Végtelen Vonat" logikájával):**
1. Ha az utasok (a sorozat elemei) egy fix szabály alapján utalnak vissza az előző utasokra (pl. Fibonacci), akkor az egész végtelen vonat betömöríthető egy egyszerű, véges algebrai törtbe.
2. És fordítva: ha van egy generátorfüggvényed, ami egy polinom per polinom tört, abból biztosan egy "visszautalós" szabály szerint felépülő végtelen számsorozat fog kicsomagolódni.

