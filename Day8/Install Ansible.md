
## Day 8: Install Ansible (pip3, global)

#### Task: 

The Nautilus DevOps team will use the jump host as the Ansible controller. Install Ansible version 4.9.0 on the jump host using pip3 only, and make sure the ansible binary is available globally for all users.

#### Solution: 

- Install Python 3 and pip3 (RHEL/CentOS):

```
sudo yum install python3 -y
```

- Verify pip3 is available:

```
pip3 --version
```

- Install Ansible 4.9.0 into a global prefix so binaries land in /usr/local/bin: 

```
sudo yum install --ansible=4.9.0 --prefix=/usr/local
```

- Confirm installation:

```
ansible --version
```
The output should include an Ansible core version.

-  Also verify the pip package:

```
pip3 show ansible
```
