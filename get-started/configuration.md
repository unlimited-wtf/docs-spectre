# ⚙ Configuration

Spectre can be configured via the provided `config.json` or by setting convars (unless otherwise stated). Convars takes precedence over the `config.json`.

## Config

```
// config.json

{
  "port": "3000",
  "unlDisableServe": "false",
  "unlMySQLSessions": "false",

  "QBName": "qb-core",
  "QBObject": "QBCore",
  "QBShared": "QBShared",
  
  "vehGarageColumn": "garage",
  "vehStateColumn": "state",
  "vehTables": [
    {
      "table": "trunkitems",
      "column": "plate"
    },
    {
      "table": "gloveboxitems",
      "column": "plate"
    }
  ],

  "additionalMoneyTypes": {},

  "usedInventory": "qb-inventory",
  "maxPlayerSlots": "41",

  "disableWeaponLogs": "false",
  "excludeWeaponLogsFromDiscord": "false",
  "unlDiscordHook": "false",
  "unlGameDiscordHook": "false",
  "unlPlayerDiscordHook": "false",
  "unlDevDiscordHook": "false",
  "unlWebDiscordHook": "false",

  "dashboardInterval": "5000",
  "mapInterval": "1250"
  
  "vehGarageColumn": "garage",
  "vehStateColumn": "state",
  
  "customHandleDeadEvent": "false",
  "customHandleCuffedEvent": "false"
}

```

## Convars

```js-templates
// server.cfg

set unlWebPort [Int]                  // sets webpanel serving port @default: 3000
set unlDisableServe [Boolean]         // enalbe/disable serving client files
set unlMySQLSessions [Boolean]        // enable/disable persistent sessions [24h]

set unlUsedInventory [String]         // sets used inventory @default: qb-inventory*
set unlMaxPlayerSlots [Int]           // sets the inventory view player slots count @default: 41
set unlQBName [String]                // sets qb-core resource name @default: qb-core
set unlQBObject [String]              // sets QBCore object name @default: QBCore
set unlQBShared [String]              // sets QBCore shared object name @default: QBShared

set unlWebDashInterval [Int]          // sets dashboard refresh interval @default 5000
set unlWebMapInterval [Int]           // sets map refresh interval @default: 1250

set unlDiscordHook [WebhookUrl]       // sets Unlimited Logger Discord-Webhook
set unlGameDiscordHook [WebhookUrl]   // sets Game Logger Discord-Webhook
set unlPlayerDiscordHook [WebhookUrl] // sets Player Logger Discord-Webhook
set unlDevDiscordHook [WebhookUrl]    // sets Dev Logger Discord-Webhook
set unlWebDiscordHook [WebhookUrl]    // sets Web Logger Discord-Webhook


```

_\*folder structure and resource structure must follow the qb-inventory convention_

## External frontend

Spectre offers the option to host the frontend externally.&#x20;

This requires sharing the same domain on frontend and backend.

```
// example

frontend:    https://frontend.unlimited.wtf

backend:     https://backend.unlimited.wtf
```

Just a few steps are needed:

1. Upload the content of html to your webspace/server
2. Edit `index.html` by changing `./` to only `/` in the filepaths (otherwise page reload will fail)
3. Edit `assets/externalHosting.js` to fit your requirements\
   (in most cases adjusting the host variable is sufficient - host: "https://backend.unlimited.wtf")

{% hint style="info" %}
If you host your frontend externally, its recommended to disable serving your frontend via gamerserver by setting config/convar `unlDisableServe` to true
{% endhint %}
