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

# 🥚 Using the egg

**If you want to install Lapsus Client on a Pterodactyl Server you can use our official egg**

## ⬇️ Download the egg

Go to [this Github Repository](https://github.com/lapsusdevs/egg) and download the .json file which is the egg

## 🪧Import it to the Pterodactyl Panel

Access the Admin Area and go to Nests -> Import Egg (upload it from your local and select a Nest Group) and click Import

<figure><img src="../.gitbook/assets/imagen.png" alt=""><figcaption><p>This is what you should see once you follow the steps mentioned before</p></figcaption></figure>

## ➕ Create a new server

Go to Servers -> Create New -> now set a name, an owner and node and it's important to select the egg you have imported (ig you can create a server on Pterodactyl)\


You can also select which version you want to install

<figure><img src="../.gitbook/assets/imagen (1).png" alt=""><figcaption></figcaption></figure>

Go to the Server Page and wait until the installation process finishes. Once it finishes, follow the next step.

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

Now click the <img src="../.gitbook/assets/imagen (2).png" alt="" data-size="line">  button if the server hasn't started yet, if you have set everything correctly, Lapsus Client will show something like this:

<figure><img src="../.gitbook/assets/imagen (13).png" alt=""><figcaption><p>If you see this, congratulations! You have setup everything correctly to use Lapsus Client</p></figcaption></figure>

Now login using the URL you setup and you will be ready to login for the first time!

<figure><img src="../.gitbook/assets/imagen (14).png" alt=""><figcaption><p>Lapsus Client - Login page</p></figcaption></figure>

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
