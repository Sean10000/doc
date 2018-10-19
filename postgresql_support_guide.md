#PostgreSQL Support Guide

--
##重启postgreSQL

[root@hdp-itg-ambari shdev]# ***su postgres***

bash-4.2$ ***pg_ctl restart -m immediate -D /var/lib/pgsql/data/*** 

***慎用*** : 推荐使用 -m fast / -m smart 

waiting for server to shut down....
 
done

server stopped

server starting

bash-4.2$ ***psql -h hdp-itg-ambari -p 5432 -U ambari -W***

Password for user ambari:

'psql (9.2.24)

Type "help" for help.

ambari=> \q

bash-4.2$ ***pg_ctl status -D /var/lib/pgsql/data/***

pg_ctl: server is running (PID: 4304)

/usr/bin/postgres "-D" "/var/lib/pgsql/data" "-p" "5432"

bash-4.2$ pg_ctl --help

```
pg_ctl is a utility to initialize, start, stop, or control a PostgreSQL server.

Usage:
  pg_ctl init[db]               [-D DATADIR] [-s] [-o "OPTIONS"]
  pg_ctl start   [-w] [-t SECS] [-D DATADIR] [-s] [-l FILENAME] [-o "OPTIONS"]
  pg_ctl stop    [-W] [-t SECS] [-D DATADIR] [-s] [-m SHUTDOWN-MODE]
  pg_ctl restart [-w] [-t SECS] [-D DATADIR] [-s] [-m SHUTDOWN-MODE]
                 [-o "OPTIONS"]
  pg_ctl reload  [-D DATADIR] [-s]
  pg_ctl status  [-D DATADIR]
  pg_ctl promote [-D DATADIR] [-s]
  pg_ctl kill    SIGNALNAME PID

Common options:
  -D, --pgdata=DATADIR   location of the database storage area
  -s, --silent           only print errors, no informational messages
  -t, --timeout=SECS     seconds to wait when using -w option
  -V, --version          output version information, then exit
  -w                     wait until operation completes
  -W                     do not wait until operation completes
  -?, --help             show this help, then exit
(The default is to wait for shutdown, but not for start or restart.)

If the -D option is omitted, the environment variable PGDATA is used.

Options for start or restart:
  -c, --core-files       allow postgres to produce core files
  -l, --log=FILENAME     write (or append) server log to FILENAME
  -o OPTIONS             command line options to pass to postgres
                         (PostgreSQL server executable) or initdb
  -p PATH-TO-POSTGRES    normally not necessary

Options for stop or restart:
  -m, --mode=MODE        MODE can be "smart", "fast", or "immediate"

Shutdown modes are:
  smart       quit after all clients have disconnected
  fast        quit directly, with proper shutdown
  immediate   quit without complete shutdown; will lead to recovery on restart

Allowed signal names for kill:
  ABRT HUP INT QUIT TERM USR1 USR2
```