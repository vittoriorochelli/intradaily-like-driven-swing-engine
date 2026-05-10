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

## Output finale single asset

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
