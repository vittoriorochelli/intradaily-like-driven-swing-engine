# 9 - Output Schema

## Scopo

Definire lo schema standard degli output prodotti dal sistema.

Lo schema serve a rendere le analisi confrontabili, tracciabili, journal-ready e utilizzabili da un agente AI.

## Output prioritario

Ogni esecuzione deve iniziare con:

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

## Output indicator setup check

[INDICATOR SETUP CHECK]

VWAP visibile:
Tipo VWAP:
VWAP utilizzabile:
Motivo VWAP:
AVWAP visibile:
Anchor AVWAP visibile/dichiarato:
Anchor AVWAP sensato:
AVWAP utilizzabile:
Motivo AVWAP:
Volume Profile visibile:
Range/ancoraggio VP sensato:
POC/VAH/VAL leggibili:
VP utilizzabile:
Motivo VP:
Indicatori utilizzabili per narrativa:
Indicatori solo di supporto:
Indicatori non utilizzabili:
Impatto sulla decisione:

## Output narrativa da screenshot

[NARRATIVA RICOSTRUITA]

Movimento precedente:
Struttura costruita:
Area chiave più vecchia:
Impulso principale:
Pullback visibile:
Breakout visibile:
Accettazione visibile:
Retest visibile:
Fallimento visibile:
Prezzo attuale rispetto alla narrativa:
Setup già partito:
Entry ancora disponibile:
Entry già passata:
Stato operativo ricavato dal grafico:
Narrativa affidabile:
Indicatori usati nella narrativa:
Indicatori non verificabili:
Indicatori ignorati:
Narrativa basata principalmente su:
Affidabilità indicatori:
Integrazione richiesta:

## Output scenario evidence e candidate discovery

[SCENARIO EVIDENCE PACK]

Supply rilevanti:
Demand rilevanti:
Livelli di rotazione:
Liquidità sopra:
Liquidità sotto:
Area di valore:
POC / VAH / VAL:
VWAP / AVWAP utilizzabili:
Indicatori non verificabili:
Prezzo attuale rispetto alle zone:
Movimento precedente:
Reazione visibile:
Spazio operativo:
Dati mancanti:
Affidabilità evidence pack:

[SCENARIO CANDIDATE]

Scenario:
Direzione:
Zona di riferimento:
Evidenze a favore:
Evidenze contro:
Dati mancanti:
Stato temporale:
Stato operativo:
Rilevanza operativa:
Candidate valido:
Motivo:

[SCENARIO DISCOVERY OUTPUT]

Evidence pack affidabile:
Numero candidate:
Candidate principale:
Scenario principale:
Direzione:
Stato temporale:
Stato operativo:
Rilevanza operativa:
Motivo scelta candidate principale:
Scenario alternativi:
Scenario scartati:
Dati mancanti:
Impatto su LTF/Trigger:

## Output conditional trade plan

[CONDITIONAL TRADE PLAN]

Scenario vivo:
Motivo scenario vivo:
Trade ora:
Motivo trade ora:
Direzione condizionale:
Livello di attivazione:
Evento richiesto:
Trigger richiesto:
Entry condizionale preliminare:
Stop tecnico preliminare:
Motivo stop preliminare:
TP1 preliminare:
Motivo TP1:
TP2 preliminare:
Motivo TP2:
R:R preliminare:
R:R preliminare valido:
Invalidazione scenario:
Scadenza temporale del piano:
Alert da impostare:
Screenshot successivo richiesto:
Dati mancanti:
Decisione piano condizionale:

[PRICE DISCOVERY / OPEN SPACE CHECK]

Prezzo vicino a massimi/minimi visibili:
Massimi/minimi superiori o inferiori visibili:
Storico sufficiente:
Price discovery confermata:
Price discovery non verificabile:
Open space condizionale:
Screenshot aggiuntivo richiesto:
TP1 strutturale:
TP2 strutturale:
TP2 di estensione ammesso:
Regola TP2 di estensione:
Qualità TP2:
Impatto su R:R:

[PARTIAL TP / BREAK-EVEN PLAN]

TP1 tecnico:
TP1 raggiungibile:
R:R su TP1:
Gestione a TP1:
Percentuale parziale:
Stop a BE dopo TP1:
Condizione per spostare SL a BE:
Runner verso TP2:
TP2 strutturale:
TP2 di estensione:
Rischio residuo dopo BE:
Trade valido senza TP2 statico:
Motivo:

## Output finale single asset

Questi blocchi devono essere prodotti anche se il trade è TRADE NON VALIDO, quando sono richiamati da Trigger, Conditional Plan o Risk.


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
[PRICE DISCOVERY / OPEN SPACE CHECK]
Prezzo vicino a massimi/minimi visibili:
Massimi/minimi superiori o inferiori visibili:
Storico sufficiente:
Price discovery confermata:
Price discovery non verificabile:
Open space condizionale:
Screenshot aggiuntivo richiesto:
TP1 strutturale:
TP2 strutturale:
TP2 di estensione ammesso:
Regola TP2 di estensione:
Qualità TP2:
Impatto su R:R:

[PARTIAL TP / BREAK-EVEN PLAN]
TP1 tecnico:
TP1 raggiungibile:
R:R su TP1:
Gestione a TP1:
Percentuale parziale:
Stop a BE dopo TP1:
Condizione per spostare SL a BE:
Runner verso TP2:
TP2 strutturale:
TP2 di estensione:
Rischio residuo dopo BE:
Trade valido senza TP2 statico:
Motivo:

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

## Output trade aperto

[ASSET: ... | DECISIONE FINALE - TRADE APERTO]

Stato trade:
Deterioramento:
Azione:
Nuovo stop:
Gestione profitto:
Uscita anticipata:
Motivo:
Sintesi operativa:

## Output multi-asset

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

## Output paper trading

[PAPER TRADING DECISION]

Paper mode:
Trade simulabile:
Motivo:
Condizioni da rispettare:
Journal richiesto:
Review richiesta:
Errore di processo se ignorato:

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
Price discovery check: (non applicabile / condizionale / non verificabile / da rivalutare / sì / no)
Esito price discovery/open space:
Storico sufficiente:
Screenshot aggiuntivo richiesto:
Regola TP2 di estensione:
Qualità TP2 di estensione:
TP2 di estensione ammesso: (non applicabile / condizionale / non verificabile / da rivalutare / sì / no)
Partial TP / BE plan: (non applicabile / condizionale / non verificabile / da rivalutare / sì / no)
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

## Regole dati mancanti

Usare sempre:

- `mancante` se il dato non è disponibile;
- `non applicabile` se il dato non serve in quel caso;
- `da aggiornare` se il dato verrà completato dopo.

Non lasciare campi ambigui.

## Regola finale

L’output deve essere più utile che elegante.

Prima viene la decisione operativa.
Poi il dettaglio.
Poi il journal.
