---
layout: post
title: "Un agente vocale in un weekend? Sì, finché non lo devi dare a una nonna italiana"
date: 2026-10-27 09:00:00 +0100
categories: [il-timone]
tags: [agenti-vocali, gdpr, ai-act, costi, stories]
translations: [en]
image:
  path: /assets/img/agente-vocale-nonna-italiana.png
  alt: "Illustrazione: dal palco della demo 'agente vocale in 20 minuti' una strada con quattro cartelli (voce, dati fuori UE, budget, AI Act) porta a una nonna al telefono; a destra l'iceberg del sistema, di cui l'LLM è solo la punta"
---

La promessa la conoscete anche voi, perché in questi mesi è ovunque: "il tuo agente vocale in venti minuti, senza scrivere una riga di codice". La ricetta è sempre la stessa. Prendi una piattaforma di voce sintetica tipo ElevenLabs, ci attacchi un modello realtime tipo quello di OpenAI, aggiungi un'automazione che salva la conversazione da qualche parte, e hai finito. Hai un'AI che risponde al telefono, prende appuntamenti, fa compagnia. Manca solo il fiocco.

E lo dico subito, perché è giusto dirlo: **la demo funziona davvero.** In un pomeriggio senti un agente che ti parla, capisce quello che dici e risponde con una voce che due anni fa sarebbe sembrata fantascienza. Chi liquida tutto come marketing, probabilmente, non ci ha mai provato.

Poi io l'ho dovuto costruire per persone di 85 anni, in Italia. E la demo è stata la parte facile.

Attenzione, signori: non è tutto oro quello che luccica. Vi spiego perché.

Prima, però, una premessa che vale per tutto il blog: qui non troverete le ultime novità del settore, ma le promesse dell'AI messe alla prova sul campo, con le falle e le assunzioni che le demo non mostrano. Perché lo faccio, e chi c'è dietro, l'ho raccontato in [Chi sono](/about/).

## Il contesto, in tre righe

Da settembre sono CTO di Stories, un'amica a voce per anziani: qualcuno con cui chiacchierare ogni giorno, che si ricorda di te e tiene la famiglia un po' più vicina. Non è un'app medica e non è telesoccorso — e più avanti vedremo che quel "non è" pesa molto più di quanto sembri.

Ve lo racconto per una ragione sola: ogni trappola qui sotto l'ho incontrata lì, sul campo, e non in un tutorial.

## Trappola 1: la voce non va bene

Le voci "fenomenali" delle demo sono costruite e provate soprattutto in inglese, per un pubblico che ascolta i podcast a velocità 1,5x. In italiano possono avere un accento leggermente spostato, una prosodia (ne avevo parlato in [L'anima della voce](/posts/anima-della-voce-prosodia-ai/)) che cade nel posto sbagliato, un ritmo troppo veloce per un orecchio di ottantacinque anni. A noi sembra naturale. A lei sembra "quella signorina che parla strano".

E il problema non è solo in uscita. Il riconoscimento vocale fatica con la voce anziana, che è più debole, più tremula, a volte impastata. Fatica con il dialetto, o anche solo con l'italiano regionale. Ma soprattutto fatica con le pause. Una persona anziana si ferma a metà frase, cerca la parola, riprende dopo tre secondi. L'agente della demo, in quei tre secondi, ha già deciso che hai finito e ti sta rispondendo sopra — come il nipote che ti finisce le frasi, ma senza l'affetto.

Capire quando l'altro ha finito di parlare (il **turn-taking**) nei tutorial è un cursore da spostare in un pannello. Per noi è diventato un problema di progetto, perché se interrompi una nonna due volte, la terza non ti richiama.

Il monito, qui, è semplice: la voce della demo l'hai scelta tu, quella del prodotto la giudica chi la ascolta.

## Trappola 2: i dati vanno fuori dall'UE

Qui il tono si fa meno divertente. Nella ricetta standard l'audio e le trascrizioni passano per i server di aziende americane, e le conversazioni di un anziano contengono quasi sempre dati sulla salute: la pressione, la pastiglia, la visita di giovedì, "stanotte non ho dormito". Per il GDPR sono **dati particolari** (articolo 9), quelli per cui le regole si fanno serie davvero.

La buona notizia è che le opzioni per tenere i dati in Europa esistono. La cattiva è dove stanno. Sono andato a verificarlo sulle fonti ufficiali dei due fornitori della ricetta:

- **ElevenLabs** offre la residenza dei dati in UE, ma la descrive come una funzione esclusiva per i clienti Enterprise. E anche lì la documentazione avverte che le integrazioni opzionali, come un LLM esterno o i webhook a fine chiamata, possono comunque trattare dati fuori dalla regione.
- **OpenAI** permette di creare progetti API con residenza europea e zero data retention, ma solo per i "clienti idonei", su endpoint idonei, e senza poter convertire un progetto già esistente.

La conformità, quindi, si può avere: ha un prezzo e un contratto da negoziare. Il che ci porta dritti alla trappola 3.

C'è poi la questione della **minimizzazione**: l'audio grezzo non ti serve, e quindi non dovresti tenerlo. Facile a dirsi. Ma quando la pipeline gira su una piattaforma che non è tua, riesci davvero a dimostrare dove finisce ogni file e per quanto tempo ci resta? Scriverlo in una privacy policy costa una riga; dimostrarlo è tutto un altro mestiere.

## Trappola 3: si sfora il budget

Nella ricetta paghi tre cose al minuto: il riconoscimento vocale, il modello che pensa e la sintesi che parla. Prese una per una sono cifre piccole. Il guaio arriva quando le moltiplichi.

Facciamo due conti, con numeri volutamente d'esempio presi dai listini pubblici e non da Stories. Una piattaforma vocale gestita oggi costa intorno agli 8 centesimi di dollaro al minuto, e il modello linguistico non è compreso: si paga a parte. Un modello realtime di fascia alta, solo per l'audio in entrata e in uscita, sta fra i 3 e i 6 dollari per un'ora di conversazione piena. Arrotondando con larghezza, un'ora di chiacchiere costa qualche dollaro.

Ora mettiamo una nonna che parla un'ora al giorno, tutti i giorni. Sono trenta ore al mese, e a quel punto il costo di una sola utente supera tranquillamente quello che una famiglia è disposta a pagare di abbonamento. E attenzione: le conversazioni lunghe e quotidiane non sono un'eccezione da gestire, sono esattamente il caso d'uso del prodotto.

È la stessa Ferrari che consuma un litro ogni cento metri di cui parlavo in [Ai sei fantastica! Sì, ma quanto mi costi?](/posts/ai-fantastica-ma-quanto-mi-costi/). Solo che qui il motore resta acceso un'ora al giorno per ogni cliente.

La conseguenza è quasi obbligata: modelli in locale o su server propri in UE, che tra l'altro risolvono in un colpo solo anche la trappola 2. Ma non è un pasto gratis. Ti ritrovi in casa tutti i lavori che prima faceva la piattaforma: GPU da dimensionare, latenza da inseguire (in voce, mezzo secondo in più si sente eccome), manutenzione, aggiornamenti e, soprattutto, la qualità da **rimisurare** da capo ogni volta che cambi un pezzo.

## Trappola 4: l'AI Act non lo trovi nel tutorial

In nessun video "agente vocale in venti minuti" ho mai sentito citare l'AI Act. Eppure c'è, e per un agente vocale ha almeno tre punti di contatto. Premessa d'obbligo: non sono un avvocato, e questa è la mia lettura da tecnico, da verificare con chi lo fa di mestiere.

**Trasparenza.** L'articolo 50 è in vigore dal 2 agosto 2026 e il Digital Omnibus non l'ha spostato: un sistema che interagisce con le persone deve far sapere che è una macchina, a meno che non sia ovvio. Con un utente di 85 anni e una voce quasi umana, non è mai ovvio. Quindi va detto, e va ripetuto in modo che resti.

**Riconoscimento delle emozioni.** È la trappola meno ovvia, e quella su cui mi sono fermato a pensare più a lungo. L'idea viene spontanea: "facciamo capire all'agente dal tono di voce se la nonna è triste". Peccato che l'AI Act definisca **sistema di riconoscimento delle emozioni** quello che deduce le emozioni a partire da dati biometrici — e la voce lo è. Un sistema così ha obblighi di informazione propri e finisce fra quelli ad alto rischio dell'allegato III. Dedurre l'umore da *cosa* dice una persona è una cosa; dedurlo da *come* lo dice ti porta in un regime diverso.

**Dispositivi medici.** Se l'agente comincia a rilevare segnali di malattia ("la voce è più impastata del solito, potrebbe essere...") smette di essere un'amica e diventa un software con finalità mediche. Entra nelle regole sui dispositivi medici e, quando serve la verifica di un organismo notificato (cosa frequente per un software che aiuta a diagnosticare), per l'AI Act diventa ad alto rischio fra i prodotti regolamentati.

Sulle date, a scanso di equivoci: con il Digital Omnibus, in vigore dal 27 luglio, gli obblighi per l'alto rischio sono slittati al 2 dicembre 2027 per i sistemi dell'allegato III e al 2 agosto 2028 per quelli integrati in prodotti regolamentati (ne avevo scritto in [Il 2 agosto è arrivato. E adesso?](/posts/ai-act-2-agosto-e-adesso/)). Rinviati, non aboliti: un prodotto che progetti oggi, in quelle date, sarà ancora lì.

Ed ecco perché quel "non è" di prima pesava così tanto. **Ogni "Stories non è…" è una scelta di architettura** che tiene il prodotto fuori da un regime molto più pesante. Non leggiamo le emozioni dalla voce e non facciamo diagnosi: sono funzioni tecnicamente a portata di mano, e abbiamo deciso di non costruirle.

## Il conto: cosa serve davvero

Mettiamo tutto in fila. A sinistra cosa ti promette la piattaforma, a destra cosa serve quando l'utente è un'anziana italiana.

| Pezzo | Cosa promette la piattaforma | Cosa serve in Italia |
|---|---|---|
| Voce in ingresso | Trascrizione accurata, rilevamento automatico del turno | Riconoscimento tarato su voci anziane e italiano regionale, turn-taking che tollera pause lunghe |
| Filtri di sicurezza | Moderazione generica dei contenuti | Regole su cosa l'agente non deve mai dire (consigli medici, farmaci, soldi) e su cosa fare quando emerge un segnale di disagio |
| Orchestratore | Un flusso disegnato a blocchi | Logica che decide quando ricordare, quando chiedere, quando avvisare la famiglia |
| Modello | Il modello migliore del momento | Un modello che costa il giusto, gira in UE, e la cui qualità sai misurare |
| Memoria per famiglia | Lo storico della chiamata | Memoria persistente e separata per ogni persona e ogni famiglia, con regole chiare su cosa si conserva |
| Voce in uscita | Voci "fenomenali" a catalogo | Una voce italiana con ritmo e prosodia adatti a chi ascolta, non a chi ha fatto la demo |
| Riassunti alla famiglia | Un webhook a fine chiamata | Riassunti utili ma rispettosi, senza trasformare l'amica in una spia |
| Log e monitoraggio | Una dashboard con i minuti consumati | Tracciabilità per GDPR e AI Act, costo per conversazione, qualità nel tempo |

Guardando la tabella, la frase che mi porto via è una sola: **l'LLM è il cervello, non il sistema.** E il cervello, paradossalmente, è il pezzo che si compra più facilmente.

## Serve qualcuno al timone

Sia chiaro: il messaggio non è "non usate ElevenLabs" o "lasciate stare i modelli realtime". Sono strumenti eccellenti, e per prototipare sono imbattibili. Il punto è sapere cosa si sta comprando — e cosa resta da costruire.

Se state per scegliere una piattaforma per un agente vocale, prima di innamorarvi della demo fatevi tre domande:

- **Dove vanno i dati?** Non in generale: su quale piano, con quale contratto, e cosa succede con le integrazioni che aggiungerete dopo.
- **Quanto costa un'ora di conversazione?** Tutta, sommando ascolto, modello e voce. Poi moltiplicatela per l'uso reale dei vostri utenti, non per quello della demo.
- **Chi decide cosa l'agente non deve mai dire?** Se la risposta è "il prompt di sistema", avete ancora del lavoro da fare.

Questo era la mappa. Nei prossimi articoli entrerò nel dettaglio di ogni trappola: il guardrail e come si misura, quanto costa davvero un'ora di conversazione, e il GDPR applicato alle conversazioni degli anziani.

Intanto la domanda la giro a te: se hai messo in produzione un agente vocale, qual è stata la prima cosa che si è rotta dopo la demo? La voce, i costi, o la prima telefonata del DPO? Raccontamelo nei commenti o scrivimi dal form qui sotto: sono problemi che si capiscono meglio messi uno accanto all'altro.
