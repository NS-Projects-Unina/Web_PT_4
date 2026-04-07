Descrizione del Progetto

Questo progetto presenta la progettazione, la configurazione e la validazione di un ambiente di rete virtualizzato, realizzato con l’obiettivo di studiare e implementare un sistema di Intrusion Detection e Intrusion Prevention basato su Suricata.

L’attività si concentra sull’analisi dell’efficacia e dei limiti delle tecniche di rilevamento e prevenzione, considerando diversi scenari di attacco. In particolare, il lavoro segue un approccio progressivo che parte dalle fasi di ricognizione e scanning, per arrivare fino allo sfruttamento di vulnerabilità applicative, permettendo di osservare il comportamento del sistema difensivo in contesti realistici.

Architettura del Laboratorio

L’ambiente di test è stato da noi progettato come un’infrastruttura completamente isolata e virtualizzata. La rete è composta da tre nodi che cooperano per simulare uno scenario di attacco e difesa.

Il nodo attaccante è rappresentato da una macchina Kali Linux, utilizzata per eseguire attività di scanning, enumerazione e attacco. Il nodo centrale svolge il ruolo di gateway e sistema di prevenzione, ed è implementato tramite una macchina Lubuntu su cui è installato e configurato Suricata. Infine, il nodo vittima è una macchina Metasploitable 2, intenzionalmente vulnerabile, che ha a bordo diversi servizi esposti come server web e database, oltre ad applicazioni web vulnerabili come DVWA e Mutillidae, utilizzate per testare attacchi a livello applicativo.

Scenari di Attacco e Difesa

L’analisi si sviluppa attraverso una serie di scenari che mettono in relazione tecniche offensive e contromisure difensive. Nella prima fase vengono esaminate attività di footprinting, scanning ed enumeration tramite Nmap, Nikto e Dirbuster. In questa fase vengono implementate tecniche di rilevamento basate sul rate del traffico e meccanismi di blocco sfruttando il modulo recent di iptables e gli xbits di Suricata.

Successivamente, l’attenzione si sposta sugli attacchi di tipo Denial of Service. In particolare, viene analizzato il comportamento di un attacco SYN Flood e la sua mitigazione attraverso regole di rate limiting applicate con iptables. Viene inoltre simulato l’attacco Slowloris, evidenziandone le caratteristiche e le modalità di rilevamento e blocco da parte del sistema.

Nell’ultima fase viene affrontato lo sfruttamento di vulnerabilità applicative, con particolare riferimento agli attacchi di SQL Injection. In questo contesto, vengono analizzati i pattern generati da SQLmap e sviluppate regole personalizzate in Suricata in grado di ispezionare il payload HTTP e bloccare le richieste malevole tramite azioni di drop.

Autori

Giovanni Falco (M63/1713)
Felice Palmiero (M63/1744)