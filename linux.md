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
