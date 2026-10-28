## Day 4: Script Execution Permissions

#### Task: 

In a bid to automate backup processes, the xFusionCorp Industries sysadmin team has developed a new bash script named xfusioncorp.sh. While the script has been distributed to all necessary servers, it lacks executable permissions on App Server 3 within the Stratos Datacenter. Your task is to grant executable permissions to the /tmp/xfusioncorp.sh script on App Server 3 and ensure all users can execute it.

#### Solution: 

- Access App Server 1 (via jump host):
```
ssh banner@stapp03 
```

- Grant executable permission to the script:
```
sudo chmod +x xfusioncorp.sh 
```

- Ensure all users can execute it:
```
sudo chmod 755 xfusioncorp.sh 
```
