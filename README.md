# Allenamento di Casa

Web app per seguire la scheda di allenamento e il piano alimentare giorno per giorno.
Si caricano due file Excel (esercizi e dieta) e l'app crea il calendario settimanale con:

- esercizi del giorno con immagine, serie, recupero, esecuzione ed errori da evitare
- spunta verde da toccare quando un esercizio è fatto
- campo per segnare peso e ripetizioni di ogni settimana (Sett. 1-8)
- pasti del giorno con kcal e totali
- pagine della dieta: settimana, obiettivi e consigli, diario del peso con grafico, dettaglio pasti, alimenti
- pagina "Come usare" presa dal file degli esercizi

È un'unica pagina HTML: nessun server, nessun database, nessuna installazione.

## Struttura

```
index.html              l'app
manifest.webmanifest    nome e icona per "Aggiungi alla schermata Home"
icons/                  icone dell'app
esempi/                 i file Excel caricati dai pulsanti "Usa la mia scheda già pronta"
.nojekyll               dice a GitHub Pages di pubblicare i file così come sono
```

## Pubblicare con GitHub Pages

1. Crea un nuovo repository su GitHub (per esempio `allenamento-casa`).
2. Carica tutti i file di questa cartella, compresa la cartella nascosta `.nojekyll`
   (dal sito: **Add file → Upload files** e trascina il contenuto della cartella).
3. Vai in **Settings → Pages**.
4. In **Build and deployment** scegli **Deploy from a branch**, branch `main`, cartella `/ (root)`, poi **Save**.
5. Dopo 1-2 minuti l'app è online su `https://TUO-NOME-UTENTE.github.io/allenamento-casa/`.

## Usarla sull'iPhone come un'app

Apri il link in Safari → tasto Condividi → **Aggiungi alla schermata Home**.

## Cambiare i file di esempio

Sostituisci i file nella cartella `esempi/` mantenendo gli stessi nomi:

- `Scheda_Allenamento_Casa.xlsx`
- `Piano_Alimentare_Settimanale.xlsx`

In alternativa, puoi sempre caricare qualsiasi file dal telefono dalle due pagine di caricamento.

## Formato dei file Excel

**Esercizi:** un foglio per ogni giorno, con il nome che inizia con il giorno
(`Lun`, `Mar`, `Mer`, `Gio`, `Ven`, `Sab`, `Dom`) e una riga di intestazione con le colonne
`#`, `Esercizio`, `Serie × Rip.`, `Recupero`, `Muscoli`, `Come si esegue`, `Errori da evitare`,
`Immagine` e `Sett. 1` … `Sett. 8`. Le immagini vanno inserite nella riga dell'esercizio.
Un foglio `Come usare` (facoltativo) diventa la pagina Info.

**Dieta:** un foglio `Calendario` con una riga di intestazione `Pasto | Lunedì | … | Domenica`,
la riga `Tipo di giorno`, per ogni pasto una riga con la descrizione seguita da una riga `kcal`,
e sotto le righe dei totali. Gli altri fogli (`Dettaglio pasti`, `Alimenti`, `Diario peso`)
vengono mostrati come pagine dell'app.

Se modifichi il file in Excel, salvalo normalmente: l'app legge i valori calcolati dalle formule.

## Dati e privacy

- I file Excel vengono letti nel browser e non vengono inviati a nessun server.
- File caricati, pesi, spunte e diario del peso restano salvati solo nel browser del dispositivo
  (localStorage): non passano da un telefono all'altro e si perdono se si cancellano i dati di Safari.
- Con GitHub gratuito il repository di GitHub Pages è **pubblico**: chiunque può scaricare
  i file della cartella `esempi/`. Se non vuoi renderli pubblici, cancella quella cartella
  e carica i file dal telefono.

## Requisiti

Browser recente: Safari su iOS 16.4 o successivo, Chrome, Edge o Firefox aggiornati.
