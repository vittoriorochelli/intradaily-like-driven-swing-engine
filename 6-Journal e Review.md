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

## Formato tabellare / CSV-friendly

Il journal deve poter essere copiato in futuro in Excel, Google Sheets, CSV o database.

Regole:

- un campo = una colonna;
- mantenere sempre lo stesso ordine dei campi;
- se un dato manca, usare `mancante`;
- se un dato non è applicabile, usare `non applicabile`;
- se un dato verrà aggiornato dopo, usare `da aggiornare`;
- evitare testo lungo nei campi tabellari;
- usare note sintetiche.

## Colonne consigliate — Setup

1. Data analisi
2. Ora analisi
3. Asset
4. Timeframe input
5. Screenshot HTF presente
6. Screenshot LTF presente
7. Materiale sufficiente
8. Modalità
9. Bias HTF
10. Stato mercato HTF
11. Zona primaria
12. Zona secondaria
13. Invalidazione strutturale
14. Reazione LTF
15. Classificazione reazione
16. Tipo entry
17. Entry
18. Stop Loss
19. Motivo Stop Loss
20. TP1
21. TP2
22. R:R su TP1
23. R:R su TP2
24. Score HTF
25. Score LTF
26. Score Trigger
27. Score R:R / qualità operativa
28. Score finale
29. Hard veto attivi
30. Decisione rischio
31. Rischio monetario fisso
32. Distanza Entry-SL
33. Size calcolabile
34. Dati mancanti per size
35. Decisione finale
36. Azione
37. Motivo principale
38. Validità temporale setup
39. Cosa monitorare
40. Trade preso
41. Esito
42. Note review

## Colonne consigliate — Trade aperto

1. Data analisi
2. Ora analisi
3. Asset
4. Direzione trade
5. Entry
6. Stop attuale
7. Target
8. Stato trade
9. Deterioramento
10. Motivo deterioramento
11. Azione consigliata
12. Nuovo stop
13. Gestione profitto
14. Uscita anticipata
15. Decisione rischio
16. Hard veto rischio
17. Azione finale
18. Motivo
19. Esito aggiornato
20. Note review

## Regola anti-overhead

Il journal deve ridurre il lavoro manuale, non aumentarlo.
L’utente deve poter copiare il blocco journal e incollarlo in una tabella senza riscrivere l’analisi.

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
