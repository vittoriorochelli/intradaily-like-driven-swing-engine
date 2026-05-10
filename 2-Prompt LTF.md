# 2 - Prompt LTF

LTF significa Lower Time Frame, cioè timeframe inferiore.

## Scopo

Leggere la reazione del prezzo dentro o a contatto con la zona HTF selezionata.

Il blocco LTF lavora principalmente sullo screenshot H4/H1.

Il blocco LTF non cerca nuove zone principali.
Deve leggere solo la reazione del prezzo dentro o a contatto con la zona HTF ricavata dal blocco HTF.

Se mancano VWAP, Volume Profile locale o dominance buyers/sellers quando sono necessari alla validazione, deve chiedere integrazione.
Se lo zoom non consente di leggere la reazione, deve chiedere screenshot più adatto.

## Timeframe

- H4: reazione ampia
- H1: timing principale

## Derivazione intraday → LTF swing

Il blocco LTF swing eredita la funzione del M5 intraday, ma lavora su H4/H1.

Deve concentrarsi su:

- prezzo dentro/fuori zona HTF
- reazione nella zona HTF
- rejection
- absorption
- acceptance
- false break
- retest
- shift strutturale
- micro-BOS
- micro-CHOCH
- VWAP se visibile e necessaria
- Volume Profile locale se visibile e necessario
- dominance buyers/sellers se visibile e necessaria
- stop tecnico potenziale
- invalidazione locale

## Classificazione reazione

Valori ammessi:

- rejection
- absorption
- acceptance
- false break
- retest
- shift strutturale
- nessuna reazione chiara

## Cosa valutare

- Prezzo dentro/fuori dalla zona HTF
- Reazione nella zona
- Classificazione reazione
- Lettura locale
- Struttura locale
- Micro-BOS
- Micro-CHOCH
- VWAP se visibile e necessaria
- Volume Profile locale se visibile e necessario
- dominance buyers/sellers se visibile e necessaria
- Setup e condizione di attivazione
- Stop tecnico potenziale
- Invalidazione locale
- Qualità timing

## Non fare

- Non generare trade definitivo
- Non fare gestione posizione
- Non inventare conferme non visibili
- Non commentare aree lontane dalla zona HTF

## Relazione con Scenario Evidence

LTF deve leggere la reazione del prezzo rispetto a:

1. zona HTF selezionata;
2. scenario principale selezionato da `12-Scenario Evidence e Candidate Discovery.md`.

LTF non deve creare nuovi scenari.
LTF deve verificare se la reazione locale conferma, indebolisce o invalida lo scenario principale.

Regole:

- Se scenario = CONTINUATION, LTF deve cercare reazione coerente con continuation: retest, acceptance, reclaim, pullback ordinato, ripartenza non tardiva.
- Se scenario = REVERSAL_CANDIDATE, LTF deve cercare failed auction, sweep/reclaim, rejection, CHOCH, perdita di accettazione della vecchia direzione.
- Se scenario = BALANCE_ROTATION, LTF deve cercare rifiuto dell’estremo di balance/value e ritorno verso POC o area centrale.
- Se scenario = NO_EDGE, LTF non deve forzare nessun setup.
- Se Stato operativo scenario = WAIT_FOR_RETEST, LTF deve verificare se il retest è avvenuto, in corso, mancato o fallito.
- Se Stato temporale scenario = TARDIVO, LTF non può promuovere il setup senza nuovo trigger/retest.

## Output LTF obbligatorio

[ASSET: ... | TIMING LTF]

Prezzo nella zona HTF:
Reazione nella zona:
Classificazione reazione:
Lettura locale:
Struttura locale:
Micro-BOS/CHOCH:
VWAP:
Volume Profile locale:
Dominance buyers/sellers:
Setup:
Operatività:
Condizione di attivazione:
Stop tecnico potenziale:
Invalidazione locale:
Qualità timing:
Scenario principale ricevuto:
Stato temporale scenario:
Stato operativo scenario:
Reazione coerente con scenario:
Retest richiesto:
Retest visibile:
Scenario confermato da LTF:
Scenario indebolito da LTF:
Scenario invalidato da LTF:
Sintesi operativa:
