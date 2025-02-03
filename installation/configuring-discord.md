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

# 💬 Configuring Discord

## 🔐 Login

Head on over to the [Discord Dev Portal](https://discord.com/developers/applications) and create a new application.

<figure><img src="../.gitbook/assets/discorddevcreate.png" alt=""><figcaption><p>Creating a new application</p></figcaption></figure>

Give it a name and create it under **Personal** (or a team it doesn't really matter).

Set your app's name and icon, this is what users will see on the login screen. Set a TOS and Privacy Policy URL if your host has them, these will also be shown at login.

<figure><img src="../.gitbook/assets/discorddevappinfo.png" alt=""><figcaption><p>Discord App Info</p></figcaption></figure>

Next go to **OAuth2**, then add a **Redirect**. This redirect should be the URL to your client (the public one, set as `oauth2.link`) with `/callback`.

Example:&#x20;

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>Example redirect</p></figcaption></figure>

Next copy your `Client ID` and `Client Secret`.

<figure><img src="../.gitbook/assets/clientsecret.png" alt=""><figcaption><p>Client ID and Secret</p></figcaption></figure>

Configure everything in `config.json` now:

{% code title="config.json" %}
```json
      "oauth2": {
        "_comment": "Go to https://discord.dev/ and create an application to set these up.",
        "id": "APPLICATION_ID",
        "secret": "YOUR_SECRET",
        "link": "https://YOUR_DOMAIN",
        // Rest of file
```
{% endcode %}

## 💰 J4R (Join 4 Rewards)

:construction:**WIP** :construction:
