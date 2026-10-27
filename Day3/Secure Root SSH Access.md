
## Day 3: Secure Root SSH Access (Disable Direct Root Login)

#### Task: 

Following security audits, the xFusionCorp Industries security team has rolled out new protocols, including the restriction of direct root SSH login.

Your task is to disable direct SSH root login on all app servers within the Stratos Datacenter.

#### Solution: 

- Access each app server: stapp01, stapp02, and stapp03 via the jump host. 

- Edit the SSH configuration file:

```
sudo vim /etc/ssh/sshd_config
```
- Update or add the directive:

```
PermitRootLogin no
```
- Restart the SSH service to apply changes:
```
sudo systemctl restart sshd
```

