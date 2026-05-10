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
