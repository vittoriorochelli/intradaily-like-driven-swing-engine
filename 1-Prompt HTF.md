# 1 - Prompt HTF

HTF significa Higher Time Frame, cioè timeframe superiore.

## Scopo

Analizzare la struttura swing dell’asset sui timeframe superiori e identificare le zone operative principali.

Il blocco HTF lavora principalmente sullo screenshot D1/H4.

L’utente non deve fornire zone già tracciate.
Il sistema deve ricavare in autonomia:

- struttura swing;
- trend/balance/transizione;
- zone supply/demand;
- zona primaria;
- zona secondaria;
- livelli chiave;
- invalidazione strutturale;
- aree di monitoraggio.

Se lo screenshot D1/H4 non permette di leggere struttura o indicatori necessari, il sistema deve chiedere integrazione.

## Timeframe

- W1: cornice opzionale
- D1: struttura primaria
- H4: struttura operativa

## Derivazione intraday → HTF swing

Il blocco HTF swing eredita la funzione del blocco strutturale intraday, ma lavora su D1/H4 invece che H1/M5.

Deve dare più peso a:

- struttura swing
- supply/demand
- Wyckoff
- Auction Market Theory
- Volume Profile
- AVWAP
- livelli di valore
- invalidazione strutturale

## Classificazione mercato

Valori ammessi:

- trend rialzista
- trend ribassista
- balance
- transizione
- non leggibile

## Lettura tecnica HTF

- Wyckoff: accumulazione, distribuzione, markup, markdown, spring, upthrust/UTAD, trading range se visibili
- Auction Market Theory: acceptance, rejection, balance, imbalance, value migration
- Volume Profile: POC, VAH, VAL, HVN, LVN
- AVWAP: usare solo se visibile e rilevante
- dominance buyers/sellers: usare solo se visibile

## Cosa valutare

- Stato mercato e bias strutturale
- Swing principali
- Zone supply/demand
- Zona primaria e tipo zona primaria
- Zona secondaria e tipo zona secondaria
- Livelli chiave
- Qualità delle zone
- Fresh/tested
- Reazione precedente alla zona
- Invalidazione strutturale
- Aree di monitoraggio
- Asset valido fuori zona
- Cosa osservare in LTF

## Non fare

- Non generare entry
- Non fare gestione posizione
- Non anticipare trigger
- Non inventare dati non visibili

## Dati strutturali per Scenario Evidence

HTF deve produrre i dati strutturali necessari alla classificazione degli scenari.

HTF non deve classificare lo scenario finale.
HTF deve fornire i dati solidi per il modulo `12-Scenario Evidence e Candidate Discovery.md`.

## Output HTF obbligatorio

[ASSET: ... | STRUTTURA HTF]

Stato mercato:
Bias strutturale:
Struttura:
Wyckoff:
AMT:
Zone demand:
Zone supply:
Zona primaria:
Tipo zona primaria:
Zona secondaria:
Tipo zona secondaria:
Livelli chiave:
Volume Profile:
AVWAP:
Dominance buyers/sellers:
Invalidazione strutturale:
Asset valido fuori zona:
Cosa osservare in LTF:
Qualità struttura:
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
Dati strutturali mancanti:
Affidabilità dati strutturali:
Sintesi operativa:

Regola:
se questi dati non sono ricavabili dallo screenshot, usare `mancante`, `non verificabile` o `non applicabile`.
Non inventare dati strutturali.
