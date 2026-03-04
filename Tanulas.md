**Alapok**

**f : A -> B = f :A -> B  f függvény, és Dom(f) A** 
  -> Dom(f) Dominium (Terület) latin szóból ered ami az értelmezési tartományt jelenti. 
  ->  f: A -> B  f olyan függvény amelyben A elemeit hozzárendeljük B-hez, 

További jelölésektől ledobtam a láncot. Erre most nem pazaroltam az időt, mentem tovább az első fejezethez. =(


# Halmazok  

**A középiskolai definició hibás:** " halmaz = azonos tulajdonságú elemek összessége"

**Cantor-tétel viszont kijelenti:** Nem létezik olyan halmaz, ami a világon MINDENT tartalmaz. Nincs egy „Szuper-Mindent-Bele Doboz”.

TFH mégis van ez a mindent tartalmazó doboz ->  ($Y := \{x \in Z \mid x \notin x\}$)

-  Vannak olyan halmazok amelyek nem tartalmazzák saját magukat.  

## Lépés: "Tartalmazza-e önmagát?"
Képzelj el egy hatalmas könyvtárat, ahol a könyvtáros különféle katalógusokat (listákat) készít a könyvekről. Egy katalógus is egy könyv, csak listák vannak benne.

Kétféle katalógus létezik:

Az 1. típus (NEM tartalmazza önmagát): Például a "Szakácskönyvek katalógusa". Mivel ez a könyv maga egy katalógus, és nem egy szakácskönyv, ezért nem írja bele saját magát a saját listájába. A dobozos példában ez az "almák halmaza", ami maga nem egy alma.

A 2. típus (TARTALMAZZA önmagát): Például a "Magyar nyelven nyomtatott könyvek katalógusa". Mivel ez a katalógus is magyarul van nyomtatva, ezért bele kell írnia a saját címét is a listába! Tehát ez a lista tartalmazza saját magát.

## Lépés: Hozzuk létre az $Y$ katalógust!

Nézzük a képletet, amit írtál, és fordítsuk le magyarra:
- $Y := \{x \in Z \mid x \notin x\}$$Y :=$ 
Jelentsen az $Y$ katalógus...
- $\{x \in Z \mid$ ... egy olyan gyűjteményt a világ összes dolga ($Z$) közül, amire igaz az a szabály, hogy...
- $x \notin x \}$ ...az adott dolog ($x$) nincs benne önmagában ($x$-ben).

## 3. Lépés: A bumm (Miért esik szét az agyunk?)

A könyvtáros szépen megírja ezt az $Y$ katalógust. De amikor a végére ér, feltesz magának egy kérdést, miközben a kezében tartja a kész $Y$ könyvet:"Vajon ezt az $Y$ katalógust beírjam-e a saját magába, vagy sem?"

### Logikai csapda:

- Ha BEÍRJA: Ha beírja magát a listába, akkor $Y$ egy olyan katalógus lett, ami tartalmazza önmagát. De várjunk! Az $Y$ borítójára az van írva, hogy ide CSAK azokat szabad beírni, amik nem tartalmazzák önmagukat. Tehát ki kell radírozni!
- Ha NEM ÍRJA BE (kiradírozza): Ha nincs benne a listában, akkor $Y$ egy olyan katalógus, ami nem tartalmazza önmagát. De várjunk! Az $Y$ szabálya az volt, hogy minden ilyet KÖTELEZŐ beírni! Tehát mégis be kell írni!

### 1.2-es definició

#### 1. Minden vizsgált objektum halmaz, lehet eleme egy másik halmaznak, nincs elem és halmaz megkülönböztetés.

#### 2. Tetszőleges x és A esetén az x ∈ A és az x ∉ A relációk közül pontosan az egyik teljesül. 
- Egy tetszőleges A halmaz pontosan akkor egyértelműen megadott vagy meghatározott, ha tetszőleges x esetén az x ∈ A és az x ∉ A relációk közül egyértelmű hogy melyik áll fenn.
#### 3.  Két tetszőleges A , B halmaz pontosan akkor azonos, A=B , ha tetszőleges x esetén az x ∈ A és az x ∈ B relációk ugyanakkor teljesülnek (ill. nem teljesülnek).
#### 4. Egy tetszőleges A halmaz üres halmaz, ha minden x esetén x ∉ A teljesül

### 1.3-es definició

#### Üres halmaz (legfeljebb) csak egy lehet.

Bizonyítás: Ha A és B mindkettő üres halmaz, akkor minden x esetén az x ∉ A és az x ∉ B relációk mindegyike teljesül, vagyis a (iii) axióma szerint A = B

## Boole- algebrák
## 1.4. Állítás

Tetszőleges $A, B, C \subseteq I$ halmazokra teljesülnek az alábbi azonosságok:

### Kommutativitás
- (BA1)  
  $$
  A \cup B = B \cup A
  $$
- (BA2)  
  $$
  A \cap B = B \cap A
  $$

- A kommutativitás azt jelenti, hogy egy adott művelet elvégzésekor a halmazok (az operandusok) sorrendje felcserélhető, és ez nem változtatja meg a végeredményt.

### Asszociativitás
- (BA3)  
  $$
  A \cup (B \cup C) = (A \cup B) \cup C
  $$
- (BA4)  
  $$
  A \cap (B \cap C) = (A \cap B) \cap C
  $$

- Az asszociativitás, vagyis a csoportosíthatóság azt jelenti, hogy ha három vagy több halmazon végig ugyanazt a műveletet (például csak uniót vagy csak metszetet) hajtjuk végre, akkor a műveletek elvégzésének sorrendjét kijelölő zárójelek szabadon áthelyezhetők, mert a végeredmény minden esetben változatlan marad.

PL:
- $A \cup (B \cup C) = (A \cup B) \cup C$ (BA3): Képzeld el, hogy turmixot csinálsz eperből ($A$), banánból ($B$) és tejből ($C$). Teljesen mindegy, hogy először a banánt és a tejet turmixolod össze (ez a zárójel), és utána dobod bele az epret, vagy először az epret és a banánt pépesíted, majd felöntöd tejjel. A végeredmény pontosan ugyanaz az epres-banános turmix lesz.
- $A \cap (B \cap C) = (A \cap B) \cap C$ (BA4): Itt a közös tulajdonságokat keressük három embernél 
($A, B, C$). Mindegy, hogy először megnézed, mi a közös $B$-ben és $C$-ben (zárójel), majd megnézed, hogy $A$-nak mi a közös ezzel a szűkített listával; vagy először $A$ és $B$ közös dolgait keresed meg, és ahhoz nézed hozzá $C$-t. A végén kapott "közös metszet" hajszálpontosan ugyanaz marad.


### Disztributivitás
- (BA5)  
  $$
  A \cup (B \cap C) = (A \cup B) \cap (A \cup C)
  $$
- (BA6)  
  $$
  A \cap (B \cup C) = (A \cap B) \cup (A \cap C)
  $$

- $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$ (BA6)Képzeld el, hogy teát készítesz, és a következő "halmazokból" válogathatsz:$A$: 
  - Fekete tea$B$:
  - Citrom$C$:
  - Cukor 
- A bal oldal jelentése ($A \cap (B \cup C)$): Kérsz egy Fekete teát ($A$), ÉS ($\cap$) mellé ízesítésnek kérsz Citromot VAGY Cukrot ($B \cup C$).
- A jobb oldal jelentése ($(A \cap B) \cup (A \cap C)$): Ez a rendelés pontosan ugyanazt jelenti, mintha azt mondanád a pincérnek: "Kérek egy citromos fekete teát ($A \cap B$) VAGY egy cukros fekete teát ($A \cap C$)".

"A disztributivitás (széttagolhatóság vagy zárójelbontás) azt jelenti, hogy amikor egy halmazműveletet (pl. metszetet) egy másik művelettel (pl. unióval) összekapcsolt halmazokon végzünk el, akkor a külső műveletet tagonként 'bevihetjük' a zárójelbe, pontosan úgy, ahogy az algebrában a szorzást felbontjuk az összeadáson."

Ez pontosan ugyanúgy működik mint ha azt csinálom, hogy: 
- A 2 * (3+4) = 3+4 = 7 és 7*2  =14
- Vagy ha felbntom a zárójelet, is ugyyanazt a számot kapom: 2*3 + 2*4 = 14 

### Elnyelési tulajdonságok
- (BA7)  
  $$
  A \cup (A \cap B) = A
  $$
- (BA8)  
  $$
  A \cap (A \cup B) = A
  $$

- **BA7** - $A \cup (A \cap B) = A$ 
  - Mi az az $(A \cap B)$? Ők a te ismerőseid közül azok, akik szeretik a pizzát (a közös rész). Ez egy kisebb csoport, ami teljesen benne van a te ismerőseid körében ($A$).
  - Most jön a külső művelet ($\cup$): Fogd az összes ismerősödet ($A$), és "öntsd hozzájuk" azokat az ismerőseidet, akik szeretik a pizzát.
  - Mi történik? Semmi! Nem adtál hozzá senki újat a csapathoz, hiszen ők már eleve ott voltak az ismerőseid között. A nagy halmaz ($A$) egyszerűen elnyelte a felesleges kört, az eredmény maradt simán $A$.

- **(BA8)** - $A \cap (A \cup B) = A$
    - Mi az az $(A \cup B)$? Egy hatalmas tömeg: mindenki, aki vagy a te ismerősöd, vagy szereti a pizzát (vagy mindkettő).
    - Most jön a külső művelet ($\cap$): Keresd meg a közös részt a te ismerőseid ($A$) és e között a hatalmas tömeg között.
    - Mivel a te ismerőseid mind ott állnak ebben a hatalmas tömegben, a "közös rész" pontosan a te ismerőseid csapata lesz. Megint eltűnt a $B$, az eredmény simán $A$ maradt.

- Az elnyelési tulajdonság (abszorpció) azt mondja ki, hogy ha egy halmazt uniózunk vagy metszünk egy olyan kifejezéssel, amelyben ő maga is szerepel a másik fajta művelettel összekötve, akkor a kívül lévő halmaz teljesen 'elnyeli' a zárójeles részt, így a végeredmény önmaga marad.


### $\emptyset$ és $I$ tulajdonságai
- (BA9)  
  $$
  A \cup \overline{A} = I
  $$
- (BA10)  
  $$
  A \cap \overline{A} = \emptyset
  $$
- (BA11)  
  $$
  A \cup \emptyset = A
  $$
- (BA12)  
  $$
  A \cap \emptyset = \emptyset
  $$
- (BA13)  
  $$
  A \cup I = I
  $$
- (BA14)  
  $$
  A \cap I = A
  $$

- A halmaz és az ellentéte (komplementere):
- $A \cup \overline{A} = I$ (BA9): 
  - Ha egy óriási teremben összeöntöd a te almáidat ($A$) az összes olyan dologgal, ami nem a te almád ($\overline{A}$), akkor logikus, hogy megkapod a világ összes létező dolgát ($I$).
- $A \cap \overline{A} = \emptyset$ (BA10):
  -  Mi a közös ($\cap$) a te almáidban és azokban a dolgokban, amik nem a te almáid? Semmi! Nem lehetsz egyszerre bent is meg kint is. Ezért az eredmény az üres halmaz ($\emptyset$).

**Találkozás a "Semmivel" ($\emptyset$)**
- :$A \cup \emptyset = A$ (BA11): Ha a te dobozodhoz ($A$) hozzáöntesz ($\cup$) egy teljesen üres dobozt ($\emptyset$), akkor nem változik semmi, marad a te dobozod ($A$). (Mintha a matekban hozzáadnál nullát).
- - $A \cap \emptyset = \emptyset$ (BA12): Mi a közös ($\cap$) a te dobozod és egy teljesen üres doboz tartalmában? Hát a semmi! Ezért a közös rész üres lesz. (Mintha a matekban szoroznál nullával).

**Találkozás a "Mindenséggel" ($I$):$A \cup I = I$ (BA13):** 
- Ha a te dobozodat bedobod a Világmindenség hatalmas dobozába, és összekevered őket ($\cup$), a végeredmény egyszerűen a Világmindenség marad ($I$), hiszen a te kis dobozod már eleve része volt a nagy egésznek.
- $A \cap I = A$ (BA14): Mi a közös ($\cap$) a te dobozodban ($A$) és a világ összes dolgában ($I$)? Pontosan a te dobozod tartalma! Hiszen a te dolgaid is a világ részei.


Az üres halmaz ($\emptyset$) és az alaphalmaz ($I$) azonosságai megmutatják, hogy ha egy halmazt a 'semmivel' ($\emptyset$), a 'mindenséggel' ($I$), vagy a saját ellentétével ($\overline{A}$) vonunk össze unióval vagy metszettel, akkor a végeredmény mindig egy alapvető halmazzá (önmagává, az üres halmazzá vagy az alaphalmazzá) egyszerűsödik.

**1.5. Definíció: Algebrai struktúra**

Az algebrai struktúra egy matematikai "csomag", amely megadja az elemeket és a velük végezhető szabályokat. 
Jelölése: $\mathcal{A} := (H, f_1, ..., f_m, R_1, ..., R_n)$.

**A struktúra felépítése:**
* **Alaphalmaz ($H$):** Egy nemüres halmaz, amelynek elemeivel dolgozunk (a "játék bábui").
* **Műveletek ($f_1, ..., f_m$):** Úgynevezett $\tau(i)$-változós függvények. Megmondják, hány elemből hozunk létre egy újat (pl. az összeadáshoz 2 szám kell).
* **Relációk ($R_1, ..., R_n$):** Úgynevezett $\pi(j)$-változós relációk. Elemek közötti viszonyokat vagy tulajdonságokat vizsgálnak (pl. kisebb-egyenlő vizsgálat 2 szám között).
* **Konstansok ($c \in H$):** Kitüntetett elemek az alaphalmazból (pl. a $0$ vagy az $1$). Ezek $0$-változós függvényeknek is tekinthetők, mert csak "vannak", nem kell hozzájuk bemenet.
* **Típus ($\text{type}(\mathcal{A})$):** Egy statisztika, ami megmutatja, hogy a csomagban lévő műveletek és relációk hány változósak, és hány konstans van benne.

---
**Példa egy algebrai struktúrára:**

Az egész számok szokásos rendszere felírva algebrai struktúraként:
$\mathcal{A} = (\mathbb{Z}, +, \cdot, \leq, 0, 1)$

* **Alaphalmaz ($H$):** $\mathbb{Z}$ (Egész számok)
* **Műveletek:** $+$ (összeadás, 2-változós) és $\cdot$ (szorzás, 2-változós)
* **Relációk:** $\leq$ (kisebb-egyenlő, 2-változós)
* **Konstansok:** $0$ és $1$

**1.6. Definíció: Boole-algebra (BA)**

**A Boole-algebra, mint "Társasjáték" (A struktúra)**

- A definíció eleje azt mondja, hogy a Boole-algebra egy $\mathcal{B} = (H, \vee, \wedge, \neg, |, \circ)$ struktúra. Mit jelent ez az előző (1.5) leckénk alapján?
  - Van egy alaphalmazunk ($H$), ezek a játékelemek.
  - Vannak műveleteink ($\vee, \wedge, \neg$).
  - Vannak kitüntetett, "konstans" bábujaink ($|$ és $\circ$).
- Mit jelent a típusa? $((2, 2, 1, 0, 0), ())
- $Emlékszel, ez volt a "doboz hátuljára írt statisztika". Bontsuk ki a számokat:
  - $2$: A $\vee$ művelethez két dolog kell (pl. A $\vee$ B).
  - $2$: A $\wedge$ művelethez is két dolog kell (pl. A $\wedge$ B).
  - $1$: A $\neg$ (ellentét) művelethez csak egy dolog kell (pl. $\neg$A).
  - $0, 0$: A két kitüntetett elemünknek ($|, \circ$) nem kell bemenet, ők csak vannak.
  - $()$: A második zárójel üres! Miért? Mert ebben a játékban nincsenek relációk (mint pl. a $\leq$), csak műveletek.
- A FőszabályEgy ilyen "játékdoboz" csak és kizárólag akkor hívható Boole-algebrának, ha az elemeivel tökéletesen el lehet játszani azt a 14 szabályt (BA1-BA14), amit az előző oldalon megtanultunk (kommutativitás, disztributivitás, stb.). Csak most az $A \cup B = B \cup A$ helyett azt írjuk, hogy $A \vee B = B \vee A$.


A Boole-algebra lényegében a halmazműveleteknél megismert játékszabályok (BA1-BA14) alkalmazása egy új jelölésrendszerrel. 

### Halmazelmélet vs. Boole-algebra jelölések

**Listás nézet:**
* **Unió / Összeöntés:** A régi $\cup$ új jele a $\vee$ (ez a "VAGY" művelet).
* **Metszet / Közös rész:** A régi $\cap$ új jele a $\wedge$ (ez az "ÉS" művelet).
* **Komplementer / Ellentét:** A régi $\overline{A}$ új jele a $\neg$ (ez a "NEM" művelet).
* **Alaphalmaz / Mindenség:** A régi $I$ új jele a $|$ (vagy $1$-es, ez az "egységelem").
* **Üres halmaz / Semmi:** A régi $\emptyset$ új jele a $\circ$ (vagy $0$-s, ez a "nullelem").

---

**Táblázatos nézet:**

| Fogalom | Halmazelmélet (Régi) | Boole-algebra (Új) | Informatikai név |
| :--- | :---: | :---: | :--- |
| **Unió / Összeöntés** | $\cup$ | $\vee$ | VAGY (OR) / Diszjunkció |
| **Metszet / Közös rész** | $\cap$ | $\wedge$ | ÉS (AND) / Konjunkció |
| **Komplementer** | $\overline{A}$ | $\neg$ | NEM (NOT) / Negáció |
| **Alaphalmaz** | $I$ | $|$ (vagy $1$) | Egységelem |
| **Üres halmaz** | $\emptyset$ | $\circ$ (vagy $0$) | Nullelem |

Egy $\mathcal{B} = (H, \vee, \wedge, \neg, |, \circ)$ struktúra akkor **Boole-algebra**, ha:
1.  **Típusa $((2, 2, 1, 0, 0), ())$**, ami a következőket jelenti:
    * $\vee$ (diszjunkció / "vagy"): 2-változós művelet (a $\cup$ megfelelője)
    * $\wedge$ (konjunkció / "és"): 2-változós művelet (a $\cap$ megfelelője)
    * $\neg$ (komplementer / "nem"): 1-változós művelet (a $\overline{A}$ megfelelője)
    * $|$ (egységelem): 0-változós konstans (az $I$ alaphalmaz megfelelője)
    * $\circ$ (nullelem): 0-változós konstans (az $\emptyset$ üres halmaz megfelelője)
    * $()$: Nincsenek benne relációk.
2.  Tökéletesen teljesülnek rá az **1.4. Állításban szereplő tulajdonságok (BA1-BA14 axiómák)**.


Egy $\mathcal{B} = (H, \vee, \wedge, \neg, |, \circ)$ - $((2, 2, 1, 0, 0), ())$** Ez az jelenti, hogy pl: 
  - 1. (VAGY ($\vee$) / Unió) szám azért 2 mert ha valaminek az unioját akaorm vizsgálni akkor 2 dologra les zszüksége,
  - 2. (ÉS ($\wedge$) / Metszet )szám azért 2 mert 2 dolgora van szükség, hogy megkeressük a közös részét
  - 3. ( NEM ($\neg$) / Ellentét ) szám azért 1 mert ha kijelölök 1 valamit aminek kell az ellentetje, az logiksuan csak 1 lehet.
  - 4. A két 0 pedig a két "kitüntetett bábunk" (az Egységelem és a Nullelem), amikhez nem kell semmilyen bemenet (0-változósak), mert csak létező konstansok a táblán.
  - 
- Az első lista (2,2,1,0,0): Ez a műveletekről (és a konstansokról) szól.
- A második lista (): Ez a relációkról (a viszonyító jelekről, mint pl. a $\leq, <$) szólna. De ha megnézzük a Boole-algebra "szereplőgárdáját" $\mathcal{B} = (H, \vee, \wedge, \neg, |, \circ)$, láthatjuk, hogy nincsenek benne ilyen viszonyító jelek! Tehát az az üres zárójel () egyszerűen csak azt jelenti: "Ebben a játékban egyáltalán nincsenek relációk."



**1.7. Példák Boole-algebrákra és "kakukktojásokra"**

A Boole-algebra egy "sablon". Bármilyen rendszer Boole-algebra, ha pontosan illenek rá az 1.4-es állítás (BA1-BA14) szabályai.

**I. Valódi Boole-algebrák (ahol a játékszabályok működnek):**
* **(a) Halmazalgebra:** A "klasszikus". Az alaphalmaz egy $I$ hatványhalmaza (összes részhalmaza). A műveletek a megszokott $\cup, \cap, \overline{\phantom{x}}, I, \emptyset$.
* **(b) Részstruktúra:** Egy zárt halmazrendszer: kiválasztott halmazok csoportja, amelyekből a műveletek (unió, metszet) során nem tudunk "kilépni".
* **(c) Logikai műveletek:** Az informatika alapja. $H = \{h, i\}$ (hamis, igaz). Műveletek: $\vee$ (vagy), $\wedge$ (és), $\neg$ (nem), $| = i$ (igaz), $\circ = h$ (hamis).
* **(e) Számelmélet:** Egy $N$ négyzetmentes szám osztói. A műveletek: lnko (legnagyobb közös osztó) és lkkt (legkisebb közös többszörös).
* **(f) Eseményalgebra (Valószínűség):** A lehetséges események tere ($\Omega$). Műveletek: események összege, szorzata, tagadása. Konstansok: biztos esemény ($I$) és lehetetlen esemény ($\emptyset$).
* **(g) Kapcsoló- és csapalgebrák:** Villanykapcsolók vagy vízcsapok soros (ÉS) és párhuzamos (VAGY) kapcsolása.
* **(h) Színek keverése:** Színek additív és szubtraktív keverése, komplementer színekkel. Egységelem: fehér, Nullelem: fekete.

**II. Kakukktojások (NEM Boole-algebrák):**
* **(d) Háromértékű logika ("Talán"):** $H = \{0, \frac{1}{2}, 1\}$. A "félig igaz" ($\frac{1}{2}$) behozatala miatt bizonyos axiómák (pl. a komplementer szabályok: BA9, BA10) nem teljesülnek, így ez csak egy *kvázi* (majdnem) Boole-algebra.
* **(i) Hagyományos matematika:** A valós számok szokásos összeadása ($+$) és szorzása ($\cdot$) NEM Boole-algebra, mert elbukik a BA1-BA14 axiómákon (pl. az elnyelési szabályon).

**1.8. Állítás: A Boole-algebra további azonosságai (Rövidítések)**

Tetszőleges $(H, \vee, \wedge, \neg, |, \circ)$ Boole-algebra tetszőleges $a, b \in H$ elemeire teljesülnek a következők:

* **(a) Idempotencia:**
  * $a \vee a = a$
  * $a \wedge a = a$
* Ha piros festéket (a) keversz össze piros festékkel (a), az eredmény egyszerűen csak piros festék marad (a).
* **(b) Involúció (kettős tagadás):**
  * $\neg\neg a = a$
* . "Nem igaz, hogy nem szeretem a pizzát." Ez pont azt jelenti, hogy szereted a pizzát! A két tagadás kioltja egymást.
* **(c) Komplementer unicitása (egyértelműsége):**
  * Ha $a \vee b = |$ és $a \wedge b = \circ$, akkor $b = \neg a$
* Ha van egy "$b$" dolog, ami az "$a$"-val együtt kiadja a Mindenséget ($|$), ÉS az "$a$"-val semmi közös metszete nincs ($\circ$), akkor az a "$b$" dolog biztosan az "$a$" hivatalos ellentéte, azaz $\neg a$. Nincs belőle több, ez egy egyedi kapcsolat. 
* **(d) De Morgan azonosság I.:**
  * $\neg(a \vee b) = \neg a \wedge \neg b$
* **(e) De Morgan azonosság II.:**
  * $\neg(a \wedge b) = \neg a \vee \neg b$
* Ha a tagadást (NEM) beviszed a zárójelbe, akkor a benti művelet megfordul (a VAGY-ból ÉS lesz, az ÉS-ből VAGY).
* "Vettél tejet VAGY kenyeret?" ($a \vee b$). Te tagadod: "NEM igaz, hogy vettem tejet vagy kenyeret" $\neg(a \vee b)$. Ez logikailag hajszálpontosan azt jelenti, hogy: "NEM vettem tejet, ÉS NEM vettem kenyeret sem" ($\neg a \wedge \neg b$). 
* **(f) Konstansok tagadása:**
  * $\neg | = \circ$ és $\neg \circ = |$
* $\neg | = \circ$: Mi a "Mindenség" ellentéte? A "Semmi".
* $\neg \circ = |$: Mi a "Semmi" ellentéte? A "Mindenség". 

**1.9. Tétel: A Dualitás Elve ("Iker-szabály")**

Ha egy Boole-algebrában felírt azonosság (egyenlet) igaz, akkor az egyenlet **duálisa** is garantáltan igaz. 

**A duális egyenlet képzésének szabálya:**
1. Minden $\vee$ jelet kicserélünk $\wedge$ jelre (és fordítva).
2. Minden $|$ jelet kicserélünk $\circ$ jelre (és fordítva).
3. A változók ($a, b, stb.$) és a tagadás ($\neg$) jelek változatlanul maradnak.

**Miért fontos ez?**
* Felezi a munkát: elég csak az egyik De Morgan azonosságot (vagy bármely más tételt) bebizonyítani, a duálisa automatikusan bizonyítottnak tekinthető.
* Hatékonyság: Igazságtáblázattal (brute-force) bizonyítani egy azonosságot sok változó ($n$) esetén $O(2^n)$ lépést jelent, ami még szuperszámítógépekkel is évezredekig tarthatna. A strukturális szabályok (mint a dualitás) ezt az időt spórolják meg.


**1.10. Definíció: Izomorfia ("Azonos alak")**

Két Boole-algebra (például $\mathcal{B}$ és $\mathcal{C}$) **izomorf** (jelben: $\mathcal{B} \cong \mathcal{C}$), ha a kettő szerkezetileg és logikailag teljesen megegyezik, csak a jelöléseikben térnek el. 

Matematikailag ez akkor igaz, ha létezik közöttük egy $f$ "szótár" (kölcsönösen egyértelmű megfeleltetés), amely **művelettartó**. Tehát a $\mathcal{B}$-ben elvégzett műveletek (unió, metszet, tagadás) pontosan megfelelnek a $\mathcal{C}$-ben elvégzett műveleteknek:
* $f(a \vee b) = f(a) \sqcup f(b)$
* $f(a \wedge b) = f(a) \sqcap f(b)$
* $f(\neg a) = \dagger f(a)$
* $f(|) = \top$ és $f(\circ) = \diamond$

**1.11. Tétel: Stone-féle reprezentációs tétel (1936)**

*Tétel:* Minden tetszőleges Boole-algebra izomorf egy halmazalgebra valamely rész-Boole-algebrájával.

*Mit jelent ez a gyakorlatban?*
Nincsenek "különböző" Boole-algebrák. Bármilyen egzotikus rendszert is vizsgálunk (pl. logika, kapcsolóáramkörök), az szerkezetileg azonos egy hagyományos halmazalgebrával. 
**Legnagyobb haszna:** Bármilyen bonyolult Boole-azonosságot elegendő egyszerű **Venn-diagramokkal** szemléltetni és ellenőrizni, mert ha a halmazokra igaz, akkor az összes többi Boole-algebrára is garantáltan igaz lesz.


**1.12. Tétel: A Boole-algebrák teljessége ("Mindent vagy Semmit")**

A tétel kimondja, hogy a Boole-algebrák szerkezete logikailag "tökéletes" és zárt rendszert alkot.

* **Univerzális érvényesség:** Ha felírunk egy $\Phi$ formulát (egyenletet) a Boole-jelekkel, az vagy **minden** létező Boole-algebrában (halmazok, áramkörök, stb.) egyaránt igaz, vagy **mindenhol** egyaránt hamis.
* **Bizonyíthatóság (Eldönthetőség):** Gödel teljességi tétele alapján a Boole-algebrákban nincsenek "megoldhatatlan rejtélyek". Bármely állításról vagy annak tagadásáról eldönthető, hogy igaz-e, és ez az igazság pusztán a 14 alapszabályból (BA1-BA14) minden esetben levezethető és bizonyítható.

*Érdekesség: Ez éles ellentétben áll a "hagyományos" matematikával, ahol Gödel nemteljességi tétele kimondja, hogy mindig léteznek bebizonyíthatatlan (eldönthetetlen) állítások.*


**1.3. Halmazok minőségi függetlensége**

A halmazok "általános helyzetű" ábrázolása azt jelenti, hogy a Venn-diagramon minden lehetséges metszetnek (kombinációnak) van egy nem üres tartománya. Három halmaznál ezt 3 körrel meg lehet oldani, négynél már csak bonyolultabb görbékkel.

**1.13. Definíció: Minőségileg független halmazok**

Vezessünk be egy egyszerűsítő jelölést egy $A$ halmazra és komplementerére:
* $A^{+1} := A$  (az eredeti halmaz)
* $A^{-1} := \overline{A}$ (a halmaz komplementere)

Tetszőleges $A_1, A_2, ..., A_n$ halmazok akkor **minőségileg függetlenek**, ha a fenti indexeket (a $+1$ és $-1$ "kapcsolókat", jelölésben $\varepsilon_i \in \{+1, -1\}$) bárhogyan is választjuk meg hozzájuk, a metszetük sosem üres halmaz:

$A_1^{\varepsilon_1} \cap A_2^{\varepsilon_2} \cap ... \cap A_n^{\varepsilon_n} \neq \emptyset$

*Konyhanyelven:* Akárhogy is variáljuk, hogy melyik halmazban akarunk benne lenni és melyikből akarunk kimaradni, ahhoz a kombinációhoz garantáltan tartozni fog valós elem (egy létező tartomány a Venn-diagramon).


**1.14. Állítás: A minőségileg független halmazok elemszáma**

Ez az állítás a Venn-diagramok "kombinációs szobáinak" létszámigényét mondja ki.

* **(i)** Ha $A_1, ..., A_n \subset I$ tetszőleges, minőségileg független halmazok, akkor az $I$ alaphalmaz elemszáma (számossága) legalább $2^n$ kell, hogy legyen ($|I| \ge 2^n$). Ennek oka, hogy az $n$ halmaz pontosan $2^n$ darab egymástól diszjunkt metszetet (kombinációt) hoz létre, és mivel a függetlenség miatt egyik sem üres, legalább $2^n$ elemre van szükség.
* **(ii)** Bármely $n \in \mathbb{N}$ esetén **létezik** is ilyen tökéletes, minimális méretű ($2^n$ elemű) $I$ alaphalmaz és rajta $n$ darab független részhalmaz. A bizonyítás alapja, hogy az alaphalmaz elemeinek megfeleltetjük a $2$-es számrendszerbeli (bináris) számokat, ahol az adott halmazhoz való tartozást a számjegyek kódolják.

**1.15. Tétel (Grünbaum):**
Tetszőleges $n \in \mathbb{N}$ számú halmazhoz felrajzolható olyan "általános" (minőségileg független) Venn-diagram a síkon, amely kizárólag konvex (egyenes szakaszokkal határolt, 180°-nál kisebb belső szögű) sokszögekből áll. Nem vagyunk szabálytalan, görbe alakzatokra utalva.


**1.16. Definíció: Generátorrendszer és Generátum**

* **Generátum ($[Y]$):** Legyen $\mathcal{B}$ egy Boole-algebra, és $Y \subset B$ egy részhalmaz. Az $Y$ generátuma (azaz $[Y]$) az a legszűkebb/legkisebb rész-Boole-algebra, amely tartalmazza az $Y$ elemeit ($Y \subseteq [Y]$). Ez azt jelenti, hogy az $Y$ elemeiből a Boole-műveletekkel ($\vee, \wedge, \neg$) "kikeverhető" összes lehetséges elem halmaza.
* **Generátorrendszer:** Ha egy $Y$ részhalmazból az egész $\mathcal{B}$ algebra előállítható (vagyis $[Y] = B$), akkor $Y$-t a $\mathcal{B}$ generátorrendszerének hívjuk.
* **Végesen generált:** Egy Boole-algebrát végesen generáltnak nevezünk, ha létezik *véges* számú elemből álló generátorrendszere ($Y$).

**1.17. Állítás: A végesen generált elemek "szabványos" alakja (Normálformák)**

Ha van egy véges generátorrendszerünk $Y = \{a_1, ..., a_m\}$, akkor az ebből kikevert $[Y]$ generátum minden egyes $x$ eleme garantáltan felírható kétféle, szigorúan kötött formátumban:

1.  **(1.2) Egyenlet (Diszjunktív normálforma / "VAGY-olt ÉS-csomagok"):**
    $x = \bigvee_{\vec{\varepsilon} \in S_x} \bigwedge_{i=1}^m a_i^{\varepsilon_i}$
    Itt az $x$-et úgy kapjuk meg, hogy az alap elemekből ($a_i$) vagy azok tagadásaiból ($\varepsilon_i \in \{+1, -1\}$) teljes konjunkciókat (ÉS-csomagokat) képzünk, majd ezeket a csomagokat diszjunkcióval (VAGY) fűzzük össze. Az $S_x$ halmaz jelöli ki, hogy pontosan mely kombinációkra van szükség az $x$ előállításához.

2.  **(1.3) Egyenlet (Konjunktív normálforma / "ÉS-elt VAGY-csomagok"):**
    $x = \bigwedge_{\vec{\nu} \in R_x} \bigvee_{i=1}^m a_i^{\nu_i}$
    Ez az előző logikai "fordítottja" (duálisa): itt VAGY-csomagokat készítünk az elemekből és tagadásaikból ($\nu_i \in \{+1, -1\}$), és azokat kötjük össze ÉS műveletekkel. Az $R_x$ halmaz adja meg a szükséges kombinációkat.

*Lényeg:* A bizonyítás megmutatja, hogy az ilyen alakú kifejezések halmaza teljesen zárt a Boole-műveletekre, így pontosan kiadják az $[Y]$ generátumot.

**1.18. Tétel és 1.19. Definíció: Normálformák, Mintermek és Maxtermek**

Ha $\mathcal{B}$ egy $Y = \{a_1, ..., a_m\}$ generátorrendszerrel generált Boole-algebra, akkor minden $b \in B$ elem felírható két speciális alakban:

* **DNF (Diszjunktív normálforma):** Az (1.2)-es egyenlet alakja. "ÉS-csomagok" (konjunkciók) vannak diszjunkcióval ($\vee$) összekötve.
* **CNF (Konjunktív normálforma):** Az (1.3)-as egyenlet alakja. "VAGY-csomagok" (diszjunkciók) vannak konjunkcióval ($\wedge$) összekötve.

Az áramkörtervezésben és logikában használt rövidítések az alap építőkövekre:
* **Minterm ($m_{\vec{\varepsilon}}$):** Olyan teljes konjunkció (ÉS-kapcsolat), amelyben a generátorrendszer *minden egyes* $a_i$ eleme pontosan egyszer szerepel (vagy önmagaként, vagy tagadva). Képlete: $m_{\vec{\varepsilon}} := \bigwedge_{i=1}^m a_i^{\varepsilon_i}$
* **Maxterm ($M_{\vec{\nu}}$):** Olyan teljes diszjunkció (VAGY-kapcsolat), amelyben szintén minden elem szerepel egyszer. Képlete: $M_{\vec{\nu}} := \bigvee_{i=1}^m a_i^{\nu_i}$

**1.20. Következmény: A generált Boole-algebra maximális mérete**

*Állítás:* Ha egy Boole-algebrát $m$ darab elem generál (azaz $\mathcal{B} = [a_1, ..., a_m]$), akkor az algebra elemeinek száma ($|B|$) felülről korlátos:
$$|B| \le 2^{2^m}$$

*Feltétel a maximumra:* Az egyenlőség ($|B| = 2^{2^m}$) *akkor és csak akkor* áll fenn, ha a generátorelemek ($a_1, ..., a_m$) **minőségileg függetlenek** egymástól.

*Bizonyítás logikája:* $m$ darab elem pontosan $2^m$ darab különböző mintermet hoz létre. A DNF (és így a Boole-algebra minden eleme) ezen mintermek valamilyen részhalmazának uniója. Egy $2^m$ elemű halmaznak összesen $2^{2^m}$ darab részhalmaza van. Ha a generátorelemek függetlenek, egyik minterm sem üres (nem nullelem), így az összes lehetséges kombináció egyedi elemet eredményez az algebrában.

Összefoglalva az ökölszabály:
DNF (Diszjunktív normál forma): Sok kis szigorú profil (ÉS-csomagok), amik közül elég, ha csak VAGY az egyik, VAGY a másik igaz. (Szorzatok összege).

CNF (Konjunktív normál forma): Sok kis megengedő szabály (VAGY-csomagok), amiknek kivétel nélkül ÉS egyszerre, ÉS mindegyiknek teljesülnie kell. (Összegek szorzata).

# 2. fejezet Elemi leszámlálások

**2. Fejezet: Elemi Leszámlálások (Kombinatorika)**

A halmazok elemszámát (számosságát) $|A|$ vagy $\#(A)$ jelöli.

**2.1. A kombinatorika alapelvei (A 3 aranyszabály leszámláláskor):**
1. Mindent összeszámoltunk?
2. Semmit sem számoltunk kétszer?
3. Csak a halmaz elemeit számoltuk meg?

**2.2. A leszámlálás két alapmódszere:**

* **a) Összeadás szabálya (A "VAGY" szabály):** Ha a megszámlálandó eseteket diszjunkt (egymást kizáró, különálló) halmazokra bontottuk, akkor a részhalmazok elemszámait **összeadjuk**. 
* **b) Szorzás szabálya (Az "ÉS" szabály):** Ha a megszámlálandó esetek több független összetevőből állnak össze (bármelyik 'A' elem párosítható bármelyik 'B' elemmel), akkor a lehetőségek számát **összeszorozzuk**. (Ez a halmazok Descartes-szorzatának felel meg.)

*(Megjegyzés: A példákban szereplő $\binom{n}{k}$ jelölés a binomiális együttható (kombináció), jelentése: $n$ elemből $k$ elem kiválasztásának száma sorrend figyelembevétele nélkül. Pontos definíciója a későbbi fejezetekben várható.)*

**2.4. II. Módszer: A bijekciók módszere ("Hasonmás" trükk)**

Ha egy halmaz elemszámát nehéz közvetlenül meghatározni, keresünk egy másik, könnyebben megszámlálható halmazt, amellyel kölcsönösen egyértelmű megfeleltetésbe (bijekcióba) hozható. Mivel a párosítás hibátlan, az eredeti és az új halmaz elemszáma garantáltan megegyezik.

**2.5. Példa: A hatványhalmaz elemszáma ($|\mathcal{P}(A)|$)**

*Kérdés:* Egy $n$ elemű $A$ halmaznak hány részhalmaza van?
*Bijekciós megoldás:* Minden egyes részhalmazt kódoljunk egy $n$ hosszúságú, 2-es számrendszerbeli sorozattal (ahol $1$ = eleme a részhalmaznak, $0$ = nem eleme). A részhalmazok és ezek a bináris sorozatok között tökéletes bijekció van. Mivel az $n$ hosszú bináris sorozatok száma $2^n$, ezért egy $n$ elemű halmaz részhalmazainak száma is pontosan **$2^n$**.

**2.6. Feladat: A lehetséges függvények száma ($B^A$)**

*Kérdés:* Hány különböző $f: A \rightarrow B$ függvény létezik? ($B^A$ elemszáma)
*Megoldás:* Ha $|A| = n$ és $|B| = m$, akkor az $A$ halmaz minden egyes $n$ eleméhez az $m$ darab lehetséges $B$-beli érték egyikét kell hozzárendelnünk. Ez megfeleltethető az $m$-alapú számrendszerben felírható $n$-jegyű számoknak. A lehetséges függvények száma: **$|B|^{|A|} = m^n$**.


**2.2. Teljes indukció (A dominó-elv)**

A teljes indukció egy bizonyítási módszer, amivel "Minden $n \ge n_0$ természetes számra igaz, hogy $\Phi(n)$" típusú, végtelen sok esetre vonatkozó állításokat tudunk hatékonyan igazolni.

**2.7. Módszer: A Teljes Indukció lépései**

$\Phi(n) -> "Fi"  -  $\Phi(n) \Rightarrow \Phi(n+1)$  ->Ha fi igaz, abból következik, hogy fi n + 1 is igaz. 

**A Teljes Indukció logikája (A Végtelen Lépcső és a Dominó-elv)**

Képzeljük el, hogy van egy végtelenül hosszú lépcső. Be akarjuk bizonyítani, hogy fel tudunk menni a legtetejére. Ehhez mindössze két dolgot kell bizonyítanunk a hitetlenkedőknek:

* **Kezdő lépés:** Rá tudunk lépni a legelső lépcsőfokra (ezt a kezdő számot hívják $n_0$-nak, ami legtöbbször 0 vagy 1). Ha már az elsőre se tudunk fellépni, bukó az egész.
* **Indukciós lépés (A Dominó-elv):** Be kell bizonyítanunk egy általános szabályt: **HA** feltételezzük, hogy valahogy eljutottunk egy tetszőleges $n$-edik lépcsőfokra, **AKKOR** onnan biztosan fel tudunk lépni a legközelebbi, $(n+1)$-edik fokra is.

**Miért zseniális ez?**
Mert ha ez a kettő igaz, akkor a bizonyítás végigfut a végtelenbe! Fel tudunk lépni az 1. fokra (kezdő lépés). Mivel fel tudunk lépni az 1-re, a 2. szabály miatt fel tudunk lépni a 2-re is. Mivel a 2-n vagyunk, a szabály miatt mehetünk a 3-ra... és így tovább a végtelenségig.


1.  **Kezdő lépés (Bázis):** Ellenőrizzük és bizonyítjuk, hogy az állítás igaz a legelső, kezdő értékre, azaz $\Phi(n_0)$ igaz.
2.  **Indukciós lépés:** Feltételezzük, hogy az állítás egy tetszőleges $n$ számra igaz (ezt hívjuk *indukciós feltevésnek*), és ebből levezetjük, hogy akkor a rákövetkező $n+1$ számra is feltétlenül igaz. 
    Képlettel: $\Phi(n) \Rightarrow \Phi(n+1)$

Ha ez a két lépés teljesül, a "lépcsőmászás" analógiájára az állítás minden $n \ge n_0$ számra bizonyítottnak tekinthető.

**Az "erős" indukció (23. oldal)**

Sok esetben az $(n+1)$-edik állítás bizonyításához nem elég csak a közvetlenül megelőző $\Phi(n)$-t feltételezni. Ilyenkor a feltevésünk az, hogy az *összes* korábbi állítás igaz, és ezekből együtt következik a következő lépés:
$$(\Phi(n_0) \wedge \Phi(n_0 + 1) \wedge \dots \wedge \Phi(n)) \Rightarrow \Phi(n+1)$$
Röviden jelölve: $\bigwedge_{n_0 \le i \le n} \Phi(i) \Rightarrow \Phi(n+1)$


**2.8. Tétel: A Teljes Indukció Tétele (Hivatalos definíció)**

Ha egy $\Phi(n_0)$ állítás igaz (ez a *kezdőlépés*), és minden $n \in \mathbb{N}, n > n_0$ természetes szám esetén igaz az a szabály, hogy $\Phi(n) \Rightarrow \Phi(n+1)$ (ha az $n$-edik igaz, abból következik az $(n+1)$-edik is), akkor a $\Phi(n)$ állítás minden $n \ge n_0$ számra igaz.

**2.9. Példa: Általánosított háromszög-egyenlőtlenség (Indukciós bizonyítás)**


**Konyhanyelvi magyarázat: A 2.9. Példa bizonyítása (A "Nagy Csomag" trükk)**

**Az alapelv ("A legrövidebb út az egyenes"):** Ha $A$-ból $C$-be mész egy $B$ kitérővel, az az út mindig hosszabb (vagy egyenlő), mintha egyenesen mentél volna. Két szakaszra ez a sima háromszög-egyenlőtlenség: $|z_1 + z_2| \le |z_1| + |z_2|$. A feladatunk az, hogy ezt a logikát kiterjesszük *bármennyi* ($n$) szakaszra.

**A bizonyítás lépései (Dominó-elv):**

1. **A kezdőlépés ($n=1$):**
   Ha csak egyetlen szakaszunk van, annak a hossza nyilván kisebb vagy egyenlő a saját hosszával ($|z_1| \le |z_1|$). Ezen nincs mit bizonyítani, felléptünk az első lépcsőfokra.

2. **A titkos alap ($n=2$):**
   A trükk működéséhez biztosnak kell lennünk a 2 szakaszos esetben. Ezt (az alap háromszög-egyenlőtlenséget) elfogadjuk ismert alapigazságnak.

3. **Az indukciós lépés (A trükk bedobása):**
   Tegyük fel, hogy a szabály $n$ darab szakaszig tökéletesen működik. Bizonyítsuk be, hogy ha hozzáadunk egy $(n+1)$-edik szakaszt, a szabály akkor is állni fog!
   * **Csomagolás:** Fogjuk az első $n$ darab szakaszt, és virtuálisan beletesszük egyetlen "Nagy Csomagba" ($\sum_{i=1}^n z_i$).
   * **Visszabutítás 2 dologra:** Így a képletben hirtelen már csak 2 dolog szerepel: a "Nagy Csomag" és az új, $(n+1)$-edik szakasz.
   * **A 2-es szabály bevetése:** Mivel csak 2 dolgot látunk, azonnal bevethetjük rájuk a 2. pontban említett alapigazságot. Így a Nagy Csomagot és az új szakaszt sikeresen különvettük egymástól.
   * **A dominó fellökése (Kibontás):** Végül ránézünk a Nagy Csomagra. Mivel ebben pont $n$ darab dolog van, és mi az elején feltételeztük, hogy $n$ darabra a szabály működik, ezért a csomag tartalmát is felbonthatjuk különálló szakaszokra.

**Konklúzió:** A "csomagolós" trükkel megmutattuk, hogy ha valami igaz $n$ darabra, akkor az $(n+1)$-edik elem hozzáadásával is igaz marad. A dominósor elindult a végtelenbe!

*Állítás:* Tetszőleges $z_1, \dots, z_n \in \mathbb{C}$ számokra (vektorokra) igaz, hogy:
$$\left| \sum_{i=1}^n z_i \right| \le \sum_{i=1}^n |z_i|$$

*Bizonyítás teljes indukcióval:*
1.  **Kezdőlépés ($n=1$):** Triviálisan igaz, hiszen $|z_1| \le |z_1|$.
2.  **Segédlépés ($n=2$):** Felhasználjuk az ismert alap háromszög-egyenlőtlenséget: $|z_1 + z_2| \le |z_1| + |z_2|$.
3.  **Indukciós lépés ($\Phi(n) \Rightarrow \Phi(n+1)$):** Tegyük fel, hogy $n$-re igaz az állítás. Vizsgáljuk meg az $(n+1)$ esetet:
    * Az összegzést megbontjuk egy $n$-tagú csoportra és egy $(n+1)$-edik elemre.
    * Erre a *két* tagra alkalmazzuk az $n=2$ esetben látott alap háromszög-egyenlőtlenséget.
    * Végül az $n$-tagú részre alkalmazzuk a $\Phi(n)$ indukciós feltételezést.
    * *Levezetés:* $\left| \sum_{i=1}^{n+1} z_i \right| = \left| \sum_{i=1}^n z_i + z_{n+1} \right| \le \left| \sum_{i=1}^n z_i \right| + |z_{n+1}| \le \sum_{i=1}^n |z_i| + |z_{n+1}| = \sum_{i=1}^{n+1} |z_i|$.
    * Ezzel bizonyítottuk az állítást minden $n \in \mathbb{N}$ természetes számra.

**Az általánosított háromszög-egyenlőtlenség lépései (2.9. Példa)**

* **A kiindulópont:** $\left| \sum_{i=1}^{n+1} z_i \right|$
    * *Konyhanyelven:* Ez a teljes út hossza, ha egyenesen mész az 1-es ponttól az $(n+1)$-edik pontig. Ebből indulunk ki.

* **1. lépés (A "Csomagolás"):** $= \left| \sum_{i=1}^n z_i + z_{n+1} \right|$
    * *Konyhanyelven:* Nem csináltunk matekot, csak **csoportosítottunk**. Leválasztottuk a legutolsó lépést ($z_{n+1}$), az összes többit előtte (1-től $n$-ig) pedig egybehagytuk egy Nagy Csomagban. Az "$=$" jel azért van ott, mert a tartalom ugyanaz maradt.

* **2. lépés (A 2-es szabály bevetése):** $\le \left| \sum_{i=1}^n z_i \right| + |z_{n+1}|$
    * *Konyhanyelven:* **Itt a varázslat!** Bevetjük az alap háromszög-egyenlőtlenséget a 2 dologra (Nagy Csomag + Utolsó lépés). A függőleges vonalakat (abszolútérték) szétszedjük rájuk külön-külön. Mivel kitérőt tettünk (szétbontottuk az utat), a távolság megnőhet, ezért jön a **$\le$** jel.

* **3. lépés (A dominó fellökése / Kibontás):** $\le \sum_{i=1}^n |z_i| + |z_{n+1}|$
    * *Konyhanyelven:* Ránézünk a Nagy Csomagra. Mivel az elején feltételeztük, hogy $n$ darabig a szabály működik ($\Phi(n)$ feltevés), a csomagot teljesen kibonthatjuk kis darabokra külön-külön utakként. A csomag kibontásával további kitérőket tettünk, így a **$\le$** jel ismét indokolt.

* **4. lépés (Visszacsomagolás a végén):** $= \sum_{i=1}^{n+1} |z_i|$
    * *Konyhanyelven:* Ez már csak takarítás. A sok különálló lépés 1-től $n$-ig, plusz az $(n+1)$-edik elem egyszerűen összeolvasva: "Add össze az összes különálló lépést 1-től $(n+1)$-ig". Az "$=$" jel mutatja, hogy csak a felírást rövidítettük le egyetlen szumma alá.


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


```mermaid
graph TD;
   A-->B-->C
   B-->C
```