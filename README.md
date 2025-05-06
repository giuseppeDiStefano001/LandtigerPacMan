🕹️ Pac-Man per LandTiger 1768

Questo progetto implementa una versione semplificata e interattiva del gioco Pac-Man sulla scheda LandTiger 1768, utilizzando lo schermo LCD, i pulsanti e il joystick della scheda. Il progetto sfrutta l’interazione tra utente e sistema in maniera efficiente, grazie alla gestione dei timer e alla modalità power-down per ridurre il consumo energetico.
📁 Struttura del Progetto
Sample.c

In questo file vengono inizializzate e configurate le principali periferiche:

    Schermo LCD

    Pulsanti

    Joystick

    Timer RIT e Timer0

Dopo l'inizializzazione, il programma entra in power-down mode, garantendo efficienza energetica e interazione fluida tra utente e sistema.
Pacman.h

Contiene tutte le dichiarazioni necessarie al funzionamento del gioco:

    Struttura della mappa di gioco

    Variabili per posizione di Pac-Man, pillole e power pills

    Gestione del punteggio

    Prototipi delle funzioni per il disegno grafico (muri, pillole, Pac-Man)

    Funzioni per la gestione del movimento e delle interazioni

Pacman.c

Gestisce la logica grafica del gioco tramite una matrice (map), con la funzione:
turnMapIntoPixels()

Scorre la matrice e disegna ogni cella in base al suo valore:

    0: sfondo nero

    1: muri del labirinto (blu)

    2: posizione di Pac-Man

    3: pillola standard (incrementa contatore)

    6: cancello centrale (rosso)

Il movimento di Pac-Man è gestito dalla funzione:
updatePacmanPosition()

    Pulisce la cella precedente

    Controlla la cella di destinazione:

        Vuota: muove Pac-Man e gestisce il teletrasporto

        Pillola standard: la consuma, aumenta il punteggio

        Power pill: la consuma, aumenta il punteggio

    Aggiorna le variabili di posizione

IRQ_timer.c

Gestisce l’interrupt del Timer0:

    Monitora il tempo di gioco (contatore decrementale)

    Mostra messaggi di "PAUSA" o "GAME OVER"

    Controlla la generazione delle power pills:

        Usa il valore di LPC_TIM0->TC come seme casuale

        Genera nuove power pills quando sono state raccolte un certo numero di pillole standard

        Chiama generatePowerPills() per posizionarle correttamente

IRQ_RIT.c

Gestisce gli input da joystick e i pulsanti:

    Cambia la direzione di Pac-Man solo se la nuova posizione è valida

    Il movimento continua nella stessa direzione finché non c'è un ostacolo o l'utente cambia direzione

    Gestisce il pulsante di pausa (INT0):

        Premuto all’inizio: avvia il gioco

        Premuto durante il gioco: mette in pausa o riprende

    Gestisce le vite: incrementa il numero quando il punteggio raggiunge 1000 o 2000 punti

🧠 Meccaniche Implementate

    Movimento continuo in una direzione, modificabile da joystick

    Raccolta di pillole e incremento del punteggio

    Power pills generate casualmente durante la partita

    Teletrasporto da un’estremità all’altra della mappa

    Messaggi su schermo: "PAUSE", "GAME OVER", e "VICTORY"

    Modalità di pausa iniziale, attivabile/disattivabile con INT0

🎉 Funzionalità Aggiuntiva: Messaggio di Vittoria

Per rispettare le tempistiche della registrazione video dimostrativa, è stato simulato l'evento di vittoria impostando manualmente a zero il valore della watch relativa alle standardPills in debug, così da visualizzare correttamente il messaggio di vittoria.
⚙️ Requisiti

    Scheda LandTiger 1768

    Ambiente di sviluppo compatibile con la scheda (Keil uVision, ecc.)

    Debugger JTAG o SWD per il caricamento del firmware
