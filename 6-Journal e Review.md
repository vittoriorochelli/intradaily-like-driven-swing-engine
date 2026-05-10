# 6 - Journal e Review

## Scopo

Registrare in modo strutturato ogni analisi prodotta dal sistema, inclusi:

- trade validi;
- trade non validi;
- setup da monitorare;
- asset non leggibili;
- aggiornamenti su trade aperti.

Il journal non serve solo a registrare operazioni eseguite.
Serve soprattutto a misurare disciplina, qualità del processo e capacità del sistema di evitare trade mediocri.

## Principio

Il journal deve essere il più automatizzato possibile.

L’utente non deve ricostruire manualmente l’analisi.
Il sistema deve produrre automaticamente un blocco journal-ready a partire dall’output di `automazione_full.md`.

## Cosa registrare sempre

Ogni analisi deve registrare:

- data analisi;
- ora analisi;
- asset;
- timeframe usati;
- screenshot disponibili;
- qualità del materiale;
- bias HTF;
- stato mercato HTF;
- zona primaria;
- zona secondaria;
- invalidazione strutturale;
- reazione LTF;
- classificazione reazione;
- tipo entry;
- entry;
- Stop Loss;
- motivo Stop Loss;
- TP1;
- TP2;
- R:R su TP1;
- R:R su TP2;
- score HTF;
- score LTF;
- score Trigger;
- score R:R / qualità operativa;
- score finale;
- hard veto attivi;
- decisione rischio;
- rischio monetario fisso;
- distanza Entry-SL;
- size calcolabile;
- dati mancanti per size;
- decisione finale;
- azione;
- motivo principale;
- validità temporale setup;
- cosa monitorare;
- trade preso;
- esito;
- note review.

## Registrare anche i non-trade

Il sistema deve registrare anche:

- TRADE NON VALIDO;
- DA MONITORARE;
- ASSET NON LEGGIBILE.

Questi casi sono fondamentali per capire:

- se il sistema filtra correttamente;
- se l’utente tende a forzare trade;
- se mancano dati ricorrenti;
- se alcuni asset sono spesso non leggibili;
- se alcuni setup vengono scartati per motivi ripetitivi.

## Tipi di errore

Quando un trade viene rivisto, classificare eventuali errori come:

- errore tecnico;
- errore di timing;
- errore di risk management;
- errore di gestione;
- errore psicologico;
- errore di processo;
- errore di input;
- nessun errore, trade correttamente eseguito.

## Review post-trade

La review deve confrontare:

- scenario previsto;
- comportamento reale del prezzo;
- qualità dell’entry;
- qualità dello Stop Loss;
- qualità dei target;
- rispetto del rischio monetario fisso;
- rispetto dei hard veto;
- rispetto dello score;
- gestione della posizione;
- decisione finale del sistema;
- decisione effettiva dell’utente.

## Output journal setup

[JOURNAL AUTO-ENTRY - SETUP]

Data analisi:
Ora analisi:
Asset:
Timeframe input:
Screenshot HTF presente:
Screenshot LTF presente:
Materiale sufficiente:
Modalità:
Bias HTF:
Stato mercato HTF:
Zona primaria:
Zona secondaria:
Invalidazione strutturale:
Reazione LTF:
Classificazione reazione:
Tipo entry:
Entry:
Stop Loss:
Motivo Stop Loss:
TP1:
TP2:
R:R su TP1:
R:R su TP2:
Score HTF:
Score LTF:
Score Trigger:
Score R:R / qualità operativa:
Score finale:
Hard veto attivi:
Decisione rischio:
Rischio monetario fisso:
Distanza Entry-SL:
Size calcolabile:
Dati mancanti per size:
Decisione finale:
Azione:
Motivo principale:
Validità temporale setup:
Cosa monitorare:
Trade preso:
Esito:
Note review:

## Output journal trade aperto

[JOURNAL AUTO-ENTRY - TRADE APERTO]

Data analisi:
Ora analisi:
Asset:
Direzione trade:
Entry:
Stop attuale:
Target:
Stato trade:
Deterioramento:
Motivo deterioramento:
Azione consigliata:
Nuovo stop:
Gestione profitto:
Uscita anticipata:
Decisione rischio:
Hard veto rischio:
Azione finale:
Motivo:
Esito aggiornato:
Note review:

## Output review post-trade

[REVIEW POST-TRADE]

Data review:
Asset:
Trade preso:
Direzione:
Entry:
Stop Loss:
TP1:
TP2:
R:R previsto:
Esito:
R multipli ottenuti:
Scenario previsto:
Scenario reale:
Entry corretta:
Stop Loss corretto:
Target corretti:
Gestione corretta:
Risk rispettato:
Hard veto rispettati:
Errore tecnico:
Errore psicologico:
Errore di processo:
Lezione:
Correzione operativa:
Modifica da valutare nel sistema:

## Regola finale

Il journal non deve diventare un esercizio narrativo.
Deve essere sintetico, ripetibile e confrontabile nel tempo.
