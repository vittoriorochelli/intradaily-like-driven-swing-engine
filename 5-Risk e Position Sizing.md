# 5 - Risk e Position Sizing

## Scopo

Validare che il trade sia compatibile con la gestione del rischio a rischio monetario fisso.

Il modulo non sceglie lo Stop Loss.
Lo Stop Loss deve arrivare dal Trigger ed essere tecnico.

## Principio operativo

Il sistema usa rischio monetario fisso per trade.

Sequenza obbligatoria:

1. definire Entry tecnica;
2. definire Stop Loss tecnico;
3. misurare distanza Entry-SL;
4. verificare se lo Stop Loss è valido;
5. calcolare o richiedere la size necessaria per mantenere fisso il rischio monetario;
6. verificare se la size è praticabile;
7. validare o bloccare il trade dal punto di vista del rischio.

## Regola fondamentale

Lo Stop Loss non si adatta alla size.
La size si adatta allo Stop Loss.

Lo Stop Loss non deve essere scelto per comodità monetaria.

## R:R statico e R:R gestito

Il sistema deve distinguere:

- R:R statico: valutazione diretta tra Entry, Stop Loss e TP2;
- R:R gestito: valutazione che considera TP1, chiusura parziale, Stop Loss a BE e runner verso TP2.

Il R:R gestito può migliorare la qualità del piano, ma non può aggirare i requisiti minimi del trade.

Regole:

- TP1 + BE non sostituisce TP2 valido;
- TP1 + BE non rende valido un trade con entry scadente;
- se TP2 è di estensione, deve essere derivato da regola oggettiva;
- se price discovery non è verificabile, il trade non può essere RISCHIO OK;
- un piano condizionale può avere rischio preliminare, ma non RISCHIO OK definitivo;
- Risk e Position Sizing valida solo trade con Entry, Stop Loss tecnico, distanza Entry-SL, TP2, R:R e dati di size sufficienti.

## Cosa valutare

- rischio monetario fisso;
- direzione trade;
- entry;
- Stop Loss tecnico;
- distanza Entry-SL;
- TP1;
- TP2;
- R:R su TP2;
- R:R statico;
- R:R gestito;
- TP1 parziale;
- Stop a BE dopo TP1;
- runner verso TP2;
- TP2 di estensione;
- price discovery verificata o non verificata;
- rischio preliminare del piano condizionale;
- size da calcolare;
- pip value / tick value / valore punto, se disponibile;
- lotto minimo;
- margine richiesto;
- spread e commissioni;
- volatilità;
- rischio aggregato;
- asset correlati.

## Hard veto rischio

Bloccare il trade se:

- Stop Loss non tecnico;
- Stop Loss arbitrario;
- Stop Loss troppo stretto rispetto a spread/volatilità;
- Stop Loss troppo largo rispetto al target disponibile;
- R:R su TP2 < 1:2;
- size non calcolabile per dati essenziali mancanti;
- size risultante non praticabile;
- lotto minimo non compatibile;
- margine insufficiente;
- rischio aggregato eccessivo;
- esposizione correlata eccessiva.

## Dati mancanti

Se mancano dati necessari per calcolare la size, il sistema non deve inventare.

Deve indicare chiaramente:

- quali dati mancano;
- se il trade può restare da monitorare;
- se il trade deve essere bloccato.

## Decisione rischio

Valori ammessi:

- RISCHIO OK
- RISCHIO NON OK
- DATI RISCHIO MANCANTI

## Output obbligatorio

[ASSET: ... | RISK E POSITION SIZING]

Rischio monetario fisso:
Direzione:
Entry:
Stop Loss tecnico:
Motivo Stop Loss:
Distanza Entry-SL:
Stop valido: sì / no
Stop troppo stretto: sì / no
Stop troppo largo: sì / no
TP1:
TP2:
R:R su TP2:
R:R statico:
R:R gestito:
TP1 parziale:
Stop a BE dopo TP1:
Runner verso TP2:
TP2 di estensione:
Price discovery verificata:
Rischio preliminare piano condizionale:
Rischio monetario applicabile: sì / no
Size da calcolare:
Size calcolabile: sì / no
Dati mancanti per size:
Compatibilità lotto minimo:
Compatibilità margine:
Spread/commissioni rilevanti:
Rischio aggregato:
Correlazioni:
Hard veto rischio:
Decisione rischio:
Sintesi operativa:
