# Installing Honeypot(Tpot)
### update
```bash
sudo apt-get update && sudo apt-get upgrade -y
```
### Create new User
```bash
adduser honeypot
```
Provide strong password for the honeypot user


### Add user to sudo group
```bash
usermod -aG sudo honeypot
```
### switch to new user 
```bash
su honeypot
```
### Install honeypot from github
```bash
sudo git clone https://github.com/telekom-security/tpotce.git
```
### move to tpot directory
```bash
cd tpotce
```
### run install.sh
```bash
./install.sh
```

### select h for Hive
### enter your webusername and password
```bash
honeypotadmin
y
your-password
```
### now reboot the system
```bash
sudo systemctl reboot -i
```

