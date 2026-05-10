# 0 - Preflight Input Check

## Scopo

Verificare che gli input forniti siano utilizzabili prima di avviare l’analisi swing/multiday.

Questo blocco non interpreta il mercato.  
Non dà bias.  
Non genera segnali.  
Serve solo a controllare qualità, coerenza e completezza degli input.

## Input attesi

- Screenshot HTF D1/H4
- Screenshot LTF H4/H1
- Eventuale indicazione di trade già aperto

## Mappa input intraday → swing

- H1 nudo intraday diventa screenshot HTF D1/H4
- M5 nudo intraday diventa screenshot LTF H4/H1
- M5 con VWAP/VP diventa H4/H1 con indicatori necessari visibili

La presenza dei due screenshot non basta.
Devono essere leggibili, con zoom adeguato e indicatori necessari presenti.

## Validità dello screenshot

La presenza dello screenshot non è sufficiente.

Uno screenshot è valido solo se contiene il timeframe richiesto, prezzo e scala leggibili, numero di barre sufficiente, struttura leggibile e gli indicatori necessari al blocco che deve alimentare.

L’utente non è tenuto a fornire zone, livelli, supply/demand o invalidazioni già tracciate: questi elementi devono essere ricavati dal sistema attraverso l’analisi.

Se il timeframe è corretto ma mancano indicatori indispensabili, oppure lo zoom non consente di leggere struttura/reazione, il materiale va classificato come parziale o insufficiente.

Il sistema non deve procedere alla decisione finale se mancano dati o indicatori indispensabili per validare struttura, timing o trigger.

## Controllo zoom e leggibilità

Classifica ogni screenshot come:

- leggibile
- troppo zoomato
- troppo wide
- non leggibile

Se troppo zoomato o troppo wide, chiedere integrazione mirata.

## Indicatori

Indicatori/elementi che possono essere necessari, a seconda del blocco:

HTF D1/H4:

- Volume Profile, se necessario alla lettura di valore;
- POC, VAH, VAL, HVN, LVN se il Volume Profile è usato;
- AVWAP se rilevante per la lettura strutturale;
- volume bars se necessari alla lettura.

LTF H4/H1:

- VWAP se usata per timing/trigger;
- Volume Profile locale se usato come conferma;
- dominance buyers/sellers se usata come conferma;
- delta/volume se presenti e rilevanti;
- volume bars se necessari alla lettura.

Se un indicatore necessario alla decisione non è visibile, il sistema deve chiedere integrazione.

## Indicator setup sanity check

Prima di usare VWAP, AVWAP o Volume Profile nella narrativa o nella decisione, il sistema deve verificare se il loro settaggio è sensato.

Regole:

- indicatore visibile non significa indicatore utilizzabile;
- se il tipo di VWAP non è chiaro, non usarlo come conferma decisiva;
- se l’ancoraggio dell’AVWAP non è visibile o dichiarato, usarla solo come riferimento debole;
- se il Volume Profile non copre il movimento o la balance rilevante, usarlo con cautela o non usarlo;
- se POC, VAH, VAL, HVN, LVN non sono leggibili, il Volume Profile non deve essere decisivo;
- se lo screenshot è troppo stretto e distorce il profilo, il VP non deve guidare la decisione;
- price action e struttura hanno priorità sugli indicatori non verificabili.

## Controlli da eseguire

- Asset dichiarato chiaramente
- Timeframe leggibili
- Prezzo e scala leggibili
- Numero di barre sufficiente
- Struttura leggibile
- Zoom adeguato
- Indicatori visibili dove richiesti
- Nessun mismatch evidente tra descrizione e immagine
- Presenza o assenza di dati critici

## Output base

[PRE-FLIGHT CHECK]

Asset:
Screenshot HTF D1/H4:
Screenshot LTF H4/H1:
Timeframe leggibili:
Prezzo/scala leggibili:
Numero barre sufficiente:
Zoom:
Indicatori HTF visibili:
Indicatori LTF visibili:
Indicatori indispensabili mancanti:
Indicatori opzionali mancanti:
Materiale sufficiente: sì / no / parziale
Integrazione richiesta:
Procedere con analisi: sì / no / solo parziale
Indicator setup check:
VWAP visibile:
Tipo VWAP:
VWAP utilizzabile:
AVWAP visibile:
Anchor AVWAP visibile/dichiarato:
Anchor AVWAP sensato:
AVWAP utilizzabile:
Volume Profile visibile:
Range/ancoraggio VP sensato:
POC/VAH/VAL leggibili:
VP utilizzabile:
Indicatori utilizzabili per narrativa:
Indicatori solo di supporto:
Indicatori non utilizzabili:
Impatto sulla decisione:

Valori ammessi:

- utilizzabile
- utilizzabile con cautela
- non verificabile
- non utilizzabile
- non visibile
