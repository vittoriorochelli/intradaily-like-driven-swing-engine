# 12 - Scenario Evidence e Candidate Discovery

## Scopo

Classificare gli scenari operativi possibili partendo da evidenze strutturali solide.

Questo modulo non genera trade.
Non produce Entry, Stop Loss, Take Profit o R:R.
Non sostituisce LTF, Trigger, Risk o Scoring.

Serve a rispondere a una domanda:

Quali scenari operativi sono realmente autorizzati dai dati visibili?

Gli scenari ammessi sono:

- CONTINUATION
- REVERSAL_CANDIDATE
- BALANCE_ROTATION
- NO_EDGE

## Regola fondamentale

Uno scenario non è una storia plausibile.

Uno scenario è valido solo se supportato da evidenze leggibili, tra cui:

- struttura prezzo;
- supply e demand;
- livelli di rotazione;
- liquidità;
- aree di valore;
- Volume Profile, se verificabile;
- POC / VAH / VAL, se leggibili;
- VWAP / AVWAP, se verificabili;
- posizione del prezzo rispetto alle zone;
- reazione visibile;
- spazio operativo residuo.

Se queste evidenze non sono sufficienti, lo scenario deve essere:

- NO_EDGE;
- FUTURO_CONDIZIONALE;
- oppure non classificabile con sufficiente affidabilità.

## Relazione con Narrativa da Screenshot

La narrativa dice cosa è successo nel grafico.
Il modulo scenario dice quale opportunità operativa, se esiste, è autorizzata da quella narrativa e dai dati strutturali.

La narrativa è descrittiva.
Lo scenario è classificativo.

## Relazione con HTF

HTF deve fornire i dati strutturali di base:

- trend, balance o transizione;
- supply principali;
- demand principali;
- livelli di rotazione;
- massimi/minimi strutturali;
- zone di liquidità evidenti;
- area di valore, se leggibile;
- POC / VAH / VAL, se Volume Profile è utilizzabile;
- VWAP / AVWAP utilizzabili o non verificabili;
- posizione del prezzo rispetto alle aree.

Il modulo scenario non deve inventare questi dati se HTF non li ha ricavati.

## Scenario Evidence Pack

Prima di proporre scenari, produrre:

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

Valori ammessi per Affidabilità evidence pack:

- ALTA
- MEDIA
- BASSA
- INSUFFICIENTE

Se Affidabilità evidence pack = INSUFFICIENTE, non produrre scenario operativo valido.

## Setup Candidate Discovery

Dopo l’evidence pack, elencare fino a 3 scenario candidate.

Per ogni candidate usare:

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

Valori ammessi per Scenario:

- CONTINUATION
- REVERSAL_CANDIDATE
- BALANCE_ROTATION
- NO_EDGE

Valori ammessi per Direzione:

- LONG
- SHORT
- N/A

Valori ammessi per Stato temporale:

- ATTIVO
- TARDIVO
- FUTURO_CONDIZIONALE
- SCARTATO

Valori ammessi per Stato operativo:

- TRADE_NOW
- WAIT_FOR_TRIGGER
- WAIT_FOR_RETEST
- NO_EDGE

Valori ammessi per Rilevanza operativa:

- ALTA
- MEDIA
- BASSA

Valori ammessi per Candidate valido:

- sì
- no
- parziale

## CONTINUATION

Uno scenario CONTINUATION richiede evidenze come:

- struttura HTF direzionale;
- sequenza coerente di massimi/minimi;
- prezzo sopra/sotto area di valore coerente con la direzione;
- demand/retest valido per long oppure supply/retest valido per short;
- breakout non già eccessivamente esteso;
- spazio operativo verso target realistico;
- VWAP/AVWAP/VP coerenti se utilizzati;
- assenza di hard veto evidenti.

Non basta che il trend sia forte.

Se il prezzo è già partito ed è lontano dalla zona logica, lo scenario può essere CONTINUATION ma lo stato temporale deve essere TARDIVO e lo stato operativo preferito è WAIT_FOR_RETEST.

## REVERSAL_CANDIDATE

Uno scenario REVERSAL_CANDIDATE richiede evidenze come:

- prezzo in supply/demand HTF significativa;
- sweep o failed auction;
- rifiuto visibile;
- mancata accettazione oltre un livello;
- perdita di momentum della direzione precedente;
- ritorno in value o reclaim di area chiave;
- Volume Profile / VWAP / AVWAP coerenti, se verificabili;
- trigger non ancora obbligatorio, ma scenario strutturale plausibile.

Non basta che il prezzo sia “alto” o “basso”.

Se mancano supply/demand, liquidità o failed auction visibile, non classificare reversal candidate.

## BALANCE_ROTATION

Uno scenario BALANCE_ROTATION richiede evidenze come:

- balance/range/value area leggibile;
- prezzo vicino a estremo alto o basso della balance;
- POC o area centrale identificabile;
- VAH/VAL o estremi strutturali leggibili;
- rifiuto dell’estremo;
- target logico verso POC o lato opposto;
- assenza di accettazione fuori dalla balance.

Se non esiste una balance leggibile, non classificare balance rotation.

## NO_EDGE

Usare NO_EDGE quando:

- struttura confusa;
- zone non leggibili;
- supply/demand non chiare;
- livelli di rotazione non identificabili;
- price action in mezzo al range;
- indicatori necessari non verificabili;
- scenari concorrenti troppo ambigui;
- nessuno scenario ha evidenze sufficienti.

## Regola candidate principale

Scegliere il candidate principale in base alla rilevanza operativa dal decision point in avanti.

Non scegliere automaticamente il candidate con maggiore evidenza storica se non è più attivabile.

Priorità:

1. TRADE_NOW
2. WAIT_FOR_TRIGGER
3. WAIT_FOR_RETEST
4. NO_EDGE / TARDIVO

Se un setup è già partito, esteso o non più attivabile, classificarlo TARDIVO e non promuoverlo a candidate principale salvo che sia l’unico scenario leggibile.

## Regola anti-confusione TRADE_NOW

TRADE_NOW nello scenario non significa TRADE VALIDO finale.

Significa solo che il candidate è operativo e può passare al Trigger.

La decisione finale resta demandata a:

- LTF;
- Trigger;
- Risk e Position Sizing;
- hard veto;
- R:R.

## Output finale del modulo

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

## Regola finale

Lo scenario deve proteggere l’utente da tre errori:

1. confondere trend forte con entry valida;
2. confondere prezzo sopra/sotto livello con breakout validato;
3. inventare reversal o rotation senza dati solidi.
