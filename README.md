# bind-status-cacti-template

====
URL : https://www.isc.org/downloads/<br>

<br>
## Requirement<br>
OS:CentOS6<br>
Package:cacti-0.8.8b-7.el6.noarch<br>
<br>
## Install<br>
-- edit snmpd.conf<br>
$ cat snmpd.conf.add >> /etc/snmp/snmpd.conf<br>
<br>
-- check example<br>
$ cat /etc/snmp/snmpd.conf|grep dnsdist<br>
extend .1.3.6.1.4.1.18689.0.4 dns-stats /usr/local/bin/bind-stats<br>
<br>
-- copy bind-stats<br>
$ cp bind-stats /usr/local/bin/<br>
$ chmod 755 /usr/local/bin/bind-stats<br>
<br>
-- check example<br>
$ /usr/local/bin/bind-stats<br>
zones:20 xfersrunning:0 xfersdeferred:0 soaqueriesinprogress:0 recursiveclient:0 recursiveclientmax:1000  tcpclient:3  tcpclientmax:100<br>
<br>
-- copy bind-stats.cron<br>
$ cp bind-stats.cron /usr/local/bin/<br>
$ chmod 755 /usr/local/bin/bind-stats.cron<br>
<br>
-- check example<br>
$ /usr/local/bin/bind-stats.cron<br>

$ ls -al /tmp/<br>
total 16<br>
drwxrwxrwt.  3 root root 4096 Dec  5 14:46 .<br>
dr-xr-xr-x. 23 root root 4096 Dec  2 09:33 ..<br>
drwxrwxrwt   2 root root 4096 Nov 30 23:34 .ICE-unix<br>
-rw-r--r--   1 root root  269 Dec  5 17:13 rndcstatus.tmp<br>

$ cat  /tmp/rndcstatus.tmp<br>
version: 9.8.2rc1-RedHat-9.8.2-0.37.rc1.el6_7.4<br>
CPUs found: 2<br>
worker threads: 2<br>
number of zones: 20<br>
debug level: 0<br>
xfers running: 0<br>
xfers deferred: 0<br>
soa queries in progress: 0<br>
query logging is ON<br>
recursive clients: 0/0/1000<br>
tcp clients: 2/100<br>
server is up and running<br>
<br>

## Notes


