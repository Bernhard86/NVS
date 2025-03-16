# Übung Subnetting

## Übung 1

Bilde aus dem Netz 192.168.0.0 /24 4 Subnetze. Netze mit Mindestzahl an nutzbaren Host aber nicht darunter wählen: Netz a mit 20, Netz b mit 15, Netz c mit 30, und das Netz d mit den Rest Anteil der Netzwerkadressen.

**Antwort**
Netz	    Netzwerkadresse	    Subnetzmaske	    Adressbereich	                Nutzbare IPs 	                Hosts    Broadcast-Adresse
Netz A	    192.168.0.0/27	    255.255.255.224	    192.168.0.0 – 192.168.0.31	    192.168.0.1 –   192.168.0.30	30       192.168.0.31
Netz B	    192.168.0.32/27	    255.255.255.224	    192.168.0.32 – 192.168.0.63	    192.168.0.33 –  192.168.0.62	30       192.168.0.63
Netz C	    192.168.0.64/26	    255.255.255.192	    192.168.0.64 – 192.168.0.127 	192.168.0.65 –  192.168.0.94	30       192.168.0.127
Netz D	    192.168.0.128/25	255.255.255.128	    192.168.0.128 – 192.168.0.255	192.168.0.129 – 192.168.0.254	126      192.168.0.255



## Übung 2

Teile das Netz 193.170.20.0 /24 in 8 gleich große Netze! Erstelle eine Tabelle mit folgenden Angaben:
Netzwerkadresse,               nutzbare Hosts,                    Broadcastadresse,              Subnetzmaske.

**Antwort**
Netz	  Netzwerkadresse	  Subnetzmaske	    Adressbereich	                    Nutzbare IPs	                Hosts  Broadcast-Adresse
1	      193.170.20.0/27	  255.255.255.224	193.170.20.0 – 193.170.20.31	    193.170.20.1 – 193.170.20.30	 30    193.170.20.31
2	      193.170.20.32/27	  255.255.255.224	193.170.20.32 – 193.170.20.63	    193.170.20.33 – 193.170.20.62    30    193.170.20.63
3	      193.170.20.64/27	  255.255.255.224	193.170.20.64 – 193.170.20.95	    193.170.20.65 – 193.170.20.94    30    193.170.20.95
4	      193.170.20.96/27	  255.255.255.224	193.170.20.96 – 193.170.20.127	    193.170.20.97 – 193.170.20.126	 30    193.170.20.127
5	      193.170.20.128/27	  255.255.255.224	193.170.20.128 – 193.170.20.159	    193.170.20.129 – 193.170.20.158	 30    193.170.20.159
6	      193.170.20.160/27	  255.255.255.224	193.170.20.160 – 193.170.20.191	    193.170.20.161 – 193.170.20.190	 30    193.170.20.191
7	      193.170.20.192/27	  255.255.255.224	193.170.20.192 – 193.170.20.223	    193.170.20.193 – 193.170.20.222	 30    193.170.20.223
8	      193.170.20.224/27	  255.255.255.224	193.170.20.224 – 193.170.20.255	    193.170.20.225 – 193.170.20.254	 30    193.170.20.255



## Übung 3

172.28.40.0 /26 Teile wie folgt auf: 2 Netze!

**Antwort**
Netz	Netzwerkadresse	    Subnetzmaske	    Adressbereich	                Nutzbare IPs	            Hosts	    Broadcast-Adresse
1	    172.28.40.0/27	    255.255.255.224	    172.28.40.0 – 172.28.40.31	    172.28.40.1 – 172.28.40.30	  30	    172.28.40.31
2	    172.28.40.32/27	    255.255.255.224	    172.28.40.32 – 172.28.40.63	    172.28.40.33 – 172.28.40.62	  30	    172.28.40.63



## Übung 4

Wie lautet die Subnetzmaske bei der Netzadresse: 17.0.0.0 mit 10 verwendbaren Subnetzen, sowie mit mindestens 12 Hosts je Subnetz?
Antwort in Sätzen, wie sie zu dieser Lösung kommen; und erstelle eine Tabelle:

**Antwort**
Die gegebene Netzadresse 17.0.0.0 gehört zur Klasse A, mit der Standard-Subnetzmaske /8 (255.0.0.0).
Das Netz in mindestens 10 Subnetze unterteilen, mindestens 12 Hosts pro Subnetz!
2 hoch h −2 ≥ 12 Hosts
Mit h = 4 ergibt sich 2hoch4 -2 = 16 -2 = 14 Hosts
also mindestens /28 .240 als Maske für die Hosts.

Netz	Netzwerkadresse	    Subnetzmaske	    Adressbereich	            Nutzbare IPs	        Hosts	    Broadcast-Adresse
1	    17.0.0.0/28	        255.255.255.240	    17.0.0.0 – 17.0.0.15	    17.0.0.1 – 17.0.0.14	 14	        17.0.0.15
2	    17.0.0.16/28	    255.255.255.240	    17.0.0.16 – 17.0.0.31	    17.0.0.17 – 17.0.0.30	 14	        17.0.0.31
3	    17.0.0.32/28	    255.255.255.240	    17.0.0.32 – 17.0.0.47	    17.0.0.33 – 17.0.0.46	 14	        17.0.0.47
4	    17.0.0.48/28	    255.255.255.240	    17.0.0.48 – 17.0.0.63	    17.0.0.49 – 17.0.0.62	 14	        17.0.0.63
5	    17.0.0.64/28	    255.255.255.240	    17.0.0.64 – 17.0.0.79	    17.0.0.65 – 17.0.0.78	 14	        17.0.0.79
6	    17.0.0.80/28	    255.255.255.240	    17.0.0.80 – 17.0.0.95	    17.0.0.81 – 17.0.0.94	 14	        17.0.0.95
7	    17.0.0.96/28	    255.255.255.240	    17.0.0.96 – 17.0.0.111	    17.0.0.97 – 17.0.0.110	 14	        17.0.0.111
8	    17.0.0.112/28	    255.255.255.240	    17.0.0.112 – 17.0.0.127	    17.0.0.113 – 17.0.0.126	 14	        17.0.0.127
9	    17.0.0.128/28	    255.255.255.240	    17.0.0.128 – 17.0.0.143	    17.0.0.129 – 17.0.0.142	 14	        17.0.0.143
10	    17.0.0.144/28	    255.255.255.240	    17.0.0.144 – 17.0.0.159	    17.0.0.145 – 17.0.0.158	 14	        17.0.0.159



## Übung 5

Bestimmen Sie die Subnetmaske mit folgenden Angaben:

Netzadresse: 210.52.190.0
Subnetze: Anzahl 5
Mindestanzahl von Hosts je Subnetz: 10

**Antwort**
Netzwerkadresse: /28
Subnetzmaske: 255.255.255.240



## Übung 6

Teile  ein /30 Netz auf!    Wozu werden diese /30 Netze am häufigsten verwendet?
 

**Antwort**
Antwort: wird oft für eine einzelne Router-zu-Router-Verbindung verwendet! 

Netz	Netzwerkadresse	    Subnetzmaske	    Adressbereich	            Nutzbare IPs	            Hosts   Broadcast-Adresse
1	    192.168.1.0/30	    255.255.255.252	    192.168.1.0 – 192.168.1.3	192.168.1.1 – 192.168.1.2	2       192.168.1.3



## Übung 7

Nennen Sie den jeweiligen Netz- und Hostanteil der Klassen A, B und C

**Antwort**
Klasse	Netzwerkadresse-Bereich	    Standard-Subnetzmaske	Netzanteil	Hostanteil	Mögliche Netze	            Mögliche Hosts pro Netz
A	    1.0.0.0 – 126.0.0.0	        255.0.0.0 (/8)	        8 Bit	    24 Bit	    128 (0 und 127 reserviert)	16.777.214 (2⁴⁴ - 2)
B	    128.0.0.0 – 191.255.0.0	    255.255.0.0 (/16)	    16 Bit	    16 Bit	    16.384 (2¹⁴)	            65.534 (2¹⁶ - 2)
C	    192.0.0.0 – 223.255.255.0	255.255.255.0 (/24)	    24 Bit	    8 Bit	    2.097.152 (2²¹)	            254 (2⁸ - 2)
