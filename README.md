# Sito personale di Giovanni Maglio

Sito statico (HTML + CSS + un filino di JS), nessuna dipendenza da Jekyll o build step:
lo pubblichi su GitHub Pages così com'è.

## Struttura

```
index.html        Home / About
research.html      Tesi, interessi di ricerca, pubblicazioni
projects.html      Progetti (RecenSito, lista film)
notes.html         Appunti
404.html           Pagina d'errore
css/style.css      Tutto lo stile
js/main.js         Menu mobile + animazione di comparsa sezioni
assets/            Immagini e PDF (vedi sotto)
.nojekyll          Dice a GitHub Pages di non processare il sito con Jekyll
```

## 1. Prima di pubblicare — aggiungi i tuoi file veri

Nella cartella `assets/` per ora ci sono solo un placeholder e delle istruzioni.
Devi aggiungere:

- `assets/cv.pdf` — il tuo CV
- `assets/thesis.pdf` — il PDF della tesi
- `assets/film-list.pdf` — la lista film
- `assets/photo.jpg` — una tua foto professionale (mezzo busto, sfondo neutro, buona luce)

Poi in **index.html** cerca la riga:

```html
<img src="assets/avatar-placeholder.svg" alt="Portrait of Giovanni Maglio">
```

e sostituiscila con:

```html
<img src="assets/photo.jpg" alt="Portrait of Giovanni Maglio">
```

A quel punto puoi cancellare `assets/avatar-placeholder.svg` e `assets/LEGGIMI-assets.txt`.

## 2. Pubblicare su GitHub Pages

Usa il repository che hai già (`giovannimaglio.github.io/giovanni.github.io`) oppure,
meglio, leggi la nota qui sotto prima di scegliere.

```bash
git clone <url-del-tuo-repo>
cd <cartella-repo>
# copia dentro TUTTO il contenuto di questa cartella (index.html, css/, js/, assets/, .nojekyll, ecc.)
git add .
git commit -m "Nuovo sito personale"
git push
```

Da Settings → Pages del repository, assicurati che la pubblicazione sia impostata
su branch `main` (o `master`), cartella `/ (root)`.

## 3. Nota importante sull'URL

Il tuo sito attuale è raggiungibile a:

```
https://giovannimaglio.github.io/giovanni.github.io/
```

con quel doppio pezzo nell'URL — non l'ideale per un sito da mandare a un professore.
Questo succede perché il repository si chiama `giovanni.github.io`, mentre GitHub Pages
tratta come "sito principale" (servito su `https://giovannimaglio.github.io/`, senza
percorso aggiuntivo) solo un repository che si chiama **esattamente**
`giovannimaglio.github.io` (uguale al tuo username, minuscolo).

Per avere l'URL pulito `https://giovannimaglio.github.io/`:

1. Su GitHub, vai nel repository → **Settings** → in alto rinomina il repository in
   `giovannimaglio.github.io` (con "maglio").
2. Aspetta un paio di minuti che GitHub Pages rigeneri il sito.
3. Se avevi già un altro repository con quel nome esatto, valuta invece di spostare
   questi file in quello, per evitare conflitti.

I link interni di questo sito sono tutti relativi, quindi funzionano
allo stesso modo sia nel caso attuale sia dopo aver rinominato il repository.

## 4. Contenuti che ho riorganizzato rispetto al sito vecchio

- La lista film, che prima era dentro "Projects" come voce principale, ora è una
  voce secondaria più piccola nella stessa pagina — RecenSito resta il progetto
  in evidenza perché mostra competenze tecniche rilevanti per una candidatura.
- Gli interessi di ricerca (Research interests) ora compaiono sia in Home sia in
  Research, quest'ultima con una riga di descrizione in più per ciascuno.
- "Publications" è una sezione vuota ma dichiarata esplicitamente, invece di
  essere assente — è normale non averne ancora a fine triennale, ed è meglio
  mostrare la sezione pronta a crescere piuttosto che ometterla.
