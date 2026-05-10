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
5. Decisione finale

### CASO B — trade aperto

1. Preflight
2. verifica HTF solo se necessario
3. verifica LTF aggiornata
4. Gestione Posizione
5. Decisione finale di gestione

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
Entry:
Stop:
Target:
R:R:
Hard veto:
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
