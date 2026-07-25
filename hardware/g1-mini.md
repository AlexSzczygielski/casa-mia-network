# Proxmox Node — HP EliteDesk 800 G1 Mini

## Specs

| | |
|---|---|
| CPU | Intel Core i5-4570T (2C/4T) |
| RAM | 8GB DDR3 |
| Storage | 128GB SSD (2.5" SATA, no M.2) |
| Form factor | USDT mini |
| Acquired | used, 170 PLN |

## BIOS / boot access

| Key | Function |
|---|---|
| `F10` | BIOS setup |
| `F9` | One-time boot menu |
| `Esc` | Startup menu (routes to F9–F12) |

## Known issue: requires a display to boot

Won't boot without a monitor plugged in — hangs at the firmware level, before GRUB even loads. Software fixes (e.g. forcing GRUB text mode) don't help.

**Fix:** DisplayPort dummy plug (EDID emulator), left in permanently. Not installed yet — for now, boot with a screen attached, then unplug once it's up.