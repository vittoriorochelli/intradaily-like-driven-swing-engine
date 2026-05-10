# 3 - Prompt Trigger

## Scopo

Decidere se il trade è realmente attivabile oppure no.

Il trigger deve rispondere alla domanda:
“Posso entrare davvero oppure no?”

Il trigger è separato dal timing.
Il timing dice se il prezzo sta reagendo bene.
Il trigger dice se si può entrare.

## Condizioni minime

Un trade è valido solo se:

- HTF è leggibile e coerente
- LTF conferma
- prezzo è in zona sensata
- trigger tecnico è presente
- stop tecnico è ricavabile
- R:R è almeno accettabile
- nessun hard veto è attivo
- gli indicatori necessari alla decisione sono visibili

Il trigger non può essere validato se mancano elementi indispensabili alla decisione.

## Hard veto

Bloccare il trade se:

- prezzo nel mezzo del range
- prezzo lontano dalla zona HTF
- struttura HTF non chiara
- LTF non conferma
- trigger assente
- stop tecnico troppo largo
- R:R insufficiente
- VWAP contraria se necessaria
- Volume Profile contrario se necessario
- dominance buyers/sellers opposta se necessaria
- screenshot insufficienti
- setup forzato

## Entry ammesse

Il sistema può validare solo entry tecniche.

Tipi di entry ammessi:

- retest di zona HTF confermata
- rejection confermata su zona HTF
- false break / presa di liquidità con reclaim
- micro-BOS / micro-CHOCH con retest
- breakout + retest da balance o struttura
- reazione su Fair Value Gap solo se coerente con HTF e LTF
- ritorno a VWAP/value area solo se coerente con struttura e zona

Hard veto:

- entry nel mezzo del range
- entry lontana dalla zona HTF
- entry senza invalidazione chiara
- entry basata solo su movimento impulsivo non confermato
- entry forzata

## Stop Loss tecnico

Lo Stop Loss deve essere tecnico e derivare da:

- invalidazione locale
- swing che invalida il setup
- lato opposto della zona supply/demand
- massimo/minimo della presa di liquidità
- struttura che ha generato il trigger

Regole:

- lo SL deve avere buffer tecnico
- lo SL non deve essere scelto per comodità monetaria
- la size si adatta allo SL, non il contrario
- il rischio monetario fisso verrà applicato dopo, tramite position sizing

Hard veto:

- SL arbitrario
- SL non tecnico
- SL troppo stretto rispetto a volatilità/spread
- SL troppo largo rispetto al target disponibile
- SL che non rappresenta vera invalidazione

## Take Profit

Il sistema deve distinguere:

- TP1: primo ostacolo tecnico
- TP2: target operativo principale
- TP finale: eventuale estensione

Target validi:

- swing high / swing low precedente
- zona supply/demand opposta
- POC / VAH / VAL / HVN / LVN rilevanti
- area di liquidità evidente
- estensione strutturale coerente
- Fair Value Gap target solo se realistico e coerente

Target non validi:

- target teorico non visibile
- target scelto solo per far tornare il R:R
- target oltre barriera strutturale importante senza motivo
- target troppo ambizioso rispetto al contesto

## Rapporto rischio/rendimento

Regole:

- R:R minimo operativo su TP2: 1:2
- TP1 può essere inferiore a 1:2 se è solo parziale
- se TP2 non offre almeno 1:2, il trade non è valido
- R:R > 1:3 è ottimo solo se il target è realistico

Classificazione:

- R:R < 1:2 = insufficiente
- R:R 1:2 - 1:2.5 = accettabile
- R:R 1:2.5 - 1:3 = buono
- R:R > 1:3 = ottimo solo se target realistico

Hard veto:

- R:R su TP2 inferiore a 1:2
- target non realistico
- target solo teorico
- stop troppo largo per consentire target realistico

## Scoring finale

Totale: 100 punti

Distribuzione:

- HTF: 30 punti
- LTF: 25 punti
- Trigger: 25 punti
- R:R / qualità operativa: 20 punti

Soglie decisionali:

- >= 75 e nessun hard veto = TRADE VALIDO
- 60-74 e nessun hard veto = DA MONITORARE
- < 60 = TRADE NON VALIDO
- qualsiasi hard veto attivo = TRADE NON VALIDO, anche se il punteggio è alto

Regola:

Il punteggio non può compensare un hard veto.  
Score alto + hard veto attivo = TRADE NON VALIDO.

Dettaglio punteggi:

HTF — 30 punti:
- struttura leggibile: 6
- bias strutturale chiaro: 6
- zona primaria/secondaria valida: 6
- Volume Profile / AVWAP / valore coerenti se visibili: 4
- invalidazione strutturale chiara: 4
- asset non nel mezzo del nulla: 4

LTF — 25 punti:
- prezzo dentro o vicino alla zona HTF: 5
- reazione leggibile: 6
- reazione coerente con bias HTF: 5
- micro-struttura favorevole: 4
- VWAP / Volume Profile locale / dominance coerenti se necessari: 3
- invalidazione locale chiara: 2

Trigger — 25 punti:
- entry tecnica ammessa: 5
- entry non forzata: 4
- Stop Loss tecnico: 6
- target tecnico realistico: 4
- trigger confermato: 4
- setup non tardivo: 2

R:R / qualità operativa — 20 punti:
- R:R su TP2 >= 1:2: 6
- target realistico e raggiungibile: 5
- stop non troppo stretto: 3
- stop non troppo largo: 3
- setup gestibile con rischio monetario fisso: 3

Specifica:

il calcolo preciso della size verrà gestito nella fase Risk e Position Sizing.  
In questa fase il sistema valuta solo la compatibilità preliminare del setup con la logica di rischio monetario fisso.

## Hard veto sistemici

Hard veto Preflight:
- screenshot insufficienti
- timeframe non leggibile
- prezzo/scala non leggibili
- indicatori indispensabili mancanti
- zoom non adeguato

Hard veto HTF:
- struttura HTF non leggibile
- bias HTF neutro/confuso
- prezzo nel mezzo del range
- zona primaria non identificabile
- invalidazione strutturale non definibile

Hard veto LTF:
- prezzo lontano dalla zona HTF
- nessuna reazione chiara
- reazione opposta al bias HTF
- LTF non conferma
- invalidazione locale non definibile

Hard veto Trigger:
- entry non tecnica
- entry forzata
- entry tardiva
- Stop Loss non tecnico
- stop troppo stretto
- stop troppo largo
- TP2 non realistico
- R:R su TP2 < 1:2

Hard veto rischio preliminare:
- setup non compatibile con rischio monetario fisso
- size presumibilmente impraticabile
- spread/volatilità rendono lo stop non utilizzabile

## Relazione con Risk e Position Sizing

- il Trigger definisce Entry, Stop Loss tecnico, TP1, TP2 e R:R;
- il Trigger non calcola la size definitiva;
- la size viene gestita nel modulo Risk e Position Sizing;
- il Trigger deve produrre livelli sufficientemente precisi per permettere il calcolo della distanza Entry-SL;
- se Entry o Stop Loss non sono precisi, il trade deve essere DA MONITORARE o TRADE NON VALIDO.

## Decisione trigger

Valori ammessi:

- TRADE VALIDO
- TRADE NON VALIDO
- DA MONITORARE

## Output trigger

[ASSET: ... | TRIGGER]

Tipo entry:
Entry:
Motivo entry:
Stop Loss:
Motivo Stop Loss:
Distanza Entry-SL:
Stop tecnico: sì / no
Stop troppo stretto: sì / no
Stop troppo largo: sì / no
TP1:
TP2:
Dati pronti per position sizing: sì / no
Dati mancanti per position sizing:
