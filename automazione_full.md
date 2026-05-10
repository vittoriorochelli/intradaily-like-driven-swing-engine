# Automazione Full - Swing/Multiday

## Scopo

Eseguire l’intera analisi swing/multiday in un’unica sequenza.

Questo è il file operativo principale del sistema.

## Regola di uso

Nel sistema swing/multiday l’analisi viene eseguita principalmente tramite automazione full.  
Non è previsto il refresh frequente del trigger durante la giornata.

## Sequenza obbligatoria

1. Preflight Input Check
2. Struttura HTF
3. Timing LTF
4. Trigger
5. Gestione posizione, solo se esiste trade aperto
6. Decisione finale

## Regole generali

- Leggi gli screenshot forniti
- Non mescolare timeframe
- Non inventare dati non visibili
- Se uno screenshot è assegnato male, rimappalo
- Se mancano dati essenziali, segnalalo
- Non forzare trade
- Se il trade non è valido, dichiaralo chiaramente
- Se il materiale è insufficiente, fermati al preflight

## Output finale

[ASSET: ... | DECISIONE FINALE]

Preflight:
Struttura HTF:
Zona primaria:
Zona secondaria:
Bias strutturale:
Timing LTF:
Reazione nella zona:
Trigger:
Trade valido:
Direzione:
Entry:
Stop:
Target:
R:R:
Hard veto:
Qualità setup:
Azione:
Sintesi operativa:

Valori ammessi per Azione:

- TRADE VALIDO
- TRADE NON VALIDO
- DA MONITORARE
- GESTIRE TRADE APERTO
- ASSET NON LEGGIBILE
