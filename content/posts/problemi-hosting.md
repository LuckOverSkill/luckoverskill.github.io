+++
title = "Le peripezie per l'hosting del sito"
date = 2023-10-17T11:12:46+02:00
series = 'gestione sito web'
description = 'Riuscire a hostare il sito seguendo il processo che volevo si è rivelato tortuoso. In questo articolo ripercorro i vari passi, analizzando cosa è andato storto.'
tags = ['Hugo']
+++

Per riuscire a hostare il sito come lo volevo e col sistema che volevo, ossia:

1. Creare nuovo post col comando `hugo new`
2. Scriverlo su [Ghostwriter](https://github.com/KDE/ghostwriter)
3. Aggiungerlo alla cartella posts su VS Code
4. Cliccare su "Commit"
5. Fine

Ho speso svariate ore. Alla fine non è come l'ho descritto, ma il nuovo metodo che uso mi va bene. 

## Cosa è andato storto
La colpa è del file README del tema che ho scelto, [poison](https://github.com/lukeorth/poison). Nella sezione *installation* troviamo:

	git clone https://github.com/lukeorth/poison.git themes/poison --depth=1

Ma così facendo, al momento del deploy del sito, ho ottenuto un errore che mi ha quasi fatto cancellare tutto. L'errore riguardava i *git submodule*, che sono una funzionalità avanzata per progetti grossi.

Ho provato di tutto per far collaborare l'host, ma non ce l'ho fatta. Allora ho deciso di cambiare tema, spostandomi su [hugo-bearcub](https://github.com/clente/hugo-bearcub).

Solo che non mi piaceva molto il layout, o meglio, mi piaceva, ma ormai mi ero affezionato a quello che vedi su questo sito. Più non supporta le serie out of the box, anche se penso bastasse aggiungere il relativo shortcode nella sezione *taxonomies* del file di configurazione.

Sono tornato a poison, deciso questa volta a farlo funzionare.

## Come ho risolto

Ricercando i diversi temi, ho notato che la maggior parte suggerivano di usare

	git submodule <link al sito>
	
E non `git clone`. 

Svelato l'inghippo. 3 ore di lavoro evitabili con il comando giusto all'inizio.

Restava comunque il problema di linkare VS Code a Github. Qui sono stato salvato da ChatGPT (anche se non subito, le prime due soluzioni che ha proposto si sono rivelate fallimentari).

Se ho ben capito, i problemi che ho affrontato, in ordine, sono stati:

1. Collegare VS Code a GitHub. Abbastanza semplice, si tratta di fare login all'account GitHub tramite VS Code 
2. Creare una repository su GitHub su cui caricare i file del sito generati da Hugo
3. Fare `git init` nella cartella root del sito web per avviare Git
4. Eseguire il comando `git remote add origin <URL della repository>` per far capire a VS Code che quando dico di fare cose a "origin" mi riferisco alla repository linkata nell'URL
5. Eseguire il comando `git add .` per aggiungere tutti i file della cartella root alla "staging area", ossia ai file pronti a essere caricati nella repository
6. Eseguire il comando `git commit -m "messaggio"` per fare il commit dei cambi (in pratica dare l'ok al software per fargli capire che i file sono a posto così, e cosa è cambiato nel messaggio)
7. Eseguire il comando `git push -u origin master` per finalmente caricare i file sulla repository. Da lì un workflow automatizzato per Hugo (impostato in *Action*) genera il sito web.
8. Per aggiungere i post futuri al sito, basterà inserire nel terminale `git add posts/nomefile.md`, fare `git commit -m "nuovo post"`, e poi `git push origin master`

Ma [non sarebbe stato meglio usare WordPress?](/posts/perche-hugo) Specie considerando che quest'ultima parte mi ha preso altre 3 ore circa, che ovviamente mi sarei potuto risparmiare scegliendo WP.

La risposta resta no, come ho scritto nel post linkato. Ora conosco le basi di Git, che penso sia molto importante in un'era come la nostra. GitHub è zeppo di software utile, e quando sei su Linux come me capire come funziona Git viene comodo.

Detto questo, la prossima volta uso [bearblog](https://bearblog.dev/). 