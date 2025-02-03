---
description: This file is located in the root of your Lapsus Client install
---

# 📄 settings.json

<details>

<summary>Example Config</summary>

Example config with default settings.

{% code title="settings.json" overflow="wrap" %}
```json
{
  "version": "2.7",
  "name": "Lapsus Client",
  "logo": {
    "url": "/assets/img/logo_background.png"
  },
  "defaulttheme": "lapsus",
  "timezone": "Europe/London",
  "main_web": "https://yourdomain.com",
  "discord_server": "https://discord.gg/invite/",
  
  "profile_json": true,

  "news": {
    "new1_type": "Recommendation",
    "new1_title": "Try Lapsus Launcher",
    "new1_message": "Our new project focused on Minecraft gaming, a next generation launcher to play Minecraft at another performance.",
    "new1_img": "/assets/img/lapsus_launcher_banner.png",
    "new1_button_text": "Try it now!",
    "new1_button_link": "https://github.com/ManucrackYT/LapsusLauncher",

    "new2_type": "Info",
    "new2_title": "Lapsus Client has been officialy released!",
    "new2_message": "Thanks for using Lapsus Client, report any bugs or problems at our Github.",
    "new2_img": "/assets/img/lapsus_client_thanks.png",
    "new2_button_text": "GitHub",
    "new2_button_link": "https://github.com/ManucrackYT/LapsusClient"
  },

  "resources": {
    "note": "Options: MB, GB. This is used to show user's resources.",
    "type": "MB"
  },
  "website": {
    "port": 8080,
    "secret": "changeme"
  },
  "pterodactyl": {
    "domain": "https://panel.yourdomain.com",
    "key": "ptla_",
    "account_key": "ptlc_"
  },
  "storelimits": {
    "ram": "5120",
    "disk": "8240",
    "cpu": "300",
    "servers": "3"
  },
  "database": "sqlite://database.sqlite",
  "api": {
    "client": {
      "misc": {
        "purger": true,
        "getip": true
      },

      "webhook": {
        "auditlogs": false
      },
      "api": {
        "enabled": false,
        "code": "lapsus"
      },
      "j4r": {
        "enabled": false,
        "ads": [
          {
            "name": "Example server 1",
            "invite": "https://discord.gg/example",
            "id": "000000000000000000",
            "coins": 25
          },
          {
            "name": "Example server 2",
            "invite": "https://discord.gg/example",
            "id": "000000000000000000",
            "coins": 200
          }
        ]
      },
      "bot": {
        "token": "BOT_TOKEN_HERE",
        "joinguild": {
          "_comment": "The Discord bot must be in these servers and have invite permissions. Automatic guild joining will not work unless role packages are configured correctly. You can always just set it to a random role & package so that only this works.",
          "enabled": true,
          "guildid": [
            "000000000000000000"
          ]
        }
      },
      "passwordgenerator": {
        "signup": true,
        "note": "Use this to disable signups",
        "length": 16
      },
      "allow": {
        "newusers": true,
        "regen": true,
        "server": {
          "create": true,
          "modify": true,
          "delete": true
        },
        "overresourcessuspend": false
      },
      "oauth2": {
        "_comment": "Go to https://discord.dev/ and create an application to set these up.",
        "id": "",
        "secret": "",
        "link": "http://localhost:8080",
        "callbackpath": "/callback",
        "prompt": true,
        "ip": {
          "trust x-forwarded-for": true,
          "block": [],
          "duplicate check": true
        }
      },
      "ratelimits": {
        "/callback": 2,
        "/create": 1,
        "/delete": 1,
        "/modify": 1,
        "/updateinfo": 1,
        "/setplan": 2,
        "/admin": 1,
        "/regen": 1,
        "/renew": 1,
        "/api/userinfo": 1
      },
      "packages": {
        "default": "default",
        "list": {
          "default": {
            "ram": 1536,
            "disk": 5120,
            "cpu": 100,
            "databases": 1,
            "servers": 1
          },

          "premium": {
            "ram": 2048,
            "disk": 10240,
            "cpu": 200,
            "databases": 3,
            "servers": 3
          }
        },
        "rolePackages": {
          "note": "This allows you to set a different plan to people who have a specific role however this requires the Discord bot to be configured and functioning. This is mainly used for Boost rewards",
          "roleServer": "00000000000000",
          "roles": {
            "000000000000000000": "role"
          }
        }
      },
      "locations": {
        "2": { "name": "Germany 🇩🇪", "city": "Node 01", "package": null }
      },
      "eggs": {
       "paper": {
          "display": "Minecraft Java - Paper",
          "minimum": {
            "ram": 1024,
            "disk": 1024,
            "cpu": 50
            
          },
          "maximum": {
            "ram": null,
            "disk": null,
            "cpu": null
            
          },
          "info": {
            "egg": 4,
            "docker_image": "ghcr.io/pterodactyl/yolks:java_17",
            "startup": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -Dterminal.jline=false -Dterminal.ansi=true -jar {{SERVER_JARFILE}}",
            "environment": {
              "SERVER_JARFILE": "server.jar",
              "BUILD_NUMBER": "latest"
            },
            "feature_limits": {
              "databases": 4,
              "backups": 4,
              "allocations": 2
            }
          }
        },
        "bungeecord": {
          "display": "Minecraft Java - BungeeCord",
          "minimum": {
            "ram": 512,
            "disk": 512,
            "cpu": 75
          },
          "maximum": {
            "ram": null,
            "disk": null,
            "cpu": null
          },
          "info": {
            "egg": 1,
            "docker_image": "ghcr.io/pterodactyl/yolks:java_17",
            "startup": "java -Xms128M -Xmx{{SERVER_MEMORY}}M -jar {{SERVER_JARFILE}}",
            "environment": {
              "SERVER_JARFILE": "bungeecord.jar",
              "BUNGEE_VERSION": "latest"
            },
            "feature_limits": {
              "databases": 4,
              "backups": 4,
              "allocations": 2
            }
          }
        },
        "bedrock": {
          "display": "Minecraft Bedrock - Vanilla",
          "minimum": {
            "ram": 512,
            "disk": 512,
            "cpu": 75
          },
          "maximum": {
            "ram": null,
            "disk": null,
            "cpu": null
          },
          "info": {
            "egg": 16,
            "docker_image": "ghcr.io/parkervcp/yolks:debian",
            "startup": "./bedrock_server",
            "environment": {
              "BEDROCK_VERSION": "latest",
              "LD_LIBRARY_PATH": ".",
              "SERVERNAME": "A Bedrock Server",
              "GAMEMODE": "survival",
              "DIFFICULTY": "easy",
              "CHEATS": "true"
            },
            "feature_limits": {
              "databases": 4,
              "backups": 4
            }
          }
        },
        "nodejs": {
          "display": "Code - NodeJS",
          "minimum": {
            "ram": 512,
            "disk": 512,
            "cpu": 75
          },
          "maximum": {
            "ram": null,
            "disk": null,
            "cpu": null
          },
          "info": {
            "egg": 15,
            "docker_image": "ghcr.io/parkervcp/yolks:nodejs_18",
            "startup": "if [[ -d .git ]] && [[ {{AUTO_UPDATE}} == \"1\" ]]; then git pull; fi; if [[ ! -z ${NODE_PACKAGES} ]]; then /usr/local/bin/npm install ${NODE_PACKAGES}; fi; if [[ ! -z ${UNNODE_PACKAGES} ]]; then /usr/local/bin/npm uninstall ${UNNODE_PACKAGES}; fi; if [ -f /home/container/package.json ]; then /usr/local/bin/npm install; fi; /usr/local/bin/node /home/container/{{BOT_JS_FILE}}",
            "environment": {
              "USER_UPLOAD": "0",
              "AUTO_UPDATE": "0",
              "MAIN_FILE": "index.js",
              "BOT_JS_FILE": "index.js"
            },
            "feature_limits": {
              "databases": 4,
              "backups": 4
            }
          }
        },
        "python": {
          "display": "Code - Python",
          "minimum": {
            "ram": 512,
            "disk": 512,
            "cpu": 75
          },
          "maximum": {
            "ram": null,
            "disk": null,
            "cpu": null
          },
          "info": {
            "egg": 19,
            "docker_image": "ghcr.io/parkervcp/yolks:python_3.10",
            "startup": "if [[ -d .git ]] && [[ {{AUTO_UPDATE}} == \"1\" ]]; then git pull; fi; if [[ ! -z {{PY_PACKAGES}} ]]; then pip install -U --prefix .local {{PY_PACKAGES}}; fi; if [[ -f /home/container/${REQUIREMENTS_FILE} ]]; then pip install -U --prefix .local -r ${REQUIREMENTS_FILE}; fi; /usr/local/bin/python /home/container/{{BOT_PY_FILE}}",
            "environment": {
              "USER_UPLOAD": "0",
              "AUTO_UPDATE": "0",
              "BOT_PY_FILE": "bot.py",
              "REQUIREMENTS_FILE": "requirements.txt"
            },
            "feature_limits": {
              "databases": 4,
              "backups": 4
            }
          }
        }
      },
      "coins": {
        "enabled": true,
        "store": {
          "_comment": "The cost and per is not intended to used with 0. This is not intended to sell resources for coins. Make sure coins are enabled too, or else there can be errors.",
          "enabled": true,
          "ram": {
            "cost": 400,
            "per": 1024
          },
          "disk": {
            "cost": 350,
            "per": 3072
          },
          "cpu": {
            "cost": 400,
            "per": 50
          },
          "databases": {
            "cost": 10,
            "per": 1
          },
          "servers": {
            "cost": 100,
            "per": 1
          }
        }
      }
    },
  },
  "whitelist": {
    "note": "This allows only specific people to be able to use the dashboard",
    "status": false,
    "users": [
      "User ID"
    ]
  },
  "servercreation": {
    "note": "You can set how much it should cost to create a server here, the default price is free",
    "cost": 0
  },
  "renewals": {
    "status": false,
    "cost": 0,
    "delay": 14
  },
  "logging": {
    "status": false,
    "webhook": "Webhook URL",
    "actions": {
      "user": {
        "signup": true,
        "create server": true,
        "gifted coins": true,
        "modify server": true,
        "buy servers": true,
        "buy ram": true,
        "buy cpu": true,
        "buy disk": true,
        "buy databases": true
      }, 
      "admin": {
        "set coins": true,
        "add coins": true,
        "set resources": true,
        "set plan": true,
        "create coupon": true,
        "revoke coupon": true,
        "remove account": true,
        "view ip": true
      }
    }
  },
  "antivpn": {
    "note": "For antivpn to work, generate an apikey on https://proxycheck.io/. If you put no key, Lapsus Client will disable antivpn automatically.",
    "status": false,
    "APIKey": "Proxycheck APIKey",
    "whitelistedIPs": ["IP address"]
  },

  "beta":{
    "notification": "This is a beta feature and can contain some bugs.",


    
    "note": "This isn't working yet",
    
    "location1_enabled": false,
    "location1_name": "Germany",
    "location1_city": "Falkenstein",
    "location1_flag": "https://flagcdn.com/h20/de.png",

    "location2_enabled": true,
    "location2_name": "Netherlands",
    "location2_city": "Eygelshoven",
    "location2_flag": "https://flagcdn.com/h20/nl.png",

    "location3_enabled": false,
    "location3_name": "Finland",
    "location3_city": "Helsinki",
    "location3_flag": "https://flagcdn.com/h20/fi.png"
  }
}
```
{% endcode %}

</details>

{% hint style="warning" %}
Any option called `note`, `_note` or `_comment` is for reference only, and doesn't do anything.
{% endhint %}

{% hint style="warning" %}
This settings.json reference may not be updated, check that the variable exists before editing it.
{% endhint %}

| Option           | Default                    | Description                                                                                                                           |
| ---------------- | -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `name`           | `Lapsus Client`            | The name of your client as displayed to users                                                                                         |
| `defaulttheme`   | `lapsus`                   | The default client theme                                                                                                              |
| `timezone`       | `Europe/London`            | Server timezone                                                                                                                       |
| `main_web`       |                            | Your client URL for production (ideally no port on the end, see reverse proxy docs for doing this)                                    |
| `discord_server` |                            | The URL to your host's Discord Server                                                                                                 |
| `database`       | `sqlite://database.sqlite` | <p>The path to an SQLite database file, starting with <code>sqlite://</code><br><br>The file will be created if it does not exist</p> |

## `logo`

| Option | Default                          | Description                                                                                 |
| ------ | -------------------------------- | ------------------------------------------------------------------------------------------- |
| `url`  | `assets/img/logo_background.png` | The logo/favicon of your client. Can be local path (relative to install root) or remote URL |

## `news`

{% hint style="info" %}
`new` entries here are incremented by 1 (ex. `new1`, `new2`, etc). We will use `new1` for reference, but it can be `new(any number)` to create new news entries.
{% endhint %}

| Option             | Default | Description                                                   |
| ------------------ | ------- | ------------------------------------------------------------- |
| `new1_type`        |         | <p>News type<br><br>Can be whatever you want</p>              |
| `new1_title`       |         | Title of news post                                            |
| `new1_message`     |         | Content of news post                                          |
| `new1_img`         |         | <p>Cover image for news post <br><br>Can be a path or URL</p> |
| `new1_button_text` |         | Text for the CTA button                                       |
| `new1_button_url`  |         | URL for the CTA button                                        |

## `resources`

| Option | Default | Description                                                                        |
| ------ | ------- | ---------------------------------------------------------------------------------- |
| `type` | `MB`    | <p>Unit used to show resources<br><br>Can be: <code>MB</code>, <code>GB</code></p> |

## `website`

| Option   | Default | Description                                                                                                                                                                                                                                                              |
| -------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `port`   | `8000`  | <p>Port used to access Lapsus<br><br><span data-gb-custom-inline data-tag="emoji" data-code="26a0">⚠️</span>This is HTTP-only. To set up HTTPS, please see <a data-mention href="../installation/configuring-a-reverse-proxy.md">configuring-a-reverse-proxy.md</a>.</p> |
| `secret` |         | The password to access the admin dashboard                                                                                                                                                                                                                               |

## `pterodactyl`

| Option        | Default | Description                                                  |
| ------------- | ------- | ------------------------------------------------------------ |
| `domain`      |         | Link to your [Pterodactyl ](https://pterodactyl.io)panel     |
| `key`         |         | Your [Pterodactyl](https://pterodactyl.io) API key           |
| `account_key` |         | Your [Pterodactyl](https://pterodactyl.io) admin account key |

## `storelimits`

| Option    | Default | Description                      |
| --------- | ------- | -------------------------------- |
| `ram`     | `5120`  | Maximum RAM users can buy        |
| `disk`    | `8240`  | Maximum disk space users can buy |
| `cpu`     | `300`   | Maximum CPU users can buy        |
| `servers` | `3`     | Maximum servers users can buy    |

## `api`

### `client`

#### `misc`

| Option   | Default | Description          |
| -------- | ------- | -------------------- |
| `purger` | `true`  | :warning:Depreceated |
| `getip`  | `true`  | :warning:Depreceated |

### `webhook`

| Option      | Default | Description                                |
| ----------- | ------- | ------------------------------------------ |
| `auditlogs` | `false` | Send auditlogs through the Discord webhook |

### `api` (client)

{% hint style="info" %}
This is different from the _other_ [`api`](settings.json.md#api).
{% endhint %}

| Option    | Default  | Description                 |
| --------- | -------- | --------------------------- |
| `enabled` | `false`  | Enables webhooks            |
| `code`    | `lapsus` | :warning:Do not change this |

### `j4r`

{% hint style="info" %}
For a guide on all this, see [#j4r-join-4-rewards](../installation/configuring-discord.md#j4r-join-4-rewards "mention").
{% endhint %}

| Option    | Default | Description                      |
| --------- | ------- | -------------------------------- |
| `enabled` | `false` | Enables **J4R** (Join 4 Rewards) |

#### `ads`

{% hint style="info" %}
You can have multiple ad blocks within the `ads` section.
{% endhint %}

| Option   | Default | Description                                                                                                                |
| -------- | ------- | -------------------------------------------------------------------------------------------------------------------------- |
| `name`   |         | The name of the Discord server                                                                                             |
| `invite` |         | The invite link                                                                                                            |
| `id`     |         | The server's Guild ID (See [#getting-the-guild-id](../installation/configuring-discord.md#getting-the-guild-id "mention")) |
| `coins`  |         | The amount of coins to give after joining                                                                                  |

### `bot`

| Option  | Default | Description      |
| ------- | ------- | ---------------- |
| `token` |         | Your bot's token |

#### `joinguild`

| Option    | Default | Description                                                                                                                 |
| --------- | ------- | --------------------------------------------------------------------------------------------------------------------------- |
| `enabled` | `true`  | <p>Is automatic guild joining enabled? <br><br>(OAuth2 app joins the guild on the user's behalf during login)</p>           |
| `guildid` |         | Your server's Guild ID (See [#getting-the-guild-id](../installation/configuring-discord.md#getting-the-guild-id "mention")) |

### `passwordgenerator`

| Option   | Default | Description                   |
| -------- | ------- | ----------------------------- |
| `signup` | `true`  | Are signups enabled?          |
| `length` | `16`    | Length of generated passwords |

### `allow`

| Option     | Default | Description                      |
| ---------- | ------- | -------------------------------- |
| `newusers` | `true`  | Are new users allowed to signup? |
| `regen`    |         |                                  |
|            |         |                                  |
