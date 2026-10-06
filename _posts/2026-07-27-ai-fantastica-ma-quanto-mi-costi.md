---
layout: post
title: "Ai sei fantastica!!! Si ma quanto mi costi!?!? -36 giorni all'alba"
date: 2026-07-27 09:00:00 +0200
categories: [il-timone]
tags: [ai-costs, roi, unit-economics, llm, token, cto, agentic-ai]
image:
  path: /assets/img/ai-quanto-mi-costi.png
  alt: "Infografica sull'economia reale dei token: il paradosso del margine, i tre buchi neri di spesa e la cassetta degli attrezzi per contenere i costi"
---

Diciamocelo: stiamo vivendo dentro un film di fantascienza, e ci stiamo divertendo un mondo. Giusto l'altro giorno vi raccontavo delle evoluzioni quasi magiche dell'AI nel campo dell'audio — se vi siete persi come i computer abbiano imparato a sussurrarci paroline dolci meglio di un doppiatore professionista, andate a recuperare [il mio articolo sulla prosodia](/posts/anima-della-voce-prosodia-ai/).

E non finisce lì. Oggi apri un social e scopri che puoi lanciare cento, sì, **cento sub-agenti** contemporaneamente. Praticamente un intero call center di entità digitali che collaborano tra loro, orchestrate da un harness di agenti superiori con una disciplina che manco un generale prussiano durante le guerre napoleoniche. Nel frattempo, da qualche altra parte nel cloud, un modello dimostra teoremi matematici mentre noi umani facciamo ancora fatica a calcolare a mente il resto della spesa al supermercato.

Tutto bellissimo. L'entusiasmo è alle stelle, i post su LinkedIn si sprecano, siamo tutti pronti a sbarcare sulla Luna della produttività infinita.

Poi arriva la fine del mese. E con lei, il postino.

## Il risveglio ha la forma di una fattura

Il risveglio dal sogno tecnologico ha la forma di una fattura AWS, OpenAI o Anthropic. Perché tutta questa meraviglia ha un piccolissimo, trascurabile effetto collaterale: consuma elettricità, potenza di calcolo e, di conseguenza, un quantitativo imbarazzante di soldi.

Se sei un singolo appassionato che gioca con le API per stupire gli amici al bar, il problema non sussiste: trenta euro al mese sono il prezzo di un hobby, e ne vale la pena. Ma se sei un'azienda che deve mettere un prodotto sul mercato, la musica cambia parecchio. A quel punto sorge una domanda tanto banale quanto drammatica: **esiste un ROI?** O stiamo solo collezionando badge di nerdaggine aziendale mentre il conto corrente sanguina?

## Il paradosso: il software scalava, l'AI no

Nel software tradizionale eravamo abituati a un paradiso economico. Scrivi il codice una volta, lo distribuisci a un milione di utenti, e il costo marginale del milionesimo utente è sostanzialmente zero: un po' di banda, un po' di database, e via. È per questo che le SaaS hanno margini lordi dell'80% e passa, ed è per questo che gli investitori le amano. Il costo sta tutto davanti — lo sviluppo — e poi la curva dei ricavi sale mentre quella dei costi resta piatta.

Con l'AI generativa siamo davanti a un paradosso quasi genetico: **il costo marginale torna a essere reale**. Ogni singola interazione dell'utente accende una GPU da qualche parte nel mondo. Più clienti usano la tua splendida, intelligentissima funzionalità, più la tua bolletta lievita. Il costo del venduto — quello che in bilancio chiamiamo COGS — non è più trascurabile: è la voce che decide se hai un'azienda o un hobby costoso.

Tradotto: la crescita degli utenti, che nel software classico era la cosa che ti salvava, adesso può essere esattamente la cosa che ti affossa. Se ogni interazione costa più di quanto quell'interazione ti rende, scalare significa perdere soldi più in fretta. Ti ritrovi in mano un prodotto tecnologicamente superbo e commercialmente fallimentare — che è il modo elegante per dire che hai costruito una Ferrari che consuma un litro ogni cento metri.

E qui si chiude un cerchio che avevo aperto qualche settimana fa. In [Il preventivo non si fa più a ore](/posts/il-preventivo-non-si-fa-piu-a-ore/) raccontavo come l'ora/uomo stia morendo come metrica di vendita, perché l'AI ha scollegato il tempo impiegato dal valore consegnato. Ecco: questa è la stessa frattura vista dall'altro lato del bilancio. Da una parte non puoi più far pagare il tempo, perché ne serve molto meno; dall'altra ti ritrovi un costo variabile che prima non avevi, che non dipende dalle tue ore ma da quelle che i tuoi clienti passano a usare il prodotto. Cambiano entrambe le colonne insieme, e chi aggiorna solo quella dei ricavi si accorge dell'altra a fattura arrivata.

## Facciamo due conti (sì, con la calcolatrice)

Prendiamo un esempio. I numeri che uso qui sono volutamente d'esempio — i listini cambiano ogni tre mesi e vanno sempre verificati sul sito del fornitore il giorno in cui fai il preventivo — ma la struttura del ragionamento no, quella resta.

Mettiamo un assistente conversazionale con un modello di punta a 3 € per milione di token in input e 15 € per milione in output. Sembrano cifre ridicole. Lo sono, finché non le moltiplichi.

Un turno di conversazione decente ha un system prompt serio (1.500 token), qualche documento recuperato via RAG (3.000), la cronologia della chat, e una risposta di 500 token. Al primo turno paghi pochi centesimi. Ma alla decima battuta stai rimandando al modello **tutta la conversazione precedente**, ogni volta, perché i modelli sono senza memoria e il contesto glielo devi riconsegnare a ogni giro.

Questo è il punto che quasi nessuno mette nel business plan: il costo di una conversazione **non cresce in modo lineare con i turni, ma quadratico**. Dieci turni non costano dieci volte un turno: ne costano circa cinquanta. Una sessione da venti battute con un utente logorroico può tranquillamente costare come cinquanta sessioni da una battuta.

Adesso fai la moltiplicazione che conta davvero: costo per sessione × sessioni per utente al mese × numero di utenti. Poi confrontalo con il tuo prezzo di abbonamento. Se vendi a 20 € al mese "chiamate illimitate" e il tuo power user fa duecento sessioni, congratulazioni: hai appena inventato un modo molto sofisticato per regalare soldi a un fornitore di cloud.

## I tre buchi neri della bolletta

Nella mia esperienza i soldi non evaporano dove pensi. Evaporano in tre posti precisi.

**1. Il contesto che ti porti dietro.** Vedi sopra: la cronologia rimandata a ogni turno, il system prompt di 4.000 token che qualcuno ha scritto sei mesi fa e nessuno ha più riletto, i venti documenti recuperati dal RAG "per sicurezza" quando ne bastavano due. È spesa silenziosa, perché non la vedi da nessuna parte se non nella fattura aggregata.

**2. Il fan-out degli agenti.** Torniamo ai famosi cento sub-agenti. Un'architettura agentica non moltiplica i costi per il numero di agenti: li moltiplica per il numero di agenti **per il numero di passi che ciascuno fa**. Un orchestratore che lancia 10 worker, ognuno dei quali fa 5 giri di ragionamento con tool call, non è una richiesta: sono 50+ chiamate, ognuna con il suo contesto. E ogni tool call rimanda in input tutto quello che è successo prima. Quei cento sub-agenti che lavorano alacremente per automatizzare un processo non campano d'aria: divorano token a colazione, pranzo e cena.

**3. I retry e i loop.** L'errore che ti costa di più è quello che non fa rumore. Una risposta malformata che il codice ritenta tre volte. Un agente che entra in loop e continua a chiamare lo stesso tool convinto che stavolta funzionerà. Un job notturno che va in errore e riparte da capo alle 3 del mattino, ogni notte, per due settimane, finché non arriva la fattura. Non è un bug funzionale — l'utente non se ne accorge — ed è esattamente per questo che sopravvive per mesi.

## La cassetta degli attrezzi di chi sa fare i conti

La buona notizia è che tra "spendere una fortuna" e "spegnere i server e tornare alla carta carbone" c'è tantissimo spazio. Un ordine di grandezza, spesso due. Le leve, più o meno in ordine di quanto rendono rispetto alla fatica che costano:

- **Routing per difficoltà.** Non tutte le richieste meritano il modello da 400 miliardi di parametri. Classifica l'intento con un modello piccolo (o, scandalo, con una regex) e manda al modello grande solo il 10-20% dei casi che lo richiedono davvero. È la leva con il miglior rapporto risparmio/fatica in assoluto.
- **Prompt caching.** Se il tuo system prompt e i tuoi documenti sono stabili tra una chiamata e l'altra, i principali fornitori ti permettono di metterli in cache a una frazione del prezzo. Sul problema del contesto quadratico è quasi un antidoto — a patto di strutturare i prompt con la parte stabile all'inizio e quella variabile alla fine, che è un dettaglio implementativo da cinque minuti con un impatto enorme.
- **Modelli piccoli, distillati, locali.** Un modello small o distillato sul tuo dominio specifico può costare un centesimo del fratello maggiore e, sul tuo compito ristretto, andare uguale o meglio. Per i task ad altissimo volume e bassa varianza — classificazione, estrazione, routing, moderazione — il modello mastodontico è quasi sempre lo strumento sbagliato. E se il volume è davvero alto, un modello quantizzato su hardware tuo cambia proprio la struttura del costo: da variabile a fisso.
- **Disciplina sull'output.** L'output costa in genere 3-5 volte l'input. Chiedere una risposta strutturata e stringata invece di un tema di terza media è un risparmio diretto. Lo stesso vale per i modelli di ragionamento: fantastici, ma pagare token di reasoning per rispondere a "qual è il mio saldo?" è un lusso difendibile solo in demo.
- **Batch e asincrono.** Tutto ciò che non deve rispondere entro due secondi può passare da un'API batch, che tipicamente costa la metà. Report notturni, arricchimento dati, reindicizzazioni: roba che nessuno sta guardando in tempo reale.
- **Caching semantico.** Nella maggior parte dei prodotti reali le domande degli utenti si somigliano in modo imbarazzante. Riconoscere che questa domanda è semanticamente identica a una già risposta ieri, e servire la risposta dalla cache, toglie di mezzo una fetta di traffico a costo praticamente zero.
- **Guardrail sui limiti.** `max_tokens` sensato, tetto massimo di passi per gli agenti, timeout, budget per tenant, alert quando la spesa giornaliera supera una soglia. Non è ottimizzazione: è il freno a mano. Serve il giorno in cui qualcosa va storto, non tutti gli altri giorni.

E la metrica da tenere sul cruscotto non è il costo per chiamata: è il **costo per task completato con successo**. Un modello che costa il doppio ma azzecca la risposta al primo colpo, invece di sbagliare due volte e farsi correggere da un umano, è il modello economico. Ottimizzare il costo per chiamata senza guardare il tasso di successo è il modo più veloce per risparmiare sulla benzina andando a piedi.

## La figura che manca in azienda

Cosa dobbiamo fare, quindi? Abbandonare la tecnologia? Certamente no.

La soluzione non è vietare l'AI: è smettere di far guidare i progetti aziendali esclusivamente da scienziati pazzi innamorati dell'ultimo modello uscito quattro giorni fa. Oggi, dentro le aziende, serve come il pane una figura diversa: una **guida pragmatica della tecnologia**. Qualcuno che sappia usare la calcolatrice e che si sieda al tavolo con tre obiettivi precisi:

- **Analizzare i processi interni** per capire dove l'AI serve davvero e dove è solo un costoso esercizio di stile. Molti processi si automatizzano benissimo con un `if` — e lo dico da uno che l'AI la usa tutti i giorni.
- **Conoscere le tecnologie in profondità**, sapendo distinguere quando serve un modello mastodontico e quando basta un modello small, distillato o locale che costa una frazione.
- **Essere focalizzati al millesimo sul bilanciamento** tra requisiti tecnici, applicazione pratica e budget previsto — e saper dire "questa feature, a questo costo unitario, non la facciamo" prima che sia il bilancio a dirlo.

Non è un ruolo da CFO prestato all'IT, né da data scientist con un foglio Excel aperto per sbaglio. È una figura tecnica a tutti gli effetti, che però tiene sempre due colonne sotto gli occhi: cosa fa e quanto costa.

## In sintesi

L'AI è fantastica, non ci piove. Ma i fornitori di cloud e di modelli fatturano ancora in euro e dollari reali, non in pacche sulle spalle o in token di stima.

Il segreto è uno solo: **definire il budget prima di accendere la macchina**, non dopo. Stimare il costo per interazione quando il prodotto è ancora su una slide, non quando è in produzione con diecimila utenti. E avere a bordo qualcuno che sappia quando è il momento di staccare la spina ai cento sub-agenti, prima che si approfittino del conto aziendale.

Tu il costo per interazione del tuo prodotto AI lo conosci, o lo scoprirai dalla prossima fattura? Se stai facendo questi conti, o la fattura che ti ha fatto sobbalzare è già arrivata, raccontamelo: sono numeri che si capiscono meglio messi uno accanto all'altro. I prossimi li porto qui, e la newsletter è in fondo alla pagina.
