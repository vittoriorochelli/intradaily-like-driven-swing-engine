# 3 - Gestione Posizione (Swing/Multiday)

## Obiettivo

Gestire il ciclo completo dell’operazione multiday con disciplina su rischio, dimensionamento, protezione dei profitti e tracciamento decisionale.

## Regole di rischio

- Rischio per trade: definito in percentuale fissa del capitale (es. 0.5%–1.0%).
- Esposizione simultanea: limite massimo aggregato per asset correlati.
- Nessun aumento della size in perdita (no martingala).

## Dimensionamento posizione

1. Definisci distanza stop in punti/percentuale.
2. Calcola size in funzione del rischio monetario prefissato.
3. Riduci size in scenari ad alta volatilità/event risk.

## Gestione attiva

- **TP parziali**: realizza parzialmente su livelli strutturali intermedi.
- **Break-even**: sposta stop a pareggio dopo conferma del primo impulso favorevole.
- **Trailing stop**: aggiorna lo stop sotto/sopra swing significativi su H4.
- **Time stop**: chiudi o riduci esposizione se il trade non evolve entro la finestra prevista.

## Uscita e revisione

- Chiusura totale su target finale o invalidazione.
- Documenta: contesto HTF, trigger LTF, execution, esito, deviazioni dal piano.
- Registra screenshot pre/durante/post trade per audit qualitativo.

## Template log operativo

- Data:
- Strumento:
- Bias HTF:
- Setup LTF:
- Entry/Stop/TP:
- Rischio % e size:
- Gestione in corso d’opera:
- Esito:
- Lesson learned:
