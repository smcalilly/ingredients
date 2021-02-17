

## etc
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

- [more granuluar permissions for a script0


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

