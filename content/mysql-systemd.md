+++
title = "MySQL in Systemd environment"
date = 2013-08-05
+++

After migrating from OpenRC to Systemd on my Gentoo machine, I've faced some troubles with running MySQL in the new environment. The problem was that by default MySQL (which is running under the ‘mysql’ system user) needs the access to /var/run/mysqld/ directory, but /var/run/ is now controlled by systemd, and this directory is created dynamically during every bootup.

The symptoms are:
```
<strong>/var/log/mysql/mysqld.err</strong><br>
	[ERROR] Can’t start server : Bind on unix socket: No such file or directory<br>
	130805 23:19:33 [ERROR] Do you already have another mysqld server running on socket: /var/run/mysqld/mysqld.sock ? <br>
	130805 23:19:33 [ERROR] Aborting
```

The solution is:
```
# /etc/systemd/system/mysqld.service</strong><br>
[Unit]<br>
Description=MySQL Server<br>
[Service]<br>
	ExecStart=/usr/sbin/mysqld –socket=/var/mysql/mysqld.sock \
	–pid-file=/var/mysql/mysql.pid<br>
	Restart=always<br>
	[Install]<br>
		Alias=mysqld.service<br>

```

Creating directory (it should be unreachable for systemd, you know):
```bash
mkdir /var/mysql<br>
chown mysql:mysql /var/mysql<br>
```

Staring service:
```bash
systemctl start mysqld
```

Finally, I wish Lennart Poettering to be burned alive for all of that shit called Systemd.
