---
title: "Installazione pulita driver video"
date: "2022-11-11"
tags: ["ITA"]
---

Ti è mai capitato di avere glitch grafici, cali prestazionali o crash inspiegabili delle tue app di grafica preferita o durante sessioni di gaming? In questi casi, spesso, è necessario effettuare un’installazione pulita dei driver video.

I driver video, nel loro insieme sono la componente software che permette alla tua GPU (scheda video) di fare il suo lavoro. Operano ad un livello privilegiato del sistema operativo (kernel level o ring 0 sulla maggior parte delle architetture) e un loro malfunzionamento può portare ai problemi citati poc’anzi. 

Scendiamo ora nel dettaglio per capire come effettuare un’installazione **************pulita************** (cioè da zero) di questi driver. Per andare avanti con questa guida ti serviranno:

- Ultima versione dei tuoi driver video compatibili
    - GPU NVidia: [https://www.nvidia.it/Download/index.aspx?lang=it](https://www.nvidia.it/Download/index.aspx?lang=it)
    - GPU AMD: [https://www.amd.com/en/support](https://www.amd.com/en/support)
    - GPU Intel (integrata nel tuo processore): [https://www.intel.it/content/www/it/it/support/intel-driver-support-assistant.html](https://www.intel.it/content/www/it/it/support/intel-driver-support-assistant.html)
- Ultima versione di ************Display Driver Uninstaller (DDU):************
    - [https://www.guru3d.com/files-details/display-driver-uninstaller-download.html](https://www.guru3d.com/files-details/display-driver-uninstaller-download.html)
- Ultimi aggiornamenti del tuo sistema operativo:
    - Puoi effettuare la ricerca di tali aggiornamenti direttamente dall’interfaccia del tuo sistema operativo. Nel caso in cui fossero disponibili degli aggiornamenti installali, riavvia il PC e continua con la guida, altrimenti ignora questo passaggio.

## Preparazione del tuo PC

Prima di andare avanti è necessario **********************scollegare********************** il tuo PC da internet. Il motivo per cui questo passaggio è necessario è per impedire al sistema operativo di reperire in autonomia i driver video una volta disinstallati con DDU. Normalmente questa cosa non è un problema, perchè il vostro sistema operativo installerà i driver corretti, tuttavia, al fine di ottenere il massimo da questa guida è bene scollegare il PC da internet in modo tale che l’installazione dei driver sia totalmente manuale, scongiurando la possibilità di conflitti. 

Una volta disconnesso il tuo PC, procedi a riavviarlo in ****************************************modalità provvisoria****************************************, seguendo le indicazioni che puoi trovare sul web su come fare questa cosa. Può capitare che i passaggi cambino tra una versione e l’altra del sistema operativo, motivo per cui non includerò qui i dettagli.

## Disinstallazione driver con DDU

Una volta completati i passaggi precedenti, se hai fatto tutto correttamente, dovresti trovarti in ****************************************modalità provvisoria.**************************************** 

A questo punto estrai il file DDU scaricato in precedenza:

![1.png](/stat-assets/01/1.png)

Continua con l’estrazione dell’eseguibile:

![2.png](/stat-assets/01/2.png)

**********N.B.********** Io sto usando 7-zip, l’interfaccia potrebbe cambiare in base al tuo gestore di archivi (winrar, unzip, ecc).

Apri la cartella con DDU estratto:

![3.png](/stat-assets/01/3.png)

Esegui ************************************************************Display Driver Uninstaller.exe,************************************************************ al primo avvio ti apparirà questa finestra. Le impostazioni predefinite vanno bene, quindi fai “Chiudi” in basso a destra.

![4.png](/stat-assets/01/4.png)

A questo punto, dall’interfaccia di DDU seleziona 1. il produttore della tua GPU (NVidia, AMD o Intel), 2. seleziona il tipo di driver da rimuovere (Scheda video o Scheda audio), 3. fai click su **********************************Pulisci e Riavvia**********************************

![5.png](/stat-assets/01/5.png)

Nel mio caso, ad esempio, ho una scheda grafica NVidia quindi l’interfaccia finale sarà questa:

![6.png](/stat-assets/01/6.png)

Una volta terminata la disinstallazione dei driver il tuo PC si riavvierà normalmente.

## Installazione nuovi driver

Se tutto è andato per il verso giusto a questo punto il tuo PC dovrebbe essere acceso normalmente, senza modalità provvisoria ********************************************************************************************************************In questa fase devi essere ancora disconnesso da internet.******************************************************************************************************************** 
Puoi procedere ora con l’installazione dei driver scaricati in precedenza dal sito del produttore. Una volta terminata l’installazione **********************************************************riavvia normalmente il tuo PC********************************************************** ancora una volta e successivamente riconnettiti ad internet! 

Congratulazioni, hai terminato tutti i passaggi! Goditi i tuoi driver video e i tuoi videogiochi preferiti!