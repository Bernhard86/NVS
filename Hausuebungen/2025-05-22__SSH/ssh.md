# SSH	
# Secure Shell	
### Sicherer Zugang zur Kommandozeile eines entfernten Computers

## VM mit HyperV
## Ubuntu 22.04

# ----------------------------------------------------------------------------
# ssh-server installieren
```bash
bernhard@bernhard-VM-Ubuntu:~$ sudo apt update

bernhard@bernhard-VM-Ubuntu:~$ sudo apt install openssh-server
```

# SSH/Port
## Port 22 für SSH erlauben
```bash
bernhard@bernhard-VM-Ubuntu:~$ sudo ufw allow ssh
```

## Port 22 für SSH nicht erlauben
```bash
bernhard@bernhard-VM-Ubuntu:~$ sudo ufw deny 22
```

# firewall
## firewall status
```bash
bernhard@bernhard-VM-Ubuntu:~$ sudo ufw status
Status: Aktiv

Zu                         Aktion      Von
--                         ------      ---
22/tcp                     ALLOW       Anywhere                  
22/tcp (v6)                ALLOW       Anywhere (v6)     
```

## ssh status abfragen
```bash
bernhard@bernhard-VM-Ubuntu:~$ sudo service ssh status
[sudo] Passwort für bernhard: 
● ssh.service - OpenBSD Secure Shell server
     Loaded: loaded (/lib/systemd/system/ssh.service; enabled; vendor preset: e>
     Active: active (running) since Wed 2025-05-28 11:56:36 CEST; 21min ago
       Docs: man:sshd(8)
             man:sshd_config(5)
    Process: 7544 ExecStartPre=/usr/sbin/sshd -t (code=exited, status=0/SUCCESS)
   Main PID: 7545 (sshd)
      Tasks: 1 (limit: 4573)
     Memory: 1.7M
        CPU: 75ms
     CGroup: /system.slice/ssh.service
             └─7545 "sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 startups"

Mai 28 11:56:36 bernhard-VM-Ubuntu systemd[1]: Starting OpenBSD Secure Shell se>
Mai 28 11:56:36 bernhard-VM-Ubuntu sshd[7545]: Server listening on 0.0.0.0 port>
Mai 28 11:56:36 bernhard-VM-Ubuntu sshd[7545]: Server listening on :: port 22.
Mai 28 11:56:36 bernhard-VM-Ubuntu systemd[1]: Started OpenBSD Secure Shell ser>
Mai 28 12:06:49 bernhard-VM-Ubuntu sshd[8178]: Accepted password for bernhard f>
Mai 28 12:06:49 bernhard-VM-Ubuntu sshd[8178]: pam_unix(sshd:session): session >
```

# ----------------------------------------------------------------------------
# SSH mit Passwort
```bash
bernhard@bernhard-VM-Ubuntu:~$ ssh bernhard@localhost
bernhard@localhost's password: 
Welcome to Ubuntu 22.04 LTS (GNU/Linux 5.15.0-27-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

671 Aktualisierungen können sofort angewendet werden.
460 dieser Aktualisierungen sind Standard-Sicherheitsaktualisierungen.
Zum Anzeigen dieser zusätzlichen Aktualisierungen bitte »apt list --upgradable« ausführen

New release '24.04.2 LTS' available.
Run 'do-release-upgrade' to upgrade to it.

Last login: Wed May 28 12:06:50 2025 from 127.0.0.1
```

## SSH Verbindung beenden
```bash
bernhard@bernhard-VM-Ubuntu:~$ exit
Abgemeldet
Connection to localhost closed.
```

# ----------------------------------------------------------------------------
# SSH ohne Passwort

## Schlüssel generieren
```bash
bernhard@bernhard-VM-Ubuntu:~$ ssh-keygen
```

## public Schlüssel anzeigen lassen 
```bash
bernhard@bernhard-VM-Ubuntu:~$ cat ~/.ssh/id_rsa.pub
```

## public Schlüssel in den Schlüsselordner einfügen
```bash
bernhard@bernhard-VM-Ubuntu:~$ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
```

## RECHTE für den Ordner ~/.ssh/authorized_keys
```bash
bernhard@bernhard-VM-Ubuntu:~$ chmod 600 ~/.ssh/authorized_keys

Zeichen     Bedeutung
-rw-------  Nur Besitzer darf lesen + schreiben (600)
```

## authorized_keys anzeigen lassen
```bash
bernhard@bernhard-VM-Ubuntu:~$ cat ~/.ssh/authorized_keys
```

# SSH ohne PW
```bash
bernhard@bernhard-VM-Ubuntu:~$ ssh bernhard@localhost
Welcome to Ubuntu 22.04 LTS (GNU/Linux 5.15.0-27-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

671 Aktualisierungen können sofort angewendet werden.
460 dieser Aktualisierungen sind Standard-Sicherheitsaktualisierungen.
Zum Anzeigen dieser zusätzlichen Aktualisierungen bitte »apt list --upgradable« ausführen

New release '24.04.2 LTS' available.
Run 'do-release-upgrade' to upgrade to it.

Last login: Wed May 28 12:17:49 2025 from 127.0.0.1
```

## SSH Verbindung beenden
```bash
bernhard@bernhard-VM-Ubuntu:~$ exit
Abgemeldet
Connection to localhost closed.
```

## SSH Server beenden
```bash
bernhard@bernhard-VM-Ubuntu:~$ sudo systemctl stop sshd
oder
bernhard@bernhard-VM-Ubuntu:~$ sudo service ssh stop
```

# ----------------------------------------------------------------------------
# SSH
# CA & Certificates

## Was ist eine SSH-CA?
Eine zentrale Stelle, die SSH-Zertifikate signiert, damit du nicht für jeden Benutzer authorized_keys pflegen musst.

## Was ist ein SSH-Zertifikat?
Ein öffentlicher Schlüssel, der von einer CA signiert wurde. 
Statt id_rsa.pub gibt es z.B. id_rsa-cert.pub.