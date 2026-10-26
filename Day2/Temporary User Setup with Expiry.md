### Day2: Temporary User Setup with Expiry

#### Task: 
As part of the temporary assignment to the **Nautilus project**, a developer named rose requires access for a limited duration. To ensure smooth access management, a temporary user account with an expiry date is needed.

Here's what you need to do:
- Create a user named ji, on App Server 2 in Stratos Datacenter.
- Set the expiry date to 2027-02-17, ensuring the user is created in lowercase as per standard protocol.

#### Solution: 

- SSH into App Server 2 using the credentials provided in the lab:

```
ssh username@hostname 
ssh steve@stapp02
```
- Create the user with an expiry date. Run the following command:

```
sudo useradd jim -e 2027-02-17
```
- Verify the user and expiry. Confirm the setup with:

```
sudo chage -l jim
```
