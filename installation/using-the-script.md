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
    visible: false
---

# ⚙️ Using the script

## 🔐 Starting the Install Script

Run this in your terminal:

```bash
bash <(curl -s https://raw.githubusercontent.com/lapsusdevs/script/main/manager.sh)
```

_✨ Now relax and let the script do its thing ✨_

Lapsus Client will run once the installation script finishes.

{% hint style="info" %}
On some systems, it's required to be already logged in as root before executing the one-line command (where `sudo` is in front of the command does not work).&#x20;

This can be achieved (if you're currently a normal user) by typing `su`, then entering `root`'s password.
{% endhint %}

{% hint style="warning" %}
**Important:**

Check that you have a compatible NodeJS version. If not, the script will try to install one for you.
{% endhint %}

## ⚙️ Editing essential settings

Now open `settings.json` and edit the file as you need, we recommend changing the following (options are explained more in the [settings.json.md](../reference/settings.json.md "mention") reference):

{% code title="The name and logo" fullWidth="false" %}
```json
"name": "Lapsus Client",
  "logo": {
    "url": "/assets/img/logo_background.png"
  },
```
{% endcode %}

{% code title="The port and secret" %}
```json
"website": {
    "port": 8000,
    "secret": "changeme"
  },
```
{% endcode %}

{% code title="Pterodactyl settings" %}
```json
"pterodactyl": {
    "domain": "https://panel.yourdomain.com",
    "key": "ptla_",
    "account_key": "ptlc_"
  },
```
{% endcode %}

{% code title="Discord OAuth2 settings" %}
```json
"oauth2": {
    "_comment": "Go to https://discord.dev/ and create an application to set these up.",
    "id": "",
    "secret": "",
    "link": "http://localhost:8080",
    [...]
```
{% endcode %}

<figure><img src="../.gitbook/assets/imagen (12).png" alt=""><figcaption><p><strong>On the Discord Developer Portal, your Redirect must end with "/callback"</strong></p></figcaption></figure>

## 💉 Starting the Client

Now run `node .` , if you set everything correctly, Lapsus Client will show something like this:

<figure><img src="../.gitbook/assets/imagen (13).png" alt=""><figcaption><p>If you see this, congratulations! You have setup everything correctly to use Lapsus Client</p></figcaption></figure>

Now login using the URL you setup and you will be ready to login for the first time!

<figure><img src="../.gitbook/assets/imagen (14).png" alt=""><figcaption><p>Lapsus Client - Login page</p></figcaption></figure>

### 🕛  Running Lapsus Client even if you close SSH

Follow these commands to make Lapsus Client work 24/7 using PM2:

```javascript
npm install pm2@latest -g
```

Check your on the LapsusClient folder

```javascript
cd LapsusClient
pm2 start index.js
```

After this, Lapsus Cient will be running 24/7 on your VPS even if you close the SSH Client (ex. PuTTY)

## ✔️ All done!

To see your next steps, continue on to the following pages:

{% content-ref url="configuring-discord.md" %}
[configuring-discord.md](configuring-discord.md)
{% endcontent-ref %}

{% content-ref url="../reference/settings.json.md" %}
[settings.json.md](../reference/settings.json.md)
{% endcontent-ref %}

{% content-ref url="extensions-and-themes.md" %}
[extensions-and-themes.md](extensions-and-themes.md)
{% endcontent-ref %}

{% content-ref url="configuring-a-reverse-proxy.md" %}
[configuring-a-reverse-proxy.md](configuring-a-reverse-proxy.md)
{% endcontent-ref %}
