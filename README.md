# intradaily-like-driven-swing-engine

Motore documentale per **trading swing/multiday** ispirato alla logica di automazione della repo intraday, ma adattato a operatività su orizzonti temporali più estesi.

## Obiettivo

Questo repository definisce prompt e regole operative per:
- analisi multi-timeframe (HTF/LTF);
- identificazione di zone di **supply** e **demand**;
- affinamento dell’entry su timeframe inferiori;
- gestione del rischio e della posizione in ottica multiday.

## Architettura operativa

Il flusso è organizzato in 4 documenti principali:

1. **0-Prompt Contexto.md**  
   Imposta il contesto strategico swing: strumenti, sessioni rilevanti, timeframe di riferimento e vincoli.
2. **1-Prompt HTF.md**  
   Analisi direzionale su timeframe alti (W1/D1): trend, struttura, aree istituzionali, bias operativo.
3. **2-Prompt LTF.md**  
   Affinamento dell’esecuzione su H4/H1: trigger, conferme volumetriche, VWAP/Volume Profile, setup long/short.
4. **3-Gestione.md**  
   Gestione posizione multiday: sizing, rischio percentuale, trailing, scaling e logging.

## Logica multi-timeframe HTF/LTF

- **HTF (W1/D1)**: definisce contesto, struttura e zone primarie di supply/demand.
- **LTF (H4/H1)**: cerca timing e conferme per ingressi con R:R coerente.
- L’operazione viene validata solo quando il segnale LTF è allineato al bias HTF, salvo setup di mean-reversion esplicitamente previsti.

## Zone di supply e demand

Le zone vengono classificate per qualità (fresh/tested, ampiezza, reazione, volume) e usate come:
- aree di interesse per pullback in trend;
- livelli di invalidazione (stop logico);
- target parziali/totali in combinazione con livelli strutturali e profilo volumetrico.

## Asset allegabili

Sono previste cartelle di supporto per screenshot e immagini annotate dei grafici, utili per audit e miglioramento continuo del processo decisionale.
