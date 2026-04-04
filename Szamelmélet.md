# Számelmélet Alapjai - Összefoglaló

## 1. Oszthatóság
**Jelölés:** $a | b$ (olvasva: $a$ osztója $b$-nek)

- **Definíció:** $a | b \iff \exists c \in \mathbb{Z} : b = a \cdot c$.
- **Maradék:** Az oszthatóság akkor áll fenn, ha az osztás maradéka 0.
- **Speciális esetek:** - Minden szám osztója a 0-nak ($n | 0$).
  - A 0 csak önmagának osztója (formálisan $0 | 0$ teljesül a definíció szerint).

### Oszthatósági szabály szorzatra
Ha $a | b$ és $c | b$, akkor a szorzatuk $(a \cdot c)$ csak akkor osztja $b$-t, ha $a$ és $c$ **relatív prímek**.
- Feltétel: $\text{lnko}(a, c) = 1$
- Példa: $3 | 12$ és $4 | 12 \implies 12 | 12$ (mivel $\text{lnko}(3,4)=1$).

---

## 2. Fontos összefüggések

### LNKO és LKKT kapcsolata
Tetszőleges $a, b$ egész számokra:
$$\text{lkkt}(a, b) = \frac{a \cdot b}{\text{lnko}(a, b)}$$

### Relatív prímek
Két szám relatív prím, ha nincs közös prímosztójuk, azaz:
$$\text{lnko}(a, b) = 1$$
*Példa:* $\text{lnko}(15, 14) = 1$, mert $15 = 3 \cdot 5$ és $14 = 2 \cdot 7$.

---

## 3. A Számelmélet Alaptétele
Minden $n \in \mathbb{N}, n > 1$ szám egyértelműen felírható prímhatványok szorzataként:
$$n = p_1^{\alpha_1} \cdot p_2^{\alpha_2} \cdot \dots \cdot p_k^{\alpha_k}$$

**Analógia:**
- **Prímszámok:** A matematika "atomjai", nem bonthatóak tovább szorzattá.
- **Egész számok:** A "molekulák", amiket prímek szorzata épít fel.
- **Multihalmaz:** A számokat a prímtényezőik halmazaként is kezelhetjük.
  - *Példa:* $12 = \{2, 2, 3\}$

## 4. Számelmélet és Halmazelmélet kapcsolata
Ha a számokat prímtényezőik multihalmazaként kezeljük (jelölése: $n_{\{\}}$), a műveletek a következőképpen feleltethetőek meg:

| Számelméleti fogalom | Halmazelméleti művelet | Jelentés |
| :--- | :--- | :--- |
| **LKKT** (legkisebb közös többszörös) | **Unió** ($\cup$) | Az összes prím a legnagyobb hatványon. |
| **LNKO** (legnagyobb közös osztó) | **Metszet** ($\cap$) | Csak a közös prímek. |
| **Oszthatóság** ($a \| b$) | **Részhalmaz** ($\subseteq$) | $a$ prímjei elemei $b$ prímjeinek. |

### Példa szemléltetésre:
Legyen $a = 12$ és $c = 18$.
- $12_{\{\}} = \{2, 2, 3\}$
- $18_{\{\}} = \{2, 3, 3\}$

1. **Metszet (LNKO):** $\{2, 2, 3\} \cap \{2, 3, 3\} = \{2, 3\} \rightarrow \mathbf{6}$
2. **Unió (LKKT):** $\{2, 2, 3\} \cup \{2, 3, 3\} = \{2, 2, 3, 3\} \rightarrow \mathbf{36}$
3. **Oszthatóság:** Mivel $\{2, 3\} \subseteq \{2, 2, 3\}$, ezért $6 | 12$ teljesül.

## 5. Boole-algebrai párhuzam és Disztributivitás

A számelmélet (oszthatóság, prímfelbontás) és a halmazelmélet (vagy Boole-algebra) között közvetlen szerkezeti hasonlóság van.

### Műveleti megfeleltetések
| Halmazművelet / Logika | Számelméleti művelet |
| :--- | :--- |
| **Unió** ($\cup$) / VAGY ($\lor$) | **LKKT** (legkisebb közös többszörös) |
| **Metszet** ($\cap$) / ÉS ($\land$) | **LNKO** (legnagyobb közös osztó) |

### Disztributivitási szabály (Széttagolhatóság)
A számelméleti műveletekre is igaz a disztributivitás, azaz az LKKT és az LNKO "felcserélhető" a zárójelbontásnál:

1. **LKKT az LNKO-ra nézve:**
   $$\text{lkkt}(a, \text{lnko}(b, c)) = \text{lnko}(\text{lkkt}(a, b), \text{lkkt}(a, c))$$

* **Mit jelent ez nekünk?** Ha van egy számunk, és annak keressük az LKKT-jét két másik szám LNKO-jával, akkor úgy is eljárhatunk, hogy a külső számot (a) külön-külön "össze-LKKT-zzuk" a belső számokkal, majd a kapott két eredménynek vesszük az LNKO-ját.
* **Példa:** Legyen $a=3$, $b=6$, és $c=9$.
  * **Bal oldal (eredeti alak):** Először kiszámoljuk a zárójelet: $\text{lnko}(6, 9) = 3$
    Utána a külső művelet: $\text{lkkt}(3, 3) = \mathbf{3}$
  * **Jobb oldal (bontott alak):** Először a két belső művelet: $\text{lkkt}(3, 6) = 6$, és $\text{lkkt}(3, 9) = 9$
    Végül ezek közös osztója: $\text{lnko}(6, 9) = \mathbf{3}$
  * *Látjuk, hogy a két oldal valóban megegyezik!*

2. **LNKO az LKKT-re nézve:**
   $$\text{lnko}(a, \text{lkkt}(b, c)) = \text{lkkt}(\text{lnko}(a, b), \text{lnko}(a, c))$$

* **Mit jelent ez nekünk?** Ez pontosan a fordítottja az előzőnek. Ha az LNKO van kívül és az LKKT belül, akkor az LNKO-t tudjuk tagonként bevinni a zárójelbe, a végén pedig a kapott eredményekből egy közös LKKT-t vonunk.
* **Példa:** Legyen $a=12$, $b=6$, és $c=8$.
  * **Bal oldal (eredeti alak):**
    Először a zárójel (többszörös): $\text{lkkt}(6, 8) = 24$
    Utána a külső művelet (osztó): $\text{lnko}(12, 24) = \mathbf{12}$
  * **Jobb oldal (bontott alak):**
    Először a két belső művelet (osztók): $\text{lnko}(12, 6) = 6$, és $\text{lnko}(12, 8) = 4$
    Végül ezek közös többszöröse: $\text{lkkt}(6, 4) = \mathbf{12}$
  * *Az egyenlőség itt is tökéletesen fennáll!*

---

## 6. Prímszámok definíciója
Egy $n \in \mathbb{P}$ szám prím, ha:
- $n > 1$ (az 1 nem prím!)
- Csak önmagával és 1-gyel osztható.
- Nem bontható fel kisebb egészek szorzatára: $n = x \cdot y \implies (x=1 \lor y=1)$.

## 7. Algoritmikus számelmélet és Bonyolultság

A számítástudományban a számelméleti problémáknál nem csak az eredmény a fontos, hanem az, hogy mennyi idő alatt kapjuk meg.

### Input mérete
A futási időt nem a szám értéke ($n$), hanem a **számjegyeinek száma ($N$)** alapján mérjük.
- Összefüggés: $N \approx \log_{10}(n)$ (tehát egy $n = 10^N$ nagyságrendű szám $N$ jegyű).

### A naiv prímtesztelés problémája (Próbaosztás)
Ha egy számról úgy akarjuk eldönteni, hogy prím-e, hogy elosztjuk az összes számmal $\sqrt{n}$-ig, a lépések száma arányos lesz $\sqrt{n}$-nel.
- Az $N$ számjegyhez viszonyítva ez $10^{N/2}$ lépést jelent.
- **Következtetés:** Ez az algoritmus **exponenciálisan lassú**. Egy 100 jegyű szám esetén a futási idő milliárd években mérhető. (kb 36 milliárd)

### A három fő számelméleti probléma (A kriptográfia alapjai)

| Probléma | Feladat | Van-e gyors (polinomiális) algoritmus? |
| :--- | :--- | :--- |
| **1. Prímtesztelés** | Eldönteni egy nagy $n$ számról, hogy prím-e. | **IGEN** (pl. AKS algoritmus, 2002). Gyorsan ellenőrizhető. |
| **2. Faktorizáció** (Felbontás) | Megtalálni egy összetett szám prímtényezőit ($n = x \cdot y$). | **NINCS** (Hagyományos gépeken). Ez adja az RSA titkosítás biztonságát! |
| **3. Prímkeresés** | Egy adott méretű (pl. 500 jegyű) véletlen prím generálása. | **IGEN** (Valószínűségi tesztekkel gyorsan megoldható). |

> **A lényeg a vizsgára:** Nagyon könnyű összeszorozni két 500 jegyű prímet (gyors). De ha csak az eredményt kapjuk meg, iszonyatosan nehéz (exponenciálisan lassú) visszafejteni belőle a két eredeti prímet (faktorizáció).