# DNS-Whitelist

**English** | [Deutsch](README.de.md)

A curated allowlist for DNS filters such as **AdGuard Home** and **Technitium DNS**.

## Why?

Blocklists protect against ads, tracking and malicious sites, but they often block more than necessary. Links in newsletters stop working, shops don't redirect, apps show errors, or banking sites don't load properly.

This list unblocks exactly those domains. You keep the protection of your blocklists, and websites, apps and services still work in everyday use.

## Files

The list comes in two formats with identical content:

| File | Format | For |
|---|---|---|
| [`whitelist-adguard.txt`](whitelist-adguard.txt) | Adblock syntax (`@@\|\|domain^`) | AdGuard Home, uBlock Origin |
| [`whitelist-technitium.txt`](whitelist-technitium.txt) | One domain per line | Technitium DNS, FRITZ!Box exceptions and other filters that expect plain domain lists |

Entries are grouped by area, for example email & communication, online shops & price comparison, ads & affiliate links, payment & banking, Google, Microsoft, Fire TV, smart TVs, game consoles and streaming. Some entries are specific to Germany.

## Setup

The best way is to add the list by URL. Your DNS server then picks up changes automatically.

### AdGuard Home

1. Open **Filters → DNS allowlists**
2. Choose **Add allowlist → Add a custom list**
3. Enter this URL:

```
https://raw.githubusercontent.com/soleil0815/DNS-Whitelist/main/whitelist-adguard.txt
```

### Technitium DNS

1. Open **Settings → Blocking**
2. Add this URL under **Allow List URLs**:

```
https://raw.githubusercontent.com/soleil0815/DNS-Whitelist/main/whitelist-technitium.txt
```

3. Save

### uBlock Origin

Under **Filter lists → Import**, enter the AdGuard URL from above.

### FRITZ!Box (FRITZ!OS 8.50 and later)

Since FRITZ!OS 8.50, the FRITZ!Box has its own DNS filter. Domain exceptions take priority over the blocklists. Not every model has the filter yet: the FRITZ!Box 7690 got it first, other models follow gradually. If the **DNS Filter** tab is missing, your FRITZ!Box doesn't support it yet.

1. Open **Home Network → Network → Network Settings → Change advanced network settings → DNS Filter** (German UI: *Heimnetz → Netzwerk → Netzwerkeinstellungen → Erweiterte Netzwerkeinstellungen ändern → DNS-Filter*)
2. Under **Domain exceptions**, click **Add domain** (*Domain-Ausnahmen → Eigene Domain hinzufügen*)
3. Enter the domains you need from [`whitelist-technitium.txt`](whitelist-technitium.txt), name only, without `https://` and without a path

Exceptions are added one by one, so only add the domains you actually need.

> **Note:** Don't use the parental controls list "Allowed websites" (*Erlaubte Internetseiten*). When it is active, the FRITZ!Box allows **only** those sites and blocks everything else.

## Tip: affiliate links from newsletters and deal sites

Links from newsletters, price comparison sites or deal sites often go through affiliate networks that blocklists block. The most important German networks are included here. If you need more, you can also add the maintained [referral allowlist by HaGeZi](https://github.com/hagezi/dns-blocklists), with around 950 such domains:

```
https://raw.githubusercontent.com/hagezi/dns-blocklists/main/adblock/whitelist-referral.txt
```

It also unblocks many tracking domains, which is why it isn't built into this list.

## Contributing

Is a site wrongly blocked by your blocklists? Feel free to open an issue with the domain and a short note on what it is needed for. New entries always go into **both** files.
