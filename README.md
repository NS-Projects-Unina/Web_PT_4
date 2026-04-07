\# Implementazione e Analisi di un Host-based IDS/IPS con Suricata



\## Descrizione del Progetto



Questo elaborato illustra la progettazione, configurazione e validazione di un ambiente di rete virtualizzato finalizzato allo studio e all'implementazione di un sistema \*\*Intrusion Detection/Prevention System (IDS/IPS)\*\* basato su \*\*Suricata\*\*. 



Il progetto mira a dimostrare l'efficacia (e i limiti) delle regole di rilevamento e prevenzione contro scenari di attacco, partendo dalle fasi di ricognizione fino allo sfruttamento di vulnerabilità a livello applicativo.



\## Architettura del Laboratorio



L'infrastruttura di test è stata isolata e virtualizzata, ed è composta da tre nodi principali:



1\. \*\*Nodo Attaccante (Kali Linux):\*\* Macchina dedicata alla simulazione delle minacce.

2\. \*\*Nodo Gateway / IPS (Lubuntu):\*\* Agisce da router/firewall per la rete interna. Ospita \*\*Suricata\*\* configurato.

3\. \*\*Nodo Vittima (Metasploitable 2):\*\* Macchina target intenzionalmente vulnerabile. Ospita servizi esposti (es. server web Apache, database) e applicazioni web vulnerabili (DVWA, Mutillidae) per testare l'efficacia delle policy di blocco.



\---



\## Tecnologie e Strumenti Utilizzati



\* \*\*Motore IDS/IPS:\*\* Suricata

\* \*\*Firewalling \& Packet Filtering:\*\* iptables

\* \*\*Information Gathering \& Scanning:\*\* Nmap

\* \*\*Web Exploitation:\*\* SQLmap

\* \*\*Denial of Service:\*\* Slowloris (Metasploit)

\* \*\*Analisi del Traffico:\*\* Wireshark



\---



\## Scenari di Attacco e Difesa Analizzati



Il progetto segue una metodologia progressiva, contrapponendo le tecniche offensive alle rispettive contromisure difensive:



\* \*\*Fase 1 - Footprinting, Scanning, Enumeration (Nmap):\*\* \* Rilevamento di scansioni stealth, Aggressive e Decoy.

&#x20; \* Implementazione di logiche di rilevamento rate-based e blocco dinamico tramite il modulo `recent` di iptables e gli `xbits` di Suricata.

\* \*\*Fase 2 - Denial of Service:\*\*

&#x20; \* Mitigazione di \*\*SYN Flood\*\* tramite regole di rate limiting (`limit`) su iptables.

&#x20; \* Analisi e blocco dell'attacco \*\*Slowloris\*\*.

\* \*\*Fase 3 - Exploitation Applicativo (SQL Injection):\*\*

&#x20; \* Rilevamento di pattern di iniezione generati da \*\*SQLmap\*\*.

&#x20; \* Creazione di firme custom in Suricata per ispezionare il payload HTTP ed eseguire il `DROP` delle richieste malevole.



\---



\## Autori



\* \*\*Giovanni Falco\*\* (Matricola: M63/1713)

\* \*\*Felice Palmiero\*\* (Matricola: M63/1744)

