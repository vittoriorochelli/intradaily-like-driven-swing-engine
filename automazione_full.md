# Automazione Full - Swing/Multiday

## Scopo

Eseguire l’intera analisi swing/multiday in un’unica sequenza.

Questo è il file operativo principale del sistema.

## File di controllo agentico

L’esecuzione deve rispettare:

- `AGENTS.md`
- `9-Output Schema.md`

## Regola di uso

Nel sistema swing/multiday l’analisi viene eseguita principalmente tramite automazione full.
Non è previsto il refresh frequente del trigger durante la giornata.

## Input ordinario richiesto

1. Screenshot HTF D1/H4
2. Screenshot LTF H4/H1

## Sequenza obbligatoria

### CASO A — nessun trade aperto

1. Preflight
2. Indicator Setup Sanity Check
3. Narrativa da Screenshot
4. HTF
5. Scenario Evidence e Candidate Discovery
6. LTF
7. Trigger
8. Conditional Trade Plan
9. Scoring finale
10. Risk e Position Sizing
11. Decisione finale
12. Journal auto-entry

### CASO B — trade aperto

1. Preflight
2. Indicator Setup Sanity Check
3. Narrativa da Screenshot
4. verifica HTF solo se necessario
5. Scenario Evidence e Candidate Discovery se serve rivalutare lo scenario
6. verifica LTF aggiornata
7. Trigger se serve rivalutare attivazione o deterioramento
8. Conditional Trade Plan se il trade non è aperto oppure se bisogna valutare una nuova condizione
9. Gestione Posizione
10. Risk e Position Sizing se stop, size o esposizione cambiano
11. Decisione finale di gestione
12. Journal auto-entry trade aperto

### CASO C — multi-asset

1. Ogni asset deve seguire la sequenza CASO A o CASO B completa, con decisione operativa e journal auto-entry.
2. Produrre decisione operativa per ogni asset
3. Escludere asset con hard veto o rischio non ok
4. Confrontare gli asset rimanenti
5. Valutare correlazione e rischio aggregato
6. Produrre ranking multi-asset
7. Generare journal auto-entry per ogni asset

## Regola di priorità con trade aperto

Se esiste un trade aperto, il sistema non deve cercare un nuovo setup sullo stesso asset, salvo richiesta esplicita.
Deve concentrarsi sulla qualità residua del trade aperto.

## Logica intraday-like

L’automazione full applica in sequenza la stessa logica mentale dell’intraday, ma su timeframe swing.

Non esistono refresh frequenti del trigger.
Il sistema swing usa principalmente automazione full.

## Regole generali

- Leggi gli screenshot forniti
- L’agente deve rispettare `AGENTS.md`.
- L’output deve rispettare `9-Output Schema.md`.
- Non mescolare timeframe
- Non inventare dati non visibili
- Non inventare zone, livelli, indicatori o conferme non visibili
- Le zone e i livelli devono essere prodotti dal sistema, non richiesti all’utente come input già tracciati
- HTF deve produrre zona primaria e zona secondaria
- Dopo HTF, il sistema deve produrre Scenario Evidence e Candidate Discovery.
- Gli scenari devono essere supportati da dati visibili: supply/demand, livelli di rotazione, liquidità, value, VP/VWAP/AVWAP se verificabili.
- Non classificare CONTINUATION solo perché il trend è forte.
- Non classificare REVERSAL_CANDIDATE solo perché il prezzo è alto o basso.
- Non classificare BALANCE_ROTATION se non esiste una balance/value area leggibile.
- Se l’evidence pack è insufficiente, classificare NO_EDGE o DA MONITORARE.
- Il candidate principale deve essere scelto per rilevanza operativa dal decision point in avanti, non per forza storica del movimento.
- Un setup TARDIVO non può diventare TRADE VALIDO senza nuovo trigger/retest.
- TRADE_NOW nello scenario non significa TRADE VALIDO finale.
- LTF deve leggere solo la reazione del prezzo rispetto alla zona HTF
- Trigger deve decidere solo: TRADE VALIDO / TRADE NON VALIDO / DA MONITORARE
- Il Trigger deve produrre Entry, SL, TP1, TP2 e R:R
- Dopo Trigger, il sistema deve produrre Conditional Trade Plan.
- Conditional Trade Plan non rende valido un trade.
- Se il trade immediato è non valido ma lo scenario è vivo, il sistema deve indicare livello di attivazione, trigger richiesto, invalidazione, alert e screenshot successivo.
- Se il TP2 non è visibile perché il prezzo è vicino a massimi/minimi, il sistema deve eseguire Price Discovery / Open Space Check.
- Se lo storico è insufficiente, chiedere screenshot W1/MN, screenshot D1 più ampio oppure conferma utente sui massimi/minimi storici.
- Se TP1 è tecnico, il sistema può proporre gestione parziale e Stop Loss a BE dopo TP1, ma questo non sostituisce TP2 valido.
- Un piano condizionale non può essere paper trade finché una nuova analisi non produce TRADE VALIDO.
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
- Se manca un dato indispensabile, chiedere una sola integrazione mirata.
- La size viene calcolata solo dopo Entry e Stop Loss tecnico
- Se uno screenshot è assegnato male, rimappalo
- Se mancano dati essenziali, segnalalo
- Se mancano indicatori necessari, fermati e chiedi integrazione mirata
- Se gli screenshot non sono leggibili o mancano indicatori indispensabili, fermati al Preflight
- Prima di usare VWAP, AVWAP o Volume Profile, il sistema deve verificarne il settaggio.
- Un indicatore visibile non è automaticamente utilizzabile.
- Se AVWAP o VP non sono verificabili, devono essere classificati come `non verificabile` o `utilizzabile con cautela`.
- La price action ha priorità sugli indicatori non verificabili.
- Se un trade richiede una conferma da VP/VWAP/AVWAP e quella conferma non è verificabile, il trade non può essere `TRADE VALIDO`.
- Non forzare trade
- Se il trade non è valido, dichiaralo chiaramente
- Se il materiale è insufficiente, fermati al preflight
- La risposta deve iniziare sempre con `[DECISIONE OPERATIVA]`, prima del dettaglio completo
- Il sistema deve sempre generare un blocco journal auto-entry
- Il journal deve essere generato anche per TRADE NON VALIDO, DA MONITORARE e ASSET NON LEGGIBILE
- Il journal non deve essere narrativo: deve essere sintetico, confrontabile e copiabile in tabella
- Se mancano dati, il journal deve riportare il dato come `mancante`, `non applicabile` o `da aggiornare`, senza inventare nulla
- Se un campo non è disponibile, usare `mancante`, `non applicabile` o `da aggiornare`.
- L’output deve essere operativo prima che narrativo.
- In modalità multi-asset, non scegliere mai un trade solo perché è il migliore tra setup deboli.
- Gli asset con hard veto non possono essere promossi.
- Se nessun asset è valido, la decisione finale deve essere NESSUN TRADE.
- Se gli asset migliori sono troppo correlati, preferire un solo setup o classificare gli altri come da monitorare.
- Il ranking deve proteggere dall’overtrading.
- Il sistema non deve suggerire trading reale se non è stata completata la fase di paper trading.
- In fase di validazione, ogni TRADE VALIDO deve essere trattato come candidato paper trade, non come ordine reale.
- Ogni paper trade deve produrre journal auto-entry e review successiva.
- Se l’utente forza un trade fuori sistema, va classificato come errore di processo.

## Output operativo prioritario

Ogni esecuzione di `automazione_full.md` deve iniziare la risposta con un blocco sintetico di decisione operativa.

Questo blocco deve venire prima del dettaglio completo.

[DECISIONE OPERATIVA]

Asset:
Decisione:
Motivo principale:
Score finale:
Hard veto attivi:
Decisione rischio:
Azione immediata:
Prossimo passo:

Valori ammessi per Decisione:

- TRADE VALIDO
- TRADE NON VALIDO
- DA MONITORARE
- GESTIRE TRADE APERTO
- ASSET NON LEGGIBILE

Regole:

- Se esiste un hard veto attivo, Decisione = TRADE NON VALIDO.
- Se il materiale non è leggibile, Decisione = ASSET NON LEGGIBILE.
- Se Score finale < 60, Decisione = TRADE NON VALIDO.
- Se Score finale è 60-74 senza hard veto, Decisione = DA MONITORARE.
- Se Score finale >= 75 senza hard veto e rischio ok, Decisione = TRADE VALIDO.
- Se esiste trade aperto, Decisione = GESTIRE TRADE APERTO, salvo trade invalidato.
- Se Decisione rischio = RISCHIO NON OK, Decisione = TRADE NON VALIDO.
- Se Decisione rischio = DATI RISCHIO MANCANTI, Decisione = DA MONITORARE o TRADE NON VALIDO.
- Il blocco deve essere sintetico: niente spiegazioni lunghe.
- Il dettaglio completo deve restare nelle sezioni successive.
- Il journal auto-entry deve restare sempre generato.

## Modalità multi-asset

Il sistema può essere usato anche su più asset.

In modalità multi-asset:

- ogni asset deve ricevere la stessa sequenza di analisi;
- ogni asset deve produrre il proprio `[DECISIONE OPERATIVA]`;
- ogni asset deve produrre il proprio score;
- ogni asset deve produrre hard veto attivi;
- ogni asset deve produrre decisione rischio;
- ogni asset deve produrre journal auto-entry;
- solo dopo, il sistema può produrre il ranking multi-asset;
- il ranking deve usare `7-Multi Asset Ranking.md`.

[MULTI-ASSET DECISION]

Asset analizzati:
Asset validi:
Asset da monitorare:
Asset non validi:
Asset non leggibili:
Miglior setup:
Secondo setup:
Rischio correlazione:
Decisione finale:
Azione immediata:
Prossimo passo:

Valori ammessi per Decisione finale:

- OPERARE MIGLIOR SETUP
- NESSUN TRADE
- MONITORARE
- RICHIEDERE INTEGRAZIONI
- GESTIRE TRADE APERTO

## Modalità paper trading

In modalità paper trading:

- il sistema non invia ordini reali;
- TRADE VALIDO significa candidato paper trade;
- ogni simulazione deve rispettare entry, Stop Loss, TP, rischio e hard veto;
- ogni simulazione deve essere registrata nel journal;
- ogni trade deve essere rivisto tramite `6-Journal e Review.md`;
- le metriche aggregate devono essere valutate secondo `8-Paper Trading Protocol.md`.

[PAPER TRADING DECISION]

Paper mode:
Trade simulabile:
Motivo:
Condizioni da rispettare:
Journal richiesto:
Review richiesta:
Errore di processo se ignorato:

## Output finale

[ASSET: ... | DECISIONE FINALE]

Preflight:
Indicator setup check:
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
TP2 di estensione ammesso:
Partial TP / BE plan:
Gestione a TP1:
Stop a BE dopo TP1:
Runner verso TP2:
Decisione piano condizionale:
Indicatori utilizzabili per narrativa:
Indicatori non verificabili:
Affidabilità indicatori:
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
TP1:
Motivo TP1:
TP2:
Motivo TP2:
R:R su TP1:
R:R su TP2:
Target realistico:
Journal auto-entry generata: sì / no
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
Rischio monetario fisso:
Distanza Entry-SL:
Size da calcolare:
Size calcolabile:
Decisione rischio:
Hard veto rischio:
Dati mancanti per size:

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

## Journal-ready output

Ogni analisi deve produrre un blocco journal automatico, anche quando la decisione finale è:

- TRADE NON VALIDO
- DA MONITORARE
- ASSET NON LEGGIBILE

Il journal deve registrare anche i trade scartati, perché servono per misurare disciplina, qualità dei filtri e prevenzione dei setup mediocri.

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

I campi `Trade preso`, `Esito`, `Esito aggiornato` e `Note review` possono restare vuoti o “da aggiornare” al momento dell’analisi iniziale.

## Regole journal auto-entry

- ogni esecuzione di `automazione_full.md` deve terminare con un blocco journal;
- il blocco journal deve essere coerente con la decisione finale;
- se la decisione è TRADE VALIDO, compilare i campi operativi disponibili;
- se la decisione è TRADE NON VALIDO, compilare soprattutto hard veto, score, motivo principale e cosa mancava;
- se la decisione è DA MONITORARE, compilare cosa monitorare e validità temporale;
- se la decisione è ASSET NON LEGGIBILE, compilare motivo e integrazione richiesta;
- se esiste trade aperto, usare il blocco `[JOURNAL AUTO-ENTRY - TRADE APERTO]`;
- non inventare dati mancanti.
