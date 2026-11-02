
## Day 9 - Fixing MariaDB Service Downtime

#### Task: 

A critical issue hit the Nautilus application in Stratos DC, connection to the database failed. After investigation, the production support team found that the mariadb service was down on the database server.

#### Solution: 

- Connected to the dbserver via SSH:

```
ssh peter@stdb01
```
- Confirmed the status of the MariaDB service:

```
sudo syatemctl status mariadb
```
Output: service was inactive (dead).

- Since the service was inactive, I restarted it:
```
sudo syatemctl start mariadb
```
Output: I got an error:

```
[peter@stdb01 ~]$ sudo systemctl start mariadb
Job for mariadb.service failed because the control process exited with error code.
See "systemctl status mariadb.service" and "journalctl -xeu mariadb.service" for details.
[peter@stdb01 ~]$
```
-  I checked the logs to see why the service failed: 
```
sudo journalctl -xeu mariadb --no-pager
```

Output showed that: MariaDB sees leftover files in /var/lib/mysql but no proper initialized database. This could have occured due to a partial or failed installation of the service.

- Check the ownership (identify the problem): 
```
ls -ld /var/lib/mysql
```
Output was: drwxr-xr-x 1 root mysql 4096 Apr 29 2026 /var/lib/mysql
Here root is the owner and mysql is the group, so it was root:mysql. It should be mysql:mysql. This was why MariaDB wouldn’t start.

- Fix the owner
```
chmod 755 /var/lib/mysql
```

- Start the service:
```
sudo systemctl start mariadb
```

- Enable auto-start on boot: 
```
sudo systemctl enable mariadb
```

- Verify the status:
```
sudo syatemctl status mariadb
```
You should see active (running).
