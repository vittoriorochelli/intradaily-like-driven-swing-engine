# intradaily-like-driven-swing-engine

Motore documentale per analisi swing/multiday derivato dalla logica del sistema `trading-intraday`.

Il progetto non è un sistema swing generico.  
È una trasposizione lenta, strutturale e multiday della logica intraday: lettura a blocchi, screenshot, struttura, timing, trigger, gestione e output rigido.

## Principio guida

Il sistema deve rispondere a una domanda:

> Esiste un’opportunità swing/multiday valida, leggibile e gestibile, derivata da struttura HTF, reazione LTF e trigger tecnico?

Il sistema non deve forzare trade.

## Architettura core

Il core system è organizzato in blocchi logici:

1. `0-Preflight Input Check.md`
2. `1-Prompt HTF.md`
3. `2-Prompt LTF.md`
4. `3-Prompt Trigger.md`
5. `4-Gestione Posizione.md`
6. `automazione_full.md`

## Uso operativo

L’uso ordinario avviene tramite:

`automazione_full.md`

I singoli file modulari servono come componenti logiche interne.  
Nel sistema swing/multiday non è previsto un refresh continuo del trigger durante la giornata.

## Derivazione da trading-intraday

Il sistema nasce come trasposizione swing/multiday della logica `trading-intraday`.

Mappa di trasformazione:

- H1 nudo intraday → D1/H4 swing per struttura HTF
- M5 nudo intraday → H4/H1 swing per reazione LTF
- M5 con VWAP e Volume Profile → H4/H1 con VWAP, Volume Profile locale e dominance se disponibile
- refresh intraday → automazione full unica nel sistema swing
- trigger rapido intraday → trigger swing più selettivo
- gestione ravvicinata intraday → gestione H4/D1

Nota:
la versione swing mantiene la logica screenshot-driven, ma riduce il numero di input ordinari a due screenshot informativi:

- HTF D1/H4
- LTF H4/H1

## Input standard

Il sistema usa ordinariamente due screenshot:

- Screenshot HTF D1/H4
- Screenshot LTF H4/H1

Lo screenshot D1/H4 serve per ricavare:

- struttura swing;
- trend, balance o transizione;
- zone supply/demand;
- livelli strutturali;
- Volume Profile se presente;
- AVWAP se presente;
- invalidazione strutturale.

Lo screenshot H4/H1 serve per ricavare:

- reazione locale;
- rejection;
- absorption;
- acceptance;
- false break;
- retest;
- micro-BOS/CHOCH;
- rapporto con VWAP se presente;
- Volume Profile locale se presente;
- dominance buyers/sellers se presente;
- stop tecnico e invalidazione locale.

L’utente non deve fornire zone/livelli già tracciati: il sistema li ricava dall’analisi.

## Timeframe di riferimento

- W1: cornice opzionale
- D1: struttura primaria
- H4: struttura operativa
- H1: timing principale e trigger
- H4/D1: gestione posizione

## Strumenti tecnici core

Il sistema dovrà progressivamente integrare:

- struttura swing
- supply/demand
- Wyckoff
- Auction Market Theory, cioè AMT
- Volume Profile
- VWAP
- AVWAP
- dominance buyers/sellers
- BOS/CHOCH
- rejection
- absorption
- acceptance
- false break
- retest
- hard veto

## Nota sul contesto macro

Il contesto macro non fa parte del core system in questa fase.  
Potrà essere aggiunto in futuro come modulo opzionale.
