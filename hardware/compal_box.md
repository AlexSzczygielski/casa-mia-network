# Router — Compal Connect Box (Play)

## Specs

| | |
|---|---|
| Model | Compal Broadband Networks CH7465LG-LC ("Connect Box") |
| Provided by | Play (formerly UPC) |
| Cable modem | DOCSIS 3.0, 24x8 |
| CPU | Intel Puma 6 (DHCE2652), 1.2 GHz, 2-core |
| WAN | Coax (cable) |
| LAN | Gigabit Ethernet ports + WiFi (802.11n 2.4GHz / 802.11ac 5GHz) |
| Default IP | `192.168.0.1` |

## Known limitations

| Limitation | Detail |
|---|---|
| No custom DNS via DHCP | DHCP settings don't expose a field for a non-ISP DNS server. Checked directly in the admin UI — not present. |
| No local DNS / static hostname feature | No section for mapping hostnames to LAN IPs. |
| Bridge mode not present | - |

## Why this matters

These limitations are why local DNS/TLS (see [Local DNS & TLS](../README.md#local-dns--tls--current-limitations)) is solved with a self-hosted resolver (AdGuard Home) rather than at the router level.