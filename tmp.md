# Non-Root write access
> If a root process access one of these files,
> it can be used to escalate privileges

## -o writable

```bash
find / -perm -o=w \
    ! -type l \
    ! -path "/rofs*" \
    ! -path "/tmp*" \
    ! -path "/home*" \
    ! -path "/dev*" \
    ! -path "/proc*" \
    ! -path "/run*" \
    ! -path "/var/spool/postfix*" \
    2>/dev/null | xargs ls -ld
```
```
drwxrwsrwt 2 root     whoopsie    3 Jun 17  2017 /var/crash
drwx-wx-wt 2 root     root        3 Jun 16  2017 /var/lib/php5
drwxrwxrwt 2 root     root        3 Oct 15  2015 /var/tmp
drwxrwxrwx 2 www-data www-data 1064 Oct 13  2015 /var/www/forum/templates_c
```

## ! -user root && -u writable

```bash
find / -perm -u=w \
    ! -user root \
    ! -type l \
    ! -path "/rofs*" \
    ! -path "/tmp*" \
    ! -path "/home*" \
    ! -path "/dev*" \
    ! -path "/proc*" \
    ! -path "/run*" \
    ! -path "/var/spool/postfix*" \
    ! -path "/var/www*" \
    ! -path "/var/log*" \
    ! -path "/var/cache*" \
    ! -path "/var/lib/mysql*" \
    2>/dev/null | xargs ls -ld
```
```
-rwsr-sr-x 1 daemon               daemon   42800 Oct 25  2011 /usr/bin/at
-rwsr-sr-x 1 libuuid              libuuid  17976 Jun 18  2014 /usr/sbin/uuidd
drwxrwsr-x 2 libuuid              libuuid      3 Oct  8  2015 /var/lib/libuuid
drwxr-xr-x 2 www-data             www-data     3 Feb 19  2012 /var/lib/phpmyadmin/tmp
drwxr-xr-x 2 postfix              postfix     96 Oct  8  2015 /var/lib/postfix
-rw------- 1 postfix              postfix     17 Jun 16  2017 /var/lib/postfix/master.lock
-rw------- 1 postfix              postfix   1024 Jun 16  2017 /var/lib/postfix/prng_exch
-rw------- 1 postfix              postfix   8192 Jun 16  2017 /var/lib/postfix/smtp_scache.db
-rw------- 1 postfix              postfix   8192 Jun 16  2017 /var/lib/postfix/smtpd_scache.db
-rw------- 1 www-data             www-data     0 Oct  8  2015 /var/lib/squirrelmail/data/ft_root.abook
-rw------- 1 www-data             www-data   571 Oct  8  2015 /var/lib/squirrelmail/data/ft_root.pref
-rw------- 1 www-data             www-data     0 Oct  8  2015 /var/lib/squirrelmail/data/laurie@borntosec.net.abook
-rw------- 1 www-data             www-data   273 Oct 13  2015 /var/lib/squirrelmail/data/laurie@borntosec.net.pref
-rw------- 1 www-data             www-data   174 Oct  8  2015 /var/lib/squirrelmail/data/zaz.pref
-rw------- 1 laurie@borntosec.net mail      3131 Oct  8  2015 /var/mail/laurie@borntosec.net
drwxrwx--T 2 daemon               daemon      27 Oct  8  2015 /var/spool/cron/atjobs
-rw------- 1 daemon               daemon       2 Oct  8  2015 /var/spool/cron/atjobs/.SEQ
drwxrwx--T 2 daemon               daemon       3 Oct 25  2011 /var/spool/cron/atspool
drwxr-xr-x 2 syslog               adm          3 Mar 30  2012 /var/spool/rsyslog
```

## ! -group root && -g writable

```bash
find / -perm -g=w \
    ! -group root \
    ! -type l \
    ! -path "/rofs*" \
    ! -path "/tmp*" \
    ! -path "/home*" \
    ! -path "/dev*" \
    ! -path "/proc*" \
    ! -path "/run*" \
    ! -path "/var/spool/postfix*" \
    ! -path "/var/www*" \
    ! -path "/var/log*" \
    ! -path "/var/cache*" \
    ! -path "/var/lib/mysql*" \
    2>/dev/null | xargs ls -ld
```
```
drwxrwsr-x 4 root    staff     57 Oct  8  2015 /usr/local/lib/python2.7
drwxrwsr-x 2 root    staff      3 Oct  8  2015 /usr/local/lib/python2.7/dist-packages
drwxrwsr-x 2 root    staff      3 Oct  8  2015 /usr/local/lib/python2.7/site-packages
drwxrwsr-x 2 root    staff      3 Oct  8  2015 /usr/local/share/ca-certificates
drwxrwsr-x 2 root    staff      3 Oct  8  2015 /usr/local/share/fonts
drwxrwsr-x 7 root    staff     91 Oct  8  2015 /usr/local/share/sgml
drwxrwsr-x 2 root    staff      3 Oct  8  2015 /usr/local/share/sgml/declaration
drwxrwsr-x 2 root    staff      3 Oct  8  2015 /usr/local/share/sgml/dtd
drwxrwsr-x 2 root    staff      3 Oct  8  2015 /usr/local/share/sgml/entities
drwxrwsr-x 2 root    staff      3 Oct  8  2015 /usr/local/share/sgml/misc
drwxrwsr-x 2 root    staff      3 Oct  8  2015 /usr/local/share/sgml/stylesheet
drwxrwsr-x 6 root    staff     76 Oct  8  2015 /usr/local/share/xml
drwxrwsr-x 2 root    staff      3 Oct  8  2015 /usr/local/share/xml/declaration
drwxrwsr-x 2 root    staff      3 Oct  8  2015 /usr/local/share/xml/entities
drwxrwsr-x 2 root    staff      3 Oct  8  2015 /usr/local/share/xml/misc
drwxrwsr-x 2 root    staff      3 Oct  8  2015 /usr/local/share/xml/schema
drwxrwsrwt 2 root    whoopsie   3 Jun 17  2017 /var/crash
drwxrwsr-x 2 libuuid libuuid    3 Oct  8  2015 /var/lib/libuuid
drwx-wx--- 2 root    www-data 139 Oct 13  2015 /var/lib/squirrelmail/data
drwxrwsr-x 2 root    staff      3 Apr 19  2012 /var/local
drwxrwsr-x 2 root    mail      55 Oct 14  2015 /var/mail
drwxrwx--T 2 daemon  daemon    27 Oct  8  2015 /var/spool/cron/atjobs
drwxrwx--T 2 daemon  daemon     3 Oct 25  2011 /var/spool/cron/atspool
drwx-wx--T 2 root    crontab    3 Apr  2  2012 /var/spool/cron/crontabs
drwx-wx--- 2 root    www-data   3 Jul 27  2011 /var/spool/squirrelmail/attach
```

# Cron

### `/etc/cron.d/php5`

```bash
[ -x /usr/lib/php5/maxlifetime ] && [ -d /var/lib/php5 ]\
    && find /var/lib/php5/ -depth \
        -mindepth 1 -maxdepth 1 \
        -type f -cmin +$(/usr/lib/php5/maxlifetime) \
        ! -execdir fuser -s {} 2>/dev/null \; -delete
```

### `/etc/cron.daily/apport`

```bash
#!/bin/sh -e
[ -d /var/crash ] || exit 0
find /var/crash/. ! -name . -prune -type f \( \( -size 0 -a \! -name '*.upload*' \) -o -mtime +7 \) -exec rm -f -- '{}' \;
```
> /var/crash is writable
>
> We can try to command injection '*.upload*' or '{}'
> But this one is hard command injection depending on shell version
> because of the single quotes

## To Check

### `/etc/cron.daily/apt`

```bash
check_stamp()
{
    stamp="$1"
    interval="$2"

    if [ $interval -eq 0 ]; then
    debug_echo "check_stamp: interval=0"
    # treat as no time has passed
        return 1
    fi

    if [ ! -f $stamp ]; then
    debug_echo "check_stamp: missing time stamp file: $stamp."
    # treat as enough time has passed
        return 0
    fi

    # compare midnight today to midnight the day the stamp was updated
    stamp_file="$stamp"
    stamp=$(date --date=$(date -r $stamp_file --iso-8601) +%s 2>/dev/null)
    if [ "$?" != "0" ]; then
        # Due to some timezones returning 'invalid date' for midnight on
        # certain dates (eg America/Sao_Paulo), if date returns with error
        # remove the stamp file and return 0. See coreutils bug:
        # http://lists.gnu.org/archive/html/bug-coreutils/2007-09/msg00176.html
        rm -f "$stamp_file"
        return 0
    fi

    now=$(date --date=$(date --iso-8601) +%s 2>/dev/null)
    if [ "$?" != "0" ]; then
        # As above, due to some timezones returning 'invalid date' for midnight
        # on certain dates (eg America/Sao_Paulo), if date returns with error
        # return 0.
        return 0
    fi

    delta=$(($now-$stamp))

    # intervall is in days, convert to sec.
    interval=$(($interval*60*60*24))
    debug_echo "check_stamp: interval=$interval, now=$now, stamp=$stamp, delta=$delta (sec)"

    # remove timestamps a day (or more) in the future and force re-check
    if [ $stamp -gt $(($now+86400)) ]; then
         echo "WARNING: file $stamp_file has a timestamp in the future: $stamp"
         rm -f "$stamp_file"
         return 0
    fi

    if [ $delta -ge $interval ]; then
        return 0
    fi

    return 1
}

update_stamp()
{
    stamp="$1"
    touch $stamp
}

check_size_constraints()
{
    MaxAge=0
    eval $(apt-config shell MaxAge APT::Archives::MaxAge)
    eval $(apt-config shell MaxAge APT::Periodic::MaxAge)

    MinAge=2
    eval $(apt-config shell MinAge APT::Archives::MinAge)
    eval $(apt-config shell MinAge APT::Periodic::MinAge)

    MaxSize=0
    eval $(apt-config shell MaxSize APT::Archives::MaxSize)
    eval $(apt-config shell MaxSize APT::Periodic::MaxSize)

    Cache="/var/cache/apt/archives/"
    eval $(apt-config shell Cache Dir::Cache::archives/d)

    # sanity check
    if [ -z "$Cache" ]; then
    echo "empty Dir::Cache::archives, exiting"
    exit
    fi

    # check age
    if [ ! $MaxAge -eq 0 ] && [ ! $MinAge -eq 0 ]; then
    debug_echo "aged: ctime <$MaxAge and mtime <$MaxAge and ctime>$MinAge and mtime>$MinAge"
    find $Cache -name "*.deb"  \( -mtime +$MaxAge -and -ctime +$MaxAge \) -and -not \( -mtime -$MinAge -or -ctime -$MinAge \) -print0 | xargs -r -0 rm -f
    elif [ ! $MaxAge -eq 0 ]; then
    debug_echo "aged: ctime <$MaxAge and mtime <$MaxAge only"
    find $Cache -name "*.deb"  -ctime +$MaxAge -and -mtime +$MaxAge -print0 | xargs -r -0 rm -f
    else
    debug_echo "skip aging since MaxAge is 0"
    fi

    # check size
    if [ ! $MaxSize -eq 0 ]; then
    # maxSize is in MB
    MaxSize=$(($MaxSize*1024))

    #get current time
    now=$(date --date=$(date --iso-8601) +%s)
    MinAge=$(($MinAge*24*60*60))

    # reverse-sort by mtime
    for file in $(ls -rt $Cache/*.deb 2>/dev/null); do
        du=$(du -s $Cache)
        size=${du%%/*}
        # check if the cache is small enough
        if [ $size -lt $MaxSize ]; then
        debug_echo "end remove by archive size:  size=$size < $MaxSize"
        break
        fi

        # check for MinAge of the file
        if [ $MinAge -ne 0 ]; then
        # check both ctime and mtime
        mtime=$(stat -c %Y $file)
        ctime=$(stat -c %Z $file)
        if [ $mtime -gt $ctime ]; then
            delta=$(($now-$mtime))
        else
            delta=$(($now-$ctime))
        fi
        if [ $delta -le $MinAge ]; then
            debug_echo "skip remove by archive size:  $file, delta=$delta < $MinAgeSec"
            break
        else
            # delete oldest file
            debug_echo "remove by archive size: $file, delta=$delta >= $MinAgeSec (sec), size=$size >= $MaxSize"
            rm -f $file
        fi
        fi
    done
    fi
}

do_cache_backup()
{
    BackupArchiveInterval="$1"
    if [ $BackupArchiveInterval -eq 0 ]; then
    return
    fi

    # Set default values and normalize
    CacheDir="/var/cache/apt"
    eval $(apt-config shell CacheDir Dir::Cache/d)
    CacheDir=${CacheDir%/}
    if [ -z "$CacheDir" ]; then
    debug_echo "practically empty Dir::Cache, exiting"
    return 0
    fi

    Cache="${CacheDir}/archives/"
    eval $(apt-config shell Cache Dir::Cache::Archives/d)
    if [ -z "$Cache" ]; then
    debug_echo "practically empty Dir::Cache::archives, exiting"
    return 0
    fi

    BackupLevel=3
    eval $(apt-config shell BackupLevel APT::Periodic::BackupLevel)
    if [ $BackupLevel -le 1 ]; then
    BackupLevel=2 ;
    fi

    Back="${CacheDir}/backup/"
    eval $(apt-config shell Back Dir::Cache::Backup/d)
    if [ -z "$Back" ]; then
    echo "practically empty Dir::Cache::Backup, exiting" 1>&2
    return
    fi

    CacheArchive="$(basename "${Cache}")"
    test -n "${CacheArchive}" || CacheArchive="archives"
    BackX="${Back}${CacheArchive}/"
    for x in $(seq 0 1 $((${BackupLevel}-1))); do
    eval "Back${x}=${Back}${x}/"
    done

    # backup after n-days if archive contents changed.
    # (This uses hardlink to save disk space)
    BACKUP_ARCHIVE_STAMP=/var/lib/apt/periodic/backup-archive-stamp
    if check_stamp $BACKUP_ARCHIVE_STAMP $BackupArchiveInterval; then
    if [ $({(cd $Cache 2>/dev/null; find . -name "*.deb"); (cd $Back0 2>/dev/null;find . -name "*.deb") ;}| sort|uniq -u|wc -l) -ne 0 ]; then
        mkdir -p $Back
        rm -rf $Back$((${BackupLevel}-1))
        for y in $(seq $((${BackupLevel}-1)) -1 1); do
        eval BackY=${Back}$y
        eval BackZ=${Back}$(($y-1))
        if [ -e $BackZ ]; then
            mv -f $BackZ $BackY ;
        fi
        done
        cp -la $Cache $Back ; mv -f $BackX $Back0
        update_stamp $BACKUP_ARCHIVE_STAMP
        debug_echo "backup with hardlinks. (success)"
    else
        debug_echo "skip backup since same content."
    fi
    else
    debug_echo "skip backup since too new."
    fi
}

random_sleep()
{
    RandomSleep=1800
    eval $(apt-config shell RandomSleep APT::Periodic::RandomSleep)
    if [ $RandomSleep -eq 0 ]; then
    return
    fi
    if [ -z "$RANDOM" ] ; then
        # A fix for shells that do not have this bash feature.
    RANDOM=$(dd if=/dev/urandom count=1 2> /dev/null | cksum | cut -c"1-5")
    fi
    TIME=$(($RANDOM % $RandomSleep))
    debug_echo "sleeping for $TIME seconds"
    sleep $TIME
}


debug_echo()
{
    # Display message if $VERBOSE >= 1
    if [ "$VERBOSE" -ge 1 ]; then
    echo $1 1>&2
    fi
}

check_power(){
    # laptop check, on_ac_power returns:
    #       0 (true)    System is on main power
    #       1 (false)   System is not on main power
    #       255 (false) Power status could not be determined
    # Desktop systems always return 255 it seems
    if which on_ac_power >/dev/null; then
        on_ac_power
        POWER=$?
        if [ $POWER -eq 1 ]; then
        debug_echo "exit: system NOT on main power"
        return 1
        elif [ $POWER -ne 0 ]; then
        debug_echo "power status ($POWER) undetermined, continuing"
        fi
        debug_echo "system is on main power."
    fi
    return 0
}


if cd /var/backups ; then
    if ! cmp -s apt.extended_states.0 /var/lib/apt/extended_states; then
    cp -p /var/lib/apt/extended_states apt.extended_states
    savelog -c 7 apt.extended_states >/dev/null
    fi
fi

if ! which apt-config >/dev/null ; then
    exit 0
fi

AutoAptEnable=1  # default is yes
eval $(apt-config shell AutoAptEnable APT::Periodic::Enable)

if [ $AutoAptEnable -eq 0 ]; then
    exit 0
fi

VERBOSE=0
eval $(apt-config shell VERBOSE APT::Periodic::Verbose)
debug_echo "verbose level $VERBOSE"
if [ "$VERBOSE" -le 2 ]; then
    # quiet for 0,1,2
    XSTDOUT=">/dev/null"
    XSTDERR="2>/dev/null"
    XAPTOPT="-qq"
    XUUPOPT=""
else
    XSTDOUT=""
    XSTDERR=""
    XAPTOPT=""
    XUUPOPT="-d"
fi
if [ "$VERBOSE" -ge 3 ]; then
    # trace output
    set -x
fi

check_power || exit 0

if which apt-get >/dev/null && ! eval apt-get check -f $XAPTOPT $XSTDERR ; then
    debug_echo "error encountered in cron job with \"apt-get check\"."
    exit 0
fi

now=$(date +%s)


UpdateInterval=0
eval $(apt-config shell UpdateInterval APT::Periodic::Update-Package-Lists)

DownloadUpgradeableInterval=0
eval $(apt-config shell DownloadUpgradeableInterval APT::Periodic::Download-Upgradeable-Packages)

UnattendedUpgradeInterval=0
eval $(apt-config shell UnattendedUpgradeInterval APT::Periodic::Unattended-Upgrade)

AutocleanInterval=0
eval $(apt-config shell AutocleanInterval APT::Periodic::AutocleanInterval)

BackupArchiveInterval=0
eval $(apt-config shell BackupArchiveInterval APT::Periodic::BackupArchiveInterval)

Debdelta=1
eval $(apt-config shell Debdelta APT::Periodic::Download-Upgradeable-Packages-Debdelta)

if [ $UpdateInterval -eq 0 ] &&
   [ $DownloadUpgradeableInterval -eq 0 ] &&
   [ $UnattendedUpgradeInterval -eq 0 ] &&
   [ $BackupArchiveInterval -eq 0 ] &&
   [ $AutocleanInterval -eq 0 ]; then

    # check cache size
    check_size_constraints

    exit 0
fi

do_cache_backup $BackupArchiveInterval

random_sleep
check_power || exit 0

if [ -r /etc/default/locale ]; then
    . /etc/default/locale
    export LANG LANGUAGE LC_MESSAGES LC_ALL
fi

UPDATED=0
UPDATE_STAMP=/var/lib/apt/periodic/update-stamp
if check_stamp $UPDATE_STAMP $UpdateInterval; then
    # check for a new archive signing key (against the master keyring)
    if eval apt-key net-update $XSTDERR; then
       debug_echo "apt-key net-update (success)"
    else
       debug_echo "apt-key net-update (failure)"
    fi
    # run apt-get update
    if eval apt-get $XAPTOPT -y update $XSTDERR; then
    debug_echo "download updated metadata (success)."
    if which dbus-send >/dev/null && pidof dbus-daemon >/dev/null; then
        if dbus-send --system / app.apt.dbus.updated boolean:true ; then
        debug_echo "send dbus signal (success)"
        else
        debug_echo "send dbus signal (error)"
        fi
    else
        debug_echo "dbus signal not send (command not available)"
    fi
    update_stamp $UPDATE_STAMP
    UPDATED=1
        # now run apt-xapian-index if it is installed to ensure the index
        # is up-to-date
        if [ -x /usr/sbin/update-apt-xapian-index ]; then
            nice ionice -c3 update-apt-xapian-index -q -u
        fi
    else
    debug_echo "download updated metadata (error)"
    fi
else
    debug_echo "download updated metadata (not run)."
fi

DOWNLOAD_UPGRADEABLE_STAMP=/var/lib/apt/periodic/download-upgradeable-stamp
if [ $UPDATED -eq 1 ] && check_stamp $DOWNLOAD_UPGRADEABLE_STAMP $DownloadUpgradeableInterval; then
    if [ $Debdelta -eq 1 ]; then
        debdelta-upgrade >/dev/null 2>&1 || true
    fi
    if  eval apt-get $XAPTOPT -y -d dist-upgrade $XSTDERR; then
    update_stamp $DOWNLOAD_UPGRADEABLE_STAMP
    debug_echo "download upgradable (success)"
    else
    debug_echo "download upgradable (error)"
    fi
else
    debug_echo "download upgradable (not run)"
fi

UPGRADE_STAMP=/var/lib/apt/periodic/upgrade-stamp
if which unattended-upgrade >/dev/null && check_stamp $UPGRADE_STAMP $UnattendedUpgradeInterval; then
    if unattended-upgrade $XUUPOPT; then
    update_stamp $UPGRADE_STAMP
    debug_echo "unattended-upgrade (success)"
    else
    debug_echo "unattended-upgrade (error)"
    fi
else
    debug_echo "unattended-upgrade (not run)"
fi

AUTOCLEAN_STAMP=/var/lib/apt/periodic/autoclean-stamp
if check_stamp $AUTOCLEAN_STAMP $AutocleanInterval; then
    if  eval apt-get $XAPTOPT -y autoclean $XSTDERR; then
    debug_echo "autoclean (success)."
    update_stamp $AUTOCLEAN_STAMP
    else
    debug_echo "autoclean (error)"
    fi
else
    debug_echo "autoclean (not run)"
fi

check_size_constraints
```

### `/etc/cron.weekly/man-db`
```bash
#!/bin/sh
#
# man-db cron weekly

set -e

iosched_idle=
# Don't try to change I/O priority in a vserver or OpenVZ.
if ! egrep -q '(envID|VxID):.*[1-9]' /proc/self/status && \
   ([ ! -d /proc/vz ] || [ -d /proc/bc ]); then
    dpkg_version="$(dpkg-query -W -f '${Version}' dpkg 2>/dev/null)"
    if dpkg --compare-versions "$dpkg_version" ge 1.15.0; then
    iosched_idle='--iosched idle'
    fi
fi

if ! [ -d /var/cache/man ]; then
    # Recover from deletion, per FHS.
    mkdir -p /var/cache/man
    chown man:root /var/cache/man || true
    chmod 2755 /var/cache/man
fi

# regenerate man database
if [ -x /usr/bin/mandb ]; then
    # --pidfile /dev/null so it always starts; mandb isn't really a daemon,
    # but we want to start it like one.
    start-stop-daemon --start --pidfile /dev/null \
              --startas /usr/bin/mandb --oknodo --chuid man \
              $iosched_idle \
              -- --quiet
fi

exit 0
```

### `/etc/cron.weekly/apt-xapian-index`
```bash
#!/bin/sh

CMD=/usr/sbin/update-apt-xapian-index

# ionice should not be called in a virtual environment
# (similar to man-db cronjobs)
egrep -q '(envID|VxID):.*[1-9]' /proc/self/status || IONICE=/usr/bin/ionice

# Check if we're on battery
if which on_ac_power >/dev/null 2>&1; then
    on_ac_power >/dev/null 2>&1
    ON_BATTERY=$?

    # Here we use "-eq 1" instead of "-ne 0" because
    # on_ac_power could also return 255, which means
    # it can't tell whether we are on AC or not. In
    # that case, run update-a-x-i nevertheless.
    [ "$ON_BATTERY" -eq 1 ] && exit 0
fi

# Rebuild the index
if [ -x "$CMD" ]
then
    if [ -x "$IONICE" ]
    then
        nice -n 19 $IONICE -c 3 $CMD --quiet
    else
        nice -n 19 $CMD --quiet
    fi
fi
```
