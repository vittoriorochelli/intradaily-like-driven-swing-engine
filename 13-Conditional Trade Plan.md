# 13 - Conditional Trade Plan

## Scopo

Costruire un piano operativo condizionale quando il trade immediato non è valido, ma lo scenario resta vivo.

Questo modulo non valida il trade.
Non produce esecuzione.
Non sostituisce Trigger, Risk, R:R o hard veto.

Serve a rispondere a questa domanda:

Se non devo entrare ora, cosa devo monitorare esattamente perché il setup possa diventare operativo?

## Regola fondamentale

TRADE NON VALIDO ora non significa sempre scenario morto.

Il sistema deve distinguere:

- trade eseguibile ora;
- scenario vivo ma non attivabile;
- piano condizionale da monitorare;
- setup tardivo;
- setup invalidato;
- no edge.

Un piano condizionale è ammesso solo se:

- esiste uno scenario principale valido o parziale;
- lo scenario non è invalidato;
- esiste un livello chiaro da monitorare;
- esiste un evento richiesto;
- esiste un trigger richiesto;
- esiste un’invalidazione chiara;
- esiste almeno un primo target tecnico;
- il trade non viene presentato come valido finché non viene rivalutato.

## Relazione con Scenario Evidence

Scenario Evidence classifica l’opportunità.

Conditional Trade Plan trasforma uno scenario vivo in istruzioni di monitoraggio.

Se Scenario Evidence produce:

- NO_EDGE;
- scenario scartato;
- evidence pack insufficiente;

allora il Conditional Trade Plan deve dichiarare:

Piano condizionale non disponibile.

## Relazione con Trigger

Il Trigger decide se il trade è attivabile ora.

Conditional Trade Plan lavora solo dopo il Trigger.

Se Trigger = TRADE VALIDO, il piano condizionale può essere non applicabile.

Se Trigger = TRADE NON VALIDO o DA MONITORARE, ma lo scenario è vivo, il sistema deve produrre un piano condizionale.

## Relazione con Risk

Il Conditional Trade Plan non può produrre RISCHIO OK.

Può solo produrre:

- rischio non applicabile;
- rischio preliminare da rivalutare;
- dati rischio mancanti;
- livelli preliminari da rivalutare.

Risk e Position Sizing resta il modulo che valida il rischio reale.

## Output obbligatorio

[CONDITIONAL TRADE PLAN]

Scenario vivo:
Motivo scenario vivo:
Trade ora:
Motivo trade ora:
Direzione condizionale:
Livello di attivazione:
Evento richiesto:
Trigger richiesto:
Entry condizionale preliminare:
Stop tecnico preliminare:
Motivo stop preliminare:
TP1 preliminare:
Motivo TP1:
TP2 preliminare:
Motivo TP2:
R:R preliminare:
R:R preliminare valido:
Invalidazione scenario:
Scadenza temporale del piano:
Alert da impostare:
Screenshot successivo richiesto:
Dati mancanti:
Decisione piano condizionale:

Valori ammessi per Scenario vivo:

- sì
- no
- parziale

Valori ammessi per Trade ora:

- valido
- non valido
- da monitorare

Valori ammessi per Decisione piano condizionale:

- PIANO CONDIZIONALE ATTIVO
- PIANO CONDIZIONALE NON DISPONIBILE
- PIANO CONDIZIONALE DA RIVALUTARE
- SETUP INVALIDATO


## Regola di produzione obbligatoria dei blocchi

Il sistema deve produrre sempre il blocco:

[CONDITIONAL TRADE PLAN]

dopo il Trigger.

Il sistema deve produrre anche:

[PRICE DISCOVERY / OPEN SPACE CHECK]

quando almeno una delle seguenti condizioni è vera:

- TP2 è mancante;
- TP2 è non verificabile;
- TP1 coincide con massimo/minimo precedente;
- il prezzo è vicino a massimi/minimi visibili;
- il prezzo rompe o minaccia di rompere massimi/minimi visibili;
- il sistema cita price discovery, open space, estensione, storico insufficiente o target superiore/inferiore non visibile;
- il sistema richiede screenshot W1/MN o D1 più ampio.

Il sistema deve produrre anche:

[PARTIAL TP / BREAK-EVEN PLAN]

quando almeno una delle seguenti condizioni è vera:

- esiste un TP1 tecnico;
- TP1 è vicino ma raggiungibile;
- TP2 è mancante o condizionale;
- il trade viene bloccato per R:R insufficiente;
- si cita gestione parziale;
- si cita break-even o BE;
- si valuta un runner verso TP2;
- il trade immediato è non valido ma lo scenario resta vivo.

Questi blocchi devono essere prodotti anche quando il risultato è:

- non applicabile;
- da rivalutare;
- condizionale;
- non verificabile.

Il sistema non deve saltare i blocchi solo perché il trade immediato è non valido.

## Regola TP2 di estensione

Il campo `TP2 di estensione ammesso` deve usare questi valori:

- sì: solo se price discovery/open space è verificata e il target deriva da una regola oggettiva;
- no: solo se il TP2 di estensione è realmente escluso da struttura contraria, supply/demand evidente, assenza di breakout o assenza di spazio operativo;
- condizionale: se il TP2 di estensione potrebbe essere valutato, ma servono screenshot più ampi, conferma di price discovery, nuovo breakout/retest o dati aggiuntivi;
- non applicabile: se il caso non riguarda open space, price discovery o estensione.

Regola:
non usare `no` solo perché il TP2 non è ancora verificato.
Se il problema è storico insufficiente, usare `condizionale` o `non verificabile`, non `no`.

## Regola Partial TP / BE

Il blocco Partial TP / BE deve distinguere:

- non applicabile ora;
- da rivalutare dopo trigger;
- condizionale;
- valido come gestione.

TP1 + BE non rende valido il trade.
TP1 + BE può solo qualificare un piano condizionale o una gestione futura.

## Price Discovery / Open Space Check

Quando il TP1 coincide con massimi/minimi precedenti o con una barriera strutturale visibile, il sistema non deve dichiarare automaticamente TP2 mancante.

Deve prima verificare se il prezzo è in open space o price discovery.

Price discovery significa che il prezzo si trova sopra i massimi storici o sotto i minimi storici rilevanti, oppure in un’area dove non sono visibili livelli storici superiori/inferiori nello screenshot fornito.

Il sistema deve distinguere:

- TP2 strutturale visibile;
- TP2 non visibile per storico insufficiente;
- price discovery confermata;
- price discovery non verificabile;
- open space condizionale.

Se lo screenshot non mostra abbastanza storico, il sistema deve chiedere una sola integrazione mirata:

- screenshot W1/MN;
- screenshot D1 più ampio;
- conferma utente che siamo sui massimi/minimi storici reali.

Il sistema non deve inventare target.

## Output Price Discovery / Open Space Check

[PRICE DISCOVERY / OPEN SPACE CHECK]

Prezzo vicino a massimi/minimi visibili:
Massimi/minimi superiori o inferiori visibili:
Storico sufficiente:
Price discovery confermata:
Price discovery non verificabile:
Open space condizionale:
Screenshot aggiuntivo richiesto:
TP1 strutturale:
TP2 strutturale:
TP2 di estensione ammesso:
Regola TP2 di estensione:
Qualità TP2:
Impatto su R:R:

Valori ammessi per TP2 di estensione ammesso:

- sì
- no
- condizionale
- non applicabile

Valori ammessi per Qualità TP2:

- alta
- media
- bassa
- non applicabile

## Regole per TP2 di estensione

Un TP2 di estensione è ammesso solo se derivato da una regola oggettiva.

Regole ammesse:

- estensione del range precedente;
- measured move, cioè proiezione della gamba precedente;
- ATR, cioè Average True Range, range medio reale del prezzo;
- round number coerente con volatilità e struttura;
- livello HTF superiore/inferiore visibile su screenshot più ampio.

Un TP2 di estensione non è ammesso se:

- viene scelto solo per far tornare il R:R;
- non esiste breakout/accettazione;
- non esiste trigger;
- lo storico è insufficiente e il sistema non ha chiesto integrazione;
- il target è puramente inventato.

Se il TP2 dipende da price discovery non verificata, il trade non può essere TRADE VALIDO.
Può al massimo essere PIANO CONDIZIONALE DA RIVALUTARE.

## Partial Take Profit / Break-Even Plan

Il sistema deve considerare la possibilità di:

- TP1 tecnico;
- chiusura parziale;
- spostamento Stop Loss a BE;
- runner verso TP2.

BE significa break-even, cioè punto di pareggio.

Questa gestione può migliorare la qualità del piano, ma non può aggirare la mancanza di un trade valido.

## Regole Partial TP / BE

- TP1 deve essere tecnico e visibile.
- TP1 non deve essere scelto solo per ridurre psicologicamente il rischio.
- Lo Stop Loss può essere portato a BE solo dopo raggiungimento di TP1 o dopo conferma strutturale forte.
- BE non deve essere usato per giustificare entry brutte.
- Runner verso TP2 è ammesso solo se esiste spazio operativo, target strutturale o price discovery verificabile/condizionale.
- Se TP2 resta non verificabile, il piano può essere condizionale ma non TRADE VALIDO pieno.

## Output Partial TP / BE

[PARTIAL TP / BREAK-EVEN PLAN]

TP1 tecnico:
TP1 raggiungibile:
R:R su TP1:
Gestione a TP1:
Percentuale parziale:
Stop a BE dopo TP1:
Condizione per spostare SL a BE:
Runner verso TP2:
TP2 strutturale:
TP2 di estensione:
Rischio residuo dopo BE:
Trade valido senza TP2 statico:
Motivo:

Valori ammessi per Gestione a TP1:

- chiusura parziale
- nessuna parziale
- da rivalutare

Valori ammessi per Percentuale parziale:

- 25%
- 33%
- 50%
- da definire

Valori ammessi per Stop a BE dopo TP1:

- sì
- no
- condizionale

## Regola anti-permissività

Il piano TP1 + BE non può trasformare automaticamente un trade non valido in trade valido.

Può trasformare un setup in:

- DA MONITORARE FORTE;
- PIANO CONDIZIONALE ATTIVO;
- PIANO CONDIZIONALE DA RIVALUTARE.

Per diventare TRADE VALIDO servono comunque:

- Entry tecnica;
- Stop Loss tecnico;
- TP1;
- TP2 strutturale o di estensione validato;
- R:R accettabile;
- Risk OK;
- nessun hard veto.

## Regola finale

Il Conditional Trade Plan deve proteggere da due errori opposti:

1. entrare male solo perché lo scenario è buono;
2. perdere un buon trade potenziale perché il sistema non ha definito cosa monitorare.
