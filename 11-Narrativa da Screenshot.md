# 11 - Narrativa da Screenshot

## Scopo

Ricostruire la storia visibile del prezzo partendo dagli screenshot forniti.

Questo modulo serve a capire dove si trova il prezzo dentro la sequenza visibile:

- impulso;
- pullback;
- breakout;
- accettazione;
- retest;
- fallimento;
- estensione;
- entry già passata;
- setup ancora in formazione.

La narrativa da screenshot non sostituisce HTF, LTF, Trigger, Risk o Scoring.
Serve a dare continuità logica all’analisi usando solo i dati visibili nel grafico.

## Regola fondamentale

Il sistema deve leggere lo screenshot da sinistra verso destra.

Deve chiedersi:

1. da dove arriva il prezzo;
2. quale struttura ha costruito;
3. quali aree ha rotto;
4. quali aree ha ritestato;
5. dove si trova ora rispetto alla storia visibile;
6. se l’entry è ancora davanti al prezzo oppure è già passata.

## Limite

Il sistema non deve inventare storia non visibile.

Se lo screenshot è troppo zoomato o non mostra abbastanza barre per ricostruire la narrativa, il sistema deve dichiarare:

Narrativa non ricostruibile con sufficiente affidabilità.

In quel caso deve chiedere uno screenshot più largo.

## Relazione con Preflight

Il Preflight controlla se lo screenshot è leggibile.

La Narrativa da Screenshot controlla se la sequenza visibile è sufficiente per capire il percorso del prezzo.

Uno screenshot può essere leggibile ma non sufficiente per ricostruire la narrativa.

## Relazione con Indicator Setup Sanity Check

Prima di usare VWAP, AVWAP o Volume Profile nella narrativa, il sistema deve verificarne il settaggio.

Un indicatore visibile non è automaticamente utilizzabile.

La narrativa deve partire dalla price action.
VWAP, AVWAP e Volume Profile possono confermare o indebolire la narrativa, ma non devono sostituire la struttura prezzo.

Se AVWAP o Volume Profile sono visibili ma non verificabili, devono essere usati solo come supporto debole oppure ignorati.

## Relazione con HTF

HTF definisce struttura, bias, zone e invalidazione.

La narrativa aiuta a capire se il prezzo:

- sta arrivando in una zona HTF;
- ha già reagito alla zona;
- ha già rotto la zona;
- sta ritestando la zona;
- è già esteso oltre la zona.

## Relazione con LTF

LTF legge la reazione locale.

La narrativa aiuta a capire se la reazione locale è:

- appena iniziata;
- già avanzata;
- in retest;
- in fallimento;
- in estensione;
- già tardiva.

## Relazione con Trigger

Il Trigger decide se il trade è attivabile.

La narrativa deve aiutare il Trigger a distinguere:

- prezzo sopra livello;
- breakout avvenuto;
- accettazione sopra livello;
- retest dall’alto;
- retest tenuto;
- entry disponibile;
- entry già passata;
- setup fallito.

## Indicatori utilizzabili

La narrativa può usare:

- price action;
- swing high / swing low;
- livelli strutturali;
- supply/demand;
- Volume Profile;
- POC / VAH / VAL;
- VWAP;
- AVWAP;
- volumi;
- dominance buyers/sellers, se visibile.

Gli indicatori non devono essere inventati.
Se non sono visibili o non sono verificabili, il sistema deve dichiararlo.

## Output obbligatorio

[NARRATIVA RICOSTRUITA]

Movimento precedente:
Struttura costruita:
Area chiave più vecchia:
Impulso principale:
Pullback visibile:
Breakout visibile:
Accettazione visibile:
Retest visibile:
Fallimento visibile:
Prezzo attuale rispetto alla narrativa:
Setup già partito:
Entry ancora disponibile:
Entry già passata:
Stato operativo ricavato dal grafico:
Narrativa affidabile:
Indicatori usati nella narrativa:
Indicatori non verificabili:
Indicatori ignorati:
Narrativa basata principalmente su:
Affidabilità indicatori:
Integrazione richiesta:

## Stati operativi descrittivi ammessi

Usare stati descrittivi, non una macchina rigida:

- nessun setup visibile;
- setup in formazione;
- attesa breakout;
- breakout avvenuto;
- attesa accettazione;
- attesa retest;
- retest in corso;
- retest tenuto;
- retest fallito;
- entry potenziale ancora disponibile;
- entry già passata;
- setup tardivo;
- setup invalidato;
- trade da gestire.

## Regola anti-reinvenzione

Se lo screenshot mostra che un livello atteso è già stato rotto, il sistema non deve scrivere semplicemente “attendere breakout”.

Deve scrivere:

- breakout già avvenuto;
- manca accettazione;
- manca retest;
- entry già tardiva;
- oppure setup invalidato.

## Regola finale

La narrativa serve a impedire che il sistema ricominci ogni analisi da zero.

Il sistema deve usare ciò che è visibile nello screenshot per capire a che punto della storia si trova il prezzo.
