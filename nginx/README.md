# nginx ssl-aplus configuration

**Note:** this document assumes your nginx config lives in `/etc/nginx`; if it
does not, you need to replace that path in these instructions *and* in `ssl-aplus.conf`
in order for everything to work

## Create DH parameters

Generate a `dhparams.pem` file in `/etc/nginx` using

    openssl dhparam -out dhparams.pem 2048

## Include the a-plus config file

Inside your `server{ }` block, add:

    include /etc/nginx/ssl-aplus.conf;

You will need to specify:

    listen 443 ssl; # or another port of your choice for ssl
    ssl_certificate /path/to/signed-cert.crt;
    ssl_certificate_key /path/to/cert-private-key.key;
    ssl_trusted_certificate /path/to/ca-bundle.pem; # get from your cert provider

As well as any usual server parameters.

## Reload configuration

   sudo nginx -s reload

## Test

1. Make sure you can visit your site with a browser without any SSL errors
2. Visit [Qualys SSL Labs](https://ssllabs.com) and test your server.