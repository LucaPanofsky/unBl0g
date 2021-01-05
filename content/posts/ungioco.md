---
title: "I Giochi"
date: 2020-12-31T19:31:45+01:00
author: Luca Panofsky
draft: false
year: "2020"
month: "2020/12"
categories:
  - Teoria dei Giochi
tags:
  - giochi
  - preferenze
  - simultaneità
  - payoff
---

La teoria dei giochi è un ramo della matematica che si occupa dello studio dei _giochi_. Un gioco è una situazione strategica in cui le scelte di due o più soggetti concorrono nel determinare un comune stato del mondo.
Ragioniamo in modo strategico ogni qual volta ci accorgiamo che le conseguenze di ciò che accade non dipendono semplicemente dal nostro comportamento ma anche dal comportamento degli altri e teniamo conto di tutto ciò mentre prendiamo le nostre decisioni.

La teoria di giochi studia le _regolarità_ nei giochi e le sue applicazioni sono veramente infinite, spaziano dalla biologia all'informatica ed è ormai uno strumento d'analisi standard in molte discipline sociali. La teoria dei giochi è un linguaggio per parlare di fenomeni complessi attraverso intuizioni strategiche. Spesso queste intuzioni sono astratte, altre volte invece possono avere un vero e proprio valore normativo come nel disegno degli schemi di voto, nelle aste e nei protocolli distribuiti. In questi post ci occuperemo di teoria dei giochi e cominciamo cercando di capire *che cos'è un gioco*.

## gioco

Una situazione strategica tra più giocatori è un gioco. Possiamo descrivere un gioco come gli scacchi o una guerra tra paesi, negoziazioni e situazioni ancora più complesse.

Un gioco è costituito da pochi elementi fondamentali:
- i giocatori (chi sono i soggetti coinvolti?)
- le azioni (quali scelte possono prendere i giocatori?)
- le preferenze (in che modo valutano i giocatori i possibili eventi?)
- l'informazione (che cosa sanno i giocatori del gioco e degli altri giocatori?)
- la dinamica (in quale ordine vengono prese le scelte?)

I giocatori sono i soggetti coinvolti nel gioco e sono liberi di prendere delle azioni. Queste azioni dipendono dal contesto e variano da gioco a gioco. Un evento, o outcome, è una descrizione delle scelte fatte da ogni singolo giocatore e gli outcome comportano delle conseguenze. I giocatori sono in grado di valutare le conseguenze derivanti dagli outcome e di ordinare gli outcome secondo un criterio di preferenza. Possono avere informazioni diverse riguardo gli altri giocatori o lo stato del gioco e le scelte possono essere prese simultaneamente o in un ordine ben preciso.

Studiamo i giochi perché siamo interessati alla evoluzione del sistema strategico che descrivono. Una soluzione di un gioco è un outcome che soddisfa particolari proprietà. Esistono diversi concetti di soluzione e ognuno di essi propone intuizioni diverse per spiegare le possibili evoluzioni di un gioco. Avremo modo di parlare delle soluzioni dei giochi nei prossimi post mentre ora ci dedichiamo alla loro rappresentazione.

Il gioco più semplice che possiamo immaginare è un semplice gioco *dinamico* tra due giocatori in cui la prima mossa spetta al *giocatore 1* e la seconda al *giocatore 2*. Dopodiché, il gioco termina con la manifestazione delle conseguenze relative all'outcome realizzato. Prima di parlare delle conseguenze però entriamo nei dettagli del gioco.

I giocatori sono liberi di scegliere una tra due possibili azioni `A` e `B`. I giocatori conoscono il gioco ma non sempre il secondo è in grado di osservare l'azione presa dal primo. Quando il *giocatore 2* osserva l'azione presa dal *giocatore 1* diciamo che è *informato*, altrimenti non lo è. Possiamo rappresentre le due varianti del gioco attraverso degli *alberi*

{{< figure class="img-fluid" src="https://vectr.com/lucapanofsky/b1rLmaKimj.svg?width=600&height=400&select=b1rLmaKimjpage0"
width="100%" >}}

 Un albero è composto da nodi e da rami. Un nodo rappresenta un punto del gioco e può avere tanti rami tante quante sono le azioni disponibili al giocatore chiamato a scegliere in quel preciso punto del gioco. A volte un giocatore è incerto riguardo la sua posizione nel gioco. In questi casi utilizziamo un contenitore, chiamato *information set*, per racchiudere tutti i nodi decisionali in cui un giocatore crede di poter essere in un determinato momento del gioco. Nel secondo albero i nodi del *giocatore 2* appartengono a un un unico information set. In altre parole, dopo la scelta del primo giocatore il secondo non è in grado di dire in quale dei due nodi si trova. I nodi dai quali non discendono rami sono nodi terminali e rappresentano gli outcome del gioco.

Quando il secondo giocatore non è informato, nessun giocatore ha un particolare vantaggio informativo nonostante la dinamica del gioco. In questi casi è come se il gioco fosse simultaneo e preferiamo rappresentarlo attraverso una tabella.

{{< figure class="img-fluid" src="https://vectr.com/lucapanofsky/bEhz7cymy.svg?width=550&height=396&select=bEhz7cymypage0" width="50%" >}}

In questo modo possiamo descrivere giochi simultanei o giochi dinamici in cui la struttura informativa del gioco annulla possibili vantaggi o svantaggi della prima mossa. Le righe e le colonne della tabella rappresentato rispettivamente le possibili azioni del *giocatore 1* e del *giocatore 2*. Le celle invece i possibili outcome del gioco.

Un outcome è un profilo di azioni la cui realizzazione produce delle conseguenze. Il gioco che abbiamo descritto ha `2 x 2 = 4` possibili outcome ai quali possiamo associare delle conseguenze, ovvero dei numeri chiamati payoff. I payoff sono unità immaginarie che modellano le preferenze dei giocatori rispetto agli outcome secondo questo semplice criterio:

*un outcome x è preferito ad un outcome y se e solo se il payoff associato a x è maggiore del payoff associato ad y*.

La scelta di modellare le preferenze attraverso i payoff non è innocua, tuttavia ci permette di iniziare a ragionare sui giochi e di sporcarci le mani. Il tema delle preferenze merita una discussione a parte, per il momento proseguiamo con i seguenti payoff

{{< figure class="img-fluid" src="https://vectr.com/lucapanofsky/bhAeFVl26.svg?width=350&height=350&select=bhAeFVl26page0" width="50%" >}}

che possiamo tradurre come

*il giocatore 1 preferisce l'outcome `(B,A)` all'outcome `(A,A)`, preferisce l'outcome `(A,A)` all'outcome `(B,B)` e preferisce l'outcome `(B,B)` all'outcome `(B,A)`*

*il giocatore 2 preferisce l'outcome `(A,B)` all'outcome `(A,A)`, preferisce l'outcome `(A,A)` all'outcome `(B,B)` e preferisce l'outcome `(B,B)` all'outcome `(A,B)`*

Possiamo verificare facilmente che i payoff che abbiamo scelto riflettono le preferenze descritte. Per esempio è vero che il *giocatore 1* preferisce `(B,A)` a `(A,A)` in quanto `2 > 1`. I payoff descrivono una relazione di preferenza e siamo interessati al loro ordinamento piuttosto che alla loro grandezza. Quando siamo interessati alla grandezza di questi numeri le preferenze vengono dette *cardinali* e ci permettono di esprimere preferenze in condizioni di incertezza e relazioni più complesse.

Dopo queste brevi considerazioni possiamo rappresentare il gioco in *forma strategica* esprimendo una relazione diretta tra outcome e i payoff in questo modo

{{< figure class="img-fluid" src="https://vectr.com/lucapanofsky/azIFvyUUi.svg?width=500&height=400&select=azIFvyUUipage0" width="50%" >}}

Grazie a questa rappresentazione è molto semplice riflettere strategicamente sul gioco. In particolare le preferenze che abbiamo descritto suggeriscono una situazione in cui possiamo decidere se essere, in un certo senso, cooperativi o meno. Per convincerci di ciò proviamo a discutere i vari possibili outcome del gioco. Esiste un unico outcome, l'evento `(A,A)`, in cui entrambi i giocatori ottengono un payoff positivo e chiamiamo questo outcome del gioco *cooperativo*. In tutti gli altri casi, almeno un giocatore ottiene un payoff negativo. In particolare abbiamo un outcome, l'evento `(B,B)`, in cui entrambi i giocatori ottengono un payoff negativo e altri 2 outcome in cui il giocatore non collaborativo ottiene un payoff positivo a scapito del giocatore collaborativo che ottiene un payoff negativo, gli eventi `(A,B)` e `(B,A)`.

Il gioco evidenzia un dilemma cooperativo noto come *dilemma del prigionerio* che viene spesso raccontato attraverso una storia di questo tipo:

Due criminali vengono accusati di aver commesso un reato e vengono arrestati. Gli investigatori li chiudono in due celle diverse, impedendo loro di comunicare. Ad ognuno di loro vengono date due scelte: collaborare, oppure non collaborare. Viene inoltre spiegato loro che:
- se solo uno dei due collabora accusando l'altro, chi ha collaborato evita la pena; l'altro viene però condannato a 2 anni di carcere;
- se entrambi accusano l'altro, vengono entrambi condannati a 1 anno;
- se nessuno dei due collabora, entrambi vengono condannati a 6 mesi di carcere, perché comunque già colpevoli di porto abusivo di armi.

Un prigioniero preferisce sempre evitare il carcere e preferisce meno anni di carcere a più anni di carcere. Per rappresentare queste preferenze attraverso i payoff possiamo attribuire ad ogni outcome una coppia di numeri correlati negativamente con gli anni di carcere.

{{< figure class="img-fluid" src="https://vectr.com/lucapanofsky/i1MNbCiswO.svg?width=527&height=400&select=i1MNbCiswOpage0" width="50%" >}}

Il dilemma del prigioniero non ha una rappresentazione unica dei payoff, al contrario tutti i giochi in cui i payoff riflettono le preferenze che abbiamo descritto sono un dilemma del prigioniero.

{{< figure class="img-fluid" src="https://vectr.com/lucapanofsky/cNFBKDAT9.svg?width=940&height=455&select=cNFBKDAT9page0" width="100%" >}}

Il gioco a sinistra è un dilemma del prigionerio mentre il gioco a destra non lo è e descrive una diversa interazione strategica.
Prima di leggere il prossimo post provate a riflettere su questi giochi cercando di formulare una soluzione, cioè una argomentazione in favore di un particolare svolgimento del gioco, in altre parole il vostro concetto di soluzione.
