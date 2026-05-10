# 3 - Prompt Trigger

## Scopo

Decidere se il trade è realmente attivabile oppure no.

Il trigger è separato dal timing.  
Il timing dice se il prezzo sta reagendo bene.  
Il trigger dice se si può entrare.

## Condizioni minime

Un trade può essere valido solo se:

- struttura HTF coerente
- prezzo in zona sensata
- LTF conferma
- trigger tecnico presente
- stop tecnico chiaro
- rapporto rischio/rendimento accettabile
- nessun hard veto attivo

Il trigger non può essere validato se mancano elementi indispensabili alla decisione, come:

- struttura locale leggibile;
- stop tecnico ricavabile;
- rapporto rischio/rendimento stimabile;
- VWAP se usata come conferma necessaria;
- Volume Profile se usato come conferma necessaria;
- dominance buyers/sellers se usata come conferma necessaria.

## Hard veto

Bloccare il trade se:

- prezzo nel mezzo del range
- prezzo lontano dalla zona HTF
- struttura HTF non chiara
- LTF non conferma
- trigger assente
- stop tecnico troppo largo
- R:R insufficiente
- VWAP contrario
- Volume Profile contrario
- dominance buyers/sellers opposta
- setup forzato
- screenshot insufficienti

## Output base

[ASSET: ... | TRIGGER]

Trigger presente:
Direzione:
Entry:
Stop:
Target:
R:R:
Conferme:
Hard veto:
Trade valido:
Azione:
Sintesi operativa:

Valori ammessi per Trade valido:

- TRADE VALIDO
- TRADE NON VALIDO
- DA MONITORARE
