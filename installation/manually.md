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

# 🛠️ Manually

## 💻 Download the code from GitHub

Go to releases on our GitHub repo and download the latest release available. Upload it to your VPS or NodeJS Server and unzip it.

## ⚙️ Editing settings

Now open `settings.json` and edit the file as you need, we recommend changing the following (options are explained more in the [settings.json.md](../reference/settings.json.md "mention") reference):

{% code title="The name and logo" %}
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
  }
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

Start the NodeJS Server with the "Start" button if you are using a Pterodactyl Server.

If you are using a VPS, go to the Lapsus directory and run `node .`

You should see something like this:

<figure><img src="../.gitbook/assets/imagen (13).png" alt=""><figcaption><p>If you see this, congratulations! You have setup everything correctly to use Lapsus Client</p></figcaption></figure>

Now login using the URL you setup and you will be ready to login for the first time!

<figure><img src="../.gitbook/assets/imagen (14).png" alt=""><figcaption><p>Lapsus Client - Login page</p></figcaption></figure>

### 🕛  Running Lapsus Client even if you close SSH

Follow these commands to make Lapsus Client work 24/7:

```javascript
sudo npm install -g forever
```

Check your on the LapsusClient folder

```javascript
forever node .
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
