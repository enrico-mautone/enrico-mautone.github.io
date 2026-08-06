---
layout: post
title: "Ma tu quanto sei maturo nell'AI Engineering - 26 giorni all'alba"
date: 2026-08-06 09:00:00 +0200
categories: [ai, engineering]
tags: [ai-engineering, context, claude-code, cto-transition]
image:
  path: /assets/img/8-levels-context-maturity.png
  alt: "Gli 8 livelli di context maturity nell'AI-native engineering, dal tab-complete agli agent swarm autonomi"
---

Qualche giorno fa ho seguito un corso su un tema che, sulla carta, sembrava fatto apposta per farmi sentire bene con me stesso: quanto è "matura" un'azienda (o un singolo sviluppatore) nell'uso dell'AI per costruire software. Otto livelli, dal principiante che usa a malapena il tab-complete fino agli sciami di agenti autonomi che si coordinano da soli. Mi sono iscritto pensando: bene, vediamo quanto sono avanti.

Poi ho fatto l'assessment. E non è andata come pensavo.

## Il problema che nessuno vede finché non lo misura

La prima cosa che il corso mette sul tavolo è un dato che fa male, perché parla direttamente a chiunque stia usando l'AI per scrivere codice ogni giorno, me compreso. L'uso dell'AI nei team è salito del 65%. Il throughput reale, misurato in pull request che arrivano a destinazione? Solo +7%. I team, interrogati direttamente, dicono di sentirsi il 19% più lenti nella delivery rispetto a prima.

Il dato che mi ha colpito di più, però, è un altro: gli sviluppatori più esperti si percepivano il 20% più veloci lavorando con l'AI. In realtà erano più lenti. Non un po' più lenti nonostante la percezione: proprio più lenti, con la percezione che diceva l'esatto contrario.

È lo stesso motore che fa più rumore e ti convince di andare più forte, mentre il tachimetro dice altro. Io mi sento produttivo quando lavoro con Claude Code tutto il giorno. Ma quanto di quella sensazione regge se qualcuno mi mette davanti i numeri veri?

C'è anche un altro dato che inquadra bene la distanza tra "uso l'AI" e "mi fido dell'AI": oggi il 60% del lavoro di ingegneria coinvolge in qualche modo l'intelligenza artificiale, ma meno del 5% può essere delegato end-to-end, senza che un umano ci metta le mani in mezzo. Il gap tra quel 60 e quel 5 è, in pratica, tutto il tema di questo articolo.

## Gli 8 livelli di maturità spiegati in maniera facile

Il concetto centrale del framework è più semplice di quanto suoni, ed è anche il più scomodo da accettare: ogni volta che apri un agente, per lui è sempre "day one". Non sa niente del tuo sistema. Non ricorda perché sei arrivato a certe scelte architetturali, cosa hai già provato e scartato, cosa non si deve mai toccare. Ripartite da zero ogni volta, tu e lui. Manca il **CONTESTO**.

E qui vale la pena fermarsi un attimo, perché è la parola su cui gira tutto il resto dell'articolo. Per un agente, il contesto è tutto quello che tu sai del tuo progetto e lui no: perché il sistema è fatto in un certo modo, cosa hai già provato e scartato, quali convenzioni segui senza nemmeno pensarci, cosa non va toccato per nessuna ragione. Un umano nuovo in azienda queste cose le assorbe in settimane, chiedendo in giro, leggendo il codice, sbagliando una volta e imparando. Un agente, se nessuno gliele scrive da qualche parte, non le ha e basta. Ogni sessione riparte da un foglio bianco, e quel foglio bianco lo riempi tu, ogni volta, a mano.

La scala degli otto livelli va da un estremo all'altro: a un capo c'è il tab-complete, dove l'unico vero "motore di contesto" è la testa dell'umano che scrive; all'altro capo ci sono sciami di agenti che si coordinano tra loro senza bisogno di un umano che tenga insieme i pezzi. In mezzo, ci sono livelli via via più sofisticati di quanto contesto il sistema riesce a portarsi dietro da solo.

Prima di salire di livello, ci sono tre trappole in cui è facile cadere, e le riconosco tutte e tre per averle viste, almeno in parte, anche nel mio piccolo:

**La trappola del contesto curato**: repository pieni di regole e file markdown scritti con le migliori intenzioni, che però marciscono nel tempo perché nessuno li aggiorna più dopo il primo mese di entusiasmo.

**Il plateau da troppi strumenti collegati**: l'agente ha accesso a mezzo mondo di strumenti e integrazioni, ma non sa più quando o perché usarne uno piuttosto che un altro, e finisce soddisfatto di aver "cercato" invece che di aver trovato.

**La palla di neve degli agenti in background**: un agente lasciato girare da solo, senza il contesto giusto, che invece di risolvere un incidente lo peggiora, aprendo un'altra crepa mentre prova a tapparne una.

Il punto che vale la pena tenersi in tasca è questo: **il costo dell'errore scala con il livello**. Un tab suggerito male lo ignori con un colpo di backspace. Un agente in background che apre da solo una pull request inutile, o peggio dannosa, no.

## Ho fatto l'assessment. Sono un noob.

Qui arriva la parte scomoda da scrivere, ma è anche il motivo per cui questo articolo esiste.

Il risultato dell'assessment: livello 2 su 8.

Pensavo di essere più avanti. Ho anni di consulenza enterprise alle spalle, ho gestito delivery complesse, e ora sto costruendo da zero un prodotto AI vero, non un giocattolo. Mi sembrava ragionevole aspettarmi qualcosa di più di un 2. E invece no, perché la scala non misura quanta esperienza hai o quanto usi l'AI ogni giorno. Misura quanto il sistema riesce a lavorare senza di te seduto lì, nella stanza.

E su questo, il quadro è chiaro. Ho un flusso di lavoro agent-first che funziona bene: Claude Code come superficie primaria, niente IDE tradizionale aperto in un'altra finestra. Il rumore quotidiano è basso. Ho trovato un loop di feedback che funziona per la UI, banalmente gli screenshot: li mando, l'agente vede cosa non torna, corregge. Ma sono ancora io il contesto. Ogni sessione vale esattamente quanto quello che io ricordo di caricarci dentro quel giorno. Non c'è ancora niente di codificato che permetta al sistema di girare senza di me al comando.

Pensavo di essere oltre il principiante che smanetta col tab-complete. Sono, tecnicamente, un principiante che smanetta con uno strumento molto più sofisticato.

## Il punto di partenza (e le due mosse per questa settimana)

Detto questo, non è un verdetto, è un punto di partenza. E qui il corso, tolto il nome del prodotto che vuole vendere, lascia comunque due indicazioni concrete che ho intenzione di seguire questa settimana.

La prima: mettere per iscritto le regole del progetto. Non un elenco vago di buone intenzioni, ma un file preciso che nomini lo stack che uso davvero, le convenzioni a cui tengo, i pattern che voglio si ripetano, e tre o cinque cose che non voglio che l'agente faccia mai, punto. L'idea è che questo file diventi l'artefatto che permette a una versione futura del mio modo di lavorare di girare anche senza di me nella stanza, che poi è esattamente il problema che l'assessment ha appena messo a nudo.

La seconda: fare l'inventario di quello che incollo ogni giorno. Venti minuti, non di più, a scrivere tutto il contesto che do all'agente in una settimana tipo: riferimenti a file, screenshot, descrizioni di API al volo, "ricorda che avevamo deciso X la settimana scorsa". Quell'inventario è la materia prima per costruire la prima versione seria delle regole scritte sopra, e mi dice anche, onestamente, quali dei miei strumenti stanno facendo lavoro vero e quali sono solo rumore che mi sono affezionato a tenere.

C'è un collegamento che non posso ignorare con quello che mi aspetta tra ventisei giorni. Il livello di maturità del contesto oggi è anche, di fatto, il livello di rischio che mi porto dietro quando il tempo per "essere io il contesto" si restringerà drasticamente: da CTO non sarò più l'unico paio di mani sulla tastiera, e un sistema che dipende solo dalla mia memoria diventa un collo di bottiglia molto più stretto.

Non ho una tesi definitiva da chiudere qui, solo un punto di partenza onesto: sono un livello 2, con margine enorme di miglioramento, e ventisei giorni per fare qualche passo avanti prima che il gioco cambi davvero.

E voi, quanto siete maturi nell'AI engineering? Mi farebbe piacere confrontarmi, sono cose che si capiscono meglio parlandone. Sentiamoci!
