# Ffuf

### Port 80 (HTTP)

```bash
dirb http://$ip
```
```
...
---- Scanning URL: http://$ip/ ----
+ http://$ip/cgi-bin/ (CODE:403|SIZE:288)
==> DIRECTORY: http://$ip/fonts/
+ http://$ip/forum (CODE:403|SIZE:285)
+ http://$ip/index.html (CODE:200|SIZE:1025)
+ http://$ip/server-status (CODE:403|SIZE:293)
...
```

### Port 443 (HTTPS)

```bash
dirb https://$ip
```
```
...
---- Scanning URL: https://$ip/ ----
+ https://$ip/cgi-bin/ (CODE:403|SIZE:289)
==> DIRECTORY: https://$ip/forum/
==> DIRECTORY: https://$ip/phpmyadmin/
+ https://$ip/server-status (CODE:403|SIZE:294)
==> DIRECTORY: https://$ip/webmail/

---- Entering directory: https://$ip/forum/ ----
+ https://$ip/forum/backup (CODE:403|SIZE:293)
+ https://$ip/forum/config (CODE:403|SIZE:293)
==> DIRECTORY: https://$ip/forum/images/
==> DIRECTORY: https://$ip/forum/includes/
+ https://$ip/forum/index (CODE:200|SIZE:4935)
+ https://$ip/forum/index.php (CODE:200|SIZE:4935)
==> DIRECTORY: https://$ip/forum/js/
==> DIRECTORY: https://$ip/forum/lang/
==> DIRECTORY: https://$ip/forum/modules/
==> DIRECTORY: https://$ip/forum/templates_c/
==> DIRECTORY: https://$ip/forum/themes/
==> DIRECTORY: https://$ip/forum/update/

---- Entering directory: https://$ip/phpmyadmin/ ----
+ https://$ip/phpmyadmin/favicon.ico (CODE:200|SIZE:18902)
+ https://$ip/phpmyadmin/index.php (CODE:200|SIZE:7540)
==> DIRECTORY: https://$ip/phpmyadmin/js/
+ https://$ip/phpmyadmin/libraries (CODE:403|SIZE:301)
==> DIRECTORY: https://$ip/phpmyadmin/locale/
+ https://$ip/phpmyadmin/phpinfo.php (CODE:200|SIZE:7540)
+ https://$ip/phpmyadmin/setup (CODE:401|SIZE:480)
==> DIRECTORY: https://$ip/phpmyadmin/themes/

---- Entering directory: https://$ip/webmail/ ----
+ https://$ip/webmail/class (CODE:403|SIZE:294)
==> DIRECTORY: https://$ip/webmail/config/
+ https://$ip/webmail/functions (CODE:403|SIZE:298)
+ https://$ip/webmail/help (CODE:403|SIZE:293)
==> DIRECTORY: https://$ip/webmail/images/
+ https://$ip/webmail/include (CODE:403|SIZE:296)
+ https://$ip/webmail/index.php (CODE:302|SIZE:0)
+ https://$ip/webmail/locale (CODE:403|SIZE:295)
==> DIRECTORY: https://$ip/webmail/plugins/
==> DIRECTORY: https://$ip/webmail/src/
==> DIRECTORY: https://$ip/webmail/themes/
```
