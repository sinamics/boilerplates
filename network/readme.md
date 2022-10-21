
# cloudflare-dns-updater.sh
A bash script to update a Cloudflare DNS A record with the external IP of the source machine.  
Used to provide DDNS service for my home
Needs the DNS record pre-creating on Cloudflare

### Add script to crontab

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