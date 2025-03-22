---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# 🚈 Configuring a Reverse Proxy

{% hint style="info" %}
**What is the a Reverse Proxy for?**

You can use and configure this if you want to use a custom domain for Lapsus Client.

For this example, we will be using [Nginx](https://nginx.org).
{% endhint %}

Follow these steps:

1. Login to your DNS and domain manager (ex. Cloudflare), go to your domain and create a DNS record of type A. For a name put what you want your subdomain to be (ex. `client` or `dash`). You can also put `@` for the root. On IPv4 Address put the IP of the VPS you'll use to configure the Nginx Reverse Proxy (yeah, you will need a VPS to do this).

{% hint style="warning" %}
**Note for Cloudflare Users**

Ensure the subdomain is _gray-clouded_ (not proxied). This is because you will need more ports than just web ones accessible.
{% endhint %}

<figure><img src="../.gitbook/assets/imagen (20).png" alt=""><figcaption><p>Cloudflare - Creating a custom domain for Lapsus Client</p></figcaption></figure>

2. Login to your VPS using SSH and run the following commands:

<pre class="language-bash"><code class="lang-bash"><strong>export DOMAIN="&#x3C;your subdomain from step 1>"
</strong>apt install nginx &#x26;&#x26; apt install certbot &#x26;&#x26;
ufw allow 80 &#x26;&#x26; # or some other fiewall
ufw allow 443 &#x26;&#x26;
certbot certonly -d $DOMAIN 
</code></pre>

Alternative method to request a certificate:

```bash
certbot certonly -d <subdomain>
```

Select option 1 (Nginx Webserver) and follow the steps you will see.\
`nano /etc/nginx/sites-enabled/lapsusclient.conf`

3. Paste the following code, **replacing `<domain>` with your domain and `<port>` with your port (default 8000).**

```nginx
server {
    listen 80;
    server_name <domain>;
    return 301 https://$server_name$request_uri;
}
server {
    listen 443 ssl http2;
location /afkwspath {
  proxy_http_version 1.1;
  proxy_set_header Upgrade $http_upgrade;
  proxy_set_header Connection "upgrade";
  proxy_pass "http://yourLapsusUrl:<port>/afkwspath";
}
    
    server_name <domain>;
ssl_certificate /etc/letsencrypt/live/<domain>/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/<domain>/privkey.pem;
    ssl_session_cache shared:SSL:10m;
    ssl_protocols SSLv3 TLSv1 TLSv1.1 TLSv1.2;
    ssl_ciphers  HIGH:!aNULL:!MD5;
    ssl_prefer_server_ciphers on;
location / {
      proxy_pass http://yourLapsusUrl:<port>/;
      proxy_buffering off;
      proxy_set_header X-Real-IP $remote_addr;
  }
}
```

2. Close your editor and run `sudo systemctl restart nginx`.

{% hint style="success" %}
If you don't get an error, everything is working correctly and now you can use your custom domain! If you get an error from your shell, check you followed all steps correctly.
{% endhint %}
