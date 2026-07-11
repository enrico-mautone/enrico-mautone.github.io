---
layout: post
title: "Il preventivo non si fa più a ore - cosa vendo davvero nell'era dell'AI agentica"
date: 2026-07-11 09:00:00 +0200
categories: [ai, career]
tags: [ai-agents, pricing, freelance, cto, agentic-ai]
---

Ieri ho seguito un corso sull'AI Act — il regolamento europeo che disciplina l'uso dei sistemi di intelligenza artificiale, in base al livello di rischio che comportano. Non è il tema di oggi, ci torno in un articolo dedicato più avanti.

Durante il corso è emersa una domanda, posta da un partecipante: "È lecito far esaminare il codice sorgente dei clienti all'AI per farci sviluppi sopra? O viola l'AI Act?". Risposta del docente: "No, non viola l'AI Act. Ma attenzione: magari non dite ai clienti che usate l'AI per scrivere codice, altrimenti non è più giustificabile chiedere compensi a ore uomo!!!"

Fulmine. Collegamento immediato: le ore/uomo sono una metrica che sta morendo? E se è così, cosa rispondo la prossima volta che un cliente mi chiede un preventivo per sviluppare un progetto SaaS?

Questo è il tema di oggi.

## Cosa sta succedendo ai vendor di tool AI

Non sono il solo a sbattere contro questo problema. Sta succedendo, in forma diversa, anche a chi vende gli strumenti che uso ogni giorno.

Fino a poco tempo fa, i tool di AI coding (Copilot, Cursor, Claude Code) si vendevano con un seat fisso al mese: pagavi una cifra, avevi accesso. Nel 2026 quasi tutti sono passati a un modello a consumo — credit o token metering — dove il seat è diventato un pavimento, non più un tetto. Usi di più, paghi di più, senza un limite chiaro in anticipo.

Il motivo è semplice: un agente che lavora per minuti o ore consuma inferenza reale, e il prezzo fisso stava sussidiando silenziosamente chi lo usava di più. Gartner ha lanciato un allarme che dà la misura del problema: entro il 2028, il costo AI di un developer potrebbe superare il suo stesso stipendio.

Il parallelo con il mio caso è diretto. Se anche chi vende lo strumento non riesce più a far quadrare un prezzo fisso legato al tempo o all'accesso, e deve legare il prezzo a quanto lavoro reale viene fatto — perché io dovrei riuscire a farlo quadrare legando il mio prezzo alle ore che ci metto?

E qui torno alla domanda che mi è rimasta in testa dal corso: è corretto, caro mio docente, far pagare i clienti a ore/uomo anche quando sviluppi tramite AI? Il consiglio che hai dato — non dirlo ai clienti, altrimenti non è più giustificabile chiedere compensi a ore — è davvero allineato allo spirito dell'AI Act e al suo utilizzo lecito, o è semplicemente un modo elegante per non affrontare il problema? Un regolamento che nasce per garantire trasparenza sull'uso dell'AI difficilmente può conciliarsi con un consiglio che dice, in sostanza, di nasconderlo al cliente per continuare a fatturare come prima.

## Perché "stima ore + margine di sicurezza" non funziona più

Il modo in cui la maggior parte di noi ha sempre fatto i preventivi è questo: una call con il cliente, una stima a spanne delle ore necessarie, e poi un margine di sicurezza — il classico 30-50% "per gli imprevisti" — spalmato sopra. Funzionava perché il tempo di sviluppo era la variabile più prevedibile che avevamo. Non era precisa, ma era stabile.

Con l'AI agentica quella stabilità è saltata. La stessa feature, con lo stesso cliente e lo stesso rischio, può costarmi due ore o due giorni a seconda di quanto l'agente "prende bene" il contesto del codice esistente — cosa che scopro solo mentre lavoro, non prima. Il tempo non è più proporzionale alla complessità del problema: è proporzionale a quanto l'AI si comporta bene su quello specifico problema, e questo lo so solo a consuntivo.

Il risultato è un incentivo perverso doppio. Da un lato, se fatturo a ora, sono penalizzato ogni volta che l'AI mi fa risparmiare tempo — guadagno meno per lo stesso output. Dall'altro, se gonfio le ore per compensare, sto chiedendo al cliente di pagare un margine di sicurezza calcolato su un'unità di misura (l'ora) che non rappresenta più in modo affidabile né il lavoro svolto né il rischio corso. Non sto stimando meglio o peggio: sto misurando la cosa sbagliata.

## Le alternative reali che il mercato sta provando

Se l'ora non funziona più come unità di misura, cosa la sostituisce? Guardando cosa stanno provando altri — vendor SaaS, agenzie, consulenti — emergono tre strade, non ancora una sola vincente.

**Outcome-based pricing.** Paghi solo per il risultato, non per il tentativo. Intercom fa pagare $0.99 per ogni conversazione di supporto risolta dal suo agente AI — se non risolve, il cliente non paga quell'interazione. Zendesk fa lo stesso a $1.50-2.00 per risoluzione automatica. Trasportato al software: pagherei per una feature che funziona e passa i test di accettazione, non per le ore spese a costruirla. È il modello più elegante sulla carta, ma anche il più acerbo — si stima un'adozione ancora intorno al 30%, e crea complicazioni contabili non banali su come e quando si riconosce il ricavo.

**Value-based pricing.** Il prezzo diventa una frazione del valore che genero per il cliente, non del tempo che ci metto. Se un progetto gli fa risparmiare 100.000€ l'anno in processi manuali, io prezzo una percentuale di quel valore — tipicamente 10-25% — puntando a un ROI per il cliente di circa 5x quello che mi paga. Il problema è che richiede quantificare il valore *prima* di iniziare, cosa che con un cliente nuovo o un progetto poco definito è difficile quanto stimare le ore.

**Discovery a pagamento + fixed price a milestone.** Il compromesso più pragmatico per chi lavora a commessa, come me: una fase di discovery breve e pagata (tipicamente 1.500-3.000€) per capire davvero la complessità del progetto, seguita da un prezzo fisso legato a milestone concrete con criteri di accettazione espliciti — non ore stimate e poi imbottite, ma uno scope chiaro con un margine di rischio dichiarato apertamente, non nascosto dentro un numero di ore gonfiato.

Nessuno di questi tre è "il" modello del 2026: la fotografia reale è ibrida, con aziende che mescolano una base fissa, un tetto di utilizzo e componenti a risultato sopra.

## Cosa userei io, concretamente, per un preventivo software oggi

Tra le tre strade, quella che userei per un progetto SaaS oggi è la terza — discovery a pagamento + fixed price a milestone — perché è l'unica che non richiede di conoscere in anticipo cose che semplicemente non posso sapere: quanto vale esattamente il progetto per il cliente, o quanto bene si comporterà l'AI su quel codice specifico. Propongo un framework in tre passi.

**1. Discovery breve e pagata.** Prima di qualsiasi preventivo, un blocco di tempo definito (qualche giorno, non settimane) per capire davvero cosa sto quotando: architettura esistente se c'è, integrazioni necessarie, requisiti non ovvi. Il cliente paga questa fase separatamente, a cifra fissa e contenuta. Serve a togliermi dalla posizione di dover indovinare, e mette subito in chiaro che il mio tempo ha un valore anche quando non sto ancora scrivendo codice.

**2. Scope con milestone e criteri di accettazione, non ore.** Il preventivo che esce dalla discovery non elenca ore per attività — elenca cosa verrà consegnato, in che fasi, e come si verifica che ogni fase è fatta bene. Il prezzo è legato alla consegna di quella milestone, non al tempo che ci ho messo per arrivarci. Se l'AI mi fa risparmiare tempo su una milestone, il guadagno resta mio — è il vantaggio di aver smesso di vendere ore.

**3. Prezzo ancorato al valore/outcome, margine di rischio esplicito.** Dove riesco a quantificare il valore per il cliente (tempo risparmiato, revenue abilitato, costi evitati), lo uso per ancorare il prezzo verso l'alto rispetto al puro costo di produzione. E il margine per l'incertezza tecnica — quanto è "nuovo" per me quel dominio, quanto è probabile che l'AI serva più supervisione del previsto — lo dichiaro al cliente come voce separata, non lo nascondo dentro un moltiplicatore di ore che lui non può verificare.

Il punto in comune ai tre passi è questo: sposto quello che vendo dal *tempo che ci metto* a *cosa consegno e quanto vale*. Non è un modello perfetto né definitivo — è il migliore compromesso che ho trovato tra onestà verso il cliente e sostenibilità per me.

## Il vero skill che vale premium ora

C'è una domanda sotto tutto questo ragionamento sul pricing: se non vendo più ore, cosa sto vendendo esattamente? La risposta a cui sono arrivato è che il lavoro che vale un premium nel 2026 non è più scrivere codice più in fretta — quello lo fa l'AI, e lo fa bene. È il giudizio che sta prima e sopra quel codice: capire cosa vale la pena costruire, cosa no, dove sta il vero rischio del progetto, quali scorciatoie oggi si pagano care domani.

L'AI esegue in modo eccellente un piano che le do. Non decide da sola se quel piano è quello giusto, non sa dirmi se il cliente sta chiedendo la funzionalità sbagliata, non capisce quando un requisito "semplice" nasconde un problema architetturale che esploderà al terzo sprint. Quel tipo di giudizio — maturato su vent'anni di codice scritto a mano, di progetti andati bene e male, di errori pagati di persona — è la cosa che oggi non si automatizza, ed è anche la cosa più difficile da metter su un preventivo perché non si misura in ore né in righe di codice.

Non è un caso che questo ragionamento mi trovi proprio ora, nella transizione da Service Manager a CTO di una startup che ho contribuito a fondare. Il ruolo di CTO non si paga per le ore passate a scrivere codice — si paga per le decisioni prese su cosa costruire, con quali rischi, e con quali strumenti. Sto scoprendo che il modo in cui vorrei fatturare ai clienti esterni e il ruolo che sto assumendo internamente stanno convergendo sullo stesso principio: il valore sta nel giudizio, non nell'esecuzione.

## Chiusura

Non ho una risposta chiusa a questo. Il pricing del software nell'era dell'AI agentica è ancora, oggi, un'area transitoria e ibrida — anche i grandi vendor che hanno le risorse per testare modelli diversi non hanno trovato un unico schema vincente, e stanno mescolando basi fisse, tetti di utilizzo e componenti a risultato. Se loro, con tutti i dati che hanno, sono ancora in fase sperimentale, io da solo non pretendo di aver trovato la formula definitiva.

Quello che ho, per ora, è un principio più chiaro di prima — smettere di vendere tempo e iniziare a vendere consegna e giudizio — e un framework pratico da testare sul prossimo preventivo reale che scrivo. Non lo so ancora se funzionerà come immagino: lo scoprirò quando lo proverò con un cliente vero, e probabilmente tornerò a scriverne con quello che avrò imparato.

Se anche a te è capitato di sbatterci contro — un preventivo che non ti convinceva, un cliente che ha notato che ci hai messo "troppo poco" tempo per quanto ti ha pagato — mi farebbe piacere confrontarmi. È esattamente il tipo di problema che si risolve meglio parlandone che pensandoci da solo.
