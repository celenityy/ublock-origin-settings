# ublock-origin-settings

My recommendations for the ultimate configuration of uBlock Origin :)

**NOTE:** This project can be found on both [Codeberg](https://codeberg.org/celenity/ublock-origin-settings), which will act as the main & preferred way to contribute, and [GitHub](https://github.com/celenityy/ublock-origin-settings).

# Settings

Privacy:

* **Disable pre-fetching (to prevent any connection for blocked network requests)** -> ✅

* **Disable hyperlink auditing** -> ✅

* **Block CSP reports** -> ✅

* **Uncloak canonical names** -> ✅

<br>

Default behavior:

* **Disable JavaScript** -> ✅ *(This **will** cause breakage, but it heavily improves privacy & security, so I'd recommend enabling it if possible and if you're willing to re-enable JavaScript for websites that need it)*

<br>

Advanced:

* **I am an advanced user** -> ✅

## Advanced settings

Select the cog to the right of **I am an advanced user**, and consider configuring the following settings:

**autoCommentFilterTemplate** -> `{{url}}`

**autoUpdateDelayAfterLaunch** -> `10`

**disableWebAssembly** -> `true`

**filterAuthorMode** -> `true`

**trustedListPrefixes** -> `-`

**updateAssetBypassBrowserCache** -> `true`

<br>

# Filter lists

**Auto-update filter lists** -> ✅

**Suspend network activity until all filter lists are loaded** -> ✅

**Parse and enforce cosmetic filters** -> ✅

**Ignore generic cosmetic filters** -> ❌

# Lists

I would generally recommend configuring your filterlists as follows. This configuration matches [what my 'Phoenix' project uses](https://phoenix.celenity.dev/content-blocking), has been thoroughly tested, & is carefully considered for a balance between privacy, security, usability, & maintaining optimal performance.

## Built-in Lists

We'll first go over lists built-in to a stock installation of uBlock Origin.

I would generally recommend configuring the built-in lists as follows:

> [!TIP]
> Lists with a ✅ should be enabled, while lists with a ❌ are unnecessary and should typically be disabled.

### Built-in

* **`uBlock filters - Ads`** -> ✅ *(Default)*
* **`uBlock filters - Badware risks`** -> ✅ *(Default)*
* **`uBlock filters - Privacy`** -> ✅ *(Default)*
* **`uBlock filters - Quick fixes`** -> ✅ *(Default)*
* **`uBlock filters - Unbreak`** -> ✅ *(Default)*

### Ads

* **`EasyList`** -> ✅ *(Default)*
* **`AdGuard - Ads`** -> ❌
* **`AdGuard - Mobile Ads`** -> ✅

### Privacy

* **`EasyPrivacy`** -> ✅ *(Default)*
* **`AdGuard Tracking Protection`** -> ❌
* **`AdGuard URL Tracking Protection`** -> ✅
* **`Block Outsider Intrusion into LAN`** -> ✅

### Malware protection, security

* **`Online Malicious URL Blocklist`** -> ✅ *(Default)*
* **`Phishing URL Blocklist`** -> ❌

### Multipurpose

* **`Peter Lowe’s Ad and tracking server list`** -> ✅ *(Default)*
* **`Dan Pollock’s hosts file`** -> ✅

### Cookie notices

* **`EasyList - Cookie Notices`** -> ✅
* **`AdGuard - Cookie Notices`** -> ❌
* **`uBlock filters - Cookie Notices`** -> ❌

### Social widgets

* **`EasyList - Social Widgets`** -> ✅
* **`AdGuard - Social Widgets`** -> ❌
* **`Fanboy - Anti-Facebook`** -> ❌

### Annoyances

* **`EasyList - Chat Widgets`** -> ✅
* **`EasyList - Newsletter Notices`** -> ✅
* **`EasyList - Notifications`** -> ✅
* **`EasyList - Other Annoyances`** -> ✅
* **`AdGuard - Mobile App Banners`** -> ❌
* **`AdGuard - Other Annoyances`** -> ❌
* **`AdGuard - Popup Overlays`** -> ❌
* **`AdGuard - Widgets`** -> ❌
* **`uBlock filters - Annoyances`** -> ✅

## External Lists

We can now go over what lists you should **manually import** to uBlock Origin.

I would generally recommend importing & enabling the following:

### Privacy

* ⭐️ **➗ Actually Legitimate URL Shortener Tool**

    ```sh
    https://gitlab.com/DandelionSprout/adfilt/-/raw/master/LegitimateURLShortener.txt
    ```

* ⭐️ **🔍 yokoffing's Block third party fonts**

    ```sh
    https://raw.githubusercontent.com/yokoffing/filterlists/main/block_third_party_fonts.txt
    ```

* ⭐️ **⛔ yokoffing's click2load filters**

    ```sh
    https://raw.githubusercontent.com/yokoffing/filterlists/main/click2load.txt
    ```

### Malware protection, security

* ⭐️ **⚠️ BadBlock - Unsafe**

    ```sh
    https://badblock.celenity.dev/abp/unsafe.txt
    ```

* ⭐️ **💊 Dandelion Sprout's Anti-Malware List**

    ```sh
    https://gitlab.com/DandelionSprout/adfilt/-/raw/master/Dandelion%20Sprout's%20Anti-Malware%20List.txt
    ```

* ⭐️ **🔏 HaGeZi - Dynamic DNS**

    ```sh
    https://gitlab.com/hagezi/mirror/-/raw/main/dns-blocklists/adblock/dyndns.txt
    ```

* ⭐️ **🔐 HaGeZi - Threat Intelligence Feeds - Mini**

    ```sh
    https://gitlab.com/hagezi/mirror/-/raw/main/dns-blocklists/adblock/tif.mini.txt
    ```

* ⭐️ **FMHY Unsafe sites filterlist**

    ```sh
    https://raw.githubusercontent.com/fmhy/FMHYFilterlist/main/filterlist-basic.txt
    ```

### Multipurpose

* ⭐️ **📕 HaGeZi - Multi ULTIMATE mini**

    ```sh
    https://gitlab.com/hagezi/mirror/-/raw/main/dns-blocklists/adblock/ultimate.mini.txt
    ```

<br>

**Additionally**, if you're fine with occasional breakage at the cost of enhanced privacy & security, you could also consider using:

* ⭐️ My **⚡️ BadBlock Lite**, **🔇 BadBlock**, OR **🔥 BadBlock+**

    * Do **not** use all 3 together, pick **one** that works best for you! **🔇 BadBlock** is recommended for most users.

        * **⚡️ BadBlock Lite**
            ```sh
            https://badblock.celenity.dev/abp/badblock_lite.txt
            ```
        * **🔇 BadBlock**
            ```sh
            https://badblock.celenity.dev/abp/badblock.txt
            ```
        * **🔥 BadBlock+**
            ```sh
            https://badblock.celenity.dev/abp/badblock_plus.txt
            ```

Furthermore, **if you don't have a DNS content blocking solution in place *(you should)***, or you just can't use the relevant list on your DNS blocker, you could also use the following:

* ⭐️ **HaGeZi's Most Abused TLDs**
    ```sh
    https://gitlab.com/hagezi/mirror/-/raw/main/dns-blocklists/adblock/spam-tlds-ublock.txt
    ```

* ⭐️ **OISD - Big**
    ```sh
    https://big.oisd.nl
    ```

Once you're finished choosing your lists, don't forget to select **Apply changes** & **Update now**.

# My filters

This is where it can really depend on you and your set-up. I'll provide my recommendations and filters here I myself use below:

First, I would highly recommend setting the following to protect against [IDN Homograph attacks](https://wikipedia.org/wiki/IDN_homograph_attack) 

*You don't need to set this if you use BadBlock **Unsafe** above or if your DNS provider already provides IDN Homograph Attacks Protection (i.e. NextDNS)*:

```sh
xn--*
xn--*$doc,popup,frame
```

I usually set the following to always enforce blocking Google's Doubleclick & Google Analytics: *[Why?](https://github.com/gorhill/uBlock/wiki/Privacy-stuff)*

```sh
||doubleclick.net^$important
||google-analytics.com^$important
```

Additionally, I set the following to block social media tracking on websites:

```sh
||facebook.com^$important,third-party
||facebook.net^$important,third-party
||linkedin.com^$important,third-party
||instagram.com^$important,third-party
||tiktok.com^$important,third-party
||twitter.com^$third-party
||x.com^$third-party
```

*See `My rules` section below for unbreaking X/Twitter...*

I also set this to block [tracking from Gravatar](https://github.com/gorhill/uBlock/wiki/Privacy-stuff):

```sh
||gravatar.com^$important,third-party
```

I also set these rules to block 3rd party sign-in prompts from Google & Apple, as they're 1: annoying and 2: a tracking concern:

```sh
||accounts.google.com^$third-party
||appleid.apple.com^$third-party
||appleid.cdn-apple.com^$third-party
@@||accounts.google.com^$domain=youtube.com|chromium.org|gstatic.com|googleusercontent.com
@@||appleid.apple.com^$domain=appleid.cdn-apple.com
@@||appleid.cdn-apple.com^$domain=appleid.apple.com
```

Since I block all 3rd-party requests *(will be explained further in `My rules` section below)*, I set the following rules to still allow CAPTCHAs for sites: *(Also see `My rules`)*

```sh
||challenges.cloudflare.com^$third-party
@@||challenges.cloudflare.com/cdn-cgi/challenge-platform/$third-party,script,frame
||www.google.com^$third-party,subdocument
@@||www.google.com/recaptcha/$third-party,subdocument
||www.gstatic.com^$third-party,script
@@||www.gstatic.com/recaptcha/$third-party,script
```

Finally, I usually set the following to block the annoying banner on Old Reddit promoting Reddit's new UI.

```sh
www.reddit.com###redesign-beta-optin-btn
old.reddit.com###redesign-beta-optin-btn
```

Once you are done here, make sure to select **Apply changes**.

# My rules

First, I typically set the following to block all 3rd party requests:

**I would not recommend this for most people, as you will basically have to unbreak pages yourself, but it provides the most private, secure, and fastest configuration possible.**

```sh
* * 3p block
* * 3p-frame block
* * 3p-script block
```

If you don't want as much breakage, you could potentially only set:

```sh
* * 3p-frame block
```

This only blocks 3rd party frames, while keeping other resources untouched. I would recommend this if you have the tolerance to allow 3rd party frames for pages that need them, but still want a nice boost in privacy, security, & performance.

I then set the following to allow CAPTCHAs for sites:

```sh
* challenges.cloudflare.com * noop
* www.google.com * noop
* www.gstatic.com * noop
```

I also set the following to unbreak X/Twitter based off the filters we set above:

```sh
x.com twitter.com * noop

twitter.com x.com * noop
```

⭐️ If you block 3rd party connections like me, then I would recommend also using the [LocalCDN](https://www.localcdn.org/) extension with the following settings, as this will reduce breakage:

# LocalCDN -> Basic

**Hide donation button** -> ✅

# LocalCDN -> Advanced

**Block Google Fonts** -> ❌ *This is already covered by Yokoffing's `Block third party fonts` list that we added, leaving Google Fonts blocked here as well will just cause issues & breakage*

<br>

Now, back to uBlock Origin, you should add the following rules in uBlock Origin for LocalCDN to be active:

```sh
* ajax.googleapis.com * noop
* ajax.aspnetcdn.com * noop
* ajax.microsoft.com * noop
* cdnjs.cloudflare.com * noop
* code.jquery.com * noop
* cdn.jsdelivr.net * noop
* fonts.googleapis.com * noop
* yastatic.net * noop
* yandex.st * noop
* apps.bdimg.com * noop
* libs.baidu.com * noop
* cdn.staticfile.org * noop
* cdn.bootcss.com * noop
* mat1.gtimg.com * noop
* lib.sinaapp.com * noop
* upcdn.b0.upaiyun.com * noop
* stackpath.bootstrapcdn.com * noop
* maxcdn.bootstrapcdn.com * noop
* netdna.bootstrapcdn.com * noop
* use.fontawesome.com * noop
* ajax.cloudflare.com * noop
* akamai-webcdn.kgstatic.net * noop
* gitcdn.github.io * noop
* vjs.zencdn.net * noop
* cdn.plyr.io * noop
* cdn.materialdesignicons.com * noop
* cdn.ravenjs.com * noop
* js.appboycdn.com * noop
* cdn.embed.ly * noop
* cdn.datatables.net * noop
* mathjax.rstudio.com * noop
* cdn.mathjax.org * noop
* code.createjs.com * noop
* sdn.geekzu.org * noop
* ajax.proxy.ustclug.org * noop
* unpkg.com * noop
* pagecdn.io * noop
* cdnjs.loli.net * noop
* ajax.loli.net * noop
* fonts.loli.net * noop
* lib.baomitu.com * noop
* cdn.bootcdn.net * noop
* fonts.gstatic.com * noop
* ajax.loli.net.cdn.cloudflare.net * noop
* akamai-webcdn.kgstatic.net.edgesuite.net * noop
* apps.bdimg.jomodns.com * noop
* cdn.bootcdn.net.maoyundns.com * noop
* cdn.bootcss.com.maoyundns.com * noop
* cdn.embed.ly.cdn.cloudflare.net * noop
* cdn.jsdelivr.net.cdn.cloudflare.net * noop
* cdnjs.loli.net.cdn.cloudflare.net * noop
* cds.s5x3j6q5.hwcdn.net * noop
* developer.n.shifen.com * noop
* dualstack.osff.map.fastly.net * noop
* fonts.loli.net.cdn.cloudflare.net * noop
* gateway.cname.ustclug.org * noop
* iduwdjf.qiniudns.com * noop
* lb.sae.sina.com.cn * noop
* lib.baomitu.com.qh-cdn.com * noop
* mat1.gtimg.com.tegsea.tc.qq.com * noop
* materialdesignicons.b-cdn.net * noop
* mscomajax.vo.msecnd.net * noop
* sdn.inbond.gslb.geekzu.org * noop
* use.fontawesome.com.cdn.cloudflare.net * noop
* vo.aicdn.com * noop
```

Once you're done configuring your rules here, select **Save** & **Commit**.

# Additional recommendations

* Use [Firefox](https://www.mozilla.org/firefox/) with my [Phoenix](https://phoenix.celenity.dev), as Firefox respects your privacy and [has the best support for uBlock Origin](https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox). **You do not need to configure uBlock Origin with this guide if you use Phoenix, as it is already pre-configured out of the box.**

* Enable Safe Browsing in your browser if possible and if it's not done in a privacy-invasive way. (You should use i.e. [Google Safe Browsing on "Standard" Mode](https://safebrowsing.google.com/), [Firefox's Safe Browsing](https://support.mozilla.org/kb/how-does-phishing-and-malware-protection-work), & [Brave's Safe Browsing](https://brave.com/privacy/browser/#safe-browsing), you should avoid most other options i.e. [Google Safe Browsing on "Enhanced" Mode](https://safebrowsing.google.com/), [Microsoft SmartScreen](https://learn.microsoft.com/windows/security/operating-system-security/virus-and-threat-protection/microsoft-defender-smartscreen/), & [Opera Sitecheck](https://blogs.opera.com/security/2021/01/making-browsing-safe-from-phishing/)).

* Use a private, secure, & reputable DNS provider of your choice. I would recommend setting up your own [NextDNS](https://nextdns.io) configuration if you are able to *(See my recommendations for NextDNS [here](https://codeberg.org/celenity/nextdns-settings))*, otherwise I would recommend [Quad9](https://quad9.net/). If you're using a Chromium browser, make sure to configure your DNS provider on **both** your OS and in your browser. This will allow you to take advantage of [Encrypted Client Hello](https://blog.cloudflare.com/announcing-encrypted-client-hello). This is unnecessary on Firefox-based browsers, however it could still be useful to set in both places if for instance you want to set a separate client name for your browser than the rest of your OS, to better determine what queries are coming from where.

* Use a (reputable) anti-virus if possible. On Windows, you can use the built-in [Microsoft Defender Antivirus](https://wikipedia.org/wiki/Microsoft_Defender_Antivirus), on macOS, you can stick to the built-in [XProtect](https://support.apple.com/guide/security/protecting-against-malware-sec469d47bd8/web) and on Linux, you can use [ClamAV](https://www.clamav.net/).
