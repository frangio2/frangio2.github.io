# Sito Accademico - Guida all'Utilizzo

Questa è una guida per gestire e aggiornare il tuo sito accademico creato con Jekyll e GitHub Pages.

## Indice

1. [Introduzione](#introduzione)
2. [Come Funziona](#come-funziona)
3. [Iniziare](#iniziare)
4. [Modificare i Contenuti](#modificare-i-contenuti)
5. [Aggiungere un Nuovo Articolo](#aggiungere-un-nuovo-articolo)
6. [Modificare le Informazioni del Sito](#modificare-le-informazioni-del-sito)
7. [Aggiungere Nuove Pagine](#aggiungere-nuove-pagine)
8. [Personalizzare lo Stile](#personalizzare-lo-stile)
9. [Lavorare con le Immagini](#lavorare-con-le-immagini)
10. [Deployare il Sito](#deployare-il-sito)
11. [Risoluzione Problemi](#risoluzione-problemi)

## Introduzione

Questo sito è costruito utilizzando [Jekyll](https://jekyllrb.com/), un generatore di siti statici, e viene ospitato su [GitHub Pages](https://pages.github.com/). Questo permette di avere un sito web completamente funzionale senza la necessità di gestire database o server complessi.

## Come Funziona

Il sito utilizza file Markdown per i contenuti e YAML per la configurazione. Quando si apportano modifiche e si caricano su GitHub, GitHub Pages compila automaticamente il sito.

## Iniziare

### Clonare il Repository

1. Installa [Git](https://git-scm.com/) sul tuo computer se non l'hai già fatto.
2. Apri il terminale (Command Prompt in Windows).
3. Naviga nella directory dove vuoi scaricare il sito:
   ```
   cd percorso/alla/directory
   ```
4. Clona il repository:
   ```
   git clone https://github.com/tuo-username/tuo-repository.git
   ```

### Testare il Sito in Locale (Opzionale)

Per testare le modifiche prima di pubblicarle online:

1. Installa [Ruby](https://www.ruby-lang.org/en/downloads/) e [Bundler](https://bundler.io/):
   ```
   gem install bundler
   ```
2. Naviga nella directory del sito:
   ```
   cd tuo-repository
   ```
3. Installa le dipendenze:
   ```
   bundle install
   ```
4. Avvia il server locale:
   ```
   bundle exec jekyll serve
   ```
5. Apri il browser e vai a `http://localhost:4000`

## Modificare i Contenuti

La maggior parte dei contenuti è scritta in Markdown, un formato di testo semplice con sintassi per formattare il testo.

### Sintassi Markdown di Base

- **Titoli**: Usa `#` per i titoli. Più `#` indicano livelli di titolo inferiori.
  ```
  # Titolo 1
  ## Titolo 2
  ### Titolo 3
  ```

- **Testo in grassetto**: Usa `**testo**` o `__testo__`
  ```
  **Questo testo è in grassetto**
  ```

- **Testo in corsivo**: Usa `*testo*` o `_testo_`
  ```
  *Questo testo è in corsivo*
  ```

- **Link**: Usa `[testo](URL)`
  ```
  [Visita il nostro sito](https://example.com)
  ```

- **Immagini**: Usa `![testo alternativo](URL-immagine)`
  ```
  ![Logo](assets/images/logo.png)
  ```

- **Liste puntate**: Usa `-`, `*` o `+` all'inizio della riga
  ```
  - Elemento 1
  - Elemento 2
  - Elemento 3
  ```

- **Liste numerate**: Usa numeri seguiti da un punto
  ```
  1. Primo elemento
  2. Secondo elemento
  3. Terzo elemento
  ```

## Aggiungere un Nuovo Articolo

1. Crea un nuovo file nella cartella `_posts` con il nome in formato: `ANNO-MESE-GIORNO-titolo.md` (es. `2025-03-17-nuovo-articolo.md`).
2. Aggiungi l'intestazione YAML all'inizio del file:
   ```
   ---
   layout: post
   title: "Titolo del Tuo Articolo"
   date: 2025-03-17 12:00:00 +0100
   categories: categoria
   author: Nome Autore
   excerpt: Un breve riassunto dell'articolo.
   ---
   ```
3. Scrivi il contenuto dell'articolo in Markdown sotto l'intestazione.
4. Salva il file.

## Modificare le Informazioni del Sito

Tutte le informazioni generali del sito sono contenute nel file `_config.yml`.

1. Apri il file `_config.yml` con un editor di testo.
2. Modifica i valori come desideri (titolo del sito, descrizione, contatti, ecc.).
3. Salva il file.

**Nota**: Quando modifichi `_config.yml` mentre stai testando in locale, dovrai riavviare il server Jekyll per vedere le modifiche.

## Aggiungere Nuove Pagine

1. Crea un nuovo file `.md` nella directory principale del sito (es. `nuova-pagina.md`).
2. Aggiungi l'intestazione YAML:
   ```
   ---
   layout: page
   title: Titolo Pagina
   permalink: /url-della-pagina/
   ---
   ```
3. Aggiungi il contenuto della pagina in Markdown.
4. Salva il file.

## Personalizzare lo Stile

I file CSS si trovano nella cartella `assets/css`. Il file principale è `main.css`.

1. Apri `assets/css/main.css` con un editor di testo.
2. Modifica gli stili come desideri.
3. Salva il file.

## Lavorare con le Immagini

1. Carica le immagini nella cartella `assets/images/`.
2. Riferisciti alle immagini nei tuoi file Markdown o HTML:
   ```
   ![Alt text]({{ "/assets/images/nome-immagine.jpg" | relative_url }})
   ```
   o in HTML:
   ```
   <img src="{{ "/assets/images/nome-immagine.jpg" | relative_url }}" alt="Alt text">
   ```

## Deployare il Sito

Per pubblicare le modifiche online:

1. Apri il terminale e naviga nella directory del sito.
2. Aggiungi le modifiche:
   ```
   git add .
   ```
3. Crea un commit con una descrizione delle modifiche:
   ```
   git commit -m "Descrizione delle modifiche"
   ```
4. Carica le modifiche su GitHub:
   ```
   git push origin main
   ```

GitHub Pages compilerà automaticamente il sito e le modifiche saranno visibili online in pochi minuti.

## Risoluzione Problemi

### Il sito non si aggiorna

- Assicurati di aver fatto il push delle modifiche su GitHub.
- Controlla i log di build di GitHub Pages nelle impostazioni del repository.
- Verifica che il nome del branch sia corretto (in genere `main` o `master`).

### Errori di formattazione

- Assicurati che l'intestazione YAML abbia tre trattini (`---`) all'inizio e alla fine.
- Verifica che non ci siano caratteri speciali o spazi nei nomi dei file.
- Controlla che la data nei nomi dei file post sia nel formato corretto.

### Problemi con le immagini

- Verifica che il percorso dell'immagine sia corretto.
- Assicurati che l'immagine sia stata caricata nella directory corretta.
- Controlla che il nome del file dell'immagine non contenga spazi o caratteri speciali.

## Struttura delle Directory

```
sito-accademico/
├── _config.yml           # Configurazione principale del sito
├── _layouts/             # Layout delle pagine
│   └── default.html      # Layout principale
├── _posts/               # Articoli del blog
│   └── 2025-03-01-esempio-articolo.md
├── _data/                # Dati del sito in formato YAML/JSON
├── assets/               # File statici
│   ├── css/              # Fogli di stile
│   │   └── main.css      # Stile principale
│   └── images/           # Immagini
├── about.md              # Pagina Chi Siamo
├── research.md           # Pagina Ricerca
├── publications.md       # Pagina Pubblicazioni
├── courses.md            # Pagina Corsi
├── contact.md            # Pagina Contatti
└── index.html            # Homepage
```

## Risorse Utili

- [Documentazione Jekyll](https://jekyllrb.com/docs/)
- [Guida a GitHub Pages](https://docs.github.com/en/pages)
- [Guida alla sintassi Markdown](https://www.markdownguide.org/basic-syntax/)
- [Liquid Templating](https://shopify.github.io/liquid/)

## Supporto

Se hai bisogno di ulteriore assistenza, puoi:
- Consultare la documentazione di Jekyll e GitHub Pages
- Cercare nella community di Jekyll o su Stack Overflow
- Contattare il team di supporto IT della tua istituzione
