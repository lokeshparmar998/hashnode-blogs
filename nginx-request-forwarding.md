```
server {
    if ($host = www.avrio.energy) {
        return 301 https://$host$request_uri;
    } # managed by Certbot


    if ($host = avrio.energy) {
        return 301 https://$host$request_uri;
    } # managed by Certbot


    listen 80;
    listen [::]:80;
    server_name avrio.energy www.avrio.energy;

    location / {
        return 301 https://klimashift.com$request_uri;
    }
}

server {
    listen 443 ssl;
    listen [::]:443 ssl;
    server_name avrio.energy www.avrio.energy;

    location / {
        return 301 https://klimashift.com$request_uri;
    }

    ssl_certificate /etc/letsencrypt/live/avrio.energy/fullchain.pem; # managed by Certbot
    ssl_certificate_key /etc/letsencrypt/live/avrio.energy/privkey.pem; # managed by Certbot

}
```
