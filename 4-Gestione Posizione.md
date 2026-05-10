# 4 - Gestione Posizione

## Scopo

Gestire un trade swing/multiday già aperto.

Questo blocco si usa solo se esiste una posizione aperta.

## Cosa valutare

- Il trade è ancora coerente con la tesi iniziale?
- La struttura HTF resta valida?
- Il timing LTF si è deteriorato?
- Il prezzo conferma o nega il movimento atteso?
- La posizione va mantenuta, protetta, ridotta o chiusa?

## Stati possibili

- Vivo
- In conferma
- In deterioramento
- Invalidato

## Azioni possibili

- Mantieni
- Porta a break-even
- Alleggerisci
- Stringi stop
- Chiudi parziale
- Chiudi totale
- Nessuna azione

## Principio

Se il trade perde qualità, va segnalato anche se stop loss o take profit non sono stati toccati.

## Output base

[ASSET: ... | GESTIONE POSIZIONE]

Coerenza attuale:
Stato trade:
Deterioramento:
Azione consigliata:
Urgenza:
Stop attuale:
Nuovo stop:
Gestione profitto:
Uscita anticipata:
Condizione di uscita anticipata:
Sintesi operativa:
