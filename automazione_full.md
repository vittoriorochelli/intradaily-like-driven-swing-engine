# Automazione Full - Swing/Multiday

## Scopo

Eseguire l’intera analisi swing/multiday in un’unica sequenza.

Questo è il file operativo principale del sistema.

## Regola di uso

Nel sistema swing/multiday l’analisi viene eseguita principalmente tramite automazione full.
Non è previsto il refresh frequente del trigger durante la giornata.

## Input ordinario richiesto

1. Screenshot HTF D1/H4
2. Screenshot LTF H4/H1

## Sequenza obbligatoria

### CASO A — nessun trade aperto

1. Preflight
2. HTF
3. LTF
4. Trigger
5. Scoring finale
6. Risk e Position Sizing
7. Decisione finale

### CASO B — trade aperto

1. Preflight
2. verifica HTF solo se necessario
3. verifica LTF aggiornata
4. Gestione Posizione
5. Risk e Position Sizing se stop, size o esposizione cambiano
6. Decisione finale di gestione

## Regola di priorità con trade aperto

Se esiste un trade aperto, il sistema non deve cercare un nuovo setup sullo stesso asset, salvo richiesta esplicita.
Deve concentrarsi sulla qualità residua del trade aperto.

## Logica intraday-like

L’automazione full applica in sequenza la stessa logica mentale dell’intraday, ma su timeframe swing.

Non esistono refresh frequenti del trigger.
Il sistema swing usa principalmente automazione full.

## Regole generali

- Leggi gli screenshot forniti
- Non mescolare timeframe
- Non inventare dati non visibili
- Non inventare zone, livelli, indicatori o conferme non visibili
- Le zone e i livelli devono essere prodotti dal sistema, non richiesti all’utente come input già tracciati
- HTF deve produrre zona primaria e zona secondaria
- LTF deve leggere solo la reazione del prezzo rispetto alla zona HTF
- Trigger deve decidere solo: TRADE VALIDO / TRADE NON VALIDO / DA MONITORARE
- Il Trigger deve produrre Entry, SL, TP1, TP2 e R:R
- Il sistema deve sempre restituire lo score finale
- Il sistema deve sempre elencare gli hard veto attivi
- Se esiste un hard veto attivo, la decisione finale deve essere TRADE NON VALIDO
- Se il materiale non è leggibile, la decisione finale deve essere ASSET NON LEGGIBILE
- Se lo score è 60-74 senza hard veto, la decisione deve essere DA MONITORARE
- Se lo score è >= 75 senza hard veto, la decisione può essere TRADE VALIDO
- Se lo score è < 60, la decisione deve essere TRADE NON VALIDO
- La decisione finale non può essere TRADE VALIDO senza SL tecnico
- La decisione finale non può essere TRADE VALIDO senza TP2 realistico almeno a 1:2
- Se Entry, SL o TP sono incerti, il sistema deve classificare DA MONITORARE o TRADE NON VALIDO
- La size non viene decisa in questa fase: verrà tarata dopo sul rischio monetario fisso
- La decisione finale non può essere TRADE VALIDO se Decisione rischio = RISCHIO NON OK
- Se Decisione rischio = DATI RISCHIO MANCANTI, il sistema deve classificare DA MONITORARE o TRADE NON VALIDO
- Il sistema non deve inventare pip value, tick value, lotto minimo o margine
- Se mancano dati broker necessari al calcolo della size, deve chiederli
- La size viene calcolata solo dopo Entry e Stop Loss tecnico
- Se uno screenshot è assegnato male, rimappalo
- Se mancano dati essenziali, segnalalo
- Se mancano indicatori necessari, fermati e chiedi integrazione mirata
- Se gli screenshot non sono leggibili o mancano indicatori indispensabili, fermati al Preflight
- Non forzare trade
- Se il trade non è valido, dichiaralo chiaramente
- Se il materiale è insufficiente, fermati al preflight

## Output finale

[ASSET: ... | DECISIONE FINALE]

Preflight:
Struttura HTF:
Zona primaria:
Zona secondaria:
Bias strutturale:
Timing LTF:
Reazione nella zona:
Trigger:
Decisione trigger:
Direzione:
Tipo entry:
Entry:
Motivo entry:
Stop:
Motivo Stop Loss:
Rischio monetario fisso:
Distanza Entry-SL:
Size da calcolare:
Size calcolabile:
Decisione rischio:
Hard veto rischio:
Dati mancanti per size:
TP1:
Motivo TP1:
TP2:
Motivo TP2:
R:R su TP1:
R:R su TP2:
Target realistico:
Journal-ready fields:
Hard veto:
Score HTF:
Score LTF:
Score Trigger:
Score R:R / qualità operativa:
Score finale:
Hard veto attivi:
Decisione finale:
Motivo principale:
Qualità setup:
Azione:
Sintesi operativa:

Valori ammessi per Azione:

- TRADE VALIDO
- TRADE NON VALIDO
- DA MONITORARE
- GESTIRE TRADE APERTO
- ASSET NON LEGGIBILE

## Output finale con trade aperto

[ASSET: ... | DECISIONE FINALE - TRADE APERTO]

Stato trade:
Deterioramento:
Azione:
Nuovo stop:
Gestione profitto:
Uscita anticipata:
Motivo:
Sintesi operativa:

Valori ammessi per Azione con trade aperto:

- MANTIENI
- PORTA A BREAK-EVEN
- STRINGI STOP
- ALLEGGERISCI
- CHIUDI PARZIALE
- CHIUDI TOTALE
- NESSUNA AZIONE
