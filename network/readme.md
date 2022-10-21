
# cloudflare-dns-updater.sh
A bash script to update a Cloudflare DNS A record with the external IP of the source machine.  
Used to provide DDNS service for my home
Needs the DNS record pre-creating on Cloudflare

Edit the file and add your cloudflare crendentials:
```bash
zone=domain.com
dnsrecord=domain.com
cloudflare_auth_email=your_email@mail.com
cloudflare_auth_key=your_cloudflare_api_key
```

# one.com-dns-updater.py
A python script to update a one.com DNS A record with the external IP of the source machine.  
Used to provide DDNS service for my home
Needs the DNS record pre-creating on one.com

Edit the file and add your one.com crendentials:
```python
# YOUR ONE.COM LOGIN
USERNAME="mail@mail.com"
PASSWORD="password"
DOMAIN="domain.com"

# LIST OF SUBDOMAINS YOU WANT POINTING TO YOUR IP
SUBDOMAINS = ["www", "another_subdomain"]
```

## Add bash script to crontab

open crontab editor
```bash 
sudo crontab -e
```


make the script executeable
```bash
sudo chmod +x cloudflare-dns-updater.sh
```

add this line to the end of file.
This will run the script every 5min
```bash
*/5 * * * * /bin/bash  /path_to_file/cloudflare-dns-updater.sh >> /path_to_logfile/domain_status.txt 2>&1
```

save the file
```
ctrl + x 
```

## Add pyhton script to crontab

open crontab editor
```bash 
sudo crontab -e
```

add this line to the end of file.
This will run the script every 5min
```bash
*/5 * * * * /usr/bin/python3 /path_to_file/one.com-dns-updater.py
```

save the file
```
ctrl + x 
```