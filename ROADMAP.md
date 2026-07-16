# ROADMAP — vergaju.github.io

Piano di miglioramento per il portfolio / GitHub Pages di Jacopo Umberto Verga.

## Indice

- [Legenda](#legenda)
- [Fase 1 — SEO & Struttura Dati](#fase-1--seo--struttura-dati)
- [Fase 2 — CV & Contenuti](#fase-2--cv--contenuti)
- [Fase 3 — Profili & Feed](#fase-3--profili--feed)
- [Fase 4 — Stile & UX](#fase-4--stile--ux)
- [Fase 5 — Pulizia & Manutenzione](#fase-5--pulizia--manutenzione)
- [Appendice A — Stato attuale dei file](#appendice-a--stato-attuale-dei-file)
- [Appendice B — Bug notati](#appendice-b--bug-notati)

---

## Legenda

| Simbolo | Significato |
|---------|-------------|
| ❌ | Non presente / da creare |
| ⚠️ | Presente ma incompleto / da migliorare |
| ✅ | Già presente e OK |

---

## Fase 1 — SEO & Struttura Dati

### 1.1 Meta description + keywords

- **Cosa:** Aggiungere `<meta name="description">` e `<meta name="keywords">` nel `<head>`.
- **Stato:** ❌ Assente in tutte le pagine.
- **Pagine coinvolte:**
  - `index.html`
  - `finance_bro/finance-bro.html`
  - `Bone_Marrow_QC/quality_control.html`
  - (Le pagine Pandoc auto-generate in `DGE_test/`, `Bone_Marrow_QC/mm/`, `Bone_Marrow_QC/healthy/`, `TFs/scenic/` non hanno `<head>` modificabile facilmente — skip.)

### 1.2 OpenGraph tags

- **Cosa:** Aggiungere `og:title`, `og:description`, `og:image`, `og:url`, `og:type`, `og:locale`.
- **Stato:** ❌ Assenti.
- **Pagine coinvolte:** Come sopra.

### 1.3 Twitter Cards

- **Cosa:** Aggiungere `twitter:card`, `twitter:site`, `twitter:creator`, `twitter:title`, `twitter:description`, `twitter:image`.
- **Stato:** ❌ Assenti.
- **Pagine coinvolte:** Come sopra.

### 1.4 JSON-LD

- **Cosa:** Aggiungere schema strutturato `Person` + `WebSite` in `<script type="application/ld+json">`.
- **Stato:** ❌ Assente.
- **Dettaglio:** Deve includere `name`, `givenName`, `familyName`, `jobTitle`, `url`, `sameAs` (LinkedIn, GitHub, ORCID, Google Scholar, ResearchGate), `description`, `image`, `email`.
- **Importanza:** Molto alta — migliora la presenza su Google Knowledge Graph e search rich snippet.

### 1.5 robots.txt

- **Cosa:** `https://vergaju.github.io/robots.txt`
- **Stato:** ❌ Assente.
- **Contenuto previsto:**
  ```
  User-agent: *
  Allow: /
  Sitemap: https://vergaju.github.io/sitemap.xml
  ```

### 1.6 sitemap.xml

- **Cosa:** `https://vergaju.github.io/sitemap.xml`
- **Stato:** ❌ Assente.
- **Contenuto previsto:** Elencare `index.html`, `finance_bro/finance-bro.html`, `Bone_Marrow_QC/quality_control.html`, `resume/index.html` (dopo creazione) con `<priority>`, `<lastmod>`, `<changefreq>`.

### 1.7 favicon.ico

- **Cosa:** File `favicon.ico` + tag `<link rel="icon">` nel `<head>`.
- **Stato:** ❌ Assente.
- **Opzioni:** Creare da foto profilo, da icona DNA, o da logo/testo "JV".

---

## Fase 2 — CV & Contenuti

### 2.1 CV versione HTML

- **Cosa:** Nuova pagina `resume/index.html` con layout strutturato del CV.
- **Stato attuale:** `resume/` contiene solo `VergaJU_resume.pdf` (208 KB). ✅ PDF presente.
- **Struttura proposta:**
  - Header con nome, titolo, foto (opzionale), links profili
  - Esperienza lavorativa (cronologico)
  - Educazione
  - Pubblicazioni (se presenti)
  - Skills (categorizzate)
  - Pulsante "Download PDF" side-by-side con "Back to Portfolio"

### 2.2 Pulsante download PDF nel CV HTML

- **Cosa:** Bottone per scaricare `VergaJU_resume.pdf` dalla nuova pagina CV.
- **Stato:** ✅ Il PDF esiste già in `resume/`. Manca la pagina HTML che lo ospiti e lo linki.
- **Fix:** Il pulsante in `index.html` ha `href="https://vergaju.github.io/resume/VergaJU_resume.pdf"` OK, ma `target="_fblank"` è un typo (vedi Bug).

### 2.3 Riscrittura "About me"

- **Cosa:** Migliorare la descrizione personale in `index.html` con più keyword e chiarezza.
- **Stato:** ⚠️ Testo presente ma migliorabile. Attuale (righe 47-52):
  > I'm a data scientist and computational biologist working at the intersection of AI and biomedical research...
- **Obiettivo:** Inserire keyword mirate: *single-cell omics, spatial transcriptomics, immuno-oncology, AI agents, systems immunology, therapeutic discovery.*

### 2.4 about-ai.md

- **Cosa:** File `https://vergaju.github.io/about-ai.md` — descrizione AI-friendly del sito e della persona.
- **Stato:** ❌ Assente.
- **Standard:** Questo file è pensato per LLM crawler e AI agent che visitano il sito. Deve contenere una descrizione chiara in markdown di: chi sei, cosa fai, progetti principali, skills, profili social, struttura del sito.

### 2.5 LLMs.txt

- **Cosa:** File `https://vergaju.github.io/LLMs.txt` — standard proposto da community per AI crawler.
- **Stato:** ❌ Assente.
- **Contenuto:** Riepilogo in plain text del sito: titolo, descrizione, sezioni principali, link a pagine chiave, profili, repository. Formato chiave: valore semplice. Ispirato a `llmstxt.org`.

---

## Fase 3 — Profili & Feed

### 3.1 Profili social — aggiunta

- **Stato attuale:** ✅ LinkedIn (`linkedin.com/in/jacopoverga`), ✅ GitHub (`github.com/VergaJU`).
- **Da aggiungere:**
  - ❌ **ORCID** — es. `orcid.org/0000-0002-XXXX-XXXX`
  - ❌ **Google Scholar** — es. `scholar.google.com/citations?user=XXXX`
  - ❌ **ResearchGate** — es. `researchgate.net/profile/Jacopo-Verga`
- **Impatto:** Vanno aggiunti in:
  - Sezione contatti di `index.html`
  - Array `sameAs` del JSON-LD
  - `LLMs.txt` e `about-ai.md`

### 3.2 feed.xml (Atom)

- **Cosa:** `https://vergaju.github.io/feed.xml`
- **Stato:** ❌ Assente.
- **Contenuto:** Feed Atom con entry per progetti e aggiornamenti del portfolio. Aggiornamento manuale. Utile per aggregatori e RSS readers.

---

## Fase 4 — Stile & UX

### 4.1 Layout reattivo — miglioramento

- **Stato:** ⚠️ Già presente media query a 900px, ma il container usa `width: 80%` senza `max-width`. Su schermi molto larghi il contenuto si allarga troppo.
- **Fix:** Aggiungere `max-width: 1200px; margin: 0 auto;`.

### 4.2 Animazioni sottili

- **Stato:** ❌ Nessuna animazione presente.
- **Proposta:** fade-in al scroll per sezioni (`IntersectionObserver` o CSS `@keyframes` con classi), hover effetti su card (scale/lift), transizioni su bottoni.

### 4.3 Tipografia

- **Stato:** ⚠️ Font DM Sans funziona, ma manca gerarchia tipografica chiara. Corpo e intestazioni hanno solo peso/colore come differenza.
- **Proposta:** Aggiungere `line-height` più arioso per paragrafi, `letter-spacing` per headings, dimensione corpo leggermente più grande (18px).

### 4.4 Sezione Skills — espansione

- **Stato:** Attualmente 6 icone: Python, R, Docker, TensorFlow, PyTorch, DNA.
- **Proposta:** Basato sulla bio, aggiungere (da confermare):
  - **Linguaggi:** Bash, SQL
  - **ML/DL:** scikit-learn, XGBoost
  - **Bioinformatica:** Scanpy, Seurat, SCENIC
  - **DevOps:** Git, GitHub Actions
  - **Viz:** matplotlib, seaborn, ggplot2
  - **Cloud/Altro:** Nextflow, AWS
  - **Categorizzare** le skills per sezioni (es. "Programming", "ML/AI", "Bioinformatics", "Tools")

### 4.5 Fix attributi link

- **Stato:** 🐛 `target="_fblank"` usato 3 volte in `index.html` (righe 36, 66, 73) — typo, non funziona.
- **Fix:** Sostituire con `target="_blank" rel="noopener noreferrer"`.

### 4.6 Sezione pubblicazioni

- **Cosa:** Aggiungere sezione per paper accademici (se presenti).
- **Stato:** ❌ Assente.
- **Proposta:** Sezione "Publications" dopo "Projects" con link a PubMed/bioRxiv, badge DOI, anno.

---

## Fase 5 — Pulizia & Manutenzione

### 5.1 Eliminare `index_old.html`

- **Stato:** Presente, 1008 righe. È una vecchia versione generata da Pandoc con stili VS Code inline enormi. Non linkata da nessuna parte nel sito attuale.
- **Azione:** Eliminare.

### 5.2 Aggiornare `.gitignore`

- **Stato:** Ignora solo `index.md`.
- **Azione:** Aggiungere pattern per `index_old.html`, file temporanei, `*.log`, `node_modules/` (se serve in futuro).

### 5.3 Aggiornare README.md

- **Stato:** Una riga: `# portfolio`.
- **Azione:** Scrivere README descrittivo: scopo del repo, come è strutturato, tecnologie usate, link al sito live.

### 5.4 Meta in tutte le sottopagine

- **Cosa:** Aggiungere OG/Twitter/JSON-LD anche a `finance_bro/finance-bro.html` e `Bone_Marrow_QC/quality_control.html`.
- **Stato:** ❌ Entrambe non hanno SEO metadata.

### 5.5 Ottimizzare immagini

- **Stato attuale:**
  - `JUV_photo.jpg` — 208 KB
  - `imagem.gif` — 1.3 MB (inutilizzato? non referenziato)
  - `MM.png` — 768 KB
  - `HT.png` — 764 KB
  - `Screenshot from 2025-05-15 10-32-25.png` — 152 KB (non referenziato)
- **Azione:** Convertire in WebP, comprimere, rimuovere immagini non referenziate, fixare `alt` text mancanti (JUV_photo.jpg, QC.png, BorderGraph.png).

---

## Appendice A — Stato attuale dei file

| File | Stato | Note |
|------|-------|------|
| `index.html` | ✅ Pagina principale | Manca SEO, meta, JSON-LD |
| `style.css` | ✅ CSS funzionante | Da migliorare layout, animazioni |
| `resume/VergaJU_resume.pdf` | ✅ CV PDF | Manca pagina HTML |
| `finance_bro/finance-bro.html` | ✅ Sottopagina funzionante | Manca SEO |
| `Bone_Marrow_QC/quality_control.html` | ✅ Sottopagina funzionante | Manca SEO |
| `Bone_Marrow_QC/mm/` | ⚠️ Report Pandoc auto-generati | No <head> modificabile |
| `Bone_Marrow_QC/healthy/` | ⚠️ Report Pandoc auto-generati | Idem |
| `DGE_test/` | ⚠️ Report Pandoc | Idem |
| `TFs/scenic/` | ⚠️ Report Pandoc | Idem |
| `index_old.html` | ❌ Da eliminare | Vecchia versione Pandoc, 1008 righe |
| `index.md` | ❌ Ignorato da .gitignore | Solo placeholder |
| `.gitignore` | ⚠️ Da espandere | Ignora solo index.md |
| `README.md` | ❌ Da riscrivere | Solo "# portfolio" |
| `LICENSE` | ✅ Apache 2.0 | OK |
| `04 Portfolio/assets/images/` | ⚠️ Da ottimizzare | Vari formati, alcuni non usati |
| `robots.txt` | ❌ Manca | Da creare |
| `sitemap.xml` | ❌ Manca | Da creare |
| `favicon.ico` | ❌ Manca | Da creare |
| `feed.xml` | ❌ Manca | Da creare |
| `LLMs.txt` | ❌ Manca | Da creare |
| `about-ai.md` | ❌ Manca | Da creare |
| `resume/index.html` | ❌ Manca | CV HTML da creare |

---

## Appendice B — Bug notati

1. `target="_fblank"` in `index.html` righe 36, 66, 73 — typo, il target corretto è `_blank`.
2. Immagini Unsplash (`index.html:82`) ed esterne potrebbero rompersi o cambiare URL.
3. `alt` text mancante in `JUV_photo.jpg` (`index.html:42`), `QC.png` (`index.html:115`), `BorderGraph.png` (`index.html:126`).
4. `imagem.gif` (1.3 MB) e `Screenshot from 2025-05-15 10-32-25.png` (152 KB) in assets ma mai referenziati — probabilmente da rimuovere.
5. Stickers SVG (`smile.svg`, `smartphone.svg`, `mail.svg`, etc.) in assets ma mai referenziati — probabilmente residui di un template precedente.
6. Nessuna direttiva `lang` coerente per acessibilità (manca anche la dichiarazione del font per i caratteri accentati italiani).
