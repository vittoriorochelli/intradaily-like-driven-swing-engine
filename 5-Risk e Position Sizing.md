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

## Cosa valutare

- rischio monetario fisso;
- direzione trade;
- entry;
- Stop Loss tecnico;
- distanza Entry-SL;
- TP1;
- TP2;
- R:R su TP2;
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
