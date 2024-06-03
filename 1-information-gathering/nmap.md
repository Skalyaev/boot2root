# nmap

```bash
nmap -A -p- -T5 $ip
#...
#21/tcp  open  ftp        vsftpd 2.0.8 or later
#...
#22/tcp  open  ssh        OpenSSH 5.9p1 Debian 5ubuntu1.7 (Ubuntu Linux; protocol 2.0)
#...
#80/tcp  open  http       Apache httpd 2.2.22 ((Ubuntu))
#...
#143/tcp open  imap       Dovecot imapd
#...
#443/tcp open  ssl/http   Apache httpd 2.2.22
#...
#993/tcp open  ssl/imaps?
#...
```

### FTP

```bash
nmap -A -p21 -T5 $ip --script ftp*
#...
#|_ftp-anon: got code 500 "OOPS: vsftpd: refusing to run with writable root inside chroot()".
#| ftp-brute:
#|   Accounts: No valid accounts found
#|_  Statistics: Performed 1002 guesses in 182 seconds, average tps: 5.3
```

### SSH

```bash
nmap -A -p22 -T5 $ip --script ssh*
#...
#| ssh-auth-methods:
#|   Supported authentication methods:
#|     publickey
#|_    password
#| ssh-hostkey:
#|   1024 07bf0220f08ac8481efc41aea446fa25 (DSA)
#|   2048 26dd80a3dfc44b531e534246ef6e30b2 (RSA)
#|_  256 cfc38c31d7477c84e2d21631b28e63a7 (ECDSA)
#| ssh-brute:
#|   Accounts: No valid accounts found
#|_  Statistics: Performed 209 guesses in 180 seconds, average tps: 1.2
#| ssh2-enum-algos:
#|   kex_algorithms: (7)
#|       ecdh-sha2-nistp256
#....
#| ssh-publickey-acceptance:
#|_  Accepted Public Keys: No public keys accepted
#|_ssh-run: Failed to specify credentials and command to run.
```

### HTTP(S)

```bash
nmap -A -p80,443 -T5 $ip --script http*
#...
#|_http-robtex-shared-ns: *TEMPORARILY DISABLED* due to changes in Robtex's API. See https://www.robtex.com/api/
#...
```

### Imap(s)

```bash
nmap -A -p143,993 -T5 $ip --script imap*
#...
#| imap-brute:
#|   Accounts: No valid accounts found
#|_  Statistics: Performed 50009 guesses in 16 seconds, average tps: 3125.6
#|_imap-capabilities: ENABLE LITERAL+ IDLE have OK more SASL-IR capabilities STARTTLS IMAP4rev1 ID listed Pre-login LOGINDISABLEDA0001 LOGIN-REFERRALS post-login
#...
```
