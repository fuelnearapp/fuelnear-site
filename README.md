# FuelNear Site

Sito web statico ufficiale di FuelNear, pronto per la pubblicazione gratuita tramite GitHub Pages. Non usa framework, dipendenze, cookie, tracker o servizi esterni.

## Struttura

```text
fuelnear-site/
├── index.html
├── privacy.html
├── terms.html
├── support.html
├── account-deletion.html
├── styles.css
├── assets/
│   ├── fuelnear-logo.png
│   ├── favicon.png
│   ├── apple-touch-icon.png
│   ├── screenshot-map.webp
│   └── screenshot-diary.webp
├── README.md
└── .gitignore
```

## Asset grafici

- `fuelnear-logo.png`: logo ufficiale FuelNear, 512×512 px, derivato dal file sorgente `Logo edit.png`.
- `favicon.png`: favicon 64×64 px derivata dal logo ufficiale.
- `apple-touch-icon.png`: icona Apple 180×180 px derivata dal logo ufficiale.
- `screenshot-map.webp`: schermata reale dell’app con mappa e prezzi, ottimizzata a 644×1400 px.
- `screenshot-diary.webp`: schermata reale del Diario di Bordo, ottimizzata a 644×1400 px.

Per aggiornare il logo in futuro, sostituire i tre file PNG mantenendo nomi, formato e dimensioni indicate. Per aggiornare gli screenshot, mantenere i nomi e preferibilmente il rapporto verticale 644×1400 px.

## Visualizzazione locale

È possibile aprire direttamente `index.html` in un browser. Per simulare meglio GitHub Pages, dalla cartella `fuelnear-site` si può avviare un server statico locale:

```bash
python3 -m http.server 8000
```

Poi visitare `http://localhost:8000/`. L’indirizzo locale serve solo per il test e non è presente nelle pagine pubbliche del sito.

## Creazione del repository GitHub

1. Accedere a GitHub e selezionare **New repository**.
2. Usare, per esempio, il nome `fuelnear-site`.
3. Creare il repository senza inizializzarlo con README, licenza o `.gitignore`.
4. Dalla cartella locale `fuelnear-site`, eseguire manualmente:

```bash
git init
git add .
git commit -m "Create FuelNear website"
git branch -M main
git remote add origin https://github.com/USERNAME/fuelnear-site.git
git push -u origin main
```

Sostituire `USERNAME` con il proprio nome utente GitHub. Queste operazioni non vengono eseguite automaticamente.

## Abilitazione di GitHub Pages

Nel repository GitHub aprire:

**Settings → Pages → Deploy from a branch → main → /root**

Salvare e attendere la pubblicazione. Con repository `fuelnear-site`, l’URL atteso è:

`https://USERNAME.github.io/fuelnear-site/`

## URL delle pagine

- Home: `https://USERNAME.github.io/fuelnear-site/`
- Privacy Policy: `https://USERNAME.github.io/fuelnear-site/privacy.html`
- Termini e condizioni: `https://USERNAME.github.io/fuelnear-site/terms.html`
- Supporto: `https://USERNAME.github.io/fuelnear-site/support.html`
- Eliminazione account: `https://USERNAME.github.io/fuelnear-site/account-deletion.html`

Tutti i collegamenti interni sono relativi e funzionano anche quando il sito è pubblicato nella sottocartella del repository.

## Aggiornamenti futuri

### URL App Store

In `index.html`, cercare il commento:

```html
<!-- Sostituire con URL App Store definitivo. -->
```

Sostituire lo `span` disabilitato immediatamente successivo con un link simile a:

```html
<a class="button button-primary" href="URL_APP_STORE">Scarica su App Store</a>
```

### Date dei documenti

Aggiornare il testo e l’attributo `datetime` dell’elemento `<time>` in `privacy.html` e `terms.html` quando i documenti cambiano.

### Dominio personalizzato

1. Configurare il dominio presso il proprio provider DNS secondo la documentazione GitHub Pages.
2. In **Settings → Pages → Custom domain**, inserire il dominio scelto.
3. Attivare **Enforce HTTPS** quando disponibile.
4. GitHub creerà o aggiornerà il file `CNAME` del sito.

Prima della pubblicazione definitiva, sottoporre Privacy Policy e Termini e condizioni a revisione legale e verificare che descrivano esattamente il comportamento corrente dell’app.
