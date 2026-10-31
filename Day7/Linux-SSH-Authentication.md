## Day 7: Linux SSH Authentication (Password-less access from jump host)

#### Task:

The system admins team of xFusionCorp Industries has set up scripts on the jump host that run at regular intervals and perform operations on all app servers in the Stratos Datacenter. 

To make these scripts work properly we need to ensure the thor user on the jump host has password-less SSH access to all app servers through their respective sudo users (for example, tony for app server 1).

Perform the steps to set up password-less authentication from thor on the jump host to all app servers.

#### Solution: 

- Generate an SSH Key Pair

```
ssh-keygen 
```
- Go to the .ssh folder and copy the public key to all the 3 app servers. 

```
ssh-copy-id tony@stapp01
ssh-copy-id steve@stapp02
ssh-copy-id banner@stapp03
```
- Now try to login all the 3 app server, it would login without password.

```
ssh tony@stapp01
ssh steve@stapp02
ssh banner@stapp03
```
