+++
title = 'Perché Hugo?'
date = 2023-10-16T10:19:10+02:00
series = 'gestione sito web'
description = 'Esplorando i motivi che mi hanno portato a spendere ore che mi sarei potuto risparmiare scegliendo un altro modo per pubblicare questo sito.'
tags = ['personale', 'esplorazione', 'tecnologia']
+++

## Introduzione

Con la moltitudine di strumenti disponibili oggi per creare un sito web, la maggior parte plug and play, viene da chiedersi perché io abbia deciso di usare un metodo meno basilare — *Hugo* per i curiosi — e complicarmi la vita.

Avrei potuto creare un blog simile su WordPress e risparmiarmi 4-5 ore di lavoro, mantenendo le stesse funzionalità.

Questo è un articolo esplorativo in cui cerco di capire le motivazioni che mi hanno portato a fare questa scelta.

## La ragion d'essere del blog
La ragion d'essere del blog è quella di **offrirmi uno spazio creativo** senza regole.

Perché un blog personale nel 2023? 

C'è LinkedIn. C'è Twitter, c'è Facebook, c'è Instagram, c'è...tutto quello che c'è là fuori. 

Un blog? Non avrei potuto usare una piattaforma che ha già tanto traffico e catturarne la parte che mi interessa? Che poi non vale lo stesso su tutto internet? Tra SEO e intenti di ricerca e parole chiave, sto comunque cercando di emergere tra milioni di altre persone.

Ma, come dice Marshall McLuhan, "il mezzo è il messaggio". Quello che posto su LinkedIn ha un taglio adatto a LinkedIn e viene letto in "modalità LinkedIn"(in realtà penso di non aver ancora affinato la tecnica, ma ci stiamo lavorando). 

Ci sono delle convenzioni non scritte da seguire. Ci sono dei tipi di contenuti che fanno meglio di altri. C'è un algoritmo che decide cosa mostrare. 

L'unico algoritmo che vige su questo blog è il mio cervello — influenzato mimeticamente e socialmente quanto vuoi — ma comunque con una prospettiva mia.

E per gli appassionati del "wow ma stai usando dati/corrente per il blog", posso garantirvi che questo blog consuma in un mese quello che consumate in 2 giorni di browsing sui social. Probabilmente anche meno.

Ora comincia la parte divertente, quella esplorativa.

## La ricerca del mezzo adatto 
Quando una persona senza particolari competenze di sviluppo web decide di creare un sito web ha bisogno di due cose:
1. Che il sito sia semplice da creare 
2. Che il sito sia facile da aggiornare

La risposta standard a entrambe le domande, che trovi in ogni singola ricerca web, è WordPress (WP).

Ma io volevo creare un semplice sito monopagina. Usare WordPress sarebbe stato come usare una 

### Perché non WordPress?

Qualsiasi host offre piani con WP già installato. I piani "vaniglia" hanno script nel proprio pannello di controllo (come cPanel) che ti permettono di installarlo con un click. Una volta installato scegli il tema che preferisci; da lì dovrai solo cliccare sugli elementi che vuoi modificare e seguire le istruzioni a schermo.

WP ha un massiccio editor di testo condito con funzionalità per il web. Aggiungere l'alt-text alle immagini è un attimo, così come cambiare titolo e description "meta" (quelle che appaiono nei risultati di Google). In più ha una libreria di plugin con cui puoi fare veramente di tutto. Editor visuali, plugin per la SEO, plugin per il caching del sito, CDN per immagini...

E quindi, **perché non WordPress**? WP è un software fantastico, ma...

- È *lento*, specie per uno come me che vuole mettere le mani ovunque. La farraginosità mi uccide l'entusiasmo. Caricare un'immagine richiede più tempo della mia soglia dell'attenzione bruciata da internet
- È *bloated* (termine tecnico per software che si traduce in gonfio), ha tantissime funzionalità che cercano di coprire il maggior numero di casi di uso possibili. Ottimo, ma è troppo per quello di cui ho bisogno io
- È *dispersivo*, con tanta complessità nascosta. È semplice iniziare a creare siti con WordPress, ma diventa difficilissimo molto in fretta appena vuoi fare qualcosa un minimo fuori dagli schermi

Volendo evitare questi problemi, ho cercato soluzioni più minimaliste possibili, finendo su Hugo.

### La scoperta di Hugo
Lungi da me il capire cosa cambia tra un sito creato in Hugo, WordPress, Wix, o fatto a mano.

So solo che volevo un sistema più semplificato e veloce possibile. E qui finisco su un video di Luke Smith, coder e writer con degli ideali che si adattavano perfettamente alla mia ricerca.

Seguo il suo video su Hugo, spulcio il sito web, e sono subito convinto: devo creare un sito con questo. O 2. Sembra divertente e stimolante, e poi sono un content writer specializzato nel settore tech: davvero devo limitarmi ad una tecnologia che non mi fa impazzire come WP?

In più mi piace sempre scegliere la strada meno battuta. Non che Hugo sia questo signor sconosciuto che mi rende hipster, però mi ha soddisfatto.

Ed eccoci qui...circa.

## Le peripezie
Per installare Hugo e creare un sito sono bastati un paio di comandi nel terminale. Ottimo. Dopo aver scelto un tema, vedo che basta scaricarlo ed indicarne il nome nel file di configurazione del sito. 

Qui è dove ho speso il grosso del tempo. Ho cercato di fare tante, troppe cose per capire bene il funzionamento del framework. Grazie a ChatGPT per l'infinita pazienza e preparazione. Sarebbe stato impensabile far tutto da solo. 

Non so ancora quasi niente di Hugo. Non ho guardato gli shortcodes, né ho ben capito come funziona il contenuto servito tramite parentesi graffe nei vari file html. 

Ho anche dovuto lottare col tema attuale per cercar di aggiungere un link alla homepage nella barra laterale. Sì, sia il nome che la foto profilo sono già link alla homepage, ma averne una testuale mi sembrava una scelta intelligente. 

Le ho provate tutte:

- Ho cercato di creare un link con URL "/"
- Ho reso la pagina about l'homepage 
- Ho provato a reindirizzare l'about alla homepage
- Ho provato a barare coi parametri di Hugo

Tutto questo non ha funzionato. A questo punto mi viene da dire che *questo tema non accetta il link base nella barra laterale*. Probabilmente è un attimo ritoccarlo, ma non lo so fare, né lo sanno fare ChatGPT e Bing AI. Poco male. 

Anche spostare la homepage dalla pagina [posts](/posts) alla homepage ha richiesto un intervento che non saprei spiegare. Ma ora funziona e va bene così. Penso la soluzione giusta fosse l'aver creato un file apposito intitolato homepage.md. 

## Ne è valsa la pena?

Direi di sì. Ora ho un epico sito web che si renderizza in una decina di millisecondi. Per avviare un nuovo post mi basta un comando nel terminale di VS Code:

	hugo new content/posts/titolo-post.md

Per SEO fan hardcore, aggiungere la meta description si fa aggiungendo alla front matter:

    description = 'questa è la meta description'

Hugo usa il markdown, un linguaggio con cui sono a mio agio e che mi permette di renderizzare il testo come meglio credo. E non ho vincoli a software legnosi per scrivere (ti vedo, Microsoft Word).

Tutti i file sono sul mio PC e posso gestirli come meglio credo. E non ci sono decine di codici occulti che mi impediscono di capire come diamine funziona il mio sito. 

Ora che il sito funziona, posso dedicarmi ad esplorare altre funzionalità di Hugo ed occuparmi della gestione del sito in sé. Ecco cosa voglio fare ora che tutto funziona come dovrebbe:

- Capire bene come funzionano meta title e description
- Padroneggiare la parte di design del sito (ho in mente un paio di progetti web e WordPress mi ha sempre fatto desistere in partenza)
- Capire cosa posso fare con gli shortcodes
- Implementare tracciamento dati senza Google Analytics, e imparare a gestire il software che intendo usare ([Plausible](https://plausible.io))

Dopo aver gestito questo sito per un paio di settimane ed aver imparato a rompere niente, mi imbarcherò in un progetto più complesso. 

## Tutto bello ma...quindi?
Penso che scriverò cose di cui non frega niente a nessuno. Sarà una specie di diario online su certe cose che penso navigando online.

Il blog da content marketer purosangue quale sono lo farò quando avrò preso dimestichezza con Hugo; immagino a breve. Lo linkerò comunque.