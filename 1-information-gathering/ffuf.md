# Ffuf

### Port 80 (HTTP)

```
ffuf -w <wordlist> -u http://<ip>/FUZZ -fl 22
...
forum                   [Status: 403, Size: 285, Words: 21, Lines: 11]
fonts                   [Status: 301, Size: 312, Words: 20, Lines: 10]
server-status           [Status: 403, Size: 293, Words: 21, Lines: 11]
.htaccess               [Status: 403, Size: 291, Words: 21, Lines: 11]
style.css               [Status: 200, Size: 1767, Words: 162, Lines: 91]
.html                   [Status: 403, Size: 287, Words: 21, Lines: 11]
.htpasswd               [Status: 403, Size: 291, Words: 21, Lines: 11]
.htm                    [Status: 403, Size: 286, Words: 21, Lines: 11]
.htpasswds              [Status: 403, Size: 292, Words: 21, Lines: 11]
.htgroup                [Status: 403, Size: 290, Words: 21, Lines: 11]
.htaccess.bak           [Status: 403, Size: 295, Words: 21, Lines: 11]
.htuser                 [Status: 403, Size: 289, Words: 21, Lines: 11]
.ht                     [Status: 403, Size: 285, Words: 21, Lines: 11]
.htc                    [Status: 403, Size: 286, Words: 21, Lines: 11]
.htacess                [Status: 403, Size: 290, Words: 21, Lines: 11]
.htaccess.old           [Status: 403, Size: 295, Words: 21, Lines: 11]
twitter.png             [Status: 200, Size: 581, Words: 1, Lines: 6]
...
```

### Port 443 (HTTPS)

```
ffuf -w <wordlist> -u https://<ip>/FUZZ -fl 22
...
forum                   [Status: 301, Size: 314, Words: 20, Lines: 10]
webmail                 [Status: 301, Size: 316, Words: 20, Lines: 10]
phpmyadmin              [Status: 301, Size: 319, Words: 20, Lines: 10]
server-status           [Status: 403, Size: 294, Words: 21, Lines: 11]
...
```

```
ffuf -w <wordlist> -u https://<ip>/forum/FUZZ -fl 81
...
images                  [Status: 301, Size: 325, Words: 20, Lines: 10]
themes                  [Status: 301, Size: 325, Words: 20, Lines: 10]
modules                 [Status: 301, Size: 326, Words: 20, Lines: 10]
includes                [Status: 301, Size: 327, Words: 20, Lines: 10]
update                  [Status: 301, Size: 325, Words: 20, Lines: 10]
js                      [Status: 301, Size: 321, Words: 20, Lines: 10]
lang                    [Status: 301, Size: 323, Words: 20, Lines: 10]
config                  [Status: 403, Size: 295, Words: 21, Lines: 11]
backup                  [Status: 403, Size: 295, Words: 21, Lines: 11]
templates_c             [Status: 301, Size: 330, Words: 20, Lines: 10]
.htaccess               [Status: 403, Size: 298, Words: 21, Lines: 11]
.html                   [Status: 403, Size: 294, Words: 21, Lines: 11]
.htpasswd               [Status: 403, Size: 298, Words: 21, Lines: 11]
.htm                    [Status: 403, Size: 293, Words: 21, Lines: 11]
.htpasswds              [Status: 403, Size: 299, Words: 21, Lines: 11]
.htgroup                [Status: 403, Size: 297, Words: 21, Lines: 11]
.htaccess.bak           [Status: 403, Size: 302, Words: 21, Lines: 11]
.htuser                 [Status: 403, Size: 296, Words: 21, Lines: 11]
.ht                     [Status: 403, Size: 292, Words: 21, Lines: 11]
.htc                    [Status: 403, Size: 293, Words: 21, Lines: 11]
.htaccess.old           [Status: 403, Size: 302, Words: 21, Lines: 11]
.htacess                [Status: 403, Size: 297, Words: 21, Lines: 11]
...
```

```
ffuf -w <wordlist> -u https://<ip>/webmail/FUZZ -fl 1
...
images                  [Status: 301, Size: 327, Words: 20, Lines: 10]
help                    [Status: 403, Size: 295, Words: 21, Lines: 11]
themes                  [Status: 301, Size: 327, Words: 20, Lines: 10]
plugins                 [Status: 301, Size: 328, Words: 20, Lines: 10]
src                     [Status: 301, Size: 324, Words: 20, Lines: 10]
include                 [Status: 403, Size: 298, Words: 21, Lines: 11]
config                  [Status: 301, Size: 327, Words: 20, Lines: 10]
class                   [Status: 403, Size: 296, Words: 21, Lines: 11]
functions               [Status: 403, Size: 300, Words: 21, Lines: 11]
po                      [Status: 403, Size: 293, Words: 21, Lines: 11]
locale                  [Status: 403, Size: 297, Words: 21, Lines: 11]
.htaccess               [Status: 403, Size: 300, Words: 21, Lines: 11]
.html                   [Status: 403, Size: 296, Words: 21, Lines: 11]
.htpasswd               [Status: 403, Size: 300, Words: 21, Lines: 11]
.htm                    [Status: 403, Size: 295, Words: 21, Lines: 11]
.htpasswds              [Status: 403, Size: 301, Words: 21, Lines: 11]
.htgroup                [Status: 403, Size: 299, Words: 21, Lines: 11]
.htaccess.bak           [Status: 403, Size: 304, Words: 21, Lines: 11]
.htuser                 [Status: 403, Size: 298, Words: 21, Lines: 11]
.ht                     [Status: 403, Size: 294, Words: 21, Lines: 11]
.htc                    [Status: 403, Size: 295, Words: 21, Lines: 11]
.htacess                [Status: 403, Size: 299, Words: 21, Lines: 11]
.htaccess.old           [Status: 403, Size: 304, Words: 21, Lines: 11]
...
```

```
ffuf -w <wordlist> -u https://<ip>/phpmyadmin/FUZZ -fl 127
...
themes                  [Status: 301, Size: 330, Words: 20, Lines: 10]
js                      [Status: 301, Size: 326, Words: 20, Lines: 10]
libraries               [Status: 403, Size: 303, Words: 21, Lines: 11]
setup                   [Status: 401, Size: 482, Words: 44, Lines: 15]
locale                  [Status: 301, Size: 330, Words: 20, Lines: 10]
pmd                     [Status: 301, Size: 327, Words: 20, Lines: 10]
favicon.ico             [Status: 200, Size: 18880, Words: 29, Lines: 30]
.htaccess               [Status: 403, Size: 303, Words: 21, Lines: 11]
.html                   [Status: 403, Size: 299, Words: 21, Lines: 11]
print.css               [Status: 200, Size: 1064, Words: 383, Lines: 70]
.htpasswd               [Status: 403, Size: 303, Words: 21, Lines: 11]
.htm                    [Status: 403, Size: 298, Words: 21, Lines: 11]
.htpasswds              [Status: 403, Size: 304, Words: 21, Lines: 11]
.htgroup                [Status: 403, Size: 302, Words: 21, Lines: 11]
.htaccess.bak           [Status: 403, Size: 307, Words: 21, Lines: 11]
.htuser                 [Status: 403, Size: 301, Words: 21, Lines: 11]
.ht                     [Status: 403, Size: 297, Words: 21, Lines: 11]
.htc                    [Status: 403, Size: 298, Words: 21, Lines: 11]
.htaccess.old           [Status: 403, Size: 307, Words: 21, Lines: 11]
.htacess                [Status: 403, Size: 302, Words: 21, Lines: 11]
Documentation.html      [Status: 200, Size: 249134, Words: 44973, Lines: 5093]
...
```
