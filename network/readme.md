
# cloudflare-dns-updater.py
A python script to update a Cloudflare DNS A record with the external IP of the source machine.  
Used to provide DDNS service for my home
Needs the DNS record pre-creating on Cloudflare

Install python3 & pip3
```bash
apt install python3 python3-pip
```

Install cloudflare python api
```bash
sudo pip3 install cloudflare
```

Edit the file and add your cloudflare crendentials:
```python
CLOUDFLARE_API_KEY="your_api_key"
CLOUDFLARE_API_EMAIL="your_cloudflare_email@mail.com"
```
Usage:
```python
python3 cloudflare-dns-updater.py domain.com
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


## Add pyhton script to crontab

open crontab editor
```bash 
sudo crontab -e
```

Example:  
add this line to the end of file.
This will run the script every 5min

```bash
*/5 * * * * /usr/bin/python3 cloudflare-dns-updater.py domain.com > cf.log
```

save the file
```
ctrl + x 
```