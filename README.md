# <p align="center">boot2root</p>
> Ce projet est conçu pour vous aider à découvrir la sécurité informatique et plusieurs domaines connexes à travers des défis multiples.
>
> Vous devrez utiliser des méthodes plus ou moins complexes pour passer root sur le serveur.
>
> Ne sous-estimez rien, il existe souvent plusieurs façons d'atteindre votre objectif ! Ce projet doit être réalisé en groupe et il y a plusieurs raisons à cela. Il est fortement recommandé d'échanger afin de progresser.

## Summary
- Information gathering
    * [Port scanning](/1-information-gathering/nmap.md)
    * [Web fuzzing](/1-information-gathering/ffuf.md)
- Exploitation
    * Port 21 (FTP)
    * Port 22 (SSH)
    * Port 80 (HTTP)
    * [Port 443 (HTTPS)](/2-exploitation/https.md)
    * Port 143 (Imap)
    * Port 993 (Imaps)
- Post-exploitation
    * SUID binary
    * `work in progress`

## ToDoList
- [x] Host port scanning `nmap`
- [x] WebApp fuzzing: `ffuf`
    * [x] http://\<ip>
    * [x] https://\<ip>
- [ ] Session spoofing check: `msfconsole`
    * [ ] http://\<ip>
    * [ ] https://\<ip>
    * [ ] https://\<ip>/forum
    * [ ] https://\<ip>/webmail
    * [ ] https://\<ip>/phpmyadmin
- [ ] Command injection check: `msfconsole`
    * [ ] http://\<ip>/fonts
    * [ ] https://\<ip>/forum/index.php
    * [ ] https://\<ip>/webmail/src/login.php
- [ ] SQLi check: `sqlmap`
    * [ ] http://\<ip>
    * [ ] https://\<ip>
    * [ ] https://\<ip>/forum (no logged)
    * [ ] https://\<ip>/forum (logged)
    * [ ] https://\<ip>/webmail
    * [ ] https://\<ip>/phpmyadmin
- [ ] File inclusion check: `msfconsole`
    * [ ] http://\<ip>
    * [ ] https://\<ip>
- `work in progress`
