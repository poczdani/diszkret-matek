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