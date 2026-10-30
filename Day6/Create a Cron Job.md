## Day 6: Create a Cron Job 

#### Task: 

The Nautilus system admins team has prepared scripts to automate several day-to-day tasks. They want them deployed on all app servers in Stratos DC on a schedule. Before that they need to test similar functionality with a sample cron job. Perform the steps below:
- Install cronie package on all Nautilus app servers and start crond service.
- Add a cron */5 * * * * echo hello > /tmp/cron_text for the root user.

#### Solution: 

```sh 
# Install cronie (RHEL/CentOS/Amazon Linux)

sudo yum install -y cronie

# Start and enable crond
sudo systemctl start crond
sudo systemctl enable crond

# Install the cron entry for root 
echo */5 * * * * echo hello > /tmp/cron_text | sudo crontab -u root - 

```
