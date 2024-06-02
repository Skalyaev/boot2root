# Ffuf

### Port 80 (HTTP)

```bash
dirb http://192.168.1.15
```
```
...
---- Scanning URL: http://192.168.1.15/ ----
+ http://192.168.1.15/cgi-bin/ (CODE:403|SIZE:288)
==> DIRECTORY: http://192.168.1.15/fonts/
+ http://192.168.1.15/forum (CODE:403|SIZE:285)
+ http://192.168.1.15/index.html (CODE:200|SIZE:1025)
+ http://192.168.1.15/server-status (CODE:403|SIZE:293)
...
```

### Port 443 (HTTPS)

```bash
dirb https://192.168.1.15
```
```
...
---- Scanning URL: https://192.168.1.15/ ----
+ https://192.168.1.15/cgi-bin/ (CODE:403|SIZE:289)
==> DIRECTORY: https://192.168.1.15/forum/
==> DIRECTORY: https://192.168.1.15/phpmyadmin/
+ https://192.168.1.15/server-status (CODE:403|SIZE:294)
==> DIRECTORY: https://192.168.1.15/webmail/

---- Entering directory: https://192.168.1.15/forum/ ----
+ https://192.168.1.15/forum/backup (CODE:403|SIZE:293)
+ https://192.168.1.15/forum/config (CODE:403|SIZE:293)
==> DIRECTORY: https://192.168.1.15/forum/images/
==> DIRECTORY: https://192.168.1.15/forum/includes/
+ https://192.168.1.15/forum/index (CODE:200|SIZE:4935)
+ https://192.168.1.15/forum/index.php (CODE:200|SIZE:4935)
==> DIRECTORY: https://192.168.1.15/forum/js/
==> DIRECTORY: https://192.168.1.15/forum/lang/
==> DIRECTORY: https://192.168.1.15/forum/modules/
==> DIRECTORY: https://192.168.1.15/forum/templates_c/
==> DIRECTORY: https://192.168.1.15/forum/themes/
==> DIRECTORY: https://192.168.1.15/forum/update/

---- Entering directory: https://192.168.1.15/phpmyadmin/ ----
+ https://192.168.1.15/phpmyadmin/favicon.ico (CODE:200|SIZE:18902)
+ https://192.168.1.15/phpmyadmin/index.php (CODE:200|SIZE:7540)
==> DIRECTORY: https://192.168.1.15/phpmyadmin/js/
+ https://192.168.1.15/phpmyadmin/libraries (CODE:403|SIZE:301)
==> DIRECTORY: https://192.168.1.15/phpmyadmin/locale/
+ https://192.168.1.15/phpmyadmin/phpinfo.php (CODE:200|SIZE:7540)
+ https://192.168.1.15/phpmyadmin/setup (CODE:401|SIZE:480)
==> DIRECTORY: https://192.168.1.15/phpmyadmin/themes/

---- Entering directory: https://192.168.1.15/webmail/ ----
+ https://192.168.1.15/webmail/class (CODE:403|SIZE:294)
==> DIRECTORY: https://192.168.1.15/webmail/config/
+ https://192.168.1.15/webmail/functions (CODE:403|SIZE:298)
+ https://192.168.1.15/webmail/help (CODE:403|SIZE:293)
==> DIRECTORY: https://192.168.1.15/webmail/images/
+ https://192.168.1.15/webmail/include (CODE:403|SIZE:296)
+ https://192.168.1.15/webmail/index.php (CODE:302|SIZE:0)
+ https://192.168.1.15/webmail/locale (CODE:403|SIZE:295)
==> DIRECTORY: https://192.168.1.15/webmail/plugins/
==> DIRECTORY: https://192.168.1.15/webmail/src/
==> DIRECTORY: https://192.168.1.15/webmail/themes/
```
