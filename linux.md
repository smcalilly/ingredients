

## etc
see logs
```bash
cat /var/log/syslog
sudo cat /var/log/auth.log
cat /var/log/mail.log

# disk stuff
cat /var/log/dmesg

# failed login attempts
sudo cat /var/log/btmp

# login/logout history
sudo cat /var/log/wtmp
```

find a word in a file, with a line number
```bash
grep -rnw '/path/to/somewhere/' -e 'pattern'
```

restart a service
```bash
sudo systemctl reload sshd.service
```

list human-readable file size
```bash
ls -lh
```

change permissions for a script
```bash
sudo chmod +x script.sh
```

search for a word in all the files within a directory:
```bash
grep lambda *
```


## ssh
how to setup ssh keys
```bash
curl https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-2
```

generate new key:
```bash
ssh-keygen -t rsa
```

print public key
```bash
cat ~/.ssh/id_rsa.pub
```
remove keys
```bash
rm -rf ~/.ssh 
```
secure copy
```bash
scp linux.md user@host:~/recipes
```

see ssh logs
```bash
tail -n 500 /var/log/auth.log | grep 'sshd'
```

## ufw
```bash
sudo ufw status verbose
```

## psad
```bash
sudo ufw reload

sudo psad -R
sudo psad --sig-update
sudo psad -H

# analyze
sudo psad --fw-analyze

# see status
sudo psad --Status
```

## fail2ban
```bash
sudo fail2ban-client start
sudo fail2ban-client reload
sudo fail2ban-client add sshd

# check the status
sudo fail2ban-client status
```

## ntp
restart ntp:
```bash
sudo /etc/init.d/ntp stop
sudo ntpd -q -g
sudo /etc/init.d/ntp start
```

## networking
troubleshoot host that is "down"
```bash
nmap <hostname> -Pn
```

what is that open port? ssh into the host once it's up
```bash
netstat -tulpn | grep <port>
```

## backups
see block devices:
```bash
lsblk -p
```

backup:
```bash
dd if=/dev/mmcblk0 dd of=~/backups/backup.img bs=1M
```
you can try to create backup image of a block device, [remotely](https://www.it-react.com/index.php/2020/02/02/backup-your-raspberry-pi-remotely/)

watch the process:
```bash
watch -n 10 ls -alh
```

## crontab
edit crontab
```bash
sudo crontab -e
```

## users
- /etc/group

## hardware key for 2fa
[thanks](https://mutschler.eu/linux/install-guides/pop-os-post-install/#yubikey-two-factor-authentication-for-adminsudo-password) 
```bash
sudo apt install -y libpam-u2f # second-factor for sudo commands
pamu2fcfg > ~/u2f_keys # When your device begins flashing, touch the metal contact to confirm the association.
pamu2fcfg -n >> ~/u2f_keys # Do the same with your backup device
sudo mv ~/u2f_keys /etc/u2f_keys
# Make this required for common-auth
echo "auth    required                        pam_u2f.so nouserok authfile=/etc/u2f_keys cue" | sudo tee -a /etc/pam.d/common-auth
# Before you close the terminal, open a new one and check whether you can do `sudo echo test`
```

## etc, pt2
```bash
htop
```

kill processes by name
```bash
pkill firefox
```

see all the ports listening for traffic
```bash
sudo ss -lntup
```

clear usb drive
```bash
sudo dd if=/dev/zero of=/dev/disk2 bs=1m count=1
```

flash a new image
```bash
sudo dd if=/path/to/disk.img of=/dev/disk2 bs=4m
```

## sed and awk
output line 164 in a file:
```bash
I have no name!@1ac3d4b9c04a:~/dist/src/processing/ImageDetectionModule$ awk 'NR==164' ImageDetectionModule.js
                doc.pages[pageIndex].pageRotation = document.pages[pageIndex].pageRotation;
I have no name!@1ac3d4b9c04a:~/dist/src/processing/ImageDetectionModule$ sed '164!d' ImageDetectionModule.js
                doc.pages[pageIndex].pageRotation = document.pages[pageIndex].pageRotation;
I have no name!@1ac3d4b9c04a:~/dist/src/processing/ImageDetectionModule$ 
```
- `awk 'NR==164' ImageDetectionModule.js`
- `sed '164!d' ImageDetectionModule.js`
