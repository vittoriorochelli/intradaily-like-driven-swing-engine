# 10 - Test Protocol

## Scopo

Definire come collaudare il sistema swing/multiday prima di usarlo in osservazione reale o paper trading.

Il test protocol non serve a dimostrare che il sistema è giusto.
Serve a trovare errori, ambiguità, campi mancanti, output inutili, forzature operative e punti in cui l’agente potrebbe inventare dati.

## Regola fondamentale

Prima di usare il sistema in PT-0 o paper trading, devono essere eseguiti test controllati con screenshot reali.

Il sistema deve essere testato per verificare se:

- produce una decisione operativa chiara;
- non forza trade;
- applica hard veto;
- calcola score coerenti;
- produce Entry, Stop Loss, TP e R:R solo quando sono leggibili;
- rispetta la logica di rischio monetario fisso;
- chiede integrazione quando mancano dati;
- genera journal auto-entry;
- segue AGENTS.md;
- segue 9-Output Schema.md.

## Test minimi obbligatori

### Test 1 — Asset leggibile ma senza trade

Obiettivo:
verificare che il sistema sappia dire TRADE NON VALIDO o DA MONITORARE senza forzare l’operazione.

Input richiesti:
- screenshot D1/H4;
- screenshot H4/H1;
- nessun trade aperto.

Output atteso:
- [DECISIONE OPERATIVA];
- score finale;
- hard veto se presenti;
- motivo principale;
- nessuna entry forzata;
- journal auto-entry.

Criterio di successo:
il sistema non deve inventare un trade solo perché il grafico è leggibile.

### Test 2 — Asset con setup potenzialmente valido

Obiettivo:
verificare se il sistema riesce a produrre un setup completo solo quando le condizioni sono davvero presenti.

Input richiesti:
- screenshot D1/H4 leggibile;
- screenshot H4/H1 leggibile;
- indicatori necessari visibili;
- nessun trade aperto.

Output atteso:
- direzione;
- entry;
- Stop Loss tecnico;
- TP1;
- TP2;
- R:R;
- score finale;
- decisione rischio;
- journal auto-entry.

Criterio di successo:
TRADE VALIDO solo se score, rischio, target e assenza di hard veto lo permettono.

### Test 3 — Screenshot incompleto o indicatori mancanti

Obiettivo:
verificare che il sistema non inventi dati quando il materiale è insufficiente.

Input richiesti:
- screenshot troppo zoomato oppure troppo largo;
- oppure indicatori necessari mancanti;
- oppure timeframe/prezzo non leggibili.

Output atteso:
- ASSET NON LEGGIBILE oppure DA MONITORARE;
- integrazione richiesta;
- nessuna entry;
- nessuno Stop Loss inventato;
- journal auto-entry con dati mancanti.

Criterio di successo:
il sistema deve chiedere una sola integrazione mirata e non procedere come se avesse dati sufficienti.

### Test 4 — Trade aperto da gestire

Obiettivo:
verificare che il sistema non cerchi nuovi setup quando esiste già un trade aperto.

Input richiesti:
- asset;
- direzione trade;
- entry;
- stop attuale;
- target;
- motivo originario del trade;
- screenshot H4/H1 aggiornato;
- screenshot D1/H4 se necessario.

Output atteso:
- GESTIRE TRADE APERTO;
- stato trade;
- deterioramento;
- azione consigliata;
- eventuale nuovo stop;
- rischio da rivalutare se stop/size/esposizione cambiano;
- journal auto-entry trade aperto.

Criterio di successo:
il sistema deve concentrarsi sulla qualità residua del trade, non cercare un nuovo setup.

### Test 5 — Multi-asset con almeno 3 asset

Obiettivo:
verificare il ranking operativo multi-asset.

Input richiesti:
- almeno 3 asset;
- per ogni asset, screenshot D1/H4 e H4/H1;
- eventuali trade aperti dichiarati.

Output atteso:
- decisione operativa per ogni asset;
- score per ogni asset;
- hard veto per ogni asset;
- decisione rischio per ogni asset;
- ranking multi-asset;
- esclusione degli asset non validi;
- segnalazione correlazione;
- journal auto-entry per ogni asset.

Criterio di successo:
il sistema deve scegliere NESSUN TRADE se nessun asset è valido. Non deve scegliere il meno brutto.

### Test 6 — Dati rischio mancanti

Obiettivo:
verificare che il sistema non inventi size, pip value, tick value, lotto minimo o margine.

Input richiesti:
- setup tecnicamente leggibile;
- Entry e Stop Loss presenti;
- dati broker mancanti o incompleti.

Output atteso:
- DATI RISCHIO MANCANTI;
- dati mancanti esplicitati;
- nessuna size inventata;
- decisione DA MONITORARE o TRADE NON VALIDO;
- journal auto-entry.

Criterio di successo:
il sistema deve rispettare la regola: non inventare dati broker.

## Criteri generali di successo

Un test è superato solo se:

- la risposta inizia con [DECISIONE OPERATIVA];
- il sistema segue la sequenza corretta;
- non inventa dati;
- esegue Preflight;
- esegue Indicator Setup Sanity Check;
- esegue Narrativa da Screenshot;
- esegue Scenario Evidence e Candidate Discovery;
- produce Scenario Evidence Pack;
- non classifica scenari senza evidenze;
- distingue tra continuation, reversal candidate, balance rotation e no edge;
- classifica correttamente scenario tardivo, futuro condizionale, attivo o scartato;
- distingue TRADE_NOW nello scenario da TRADE VALIDO finale;
- non salta Risk e Position Sizing;
- applica hard veto;
- restituisce score finale;
- produce journal auto-entry;
- chiede una sola integrazione mirata se manca un dato indispensabile;
- usa `mancante`, `non applicabile` o `da aggiornare` per i dati non disponibili.

## Criteri di fallimento

Un test fallisce se il sistema:

- inventa livelli;
- inventa indicatori;
- produce trade valido con hard veto attivo;
- produce trade valido senza Stop Loss tecnico;
- produce trade valido senza TP2 realistico almeno 1:2;
- produce trade valido con rischio non ok;
- non genera journal auto-entry;
- non inizia con [DECISIONE OPERATIVA];
- cerca un nuovo setup quando esiste un trade aperto;
- sceglie il meno brutto in multi-asset;
- suggerisce trading reale;
- ignora dati mancanti.
- usa VWAP, AVWAP o Volume Profile senza verificarne il settaggio;
- usa un AVWAP come conferma decisiva senza anchor visibile o dichiarato;
- usa un Volume Profile come conferma decisiva senza range coerente o leggibile;
- ricomincia la narrativa da zero ignorando la sequenza visibile nello screenshot;
- scrive “attendere breakout” quando il breakout è già visibile;
- non distingue tra breakout avvenuto, accettazione, retest, entry tardiva o setup invalidato.
- classifica CONTINUATION solo perché il trend è forte;
- classifica REVERSAL_CANDIDATE solo perché il prezzo è alto o basso;
- classifica BALANCE_ROTATION senza balance/value area leggibile;
- sceglie come principale uno scenario storicamente forte ma non più attivabile;
- non dichiara dati scenario mancanti;
- interpreta TRADE_NOW come TRADE VALIDO finale;
- promuove scenario TARDIVO senza nuovo trigger/retest.

## Registro problemi di test

Ogni test deve produrre un registro problemi:

[TEST ISSUE LOG]

Test:
Asset:
Problema trovato:
File coinvolto:
Tipo problema:
Gravità:
Impatto operativo:
Correzione proposta:
Priorità:
Stato:

Valori ammessi per Gravità:

- BLOCCANTE
- ALTA
- MEDIA
- BASSA

## Tipi di problema

Classificare ogni problema come:

- errore Preflight;
- errore HTF;
- errore LTF;
- errore Trigger;
- errore Risk;
- errore Gestione;
- errore Journal;
- errore Multi-asset;
- errore Output Schema;
- errore Agentico;
- ambiguità di prompt;
- output troppo lungo;
- output troppo narrativo;
- dato mancante non gestito;
- hard veto ignorato;
- errore Indicator Setup;
- errore Narrativa;
- uso improprio VWAP/AVWAP/VP;
- narrativa non ricostruita;
- narrativa incoerente con screenshot;
- errore Scenario Evidence;
- scenario non supportato da dati;
- scenario tardivo promosso a trade;
- candidate principale scelto male;
- evidence pack insufficiente;
- TRADE_NOW frainteso;
- hard veto scenario ignorato.

## Patch dopo test

Dopo ogni ciclo di test:

1. raccogliere i problemi;
2. classificarli per gravità;
3. correggere prima i problemi BLOCCANTI;
4. non aggiungere nuove funzioni se ci sono errori bloccanti;
5. rieseguire il test fallito;
6. procedere solo quando i test minimi sono superati.

## Uscita dal collaudo

Il sistema può passare a PT-0 solo se:

- tutti i test minimi sono stati eseguiti;
- nessun problema BLOCCANTE resta aperto;
- nessun hard veto viene ignorato;
- il journal viene sempre generato;
- il sistema non forza trade;
- il sistema chiede integrazioni quando il materiale è insufficiente;
- l’output operativo è chiaro e utilizzabile.

## Regola finale

Il test serve a rompere il sistema, non a confermarlo.

Se durante i test emergono problemi, il sistema va corretto prima di qualsiasi paper trading.
