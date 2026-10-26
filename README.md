# Botkassa

Botsystem for studenthusholdninger. Bygget som PWA — funker som en app på telefonen.

## Slik laster du opp til GitHub Pages

### 1. Lag et nytt repository
- Gå til github.com og klikk grønne **Create repository**-knappen
- Repository name: `botkassa` (eller hva du vil)
- Sett til **Public** (Pages krever public på gratisplan)
- Hak **IKKE** av for "Add README" — vi har allerede en
- Klikk **Create repository**

### 2. Last opp filene
På den tomme repository-siden:
- Klikk **uploading an existing file** (i den blå linja øverst)
- Dra inn **alle filene** fra denne mappen (eller velg dem):
  - `index.html`
  - `manifest.json`
  - `sw.js`
  - `icon-192.png`
  - `icon-512.png`
  - `icon-512-maskable.png`
  - `apple-touch-icon.png`
- Scroll ned og klikk **Commit changes**

### 3. Aktiver GitHub Pages
- Gå til **Settings** (toppmenyen i repoet)
- I venstre meny: klikk **Pages**
- Under "Source" velg **Deploy from a branch**
- Velg branch **main** og folder **/ (root)**
- Klikk **Save**
- Vent ~1 minutt

Du får en URL som ser ut som:
```
https://DITT-BRUKERNAVN.github.io/botkassa/
```

### 4. Legg til på iPhone
- Åpne URL-en i **Safari** (må være Safari, ikke Chrome)
- Trykk **Del**-knappen (firkanten med pil opp)
- Scroll ned og velg **Legg til på Hjem-skjerm**
- Navngi den "Botkassa" og trykk Legg til

Du har nå en app på telefonen!

### 5. Legg til på Android
- Åpne URL-en i Chrome
- Trykk på menyen (tre prikker øverst)
- Velg **Legg til på startsiden**

## Oppdatere appen senere

Når du vil endre noe:
- Last opp den oppdaterte fila i repoet (klikk fila → blyant-ikon → endre → Commit)
- GitHub Pages oppdaterer seg automatisk på ~1 minutt
- Appen henter alltid nyeste versjon når telefonen er på nett, så alle får oppdateringen samtidig

## Hva som er inkludert

- Felles data for hele kollektivet via Supabase (prosjektet «botkassa»), synket mellom alle telefonene
- Felles kollektiv-kode, og «Hvem er du?» på hver telefon
- Del-lenke (Beboere → «Del appen med kollektivet») som logger rett inn uten å skrive kode
- Felleskasse med bøteregistrering
- Joker-system: 1 fast joker per måned, pluss jokere fra to husarbeid-oppgaver
  (støvsuge/tørke støv og vaske dusj/do). Hver oppgave kan gjøres én gang per kalenderuke, uansett hvem.
- Slette feilregistrerte bøter. Slettingen logges i Arkiv med hvem som slettet.
- Månedsavslutning med innbetalingslogg
- Arkiv over avsluttede måneder
- Offline: viser siste lagrede data uten nett (endringer krever nett)

## Database

Supabase-prosjekt `botkassa` (eu-north-1). Tabellene er stengt for direkte tilgang. Appen bruker bare
`bk_`-funksjonene, som sjekker kollektiv-koden. Gratisprosjekter settes på pause etter 7 dager uten bruk.
Da viser appen en melding, og du må trykke «Restore project» på supabase.com.

## Hva som mangler (kan bygges senere)

- Push-varsler
- Eksport av arkivert måned som PDF
