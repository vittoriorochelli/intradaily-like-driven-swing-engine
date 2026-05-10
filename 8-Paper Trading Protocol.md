# 8 - Paper Trading Protocol

## Scopo

Validare il sistema in ambiente paper trading prima di qualsiasi uso con denaro reale.

Il paper trading non serve a dimostrare che ogni trade funziona.
Serve a verificare se il processo produce decisioni disciplinate, ripetibili e misurabili.

## Regola fondamentale

Il sistema non è pronto per trading reale finché non esiste una fase documentata di paper trading con risultati sufficienti.

Il paper trading deve precedere qualsiasi forma di:
- ordine reale;
- semi-automazione;
- automazione broker;
- aumento di size;
- uso su conto prop o conto personale reale.

## Fasi del paper trading

## Conditional plan e paper trading

Un Conditional Trade Plan non è un paper trade.

Il piano condizionale serve solo a preparare monitoraggio, alert e rivalutazione.

Un trade può essere simulato in PT-1 solo se, dopo nuova analisi o aggiornamento screenshot, il sistema produce:

- TRADE VALIDO;
- score >= 75;
- nessun hard veto;
- Decisione rischio = RISCHIO OK;
- Entry, Stop Loss, TP1 e TP2 definiti;
- R:R su TP2 >= 1:2 oppure R:R gestito esplicitamente validato secondo le regole del sistema;
- journal completo.

Se il piano condizionale è attivo ma non ancora validato, la decisione resta:

- DA MONITORARE;
- PIANO CONDIZIONALE ATTIVO;
- nessun paper trade.

### Fase PT-0 — Osservazione senza esecuzione

Obiettivo:
verificare se il sistema legge correttamente il mercato senza prendere trade.

Durata minima:
- almeno 20 analisi complete;
- almeno 5 asset diversi se disponibili;
- almeno 2 settimane operative.

Regole:
- nessun trade simulato;
- solo analisi;
- registrare ogni output nel journal;
- controllare se gli hard veto sono coerenti;
- controllare se i setup scartati erano davvero deboli.

### Fase PT-1 — Paper trading assistito

Obiettivo:
simulare trade solo quando il sistema produce TRADE VALIDO.

Durata minima:
- almeno 30 trade simulati;
- almeno 4 settimane operative;
- nessun trade fuori sistema.

Regole:
- prendere solo trade con score >= 75;
- nessun hard veto attivo;
- Decisione rischio = RISCHIO OK;
- Entry, Stop Loss, TP1 e TP2 definiti;
- R:R su TP2 >= 1:2 oppure R:R gestito esplicitamente validato secondo le regole del sistema;
- journal obbligatorio;
- review post-trade obbligatoria.

Nota:
R:R gestito non significa piano condizionale.
Un piano condizionale resta non simulabile finché una nuova analisi non produce TRADE VALIDO.

### Fase PT-2 — Paper trading controllato

Obiettivo:
verificare la robustezza del processo su più asset e su condizioni di mercato diverse.

Durata minima:
- almeno 50 trade simulati complessivi;
- almeno 8 settimane operative;
- uso del multi-asset ranking;
- monitoraggio delle correlazioni;
- review settimanale.

Regole:
- massimo numero di setup simulati per settimana;
- evitare overtrading;
- se il sistema dice NESSUN TRADE, non si forza nessun trade;
- se il sistema richiede integrazioni, il trade non viene simulato finché i dati non sono completi.

## Metriche minime da tracciare

- numero analisi totali;
- numero trade validi;
- numero trade non validi;
- numero setup da monitorare;
- numero asset non leggibili;
- win rate;
- average R;
- expectancy;
- massimo drawdown in R;
- numero hard veto rispettati;
- numero hard veto violati;
- numero trade fuori sistema;
- numero trade non presi ma validi;
- numero trade presi ma non validi;
- qualità media score;
- qualità media risk decision;
- errori tecnici;
- errori psicologici;
- errori di processo.

## Criteri minimi per passare oltre

Prima di valutare qualunque uso reale, devono essere soddisfatti almeno questi criteri:

- almeno 50 trade simulati;
- almeno 8 settimane operative;
- journal completo;
- nessun trade fuori sistema nelle ultime 3 settimane;
- hard veto rispettati al 100%;
- expectancy positiva;
- drawdown controllato;
- errori ricorrenti identificati;
- modifiche al sistema documentate;
- nessun problema grave su entry, Stop Loss, TP o risk sizing.

## Stop del paper trading

Il paper trading deve essere sospeso e il sistema rivisto se:

- vengono presi trade fuori sistema;
- hard veto vengono ignorati;
- il journal non viene compilato;
- lo score viene forzato;
- entry, Stop Loss o TP sono spesso ambigui;
- la decisione rischio viene ignorata;
- il sistema produce troppi falsi trade validi;
- l’utente modifica manualmente la tesi dopo l’ingresso.

## Review settimanale

Ogni settimana produrre:

[WEEKLY PAPER REVIEW]

Settimana:
Numero analisi:
Trade validi:
Trade simulati:
Trade non validi:
Setup da monitorare:
Asset non leggibili:
Win rate:
Average R:
Expectancy:
Max drawdown R:
Hard veto rispettati:
Trade fuori sistema:
Errore principale:
Correzione processo:
Modifica sistema richiesta:
Decisione settimana successiva:

## Regola finale

Il paper trading non è una formalità.
È il filtro che decide se il sistema è realmente utilizzabile.

Se il paper trading non dimostra disciplina, ripetibilità e controllo del rischio, il sistema non deve passare al trading reale.
