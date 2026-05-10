# 3 - Prompt Trigger

## Scopo

Decidere se il trade è realmente attivabile oppure no.

Il trigger deve rispondere alla domanda:
“Posso entrare davvero oppure no?”

Il trigger è separato dal timing.
Il timing dice se il prezzo sta reagendo bene.
Il trigger dice se si può entrare.

## Condizioni minime

Un trade è valido solo se:

- HTF è leggibile e coerente
- LTF conferma
- prezzo è in zona sensata
- trigger tecnico è presente
- stop tecnico è ricavabile
- R:R è almeno accettabile
- nessun hard veto è attivo
- gli indicatori necessari alla decisione sono visibili

Il trigger non può essere validato se mancano elementi indispensabili alla decisione.

## Hard veto

Bloccare il trade se:

- prezzo nel mezzo del range
- prezzo lontano dalla zona HTF
- struttura HTF non chiara
- LTF non conferma
- trigger assente
- stop tecnico troppo largo
- R:R insufficiente
- VWAP contraria se necessaria
- Volume Profile contrario se necessario
- dominance buyers/sellers opposta se necessaria
- screenshot insufficienti
- setup forzato

## Decisione trigger

Valori ammessi:

- TRADE VALIDO
- TRADE NON VALIDO
- DA MONITORARE

## Output trigger

[ASSET: ... | TRIGGER]

Trigger presente:
Direzione:
Entry:
Stop:
Target:
R:R:
Conferme:
Hard veto:
Decisione trigger:
Azione:
Sintesi operativa:
