---
layout: post
title: "Il 2 agosto è arrivato. E adesso? -27 giorni all'alba"
date: 2026-08-05 09:00:00 +0200
categories: [ai, business]
tags: [ai-act, compliance, regolamentazione, gdpr, shadow-ai, cto]
image:
  path: /assets/img/ai-act-2-agosto-adesso.png
  alt: "Le quattro categorie di rischio dell'AI Act, il confine tra strumenti aziendali e personali, e la checklist minima per adeguarsi dopo il 2 agosto 2026"
---

Per un anno intero il 2 agosto 2026 è stato raccontato come il giorno del giudizio. Post allarmistici, webinar con il countdown, consulenti che vendevano "l'ultima chiamata prima delle sanzioni milionarie". È arrivato lunedì. Non è successo niente di visibile: nessuna azienda è stata multata per posta, LinkedIn non è esploso, il mondo ha continuato a girare esattamente come prima.

E qui sta il problema, perché "non è successo niente di visibile" non vuol dire "non è cambiato niente". È cambiato qualcosa, solo non quello che la maggior parte delle persone che ho sentito in questi giorni pensa che sia cambiato. Ne ho parlato con un cliente proprio mercoledì, mentre preparavo le ultime cose prima di settembre — quando, tra 27 giorni, comincio ufficialmente come CTO. Mi ha chiesto: "quindi adesso siamo tutti in regola o no?". Onestamente, non lo sapevo con certezza nemmeno io fino a qualche giorno fa. Quindi ho passato il weekend a leggermi le fonti giuste, e questo articolo è il riassunto di quello che ho capito — meno per fare il consulente legale (non lo sono, e su questo materiale conviene sempre un confronto con chi lo è davvero) e più per mettere ordine, cosa che faccio meglio scrivendo che pensandoci da solo.

## Cosa è vigente oggi

Il malinteso più diffuso in questi giorni è: "tanto con il Digital Omnibus è tutto rinviato". Falso, o meglio: vero solo a metà.

Il **Digital Omnibus** (Regolamento UE 2026/1744) è entrato in vigore il 27 luglio, cinque giorni prima della scadenza che tutti aspettavano, e ha spostato in avanti gli obblighi più pesanti — quelli sui sistemi **ad alto rischio** — al 2 dicembre 2027 per i sistemi autonomi e al 2 agosto 2028 per quelli integrati in prodotti già regolamentati (dispositivi medici, macchinari). Chi si era organizzato sulla vecchia scadenza ha guadagnato tempo vero, non uno scenario da PowerPoint.

Quello che **non** è stato toccato è l'articolo 50, quello sulla trasparenza: se usi un chatbot, generi contenuti sintetici o gestisci sistemi che riconoscono emozioni, gli obblighi di informare l'utente sono legge dal 2 agosto 2026. Punto. Non è la scadenza da cui aspettarsi conseguenze immediate e drammatiche, ma è quella che riguarda concretamente la maggior parte delle aziende e degli studi professionali che oggi usano AI — molte più di quante pensino di essere coinvolte.

## Cosa sono i livelli di rischio e dove sta la tua azienda

Qui sta il pezzo che vale davvero la pena capire bene, perché è quello su cui si basa tutto il resto: l'AI Act non tratta l'intelligenza artificiale come un blocco unico, la divide in quattro categorie di rischio, e gli obblighi cambiano radicalmente da una all'altra.

**Rischio minimo.** La maggior parte degli strumenti di produttività interna — un assistente che ti aiuta a riassumere documenti, uno strumento di ricerca interna. Nessun obbligo specifico previsto dal regolamento, ma "nessun obbligo AI Act" non significa "nessuna attenzione ai dati che ci passi dentro" — e qui arriviamo al punto che, dei quattro, è quello che vedo trattato meno.

**Rischio limitato.** Chatbot, assistenti virtuali, strumenti che generano o modificano testi, immagini, audio, video. È la categoria che riguarda quasi chiunque usi AI oggi, ed è quella con gli obblighi già pienamente attivi: informare chi interagisce che sta parlando con una macchina, marcare i contenuti generati artificialmente. Se hai un chatbot sul sito o usi strumenti generativi per produrre contenuti verso l'esterno, sei qui, e la scadenza è già passata sopra la tua testa — bene se l'hai già gestita, altrimenti è la prima cosa da sistemare.

**Alto rischio.** È la categoria dove l'AI incide su una decisione che tocca i diritti di una persona: selezione del personale, valutazione delle performance, accesso al credito, sistemi impiegati in sanità o istruzione. La domanda-guida che uso per riconoscerli è semplice: *questo sistema prende, o influenza pesantemente, una decisione su una persona specifica?* Se la risposta è sì, sei nell'alto rischio — e qui, come abbiamo visto, gli obblighi pesanti (documentazione tecnica, gestione del rischio, sorveglianza umana strutturata, eventuale FRIA) sono rinviati al 2027/2028. Rinviati, non aboliti: vanno comunque mappati ora, perché il tempo che sembra tanto si consuma più in fretta di quanto sembri quando il sistema è tecnicamente complesso.

**Rischio inaccettabile.** Sono le pratiche vietate per definizione: social scoring, manipolazione subliminale delle persone, sistemi che inferiscono emozioni sul posto di lavoro, categorizzazione biometrica indiscriminata. Se stai leggendo questo articolo per la tua PMI o il tuo studio, quasi certamente non ci rientri — ma "quasi certamente" non basta: va escluso esplicitamente nell'inventario, non per omissione silenziosa.

Per classificare un sistema che usi in azienda, tre domande in sequenza bastano quasi sempre:

- **Incide su una decisione riguardante una persona specifica?** Se sì, sei nell'alto rischio (o, nei casi più estremi, in una pratica vietata).
- **Interagisce direttamente con utenti o genera contenuti verso l'esterno?** Se sì, sei nel rischio limitato, con obblighi già attivi.
- **È uno strumento puramente interno di produttività?** Se sì, sei nel rischio minimo — ma la disciplina sui dati che ci passi dentro resta comunque tua responsabilità.

Le risposte, in ordine, ti portano dritto alla categoria giusta.

## Come adeguarsi, concretamente

Non serve un progetto di sei mesi per partire. Serve un ordine di lavoro:

**Inventario reale, non quello ufficiale.** Elenca tutti i sistemi AI effettivamente in uso in azienda — non solo quelli acquistati con fattura e approvati dall'IT, ma anche quelli che ogni collega usa di sua iniziativa. Questo passaggio, da solo, di solito rivela più cose di quante ci si aspetti.

**Classifica ognuno** con le tre domande di prima. Ti serve per sapere cosa ha una scadenza vicina (rischio limitato, già attivo) e cosa ha respiro fino al 2027 (alto rischio).

**Metti in piedi le disclosure dell'articolo 50** dove servono: un avviso chiaro al primo contatto con un chatbot, la marcatura dei contenuti generati che pubblichi verso l'esterno.

**Individua chi in azienda è responsabile** della supervisione umana su ogni sistema — non deve essere un ruolo nuovo creato apposta, ma deve essere una persona con nome e cognome, non "il reparto IT" in astratto.

Qui vale la pena essere precisi, perché è la domanda che mi sento fare più spesso: serve una figura come il DPO del GDPR o il responsabile della sicurezza sul lavoro? La risposta onesta è no, non ancora — l'AI Act non impone per legge un ruolo dedicato equivalente. Chiede però che qualcuno, con competenze reali e non solo sulla carta, eserciti la supervisione umana ed elabori il livello minimo di alfabetizzazione AI per chi usa questi sistemi (l'AI literacy, obbligatoria dal 2 febbraio 2025). Le audizioni parlamentari sul decreto italiano hanno fatto emergere proprio questo: manca ancora una definizione delle competenze di chi deve validare input e output dei sistemi ad alto rischio, e figure come l'AI auditor non hanno oggi un riconoscimento normativo. Per una PMI o uno studio, la scelta pratica è affidare il ruolo a chi già segue GDPR e sicurezza informatica, ampliandone il mandato — non aspettare che la legge disegni una nuova casella in organigramma.

**Tieni traccia.** Log, evidenze, screenshot di cosa hai comunicato e da quando. Non è burocrazia fine a se stessa: è la differenza tra poter dimostrare la conformità e poterla solo dichiarare a voce, che in caso di controllo non vale granché.

## Il punto che quasi nessuno tratta: i tuoi strumenti personali non bastano più

Questa è la parte che, guardando in giro, vedo trattare pochissimo, ed è quella su cui vorrei insistere di più.

Se un collaboratore incolla il contratto di un cliente in un account ChatGPT personale per farsi riassumere una clausola, o carica un CV in Gemini gratuito per uno screening veloce, non è solo un problema GDPR — che già da solo basterebbe. È un problema di conformità AI Act, perché in quel momento l'azienda ha perso ogni possibilità di dimostrare dove sono finiti quei dati, chi li ha visti, con quali garanzie sono stati trattati. Non puoi documentare la supervisione umana su uno strumento che non controlli, e non puoi tracciare quello che è già uscito dal perimetro aziendale.

È il fenomeno che in gergo si chiama **shadow AI**: l'uso non autorizzato di strumenti AI personali con dati aziendali, spesso in perfetta buona fede — un collega che vuole solo essere più veloce, non certo aggirare una norma di cui probabilmente non conosce nemmeno l'esistenza. Il problema è che l'intenzione non conta in un audit: conta cosa è dimostrabile.

La soluzione non è vietare l'AI ai propri collaboratori, sarebbe come vietare l'email. La soluzione è dare loro uno strumento aziendale — un account con contratto, con garanzie sul trattamento dei dati, dentro il perimetro che l'azienda controlla — e una policy scritta, breve, che dica chiaramente cosa si può incollare in una chat AI e cosa no. Non serve un documento di venti pagine: bastano due paragrafi chiari e la formazione minima per farli capire davvero, non solo firmare per presa visione.

## Le sanzioni, senza allarmismo

Per dare peso reale al discorso, senza scivolare nel panico da titolo: le sanzioni previste vanno da un massimo di 35 milioni di euro o il 7% del fatturato mondiale per le pratiche vietate, fino a 15 milioni o il 3% per le violazioni sugli obblighi di trasparenza e alto rischio, con un regime di favore per PMI e startup che limita l'impatto in valore assoluto. Sono cifre pensate per i casi più gravi e ripetuti, non per il piccolo studio che ha dimenticato un avviso su un chatbot. Ma sono comunque la cornice dentro cui vale la pena muoversi con ordine, non per paura, ma perché mettere ordine nei propri sistemi AI è comunque un lavoro sensato a prescindere dalla multa.

## Una riga sull'Italia

Il decreto italiano di attuazione, l'AG 421, è ancora in Parlamento — parere delle Commissioni atteso per il 16 agosto, con le due autorità di riferimento che saranno AgID e ACN. Non serve aspettare che il decreto sia definitivo per iniziare: gli obblighi europei che abbiamo visto sopra sono già vigenti indipendentemente da come l'Italia chiuderà i dettagli sulla vigilanza nazionale.

## In sintesi

Il vero tema, per me, non è la multa da evitare. È che mappare i propri sistemi AI, classificarli e vietare l'uso di strumenti personali con dati sensibili è un lavoro che ogni azienda avrebbe dovuto fare comunque, a prescindere da qualsiasi regolamento — un po' come tenere in ordine le password o sapere chi ha accesso a cosa. L'AI Act l'ha solo reso obbligatorio, con una scadenza precisa da rispettare.

Se stai affrontando lo stesso esercizio in questi giorni — o se hai già trovato dello shadow AI in azienda e vuoi confrontarti su come è andata — mi fa piacere parlarne. Sono cose che si capiscono meglio raccontandosele a vicenda che leggendo un regolamento da soli. Sentiamoci!
