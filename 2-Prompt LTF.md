# 2 - Prompt LTF (H4/H1)

## Obiettivo

Raffinare il timing di ingresso in coerenza col bias HTF usando segnali su H4/H1, conferme volumetriche e comportamento del prezzo in prossimità delle zone.

## Procedura LTF

1. **Allineamento con HTF**
   - Considera prioritari solo i setup coerenti con bias W1/D1.
   - In caso di contro-trend, richiedi conferme multiple e size ridotta.

2. **Trigger di prezzo**
   - Rejection netta su zona supply/demand.
   - Micro-BOS/CHOCH su H1/H4.
   - Pattern di continuazione o inversione con invalidazione chiara.

3. **VWAP e Volume Profile**
   - Usa VWAP come riferimento dinamico di fair value intraday esteso.
   - Usa Volume Profile per localizzare POC, HVN, LVN e possibili magnet/repulsion levels.
   - Preferisci ingressi dove prezzo + struttura + volume convergono.

4. **Generazione segnale**
   - Tipo: `BUY` / `SELL` / `NO TRADE`
   - Entry: prezzo o zona
   - Stop: tecnico (oltre swing/oltre zona)
   - Target: TP1/TP2/TP3 con logica strutturale/volumetrica
   - R:R atteso minimo 1:2

## Formato output LTF

- Setup:
- Allineamento HTF:
- Entry zone:
- Stop loss:
- Take profit (TP1/TP2/TP3):
- Conferme VWAP/VP:
- Motivazione operativa:
