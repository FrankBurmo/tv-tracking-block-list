# Smart TV Tracking & Telemetry Blocklist

A DNS blocklist for domains associated with automatic content recognition (ACR), advertising, and telemetry on selected smart TV platforms. The list is intended for use with AdGuard Home and other DNS filtering services that support AdGuard-style rules.

## What it covers

The rules in [`blocklist.txt`](blocklist.txt) currently target:

- **LG webOS** — advertising, service discovery, ACR, and home-screen reporting
- **Samsung Tizen** — ACR, advertising, and Smart Hub reporting
- **Samba TV** — ACR domains used on some TVs, including Sony, Hisense, and TCL
- **Google TV / Android TV** — app measurement
- **Roku OS** — selected telemetry endpoints
- **Vizio** — Inscape ACR

The list is community-maintained and is not affiliated with or endorsed by any TV manufacturer. Domains and services can change, and some listed domains may also support other features.

## Add the list to AdGuard Home

1. Open **Filters → DNS blocklists** in AdGuard Home.
2. Choose **Add blocklist**, then add the raw URL for [`blocklist.txt`](blocklist.txt) from this repository.
3. Save the list and update the filters.

You can also copy the rules into **Filters → Custom filtering rules**. The `||domain^` syntax blocks a domain and its subdomains.

## Limitations and troubleshooting

- DNS blocking can affect TV apps or features as well as tracking. If something stops working, review AdGuard Home’s **Query Log** and add a narrow allow rule, for example `@@||example.com^`.
- Some TVs use hard-coded DNS servers or DNS-over-HTTPS (DoH), which can bypass your DNS filter. Network-level DNS enforcement may be needed for those devices.
- A blocklist does not replace disabling ACR or personalized advertising in the TV’s privacy settings.
- **Do not block `roku.com`, `*.sr.roku.com`, or `*.cs.roku.com`.** Blocking these can interfere with Roku’s TV guide, antenna TV, or firmware updates.

## Contributing

Before adding a domain, check that it is associated with tracking or advertising and consider whether blocking it could break essential TV functionality. Include a short explanation with proposed changes, and report false positives with the affected device and feature where possible.
