# Bici + treno — quanto costa portare una bicicletta sui treni regionali?

Simulatore interattivo per confrontare **quanto costa trasportare una bicicletta tradizionale montata sui treni regionali italiani**, in funzione dei giorni di utilizzo al mese e delle agevolazioni individuate nei tariffari.

**[Apri la dashboard](https://antoniomassariolo.github.io/treno-bici-italia/)**

> **Stato: prototipo in verifica.** Rilevazione tariffaria di riferimento: **12 ottobre 2026**. Le cifre sono simulazioni indicative, non preventivi. Prima di pubblicare un confronto giornalistico definitivo o di viaggiare, verificare i tariffari e le condizioni aggiornate dei gestori.

## Cosa puoi fare

- Scegliere uno dei **21 territori** considerati: 19 regioni e le province autonome di Trento e Bolzano, gestite separatamente.
- Impostare da **1 a 26 giorni di utilizzo al mese** e da **1 a 12 mesi all'anno**.
- Distinguere **solo andata** e **andata-ritorno** dove il supplemento è applicato per singola corsa.
- Visualizzare **costo mensile e annuale**, frequenze alternative e un piccolo confronto grafico.
- Visualizzare, quando presenti nel database, **abbonamenti e riduzioni** in relazione ai requisiti dichiarati.
- Consultare le condizioni essenziali e i **link alle fonti tariffarie** per il territorio selezionato.

## Come sono calcolati gli importi

Il simulatore considera il **solo supplemento per la bicicletta**: il biglietto o abbonamento del passeggero **non è incluso**.

- **Tariffa giornaliera**: prezzo per giornata × giorni di utilizzo mensili.
- **Tariffa per corsa**: prezzo per corsa × corse al giorno (1 o 2) × giorni mensili.
- **Stima annuale ordinaria**: costo mensile × numero dei mesi selezionati.
- **Agevolazioni**: le formule individuate vengono mostrate quando i dati permettono una simulazione e, per i casi che lo richiedono, dopo aver selezionato il requisito pertinente. Non sono automaticamente applicabili a tutte le tratte.

## Copertura e limiti dei dati

- Per ciascun territorio è rappresentato il **principale servizio ferroviario regionale censito**, non l'intera offerta di tutte le imprese ferroviarie e linee locali.
- Le condizioni possono cambiare in base a **operatore, confini regionali, treno abilitato, capienza, orario, tratta, residenza, tipo di abbonamento** e disponibilità di spazi bici.
- Le bici **pieghevoli chiuse**, smontate o trasportate in sacca seguono spesso regole differenti e **non sono incluse** in questa simulazione.
- I servizi **Alta Velocità, Intercity e le tratte transfrontaliere** non fanno parte del confronto.
- In **Toscana** non è disponibile nel database un prezzo ordinario unico valido per ogni situazione: il simulatore non produce un costo ordinario artificiosamente uniforme e mostra soltanto le formule documentate.
- Le gratuità e le promozioni particolari restano soggette alle specifiche condizioni dei gestori. Una voce non trovata nel censimento **non dimostra l'assenza** di agevolazioni.

## Fonti e aggiornamento

I dati sono incorporati direttamente in `index.html`, nel blocco JSON con `id="tariffe-dati"`. Ogni territorio contiene, fra gli altri, i campi `source1`, `source2`, `conditions`, `notes`, `status` e `date`. La dashboard mostra i collegamenti alle fonti relative alla regione selezionata.

Per aggiornare una tariffa occorre correggere il relativo record, verificare che l'unità sia `giorno` oppure `corsa`, controllare le condizioni delle agevolazioni e aggiornare la data della rilevazione nel testo e nelle note metodologiche. **Non modificare solo il prezzo senza ricontrollare le condizioni d'uso.**

## Pubblicazione e incorporamento

Il progetto è un sito statico autonomo in **HTML, CSS e JavaScript**, senza framework o fase di compilazione. GitHub Pages pubblica `index.html` dal ramo `main`, cartella `/ (root)`.

Per incorporare la dashboard in una pagina web che consente gli iframe:

```html
<iframe
  src="https://antoniomassariolo.github.io/treno-bici-italia/"
  width="100%"
  height="780"
  style="border:0"
  loading="lazy"
  title="Simulatore del costo del trasporto bici in treno">
</iframe>
```

L'altezza dell'iframe è indicativa e potrebbe dover essere aumentata per schermi piccoli o per le note visualizzate dal simulatore.

## Correzioni e segnalazioni

Per segnalare dati da verificare, modifiche tariffarie o collegamenti non più validi, si può [aprire una segnalazione su GitHub](https://github.com/AntonioMassariolo/treno-bici-italia/issues), indicando **territorio, gestore, tariffa, data e fonte ufficiale**.

---

Progetto di data journalism a cura di [Antonio Massariolo](https://github.com/AntonioMassariolo).