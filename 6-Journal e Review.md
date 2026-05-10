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
8. Indicator setup check
9. Indicatori utilizzabili per narrativa
10. Indicatori non verificabili
11. Affidabilità indicatori
12. Narrativa ricostruita
13. Setup già partito
14. Entry ancora disponibile
15. Entry già passata
16. Stato operativo da narrativa
17. Scenario evidence pack
18. Affidabilità evidence pack
19. Scenario principale
20. Direzione scenario
21. Stato temporale scenario
22. Stato operativo scenario
23. Rilevanza operativa scenario
24. Scenario alternativi
25. Dati scenario mancanti
26. Conditional trade plan
27. Scenario vivo
28. Trade ora
29. Livello di attivazione
30. Evento richiesto
31. Trigger richiesto
32. Invalidazione scenario
33. Alert da impostare
34. Price discovery check
35. Esito price discovery/open space
36. Storico sufficiente
37. Screenshot aggiuntivo richiesto
38. Regola TP2 di estensione
39. Qualità TP2 di estensione
40. TP2 di estensione ammesso
41. Partial TP / BE plan
42. Gestione a TP1
43. Stop a BE dopo TP1
44. Runner verso TP2
45. Decisione piano condizionale
46. Modalità
47. Bias HTF
48. Stato mercato HTF
49. Zona primaria
50. Zona secondaria
51. Invalidazione strutturale
52. Reazione LTF
53. Classificazione reazione
54. Tipo entry
55. Entry
56. Stop Loss
57. Motivo Stop Loss
58. TP1
59. TP2
60. R:R su TP1
61. R:R su TP2
62. Score HTF
63. Score LTF
64. Score Trigger
65. Score R:R / qualità operativa
66. Score finale
67. Hard veto attivi
68. Decisione rischio
69. Rischio monetario fisso
70. Distanza Entry-SL
71. Size calcolabile
72. Dati mancanti per size
73. Decisione finale
74. Azione
75. Motivo principale
76. Validità temporale setup
77. Cosa monitorare
78. Trade preso
79. Esito
80. Note review

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
- indicator setup check;
- indicatori utilizzabili per narrativa;
- indicatori non verificabili;
- affidabilità indicatori;
- narrativa ricostruita;
- setup già partito;
- entry ancora disponibile;
- entry già passata;
- stato operativo da narrativa;
- scenario evidence pack;
- affidabilità evidence pack;
- scenario principale;
- direzione scenario;
- stato temporale scenario;
- stato operativo scenario;
- rilevanza operativa scenario;
- scenario alternativi;
- dati scenario mancanti;
- conditional trade plan;
- scenario vivo;
- trade ora;
- livello di attivazione;
- evento richiesto;
- trigger richiesto;
- invalidazione scenario;
- alert da impostare;
- price discovery check;
- esito price discovery/open space;
- storico sufficiente;
- screenshot aggiuntivo richiesto;
- regola TP2 di estensione;
- qualità TP2 di estensione;
- TP2 di estensione ammesso;
- partial TP / BE plan;
- gestione a TP1;
- stop a BE dopo TP1;
- runner verso TP2;
- decisione piano condizionale;
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

Il journal deve permettere di verificare se il sistema ha classificato correttamente continuation, reversal candidate, balance rotation o no edge.

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
Indicator setup check:
Indicatori utilizzabili per narrativa:
Indicatori non verificabili:
Affidabilità indicatori:
Narrativa ricostruita:
Setup già partito:
Entry ancora disponibile:
Entry già passata:
Stato operativo da narrativa:
Scenario evidence pack:
Evidence pack affidabile:
Scenario principale:
Direzione scenario:
Stato temporale scenario:
Stato operativo scenario:
Rilevanza operativa scenario:
Scenario alternativi:
Dati scenario mancanti:
Conditional trade plan:
Scenario vivo:
Trade ora:
Livello di attivazione:
Evento richiesto:
Trigger richiesto:
Invalidazione scenario:
Alert da impostare:
Price discovery check:
Esito price discovery/open space:
Storico sufficiente:
Screenshot aggiuntivo richiesto:
Regola TP2 di estensione:
Qualità TP2 di estensione:
TP2 di estensione ammesso:
Partial TP / BE plan:
Gestione a TP1:
Stop a BE dopo TP1:
Runner verso TP2:
Decisione piano condizionale:
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
