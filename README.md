# ublock-origin-settings

My recommendations for the ultimate configuration of uBlock Origin :)

# Settings

Privacy:

**Disable pre-fetching (to prevent any connection for blocked network requests)** -> ✅

**Disable hyperlink auditing** -> ✅

**Block CSP reports** -> ✅

**Uncloak canonical names** -> ✅

Default behavior:

**Disable JavaScript** -> ✅ *(This **will** cause breakage, but it heavily improves privacy & security, so I'd recommend enabling it if possible and if you're willing to re-enable JavaScript that need it)*

Advanced:

**I am an advanced user** -> ✅

# Filter lists

**Auto-update filter lists** -> ✅

**Suspend network activity until all filter lists are loaded** -> ✅

**Parse and enforce cosmetic filters** -> ✅

**Ignore generic cosmetic filters** -> ❌

Here's where it gets fun, to the lists. I would generally recommend enabling **all** of the built-in filters, **besides** those under the `Regions, languages` category. These are all extremely carefully picked lists with strong coverage and minimal breakage, and **I would recommend enabling them for the best coverage possible**.

Built-in:

* ⭐️ `uBlock filters` -> ✅

Ads:

* ⭐️ `EasyList` -> ✅

* ⭐️ `AdGuard - Ads` -> ✅

* ⭐️ `AdGuard - Mobile Ads` -> ✅

Privacy:

* ⭐️ `EasyPrivacy` -> ✅

* ⭐️ `AdGuard Tracking Protection` -> ✅

* ⭐️ `AdGuard URL Tracking Protection` -> ✅

* ⭐️ `Block Outsider Intrusion into LAN` -> ✅

Malware protection, security:

* ⭐️ `Online Malicious URL Blocklist` -> ✅

* ⭐️ `Phishing URL Blocklist` -> ✅

Multipurpose:

* ⭐️ `Peter Lowe's Ad and tracking server list` -> ✅

* ⭐️ `Dan Pollock's hosts file` -> ✅

Cookie notices:

* ⭐️ `EasyList/uBO - Cookie Notices` -> ✅

* ⭐️ `AdGuard/uBO - Cookie Notices` -> ✅

Social widgets:

* ⭐️ `EasyList - Social Widgets` -> ✅

* ⭐️ `AdGuard - Social Widgets` -> ✅

* ⭐️ `Fanboy - Anti-Facebook` -> ✅

Annoyances:

* ⭐️ `EasyList - Annoyances` -> ✅

* ⭐️ `AdGuard - Annoyances` -> ✅

* ⭐️ `uBlock filters - Annoyances` -> ✅

Custom:

I would recommend importing the following lists:

* ⭐️ Actually Legitimate URL Shortener Tool - `https://raw.githubusercontent.com/DandelionSprout/adfilt/master/LegitimateURLShortener.txt`

* ⭐️ Divested Fingerprinting Blocklist - `https://divested.dev/blocklists/Fingerprinting.ubl`

* ⭐️ HaGeZi's Threat Intelligence Feeds - IPs: `https://raw.githubusercontent.com/hagezi/dns-blocklists/main/ips/tif.txt` *(Even if you use this list in i.e. AdGuard Home, you should also apply it here for an extra level of protection from these IPs outside of just the DNS level)*

* ⭐️ pfBlockerNG MS-1: `https://gist.githubusercontent.com/BBcan177/bf29d47ea04391cb3eb0/raw/7290e0681bcd07415420b5c80a253652fd13f840/MS-1` *(Even if you use this list in i.e. AdGuard Home, you should also apply it here for an extra level of protection from these IPs outside of just the DNS level)*

* ⭐️ Yokoffing's `Block third party fonts` - `https://raw.githubusercontent.com/yokoffing/filterlists/main/block_third_party_fonts.txt`

Additionally, if you don't have a DNS content blocking solution in place *(you should)*, or you just can't use the relevant list on your DNS blocker, you should import the following:

* ⭐️ Dandelion Sprout's Anti-Malware List: `https://raw.githubusercontent.com/DandelionSprout/adfilt/master/Dandelion%20Sprout's%20Anti-Malware%20List.txt`

* ⭐️ Divested Combined Blocklist: `https://divested.dev/hosts-domains-wildcards`

* ⭐️ HaGeZi's Badware Host Blocking: `https://gitlab.com/hagezi/mirror/-/raw/main/dns-blocklists/adblock/hoster.txt`

* ⭐️ HaGeZi's Most Abused TLDs: `https://gitlab.com/hagezi/mirror/-/raw/main/dns-blocklists/adblock/spam-tlds-ublock.txt`

* ⭐️ HaGeZi Multi PRO++: `https://gitlab.com/hagezi/mirror/-/raw/main/dns-blocklists/adblock/pro.plus.txt`

* ⭐️ HaGeZi's Threat Intelligence Feeds: `https://gitlab.com/hagezi/mirror/-/raw/main/dns-blocklists/adblock/tif.txt`

* ⭐️ HaGeZi/xRuffKez's Newly Registered Domains (14 days): `https://raw.githubusercontent.com/xRuffKez/NRD/main/nrd-14day_adblock.txt`

* ⭐️ OISD - Big: `https://big.oisd.nl`

Additionally, if you're fine with a little breakage, I would highly recommend:

* ⭐️ 1Hosts **Pro**: `https://o0.pages.dev/Pro/adblock.txt`

* ⭐️ HaGeZi Multi **Ultimate** instead of HaGezi Multi **Pro++**: `https://gitlab.com/hagezi/mirror/-/raw/main/dns-blocklists/adblock/ultimate.txt`

Once you're finished choosing your lists, don't forget to select **Apply changes** & **Update now**.

# My filters

This is where it can really depend on you and your set-up. I'll provide my recommendations and filters here I myself use below:

First, I would highly recommend setting the following to protect against [IDN Homograph attacks](https://wikipedia.org/wiki/IDN_homograph_attack) *You don't need to set this if your DNS provider already provides IDN Homograph Attacks Protection (i.e. NextDNS)*:

`xn--*`

`xn--*$doc,popup,frame`

I usually set the following to always enforce blocking Google's Doubleclick & Google Analytics: *((Why?)[https://github.com/gorhill/uBlock/wiki/Privacy-stuff])*

`||doubleclick.net^$important`
`||google-analytics.com^$important`

Additionally, I set the following to block social media tracking on websites:

`||facebook.com^$important,third-party`

`||facebook.net^$important,third-party`

`||linkedin.com^$important,third-party`

`||instagram.com^$important,third-party`

`||tiktok.com^$important,third-party`

`||twitter.com^$third-party`

`||x.com^$third-party`

*See `My rules` section below for unbreaking X/Twitter...*

I also set this to block [tracking from Gravatar](https://github.com/gorhill/uBlock/wiki/Privacy-stuff):

`||gravatar.com^$important,third-party`

I also set these rules to block 3rd party sign-in prompts from Google & Apple, as they're 1: annoying and 2: a tracking concern:

`||accounts.google.com^$third-party`

`||appleid.apple.com^$third-party`

`||appleid.cdn-apple.com^$third-party`

`@@||accounts.google.com^$domain=youtube.com|chromium.org|gstatic.com|googleusercontent.com`

`@@||appleid.apple.com^$domain=appleid.cdn-apple.com`

`@@||appleid.cdn-apple.com^$domain=appleid.apple.com`

Since I block all 3rd-party requests *(will be explained further in `My rules` section below)*, I set the following rules to still allow CAPTCHAs for sites: *(Also see `My rules`)*

`||challenges.cloudflare.com^$third-party`

`@@||challenges.cloudflare.com/cdn-cgi/challenge-platform/$third-party,script,frame`

`||www.google.com^$third-party,subdocument`

`@@||www.google.com/recaptcha/$third-party,subdocument`

`||www.gstatic.com^$third-party,script`

`@@||www.gstatic.com/recaptcha/$third-party,script`

Finally, I usually set the following to block the annoying banner on Old Reddit promoting Reddit's new UI.

`www.reddit.com###redesign-beta-optin-btn`

`old.reddit.com###redesign-beta-optin-btn`

Once you are done here, make sure to select **Apply changes**.

# My rules

First, I typically set the following to block all 3rd party requests:

**I would not recommend this for most people, as you will basically have to unbreak pages yourself, but it provides the most private, secure, and fastest configuration possible.**

`* * 3p block`
`* * 3p-frame block`
`* * 3p-script block`

If you don't want as much breakage, you could potentially only set:

`* * 3p-frame block`

This only blocks 3rd party frames, while keeping other resources untouched. I would recommend this if you have the tolerance to allow 3rd party frames for pages that need them.

I then set the following to allow CAPTCHAs for sites:

`* challenges.cloudflare.com * noop`

`* www.google.com * noop`

`* www.gstatic.com * noop`

I also set the following to unbreak X/Twitter based off the filters we set above:

`x.com twitter.com * noop`

`twitter.com x.com * noop`

⭐️ If you block 3rd party connections like me, then I would strongly recommend also using the [LocalCDN](https://www.localcdn.org/) extension with the following settings, as this will reduce breakage:

# Basic

**Hide donation button** -> ✅

# Advanced

**Block Google Fonts** -> ❌ *This is already covered by Yokoffing's `Block third party fonts` list that we added, leaving Google Fonts blocked here as well will just cause issues & breakage*


Now, you should add the following rules in uBlock Origin for LocalCDN to be active:

`* ajax.googleapis.com * noop`

`* ajax.aspnetcdn.com * noop`

`* ajax.microsoft.com * noop`

`* cdnjs.cloudflare.com * noop`

`* code.jquery.com * noop`

`* cdn.jsdelivr.net * noop`

`* fonts.googleapis.com * noop`

`* yastatic.net * noop`

`* yandex.st * noop`

`* apps.bdimg.com * noop`

`* libs.baidu.com * noop`

`* cdn.staticfile.org * noop`

`* cdn.bootcss.com * noop`

`* mat1.gtimg.com * noop`

`* lib.sinaapp.com * noop`

`* upcdn.b0.upaiyun.com * noop`

`* stackpath.bootstrapcdn.com * noop`

`* maxcdn.bootstrapcdn.com * noop`

`* netdna.bootstrapcdn.com * noop`

`* use.fontawesome.com * noop`

`* ajax.cloudflare.com * noop`

`* akamai-webcdn.kgstatic.net * noop`

`* gitcdn.github.io * noop`

`* vjs.zencdn.net * noop`

`* cdn.plyr.io * noop`

`* cdn.materialdesignicons.com * noop`

`* cdn.ravenjs.com * noop`

`* js.appboycdn.com * noop`

`* cdn.embed.ly * noop`

`* cdn.datatables.net * noop`

`* mathjax.rstudio.com * noop`

`* cdn.mathjax.org * noop`

`* code.createjs.com * noop`

`* sdn.geekzu.org * noop`

`* ajax.proxy.ustclug.org * noop`

`* unpkg.com * noop`

`* pagecdn.io * noop`

`* cdnjs.loli.net * noop`

`* ajax.loli.net * noop`

`* fonts.loli.net * noop`

`* lib.baomitu.com * noop`

`* cdn.bootcdn.net * noop`

`* fonts.gstatic.com * noop`

`* ajax.loli.net.cdn.cloudflare.net * noop`

`* akamai-webcdn.kgstatic.net.edgesuite.net * noop`

`* apps.bdimg.jomodns.com * noop`

`* cdn.bootcdn.net.maoyundns.com * noop`

`* cdn.bootcss.com.maoyundns.com * noop`

`* cdn.embed.ly.cdn.cloudflare.net * noop`

`* cdn.jsdelivr.net.cdn.cloudflare.net * noop`

`* cdnjs.loli.net.cdn.cloudflare.net * noop`

`* cds.s5x3j6q5.hwcdn.net * noop`

`* developer.n.shifen.com * noop`

`* dualstack.osff.map.fastly.net * noop`

`* fonts.loli.net.cdn.cloudflare.net * noop`

`* gateway.cname.ustclug.org * noop`

`* iduwdjf.qiniudns.com * noop`

`* lb.sae.sina.com.cn * noop`

`* lib.baomitu.com.qh-cdn.com * noop`

`* mat1.gtimg.com.tegsea.tc.qq.com * noop`

`* materialdesignicons.b-cdn.net * noop`

`* mscomajax.vo.msecnd.net * noop`

`* sdn.inbond.gslb.geekzu.org * noop`

`* use.fontawesome.com.cdn.cloudflare.net * noop`

`* vo.aicdn.com * noop`

Once you're done configuring your rules here, select **Save** & **Commit**.

# Additional recommendations

* Use [Firefox](https://www.mozilla.org/firefox/), as it respects your privacy and [has the best support for uBlock Origin](https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox).

* Enable Safe Browsing in your browser if possible and if it's not done in a privacy-invasive way. (You should use i.e. [Google Safe Browsing on "Standard" Mode](https://safebrowsing.google.com/), [Firefox's Safe Browsing](https://support.mozilla.org/kb/how-does-phishing-and-malware-protection-work), & [Brave's Safe Browsing](https://brave.com/privacy/browser/#safe-browsing), you should avoid most other options i.e. [Google Safe Browsing on "Enhanced" Mode](https://safebrowsing.google.com/), [Microsoft SmartScreen](https://learn.microsoft.com/windows/security/operating-system-security/virus-and-threat-protection/microsoft-defender-smartscreen/), & [Opera Sitecheck](https://blogs.opera.com/security/2021/01/making-browsing-safe-from-phishing/)).

* Use a private, secure, & reputable DNS provider of your choice. I would recommend setting up your own [NextDNS](https://nextdns.io) configuration if you are able to (See my recommendations for NextDNS [here](https://codeberg.org/Magnesium1062/nextdns-settings)), otherwise I would recommend [Quad9](https://quad9.net/): `https://dns.quad9.net/dns-query` *(Even if you have a private/secure DNS provider set on your OS/network level, make sure to still set it in your browser as well, so that you can take advantage of [Encrypted Client Hello](https://blog.cloudflare.com/announcing-encrypted-client-hello))*

* Use a (reputable) anti-virus if possible. On Windows, you can use the built-in [Microsoft Defender Antivirus](https://en.wikipedia.org/wiki/Microsoft_Defender_Antivirus), on macOS, you can stick to the built-in [XProtect](https://support.apple.com/guide/security/protecting-against-malware-sec469d47bd8/web), on Android, you can use [Hypatia](https://f-droid.org/packages/us.spotco.malwarescanner/), and on Linux, you can use [ClamAV](https://www.clamav.net/). **NOTE:** You should install Hypatia through the [DivestOS Official Repo](https://divestos.org/fdroid/official/?fingerprint=E4BE8D6ABFA4D9D4FEEF03CDDA7FF62A73FD64B75566F6DD4E5E577550BE8467) instead of F-Droid's main repo, as it will allow you to receive quicker updates directly from the developer. It's also recommended to use [F-Droid Basic](https://f-droid.org/en/packages/org.fdroid.basic/) as your F-Droid client of choice.