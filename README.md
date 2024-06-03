# <p align="center">boot2root</p>
> Ce projet est conçu pour vous aider à découvrir la sécurité informatique et plusieurs domaines connexes à travers des défis multiples.
>
> Vous devrez utiliser des méthodes plus ou moins complexes pour passer root sur le serveur.
>
> Ne sous-estimez rien, il existe souvent plusieurs façons d'atteindre votre objectif ! Ce projet doit être réalisé en groupe et il y a plusieurs raisons à cela. Il est fortement recommandé d'échanger afin de progresser.

## Summary
- Information gathering
    * [port scanning](/1-information-gathering/nmap.md)
    * [web fuzzing](/1-information-gathering/dirb.md)
- Exploitation
    * [port 21 (FTP)](/2-exploitation/ftp.md)
    * [port 443 (HTTPS)](/2-exploitation/https.md)
- Post-exploitation
    * [as www-data](/3-post-exploitation/www-data.md)
    * [as laurie](/3-post-exploitation/laurie.md)
    * [as thor](/3-post-exploitation/thor.md)
    * [as zaz](/3-post-exploitation/zaz.md) `to root`
    * [CVE-2016-5195 - dirtycow](/3-post-exploitation/dirtycow.md) `to root`
- 42challenges
    * [ft_fun](/42challenges/ft_fun.md)
    * [bomb](/42challenges/bomb.md)
    * [turtle](/42challenges/turtle.md)

## Checklist
- [x] Host port scanning `nmap`
- [x] WebApp fuzzing: `dirb`
    * [x] `http://$ip`
    * [x] `https://$ip`
- [x] SQL vulnerability check: `sqlmap`
    * [x] `http://$ip`
    * [x] `http://$ip/fonts`
    * [x] `https://$ip`
    * [x] `https://$ip/forum`
    * [x] `https://$ip/webmail`
    * [x] `https://$ip/phpmyadmin`
- [x] Common web vulnerability check: `msfconsole`
    * [x] `http://$ip`
    * [x] `http://$ip/fonts`
    * [x] `https://$ip`
    * [x] `https://$ip/forum`
    * [x] `https://$ip/webmail`
    * [x] `https://$ip/phpmyadmin`
- [x] FTP vulnerability check: `msfconsole`
    * [x] Not logged in
    * [x] Using `anonymous`
    * [x] Using `lmezard`
- [x] IMAP vulnerability check: `msfconsole`
    * [x] Not logged in
    * [x] Using `lmezard`
- [x] SSH vulnerability check: `msfconsole`
    * [x] Not logged in
    * [x] Using `laurie`
    * [x] Using `thor`
    * [x] Using `zaz`
- [ ] CVE check:
    * [x] [CVE-2016-5195](https://github.com/dirtycow/dirtycow.github.io/wiki/VulnerabilityDetails) - dirtycow [[download](https://www.exploit-db.com/download/40839)]
    * [x] [CVE-2015-3202](http://seclists.org/oss-sec/2015/q2/520) - fuse (fusermount) [[download](https://www.exploit-db.com/download/37089)]
    * [x] [CVE-2014-4014](http://www.openwall.com/lists/oss-security/2014/06/10/4) - inode_capable [[download](https://www.exploit-db.com/download/33824)]
    * [x] [CVE-2021-3156](https://www.qualys.com/2021/01/26/cve-2021-3156/baron-samedit-heap-based-overflow-sudo.txt) - sudo Baron Samedit [[download](https://codeload.github.com/worawit/CVE-2021-3156/zip/main)]
    * [x] [CVE-2021-22555](https://github.com/google/security-research/blob/master/pocs/linux/cve-2021-22555/exploit.c) - Netfilter heap out-of-bounds write [[download](https://raw.githubusercontent.com/google/security-research/master/pocs/linux/cve-2021-22555/exploit.c)]
    * [x] [CVE-2019-18634](https://dylankatz.com/Analysis-of-CVE-2019-18634/) - sudo pwfeedback [[download](https://github.com/saleemrashid/sudo-cve-2019-18634/raw/master/exploit.c)]
    * [x] [CVE-2017-7308](https://googleprojectzero.blogspot.com/2017/05/exploiting-linux-kernel-via-packet.html) - af_packet [[download](https://raw.githubusercontent.com/xairy/kernel-exploits/master/CVE-2017-7308/poc.c)]
    * [x] [CVE-2017-6074](http://www.openwall.com/lists/oss-security/2017/02/22/3) - dccp [[download](https://www.exploit-db.com/download/41458)]
    * [x] [CVE-2017-1000370](https://www.qualys.com/2017/06/19/stack-clash/stack-clash.txt) - linux_offset2lib [[download](https://www.qualys.com/2017/06/19/stack-clash/linux_offset2lib.c)]
    * [x] [CVE-2015-8660](http://www.halfdog.net/Security/2015/UserNamespaceOverlayfsSetuidWriteExec/) - overlayfs (ovl_setattr) [[download](https://www.exploit-db.com/download/39166)]
    * [x] [CVE-2014-5119](http://googleprojectzero.blogspot.com/2014/08/the-poisoned-nul-byte-2014-edition.html) - __gconv_translit_find [[download](https://gitlab.com/exploit-database/exploitdb-bin-sploits/-/raw/main/bin-sploits/34421.tar.gz)]
    * [ ] [CVE-2014-0196](http://blog.includesecurity.com/2014/06/exploit-walkthrough-cve-2014-0196-pty-kernel-race-condition.html) - rawmodePTY [[download](https://www.exploit-db.com/download/33516)]
    * [ ] [CVE-2013-2094](http://timetobleed.com/a-closer-look-at-a-recent-privilege-escalation-bug-in-linux-cve-2013-2094/) - semtex [[download](https://www.exploit-db.com/download/25444)]
    * [ ] [CVE-2013-1959](http://www.openwall.com/lists/oss-security/2013/04/29/1) - userns_root_sploit [[download](https://www.exploit-db.com/download/25450)]
    * [ ] [CVE-2013-0268](https://www.exploit-db.com/exploits/27297/) - msr [[download](https://www.exploit-db.com/download/27297)]
    * [ ] [CVE-2012-0809](http://seclists.org/fulldisclosure/2012/Jan/att-590/advisory_sudo.txt) - death_star (sudo) [[download](https://www.exploit-db.com/download/18436)]
