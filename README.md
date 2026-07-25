# Casa Mia Network

Home network and homelab documentation — topology, IP allocation, and node configuration.

## Topology

```mermaid
graph TD
    ISP((ISP)) --- Router[Router<br>192.168.0.1]
    Router --> PVE[Proxmox VE<br>192.168.0.5]
    Router --> Pi[Raspberry Pi<br>192.168.0.241]
    Router --> Laptop[Acer Laptop<br>192.168.0.228]
```

## Components

```mermaid
architecture-beta
    group lan(cloud)[Home LAN]

    service internet(internet)[ISP]
    service router(server)[Router Compal Connect Box] in lan
    service pve(server)[Proxmox VE HP G1 Mini] in lan
    service pi(server)[RaspberryPi 4B] in lan
    service laptop(server)[Acer Laptop] in lan

    internet:R -- L:router
    router:R -- L:pve
    router:B -- T:pi
    router:T -- B:laptop
```

## Network layout

| Range | Purpose |
|---|---|
| `192.168.0.0/24` | Home LAN |
| `192.168.0.1` | Router / gateway / DNS |
| `192.168.0.2 – .9` | Reserved for static hosts |
| `192.168.0.10 – .254` | Router DHCP pool |


## Nodes

| Host | IP | Role | Notes |
|---|---|---|---|
| Proxmox VE | `192.168.0.5/24` | Hypervisor node | See [hardware/g1-mini.md](hardware/g1-mini.md) |
| Acer Laptop | `192.168.0.228` | Windows PC, remote desktop | Fixed via DHCP reservation |
| Raspberry Pi | `192.168.0.241` | Remote Wake-on-LAN | No SSH exposed — see [vps-wake-on-lan-no-ssh](https://github.com/AlexSzczygielski/vps-wake-on-lan-no-ssh). Fixed via DHCP reservation |

## Access

```bash
ssh casa_mia_proxmox
```
Web UI: [https://192.168.0.5:8006](https://192.168.0.5:8006)

## Status

- [x] Proxmox VE installed, static IP + SSH key auth configured
