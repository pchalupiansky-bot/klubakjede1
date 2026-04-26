# Klubák jede – microsite

Fundraisingová microsite Sociálního podniku Klubák.
URL: **www.klubakjede.cz**
Cílová částka od veřejnosti: **270 000 Kč**

---

## 📁 Struktura

```
klubakjede/
├── index.html       ← hlavní stránka
├── style.css        ← styly
├── img/
│   └── peckova.jpg  ← fotka ředitelky
└── README.md        ← tento návod
```

---

## 🚀 NASAZENÍ NA VERCEL (zdarma, ~30 minut)

### Co budeš potřebovat

- ✅ GitHub účet (zdarma) — github.com
- ✅ Vercel účet (zdarma) — vercel.com
- ✅ Doménu klubakjede.cz (už máš)
- ✅ Tyto soubory (máš)

---

### KROK 1: Vytvoření GitHub repository (5 minut)

1. Jdi na **github.com** → přihlaš se (nebo si vytvoř účet)
2. Vpravo nahoře klikni na **+** → **New repository**
3. Vyplň:
   - Repository name: `klubakjede`
   - Description: „Microsite kampaně Klubák jede"
   - Public ✅ (Vercel free tier potřebuje veřejné repo)
   - **NEZAŠKRTÁVEJ** „Initialize with README"
4. Klik **Create repository**
5. Na další stránce uvidíš návod – my použijeme jednodušší cestu níže

### KROK 2: Nahrání souborů na GitHub (5 minut)

**Nejjednodušší cesta — drag & drop:**

1. Na své prázdné stránce repository klikni na **„uploading an existing file"**
   (nebo na URL `https://github.com/TVUJUSER/klubakjede/upload/main`)
2. **Přetáhni do okna všechny soubory:**
   - `index.html`
   - `style.css`
   - `README.md`
   - **složku `img/` celou** (s fotkou peckova.jpg)
3. Dole napíš commit message: „První nasazení"
4. Klik **Commit changes**
5. ✅ Soubory jsou na GitHubu

### KROK 3: Připojení k Vercel (5 minut)

1. Jdi na **vercel.com** → **Sign Up** (přihlas se přes GitHub – pohodlnější)
2. Po přihlášení klik **Add New** → **Project**
3. Vyber repository **klubakjede** ze seznamu → **Import**
4. Nastavení:
   - Framework Preset: **Other** (Vercel rozezná HTML stránku)
   - Root Directory: `/` (nech defaultní)
   - Build Command: nech prázdné
   - Output Directory: nech prázdné
5. Klik **Deploy**
6. Počkej ~30 sekund, Vercel vystaví web na adrese typu **klubakjede.vercel.app**
7. ✅ Můžeš si ji už prohlédnout (klikni na URL)

### KROK 4: Připojení vlastní domény klubakjede.cz (10 minut)

#### Ve Vercelu:

1. V projektu klik **Settings** → **Domains**
2. Vlož `www.klubakjede.cz` → **Add**
3. Vlož také `klubakjede.cz` → **Add** (Vercel přesměruje z non-www na www)
4. Vercel ti zobrazí DNS instrukce — **2 záznamy**, které musíš přidat:
   - **Pro klubakjede.cz** → A record na IP `76.76.21.21`
   - **Pro www.klubakjede.cz** → CNAME na `cname.vercel-dns.com`

#### V administraci své domény:

(Záleží, kde máš doménu zaregistrovanou — Wedos, Forpsi, GoDaddy, Active24…)

1. Přihlaš se k registrátorovi
2. Najdi **DNS** nebo **DNS settings** pro klubakjede.cz
3. Smaž / uprav existující A a CNAME záznamy pro @ a www
4. Přidej nové záznamy podle Vercelu:

   | Typ | Host | Cíl |
   |---|---|---|
   | A | @ | 76.76.21.21 |
   | CNAME | www | cname.vercel-dns.com |

5. Ulož

#### Počkej na propagaci

- Trvá **5–60 minut** (občas až několik hodin)
- Ve Vercel admin se ti u domény objeví ✅
- Vercel automaticky vystaví **SSL certifikát zdarma** → web jede na **HTTPS**

### KROK 5: Otestuj (5 minut)

1. Otevři **https://www.klubakjede.cz**
2. Zkontroluj:
   - ✅ Stránka se načítá rychle
   - ✅ Fotka paní Peckové se zobrazuje
   - ✅ Tlačítka „Darovat" otevírají Darujme.cz v novém tabu
   - ✅ Mobilní verze (otevři si web na telefonu)
   - ✅ Sticky CTA „Přispět" se objeví po proscrollování dolů
3. Pošli URL kolegům na otestování

---

## ✏️ ÚPRAVY OBSAHU PO NASAZENÍ

Editovat můžeš dvěma způsoby:

### Cesta A: Přímo na GitHubu (snadnější)

1. Jdi na **github.com/TVUJUSER/klubakjede**
2. Klikni na soubor (např. `index.html`)
3. Klikni na **ikonu tužky** (Edit)
4. Změň text
5. Klik **Commit changes**
6. **Vercel automaticky redeployne** během ~30 sekund

### Cesta B: Lokálně (pro pokročilé)

1. Naklonuj repo na svůj počítač (Git)
2. Edituj soubory v editoru (VS Code)
3. `git push` → Vercel redeployne

---

## 🛠️ CO JE V SOUBORU – aby ses mohl/a orientovat

### V `index.html`

| Sekce | Kde najdeš | Co můžeš měnit |
|---|---|---|
| Hero | `<section class="hero">` | Claim, podtitulek |
| Progress bar | `<section class="main-call">` | Vybranou částku, %, tituly |
| Slovo ředitelky | `<section class="director">` | Citaci |
| Tváře | `<section class="faces">` | Jména, citáty, fotky |
| Vzkazy | `<section class="messages">` | Text, jméno, město, částka |
| Pro firmy | `<section class="companies">` | Balíčky, ceny, kontakt |
| FAQ | `<section class="faq">` | Otázky / odpovědi |

### Důležité odkazy v souboru

- **Tlačítka „Darovat" mají URL:** `https://www.darujme.cz/darovat/1212991`
  - Pokud změníš ID Darujme projektu, najdi a nahraď tento URL všude
- **E-mail pro firmy:** `kslavik@klubickoberoun.cz`
- **Telefon:** `+420 602 628 954`

---

## 📊 PROGRESS BAR – ručně aktualizovat

Tady je drobnost: progress bar zobrazuje **statickou částku** (63 400 Kč). Není napojený na live data Darujme.cz.

**Aktualizace** (raz za týden / po větších darech):

1. Edituj `index.html`
2. Najdi tyto řádky (jsou uprostřed souboru):

```html
<span class="stat-value-big">63 400 Kč</span>
<span class="stat-value-small">/ 270 000 Kč</span>
...
<div class="stat-value-coral">206 600 Kč</div>
...
<div class="progress-fill" style="width: 23%;">
```

3. Spočítej:
   - **Vybráno**: aktuální částka z Darujme dashboardu
   - **Chybí**: 270 000 − vybráno
   - **Procenta**: (vybráno / 270 000) × 100, zaokrouhli
4. Změň hodnoty, ulož → Vercel automaticky updatne

**Tip:** Pokud chceš plně automatický live progress, později můžeš napojit Darujme API (vyžaduje vývojáře).

---

## 🎨 PŘIDÁNÍ DARUJME WIDGETU (volitelné)

Aktuálně tlačítka „Darovat" otevírají Darujme.cz v novém tabu. Pokud chceš mít widget přímo v stránce (bez opouštění):

1. V `index.html` najdi sekci `<section class="main-call">`
2. Před `<div class="text-center">` s tlačítkem „Darovat" vlož:

```html
<div data-darujme-widget-token="v2y5zuw0m2gxkgl9"></div>
<script type="text/javascript">
  +function(w, d, s, u, a, b) {
    w['DarujmeObject'] = u;
    w[u] = w[u] || function () { (w[u].q = w[u].q || []).push(arguments) };
    a = d.createElement(s); b = d.getElementsByTagName(s)[0];
    a.async = 1; a.src = "https://www.darujme.cz/assets/scripts/widget.js";
    b.parentNode.insertBefore(a, b);
  }(window, document, 'script', 'Darujme');
  Darujme(1, "v2y5zuw0m2gxkgl9", 'render', "https://www.darujme.cz/widget?token=v2y5zuw0m2gxkgl9", "270px");
</script>
```

3. Případně skryj progress bar, který by tam pak duplicitně visel.

---

## 🆘 TROUBLESHOOTING

**Doména se nepřipojí:**
- Počkej 30 minut (DNS propagace bývá pomalá)
- Zkontroluj DNS záznamy přes nslookup.io – musí ukazovat na Vercel
- Pokud je problém déle než 24 hodin, kontaktuj Vercel support nebo registrátora domény

**Stránka se nenačítá:**
- Zkontroluj, že máš všechny 3 soubory + složku `img/` na GitHubu
- Mrkni do Vercel **Deployments** → klikni na deployment → **Build Logs**

**Fotka paní Peckové se nezobrazuje:**
- Ujisti se, že soubor má **přesně název** `peckova.jpg` (malá písmena!)
- Musí být ve složce `img/` (ne v rootu)

---

## 💰 NÁKLADY

| Položka | Cena |
|---|---|
| Vercel (free tier) | **0 Kč/měsíc** |
| GitHub (public repo) | **0 Kč/měsíc** |
| Doména klubakjede.cz | (už platíš registrátorovi) |
| **Celkem za microsite** | **0 Kč/měsíc** ✅ |

Vercel free tier zvládne **stovky tisíc návštěv měsíčně** — pro Klubák kampaň je to víc než dost.

---

## 📞 V případě potíží

Pokud něco nefunguje, můžeš mi vždycky napsat zpátky a vyřešíme to. ✊

**Hodně štěstí s kampaní! Klubák jede! 🚐💨**
