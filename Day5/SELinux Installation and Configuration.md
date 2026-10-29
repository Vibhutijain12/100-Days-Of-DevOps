## Day 5: SELinux Installation and Configuration

#### Task: 
Following a security audit, the xFusionCorp Industries security team has opted to enhance application and server security with SELinux. 

- For App Server 2 in the Stratos Datacenter: install required SELinux packages, and permanently disable SELinux for now (the server will be rebooted as part of scheduled maintenance tonight). 
- Disregard current runtime status; the final post-reboot state should be disabled.

#### Solution: 

- Step 1: Install SELinux packages
Debian/Ubuntu:
```
sudo apt-get install -y selinux selinux-utils selinux-policy-default
```

- Step 2: Permanently disable SELinux (so it is disabled after reboot)
```
sudo vi /etc/selinux/config
```
Change the line:
```
SELINUX=enforcing
```
to 
```
SELINUX=disabled
```

- Verification:
```
grep SELINUX= /etc/selinux/config
```
