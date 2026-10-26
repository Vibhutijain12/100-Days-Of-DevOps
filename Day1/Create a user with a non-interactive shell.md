### Day 1: Create a User with a Non-Interactive Shell

#### Task: 

To accommodate the backup agent tool's specifications, the system admin team at xFusionCorp Industries requires the creation of a user with a non-interactive shell.

Here's your task:
- Create a user named yousuf with a non-interactive shell on App Server 3.

#### Solution:

- Login to the App Server 3 using the provided credentials:

```
ssh banner@stapp03
```
- Here’s a command to create a user with non-interactive shell: 

```
sudo useradd -s /sbin/nologin yousuf
```

Alternatively, some users prefer:

```
sudo adduser yousuf --shell /sbin/nologin
```
