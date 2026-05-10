# 4 - Gestione Posizione

## Scopo

Gestire un trade swing/multiday già aperto.

Questo blocco si usa solo se esiste un trade aperto.

## Input richiesti per gestione

- asset
- direzione trade: long / short
- entry
- stop attuale
- target o target parziali
- motivo originario del trade
- output precedente di HTF, LTF e Trigger se disponibile
- screenshot aggiornato H4/H1
- screenshot D1/H4 se la struttura superiore è cambiata o non è chiara

## Cosa valutare

- Il trade è ancora coerente con la tesi iniziale?
- La struttura HTF resta valida?
- Il timing LTF si è deteriorato?
- Il prezzo conferma o nega il movimento atteso?
- La posizione va mantenuta, protetta, ridotta o chiusa?

## Stati del trade

Valori ammessi:

- VIVO
- IN CONFERMA
- IN DETERIORAMENTO
- INVALIDATO

Definizioni:

- VIVO: la tesi resta valida, ma il trade non ha ancora confermato pienamente.
- IN CONFERMA: il prezzo si muove coerentemente con la tesi.
- IN DETERIORAMENTO: la tesi perde qualità anche senza stop colpito.
- INVALIDATO: la ragione tecnica del trade non esiste più.

## Deterioramento del trade

Il trade è in deterioramento se compare uno o più di questi segnali:

- perdita della zona HTF che sosteneva il setup
- fallimento della reazione LTF
- acceptance contraria alla direzione del trade
- rottura strutturale opposta
- perdita di dominance coerente
- Volume Profile sfavorevole se usato nella tesi
- VWAP sfavorevole se usata nella tesi
- mancata evoluzione dopo tempo ragionevole
- prezzo torna nel mezzo del range senza continuazione

## Azioni ammesse

- MANTIENI
- PORTA A BREAK-EVEN
- STRINGI STOP
- ALLEGGERISCI
- CHIUDI PARZIALE
- CHIUDI TOTALE
- NESSUNA AZIONE

## Regola anti-rumore

La gestione swing/multiday deve lavorare soprattutto su H4/D1.
Non deve essere iper-reattiva.
Non deve chiudere un trade valido solo per rumore locale.
Non deve fare micro-management.

Se il trade perde qualità, il sistema deve segnalarlo anche se stop loss o take profit non sono stati toccati.
Se il trade resta tecnicamente valido, il sistema deve evitare uscite premature.

## Modifica stop e rischio

- se durante la gestione lo Stop Loss viene modificato, il sistema deve rivalutare il rischio;
- se lo stop viene allargato, la modifica deve essere trattata come critica;
- lo stop non deve essere allargato per evitare una perdita;
- se lo stop viene stretto, il sistema deve verificare che non diventi troppo stretto rispetto al rumore;
- eventuali aggiunte di posizione richiedono nuova validazione del rischio.

## Output obbligatorio

[ASSET: ... | GESTIONE POSIZIONE]

Direzione trade:
Entry:
Stop attuale:
Target:
Tesi originaria:
Coerenza con HTF:
Coerenza con LTF:
Coerenza con Trigger:
Stato trade:
Deterioramento:
Motivo deterioramento:
Azione consigliata:
Nuovo stop:
Gestione profitto:
Uscita anticipata:
Condizione di uscita anticipata:
Urgenza:
Sintesi operativa:
