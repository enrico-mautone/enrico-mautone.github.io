---
layout: post
title: "L'anima della voce - cos'è la prosodia e come l'AI ha imparato a recitare -38 giorni all'alba"
date: 2026-07-25 09:00:00 +0200
categories: [cantiere]
tags: [tts, prosody, prosodia, voice-agents, llm, speech-synthesis]
image:
  path: /assets/img/evoluzione-prosodia-tts.png
  alt: "Timeline dell'evoluzione tecnica della prosodia nella sintesi vocale, dal 2016 al 2026"
---

Non avrei mai pensato, alla mia età, di dovermi mettere a studiare cos'è la prosodia. È una di quelle parole che finché fai lo sviluppatore stanno bene nel cassetto della linguistica, insieme ai fonemi e ai sintagmi, e tu tiri dritto. Poi però ti metti in testa di costruire un agente che parla — non che scrive, che parla — e scopri che quel cassetto ti tocca aprirlo per forza.

Il problema è tutto lì. Un agente vocale che risponde con una voce piatta, monocorde, che scandisce le sillabe come un tostapane che legge il bugiardino, non lo vuole nessuno. La differenza tra un prodotto che le persone usano e uno che spengono dopo trenta secondi non sta in cosa dice l'agente: sta in come lo dice. E quel "come" ha un nome tecnico preciso. Si chiama prosodia. Quindi eccomi qui, a mezza età, a rifare linguistica per non fare un prodotto che sembra un navigatore satellitare del 2008.

Questo articolo è il mio quaderno di studio messo in ordine: cos'è la prosodia, e soprattutto come le macchine sono passate dal leggere sillabe al capire — o dare l'impressione di capire — il sentimento dietro una frase.

## Che cos'è la prosodia, spiegata a uno sviluppatore

La prosodia è l'architettura melodica, ritmica e dinamica del parlato. Detta in modo brutale: non cambia cosa dici — quello è il lessico, le parole — ma determina come lo dici, cioè l'intenzione.

L'analogia che mi ha fatto scattare la molla è quella dello spartito. Due musicisti possono leggere le stesse identiche note. Uno le esegue in modo meccanico, corretto e morto. L'altro le interpreta, e ti viene la pelle d'oca. Le note sul foglio sono il testo. Tutto quello che ci mette il secondo musicista — e che non è scritto da nessuna parte sullo spartito — è la prosodia.

Da un punto di vista fisico, tutta questa magia poggia su tre pilastri misurabili:

- **Frequenza fondamentale (F₀)** — l'altezza tonale, il pitch. È la melodia della frase: quando la voce sale e quando scende.
- **Durata** — il ritmo. Quanto dura ogni fonema, quanto vai veloce, e soprattutto dove metti le pause. Le pause sono metà del lavoro.
- **Energia** — l'intensità, il volume. Dove calchi e dove smorzi.

Vuoi l'esempio più economico del mondo? La parola "sì". Una sillaba. Prova a dirla come una domanda ("sì?"), come un'affermazione decisa ("sì."), e con quel filo di sarcasmo che tutti conosciamo ("sìì, certo"). Stesso testo, tre significati diversi. Non hai cambiato una lettera: hai cambiato frequenza, durata ed energia. Quella è la prosodia, ed è esattamente la cosa che un modello di sintesi vocale deve azzeccare per non suonare finto.

Chiarito cosa dobbiamo insegnare alle macchine, la parte che mi ha affascinato di più è stata scoprire come ci sono arrivate. Perché non ci sono arrivate in un colpo solo: è una storia in cinque fasi, e ognuna risolve un problema che la fase prima non sapeva nemmeno di avere.

![Timeline dell'evoluzione tecnica della prosodia nella sintesi vocale, dal 2016 al 2026](/assets/img/evoluzione-prosodia-tts.png)
_Le fasi in cui la sintesi vocale ha imparato a "recitare", dall'era di WaveNet/Tacotron (2016) alla modellazione dinamica e verificabile (2025–2026)._

## Fase 1 — l'era robotica _(fino alla metà degli anni 2010)_

All'inizio c'erano i sistemi parametrici e concatenativi: regole rigide o pura statistica. O incollavi insieme pezzetti di voce umana registrata, o generavi il segnale da un modello statistico dei parametri acustici.

Il problema di fondo di questa era ha un nome che trovo bellissimo: la "prosodia media". Il modello, non sapendo quale intonazione servisse in quel preciso contesto, faceva la cosa più prudente possibile: puntava a un compromesso statistico, la via di mezzo tra tutte le intonazioni possibili. Il risultato è quella voce piatta, robotica, senza vita che tutti associamo al TTS di vent'anni fa. Non era sbagliata nota per nota — era mediata, e la media di tutte le emozioni è l'assenza di emozione.

## Fase 2 — la rivoluzione neurale _(2016–2020)_

Il salto arriva quando si passa da regole deterministiche a modelli probabilistici condizionati. In parole povere: invece di dire alla macchina "quando vedi questo, fai esattamente quest'altro", le si dà una montagna di esempi e le si chiede di imparare da sola la distribuzione di come suona il parlato reale.

Comincia con l'era di **WaveNet e Tacotron (2016–2017)**, le prime architetture end-to-end capaci di generare forme d'onda naturali, e prosegue con **FastSpeech 1 & 2 (2019–2020)**, che introducono modelli non-autoregressivi con predittori espliciti di durata, altezza tonale ed energia. Due innovazioni tecniche hanno cambiato tutto:

- I **meccanismi di attenzione**, per allineare automaticamente il testo all'audio — cioè capire quale pezzo di suono corrisponde a quale pezzo di testo, senza doverglielo dire a mano.
- I **vocoder neurali** come WaveNet o HiFi-GAN, che generano l'onda sonora vera e propria con un realismo che prima era impensabile.

Qui la voce smette di suonare da robot. Diventa fluida, naturale, credibile. Ma resta un pezzo mancante, e per il mio prodotto è il pezzo che conta.

## Fase 3 — il controllo dello stile _(2018–2022)_

La domanda che chiude la fase 2 è questa: bello, la voce è naturale. Ma come faccio a dirle di parlare arrabbiata? O di sussurrare? Un modello Tacotron ti dà una bella voce, ma è la voce che ha deciso lui, non quella che serve a te in quel momento.

La risposta, nel **2018**, sono i **Global Style Tokens (GST)** e i VAE (Variational Autoencoders). Senza entrare troppo nel motore: questi modelli imparano a estrarre lo stile — l'emozione, il tono, il modo — da un file audio di riferimento, e ad applicarlo a un testo completamente diverso. Si chiama prosody transfer: registri (o gli dai in pasto) tre secondi di qualcuno che parla con un certo trasporto, e il modello ti recita il tuo testo con quel trasporto.

Nel **2021–2022** arriva un ulteriore passo: i controlli prosodici gerarchici (HPC), che scompongono la prosodia in livelli linguistici — frasi, parole, sillabe — per un controllo molto più granulare. Non più uno "stile" unico spalmato su tutta la frase, ma la possibilità di intervenire a diverse scale.

Per chi come me deve costruire un prodotto, questa è la prima fase in cui la voce diventa una leva di design e non solo un output. Ma è ancora una leva un po' rigida.

## Fase 4 — l'era dei Large Language Models _(2023–2024)_

Qui c'è il cambio di paradigma che, da persona che con gli LLM ci lavora tutti i giorni, mi ha fatto sorridere. L'idea è tanto semplice quanto potente: trattare la voce come un linguaggio.

Il trucco è discretizzare l'audio in "token acustici" — piccoli pezzi discreti, esattamente come le parole sono token per un modello di testo. A farlo sono codec neurali come EnCodec o XCodec2. Una volta che l'audio è una sequenza di token, un LLM può "leggerlo" e predirlo esattamente come predice il testo. Modelli come VALL-E e LLaSA fanno proprio questo. Nello stesso periodo si diffonde il TTS pilotato da prompt — descrizioni in linguaggio naturale dello stile (PromptTTS) — e i modelli a diffusione come StyleTTS 2.

Il punto di forza è la scala. Questi modelli imparano schemi prosodici complessissimi da dataset enormi — fino a milioni di ore di audio. Non gli insegni le regole dell'intonazione: gliene fai vedere così tante che le assorbe. È lo stesso motivo per cui un LLM di testo "sa" scrivere: non gli hai spiegato la grammatica, gliel'hai fatta vedere un miliardo di volte.

## Fase 5 — prosodia dinamica e conversazionale, il presente _(2025–2026)_

E arriviamo a oggi, che è la fase che per il mio agente conta davvero.

Tutte le fasi precedenti, in un modo o nell'altro, pianificavano la prosodia dell'intera frase prima di pronunciarla — una specie di "chain-of-thought prosodico", decido tutta l'intonazione in anticipo e poi la eseguo. Funziona per leggere un audiolibro. Non funziona per conversare, perché in una conversazione l'intonazione giusta di adesso dipende da cosa è successo un istante fa.

Il presente supera questa staticità con la predizione dinamica a livello sillabico: la prosodia si decide istante per istante, sillaba per sillaba, in base a come sta andando il dialogo. Modelli come Moshi o CSM-1B adattano il tono in tempo reale, sul momento, tenendo conto del contesto e dell'interlocutore.

E c'è l'ultimo pezzo, quello che chiamano comprensione paralinguistica: agenti che non solo parlano bene, ma "capiscono" chi hanno davanti — l'età, l'emozione di chi sta parlando (è la direzione di modelli come TextPro-SLM) — e calibrano la risposta di conseguenza per essere più comprensibili. Se dall'altra parte c'è una persona anziana o in difficoltà, l'agente rallenta, scandisce meglio, ammorbidisce. Questo, per il tipo di prodotto che ho in testa, non è un dettaglio estetico: è il cuore del valore.

## Perché mi tocca sapere tutto questo

Torno da dove sono partito. Ho iniziato a studiare la prosodia sbuffando, come si sbuffa davanti a una cosa che sembra un ostacolo burocratico tra te e il codice. Ho finito con il rendermi conto che la prosodia è il prodotto, non un accessorio sopra il prodotto.

Per anni la sintesi vocale ha trattato l'intonazione come la ciliegina: prima faccio funzionare la voce, poi semmai la "coloro". La traiettoria di questi cinque stadi racconta l'esatto contrario. Man mano che le macchine hanno padroneggiato la prosodia — dalla "media" piatta delle regole, allo stile trasferibile, fino all'adattamento dinamico in tempo reale — il confine tra naturale e sintetico si è assottigliato fino quasi a sparire. E quando quel confine sparisce, si aprono le porte a quello che voglio costruire io: assistenti vocali che non recitano una parte, ma stanno davvero dentro la conversazione.

Quindi sì, alla mia età mi tocca rifare linguistica. Ma almeno adesso so perché. E la prossima volta che il mio agente dirà "sì", saprò esattamente quale dei tre "sì" gli ho chiesto di dire.

Questo è un passo nella costruzione di un agente vocale vero: quello di [Stories](https://stories-app.it), che deve parlare con persone anziane e farsi capire. E tu, quando hai scelto una voce sintetica per un prodotto, l'hai scelta per come suona o per come recita? Se ci stai sbattendo contro anche tu, scrivimi: sono cose che si capiscono meglio parlandone. E se vuoi sapere come va a finire, la newsletter è qui sotto.
