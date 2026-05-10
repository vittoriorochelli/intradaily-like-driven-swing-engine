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
Motivo TP1:
TP2:
Motivo TP2:
Target realistico: sì / no
R:R su TP1:
R:R su TP2:
Conferme:
Hard veto:
Decisione trigger:
Azione:
Sintesi operativa:
