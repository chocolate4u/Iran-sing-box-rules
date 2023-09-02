<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/logo-white.png">
  <source media="(prefers-color-scheme: light)" srcset="assets/logo-dark.png">
  <img alt="a logo for iran sing-box rules in both dark and light mode" src="assets/logo-dark.png">
</picture>

<p align="center">
<img alt="GitHub Workflow Status" src="https://flat.badgen.net/github/checks/Chocolate4U/Iran-sing-box-rules/main/build?icon=github">
<img alt="GitHub release" src="https://flat.badgen.net/github/release/Chocolate4U/Iran-sing-box-rules">
<img alt="GitHub Release Date" src="https://flat.badgen.net/github/last-commit/Chocolate4U/Iran-sing-box-rules/release?label=release%20date">
<img alt="license" src="https://flat.badgen.net/github/license/Chocolate4U/Iran-sing-box-rules">
</p>

# :writing_hand: Introduction
This is an Enhanced and All-in-One set of geo-location routing files optimized for Iranian users to use in sing-box and all it's compatible clients.

:bulb: For V2Ray geolocation rules please refer to [Iran V2Ray Rules](https://github.com/Chocolate4U/Iran-v2ray-rules)  
:bulb: For Clash geolocation rules please refer to [Iran Clash Rules](https://github.com/Chocolate4U/Iran-clash-rules)

# :page_with_curl: Categories

## GeoIP  
- `geoip:ir`  
  Contains Iran IP addresses from Maxmind database and IP addresses of Iranian messengers such as `eitaa`, `rubika`, etc.

- `geoip:private`  
  Contains a list of local (LAN) IP addresses.

- `geoip:arvancloud`  
  Contains IP addresses of ArvanCloud.ir CDN.

- `geoip:derakcloud`  
  Contains IP addresses of Derak.cloud CDN.

- `geoip:iranserver`  
  Contains IP addresses of IranServer.com CDN.

- `geoip:cloudflare`  
  Contains IP addresses of ClouFlare CDN.

- `geoip:google`  
  Contains IP addresses of Google, GoogleCloud and GoogleBot.

- `geoip:amazon`  
  Contains IP addresses of Amazon and Amazon Web Services (AWS).

- `geoip:microsoft`  
  Contains IP addresses of Microsoft and Azure Platform.

- `geoip:bing`  
  Contains IP addresses of Bing and Bingbot.

- `geoip:github`  
  Contains IP addresses of GitHub.

- `geoip:facebook`  
  Contains IP addresses of Meta ecosystem, including Facebook, Instagram and WhatsApp.

- `geoip:twitter`  
  Contains IP addresses of Twitter (now called X!).

- `geoip:telegram`  
  Contains IP addresses of Telegram Messenger.

- `geoip:oracle`  
  Contains IP addresses of Oracle Cloud.

- `geoip:digitalocean`  
  Contains IP addresses of DigitalOcean related services.

- `geoip:linode`  
  Contains IP addresses of Linode related services.

- `geoip:openai`  
  Contains IP addresses of OpenAI and ChatGPT.

- `geoip:phishing`  
  Contains Phishing IP addresses.

- `geoip:malware`  
  Contains Active Malware IP addresses.

## GeoSite  
- `geosite:ir`  
  Contains non-ir TLD Iranian domains (e.g. `.com` `.net` `.org` etc.) and rules to bypass all `.ir` domains.

- `geosite:ads`  
  Contains a curated list of Persian and Foreign advertisement and tracking domains based on multiple sources. It is optimized to has as low as possible false positives while also retain small size and efficiency.

- `geosite:malware`  
  Contains a list of active malware domains.

- `geosite:category-ads-all`  
  Contains domains from `geosite:ads` and `geosite:malware`.

- `geosite:phishing`  
  Contains a list of scam and phishing domains.  

- `geosite:cryptominers`  
  Contains a list of cryptocurrency miners that run in the background of a web browser and affect system performance.  

- `geosite:social`  
  Contains Domain Addresses of popular social media platforms, including `Facebook`, `Instagram`, `Whatsapp`, `Twitter`, `LinkedIn`, `MySpace`, `Pinterest`, `Tumblr`, `Reddit`, `TikTok`, `clubhouse`.

- `geosite:nsfw`
  Contains a list of porn and gambling websites.

# :arrow_down: How to download
## <picture><source media="(prefers-color-scheme: dark)" srcset="https://cdn.simpleicons.org/github/white"><source media="(prefers-color-scheme: light)" srcset="https://cdn.simpleicons.org/github/dark"><img height="32" width="32" alt="github logo in dark and light mode." src="https://cdn.simpleicons.org/github/dark"></picture> From GitHub
[https://github.com/chocolate4u/Iran-sing-box-rules/releases/latest/download/geoip.db](https://github.com/chocolate4u/Iran-sing-box-rules/releases/latest/download/geoip.db)  
[https://github.com/chocolate4u/Iran-sing-box-rules/releases/latest/download/geosite.db](https://github.com/chocolate4u/Iran-sing-box-rules/releases/latest/download/geosite.db)  

## <picture><source media="(prefers-color-scheme: dark)" srcset="https://cdn.simpleicons.org/jsdelivr/white"><source media="(prefers-color-scheme: light)" srcset="https://cdn.simpleicons.org/jsdelivr/dark"><img height="32" width="32" alt="github logo in dark and light mode." src="https://cdn.simpleicons.org/jsdelivr/dark"></picture> From jsdelivr CDN
[https://cdn.jsdelivr.net/gh/chocolate4u/Iran-sing-box-rules@release/geoip.db](https://cdn.jsdelivr.net/gh/chocolate4u/Iran-sing-box-rules@release/geoip.db)  
[https://cdn.jsdelivr.net/gh/chocolate4u/Iran-sing-box-rules@release/geosite.db](https://cdn.jsdelivr.net/gh/chocolate4u/Iran-sing-box-rules@release/geosite.db)  

# :computer: Usage
## sing-box core
Add the following to your sing-box client configuration:
```
"outbounds": [
  {
    "type": "direct",
    "tag": "direct"
  },
  {
    "type": "block",
    "tag": "block"
  }
],
"route": {
  "geoip": {
      "download_url": "https://github.com/Chocolate4U/Iran-sing-box-rules/releases/latest/download/geoip.db"
  },
  "geosite": {
    "download_url": "https://github.com/Chocolate4U/Iran-sing-box-rules/releases/latest/download/geosite.db"
  },
  "rules": [
    {
      "geosite": [
        "ads",
        "malware",
        "phishing",
        "cryptominers"
      ],
      "outbound": "block"
    },
    {
      "geoip": [
        "malware",
        "phishing"
        ],
      "outbound": "block"
    }
    {
      "geosite": "ir",
      "outbound": "direct"
    },
    {
      "geoip": [
          "ir",
          "private",
          "arvancloud"
        ],,
      "outbound": "direct"
    }
  ]
},
```

# :information_desk_person: How is this made?  
`geoip.db` is generated using source code from my [fork](https://github.com/Chocolate4U/sing-geoip) of [sing-geoip](https://github.com/SagerNet/sing-geoip). It uses `Country.mmdb` from [Iran V2Ray Rules](https://github.com/Chocolate4U/Iran-v2ray-rules) to generate `geoip.db`.  
`geosite.db` is generated using source code from my [fork](https://github.com/Chocolate4U/sing-geosite) of [sing-geosite](https://github.com/SagerNet/sing-geosite). It uses `geosite.dat` from [Iran V2Ray Rules](https://github.com/Chocolate4U/Iran-v2ray-rules) to generate `geosite.db`.  

# :handshake: Contribution
All contributions are welcome and appreciated. You can contribute to this project in 2 ways:  
1. Contribute to it's upstream sources  
   Do you know a Domain that should be bypassed? report it to [Iran Hosted Domains](https://github.com/bootmortis/iran-hosted-domains)  
   Do you know a persian advertisement domain that should be blocked or a false positive? report it to [PersianBlocker](https://github.com/MasterKia/PersianBlocker)  
   Do you know... OK you got the idea!  
2. Contribute directly to this project  
   Report issues, open pull requests, suggest new sources or categories or any idea in general to make this repository more useful for everyone.  

:raising_hand_man: Also one more thing, if this repository was useful to you, kindly leave a :star: up there so this project can be seen by more people.


# :copyright: License
This project, except for upstream sources, is licensed under the GNU GPLv3 License - see the [LICENSE](LICENSE) file for details.

All rights are reserved for All upstream sources used in this project according to their respective licenses. Please refer to [Sources](#sources) section for more details.

# :package: Sources
## GeoIP
| Source                 | Maintainer           | Home Page                                                                                 | License                                                                              | Category          |
| ---------------------- | -------------------- | ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ | ----------------- |
| GeoLite2               | MaxMind              | [Home Page](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data)                 | [CC BY-SA 4.0](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data#license) | ir                |
| ITO GOV                | ITO GOV              | [Home Page](https://eservices.ito.gov.ir/Page/IPListMessenger)                            | N/A                                                                                  | ir(messenger IPs) |
| Arvan Cloud            | Arvan Cloud          | [Home Page](https://www.arvancloud.ir/en/dev/ips)                                         | All rights reserved                                                                  | arvancloud        |
| Derak Cloud            | Derak Cloud          | [Home Page](https://derak.cloud/لیست-بازه-های-ip)                                         | All rights reserved                                                                  | derakcloud        |
| IranServer             | IranServer           | [Home Page](https://docs.iranserver.com/irserver-cloud/cdn/allow-iranserver-ip-addresses) | All rights reserved                                                                  | iranserver        |
| Cloudflare             | Cloudflare           | [Home Page](https://www.cloudflare.com/ips)                                               | All rights reserved                                                                  | cloudflare        |
| Telegram               | Telegram             | [Home Page](https://core.telegram.org/resources/cidr.txt)                                 | All rights reserved                                                                  | Telegram          |
| URLhaus                | abuse.ch             | [Home Page](https://urlhaus.abuse.ch)                                                     | [CC0](https://urlhaus.abuse.ch/api/#tos)                                             | malware           |
| Phishing URL Blocklist | malware-filter Group | [Home Page](https://gitlab.com/malware-filter/phishing-filter)                            | [MIT](https://gitlab.com/malware-filter/phishing-filter/-/blob/main/LICENSE)         | phishing          |
| IPRanges               | lord-alfred          | [Home Page](https://github.com/lord-alfred/ipranges)                                      | [CC0 1.0](https://github.com/lord-alfred/ipranges/blob/main/LICENSE)                 | everything else   |

## GeoSite
| Source                      | Maintainer           | Home Page                                                      | License                                                                         | Category     |
| --------------------------- | -------------------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------ |
| Iran Hosted Domains         | bootmortis           | [Home Page](https://github.com/bootmortis/iran-hosted-domains) | [MIT](https://github.com/bootmortis/iran-hosted-domains/blob/main/LICENSE)      | ir           |
| PersianBlocker              | MasterKia            | [Home Page](https://github.com/MasterKia/PersianBlocker)       | [AGPL-3.0](https://github.com/MasterKia/PersianBlocker/blob/main/LICENSE)       | ads          |
| DNS Blocklists              | Hagezi               | [Home Page](https://github.com/hagezi/dns-blocklists)          | All rights reserved                                                             | ads          |
| Ad and tracking server list | Peter Lowe           | [Home Page](https://pgl.yoyo.org/adservers)                    | [McRae GPL](https://pgl.yoyo.org/license)                                       | ads          |
| GoodbyeAds                  | jerryn70             | [Home Page](https://github.com/jerryn70/GoodbyeAds)            | [MIT](https://github.com/jerryn70/GoodbyeAds/blob/master/LICENSE)               | ads          |
| AdGuard DNS filter          | Adguard Team         | [Home Page](https://github.com/AdguardTeam/AdGuardSDNSFilter)  | [GPL-3.0](https://github.com/AdguardTeam/AdGuardSDNSFilter/blob/master/LICENSE) | ads          |
| URLhaus                     | abuse.ch             | [Home Page](https://urlhaus.abuse.ch)                          | [CC0](https://urlhaus.abuse.ch/api/#tos)                                        | malware      |
| Phishing URL Blocklist      | malware-filter Group | [Home Page](https://gitlab.com/malware-filter/phishing-filter) | [MIT](https://gitlab.com/malware-filter/phishing-filter/-/blob/main/LICENSE)    | phishing     |
| NoCoin adblock list         | hoshsadiq            | [Home Page](https://github.com/hoshsadiq/adblock-nocoin-list)  | [MIT](https://github.com/hoshsadiq/adblock-nocoin-list/blob/master/LICENSE)     | cryptominers |
| Unified Hosts               | StevenBlack          | [Home Page](https://github.com/StevenBlack/hosts)              | [MIT](https://github.com/StevenBlack/hosts/blob/master/license.txt)             | social, nsfw |

# :warning: Disclaimer
This repository is not affiliated, associated, authorized, endorsed by, or in any way officially connected to any of the aforementioned resources, websites, services, or any entity which this may concern, in any way.  
The data in this repository is gathered from publicly available resources and is provided as-is, intended for informational purposes only with no guarantee of accuracy, liability or availability and We are not responsible for any harm or damage that may arise from using the data in this repository. Please do your research before using any data from this repository.

# :pray: Special Thanks
- All maintainers that mentioned in this project.
- [Project S](https://github.com/SagerNet)
