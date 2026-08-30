# RF Centro Tratte

App web per pianificare camionisti, tratte e manutenzioni della flotta. È un unico file (`index.html`), non serve installare nulla.

## Come metterla online con GitHub Pages (senza usare comandi)

1. Vai su [github.com](https://github.com) e crea un account gratuito, se non ce l'hai già.
2. In alto a destra clicca sul **+** poi **New repository**. Dai un nome (es. `rf-centro-tratte`), lascialo **Public** (per Pages gratuito deve essere pubblico — vedi nota sotto), poi **Create repository**.
3. Nella pagina del repository appena creato, clicca **Add file → Upload files** e trascina dentro il file `index.html` di questa cartella. In basso clicca **Commit changes**.
4. Vai su **Settings** (in alto nel repository) → **Pages** (nel menu a sinistra). Sotto "Build and deployment", alla voce **Branch** scegli `main` e cartella `/ (root)`, poi **Save**.
5. Dopo un minuto o due, GitHub mostra in cima alla stessa pagina il link pubblico, del tipo:
   `https://tuonomeutente.github.io/rf-centro-tratte/`
   Questo è il link da mandare al cliente.

## Per aggiornare l'app in futuro

Vai nel repository, apri `index.html`, clicca l'icona della matita (Edit), incolla il nuovo contenuto, poi **Commit changes**. Il sito pubblico si aggiorna da solo in un minuto.

## Per togliere l'accesso al cliente dopo i 30 giorni

Due modi, entrambi in **Settings → Pages**:
- **Veloce e reversibile**: sotto "Branch" rimetti su "None" — la pagina smette di essere raggiungibile, il link del cliente non funziona più. Per riattivarla basta rimettere `main`.
- **Definitivo**: vai in **Settings → General**, in fondo alla pagina **Delete this repository**.

In alternativa puoi rendere il repository **Private** (Settings → General → Danger Zone → Change visibility) — ma con un account GitHub gratuito un repository privato non può usare GitHub Pages, quindi il sito smetterebbe comunque di essere raggiungibile: stesso effetto del primo metodo, solo un passaggio più lungo.

## Un limite importante da sapere

I dati che tu o il cliente inserite (camion, tratte, richieste) si salvano **solo nel browser di chi li inserisce**, non su un server condiviso. Questo significa:

- Se tu aggiungi una tratta dal tuo computer, il cliente che apre lo stesso link da un altro dispositivo **non la vede** — vede i dati di esempio con cui è partita l'app, o quelli che ha inserito lui.
- Se il cliente cancella la cronologia del browser, i suoi dati si perdono.
- Non c'è un database vero dietro: va benissimo per fargli provare l'interfaccia e il funzionamento, non ancora per un uso operativo reale in cui tu e il cliente dovete vedere le stesse tratte in tempo reale.

Per avere dati realmente condivisi tra più persone serve un backend (anche semplice, es. Firebase o Supabase gratuiti) — è un passo successivo, non incluso in questa versione.

## Esportazione dati

Il pulsante "Esporta" in alto scarica 3 file CSV (calendario tratte, anagrafica flotta, manutenzioni), apribili direttamente in Excel.
