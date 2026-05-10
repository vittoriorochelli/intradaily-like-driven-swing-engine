# 7 - Multi Asset Ranking

## Scopo

Confrontare più asset analizzati con lo stesso sistema swing/multiday e produrre una priorità operativa.

Il modulo non deve creare nuovi setup.
Deve confrontare gli output già prodotti da:

- Preflight
- HTF
- LTF
- Trigger
- Scoring finale
- Risk e Position Sizing
- Journal auto-entry

## Principio

Il ranking non serve a scegliere per forza un trade.

Serve a decidere:

- quale asset ha il setup migliore;
- quale asset va monitorato;
- quale asset va escluso;
- quale asset non è leggibile;
- se non c’è nessun trade valido.

Regola fondamentale:

Meglio zero trade che scegliere il meno brutto.

## Input richiesti

Per ogni asset:

- nome asset;
- screenshot HTF D1/H4;
- screenshot LTF H4/H1;
- eventuale trade aperto;
- output completo di `automazione_full.md`, se già disponibile.

## Classificazione per asset

Ogni asset deve essere classificato in uno dei seguenti stati:

- TRADE VALIDO
- TRADE NON VALIDO
- DA MONITORARE
- GESTIRE TRADE APERTO
- ASSET NON LEGGIBILE

## Criteri di ranking

Un asset può entrare nel ranking operativo solo se:

- non ha hard veto attivi;
- score finale >= 75;
- Decisione rischio = RISCHIO OK;
- entry, Stop Loss e TP2 sono definiti;
- R:R su TP2 >= 1:2;
- il target è realistico;
- il materiale è leggibile.

Gli asset con hard veto non possono essere promossi dal ranking.

## Criteri di priorità

Tra asset validi, dare priorità a:

1. assenza di hard veto;
2. score finale più alto;
3. maggiore chiarezza HTF;
4. migliore reazione LTF;
5. trigger più pulito;
6. R:R migliore solo se il target è realistico;
7. rischio più gestibile;
8. minore correlazione con altri trade o setup;
9. migliore qualità dei dati/screenshot.

## Correlazione e rischio aggregato

Il sistema deve segnalare se più asset esprimono lo stesso rischio direzionale.

Esempi:

- più indici azionari long nello stesso momento;
- USD long o short ripetuto su più coppie forex;
- oro e dollaro con letture conflittuali;
- asset fortemente correlati con setup simili.

Se due setup sono molto correlati, il sistema deve preferire il migliore e classificare gli altri come secondari o da monitorare.

## Hard veto multi-asset

Bloccare la scelta operativa se:

- tutti gli asset hanno hard veto;
- nessun asset raggiunge score minimo;
- i migliori asset sono troppo correlati;
- i dati rischio sono mancanti;
- gli screenshot sono insufficienti;
- il ranking sceglierebbe solo “il meno brutto”.

## Output multi-asset obbligatorio

[MULTI-ASSET DECISION]

Asset analizzati:
Asset validi:
Asset da monitorare:
Asset non validi:
Asset non leggibili:
Asset con trade aperto:
Miglior setup:
Secondo setup:
Motivo ranking:
Rischio correlazione:
Asset esclusi per hard veto:
Asset esclusi per rischio:
Decisione finale:
Azione immediata:
Prossimo passo:

Valori ammessi per Decisione finale:

- OPERARE MIGLIOR SETUP
- NESSUN TRADE
- MONITORARE
- RICHIEDERE INTEGRAZIONI
- GESTIRE TRADE APERTO

## Output ranking per asset

[ASSET RANKING ITEM]

Asset:
Decisione asset:
Score finale:
Hard veto attivi:
Decisione rischio:
R:R su TP2:
Qualità HTF:
Qualità LTF:
Qualità Trigger:
Correlazione:
Priorità:
Motivo:

## Regola finale

Il ranking deve proteggere l’utente dall’overtrading.

Il sistema deve scegliere il miglior setup solo se esiste davvero un setup valido.
Se nessun asset è valido, la decisione corretta è NESSUN TRADE.
