# 1 - Prompt HTF

HTF significa Higher Time Frame, cioè timeframe superiore.

## Scopo

Analizzare la struttura swing dell’asset sui timeframe superiori e identificare le zone operative principali.

Il blocco HTF lavora principalmente sullo screenshot D1/H4.

L’utente non deve fornire zone già tracciate.
Il sistema deve ricavare zone supply/demand, livelli chiave, invalidazione e aree di monitoraggio.

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

## Cosa valutare

- Trend, balance o transizione
- Bias strutturale long, short o neutro
- Swing principali
- Zone supply/demand
- Livelli chiave
- Qualità delle zone
- Fresh/tested
- Reazione precedente alla zona
- Struttura Wyckoff se visibile
- Lettura AMT: acceptance, rejection, balance, imbalance
- Volume Profile: POC, VAH, VAL, HVN, LVN
- AVWAP se presente
- Dominance buyers/sellers se visibile
- Invalidazione strutturale
- Zona primaria da monitorare
- Zona secondaria da monitorare
- Validità dell’asset fuori zona

## Non fare

- Non generare entry
- Non fare gestione posizione
- Non anticipare trigger
- Non inventare dati non visibili

## Output base

[ASSET: ... | STRUTTURA HTF]

Stato mercato:
Bias strutturale:
Struttura:
Wyckoff:
AMT:
Zone demand:
Zone supply:
Livelli chiave:
Volume Profile:
AVWAP:
Dominance buyers/sellers:
Zona primaria:
Zona secondaria:
Invalidazione strutturale:
Aree di monitoraggio:
Asset valido fuori zona:
Cosa osservare in LTF:
Qualità struttura:
Sintesi operativa:
