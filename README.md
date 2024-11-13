# Olimex Ethernet Link Patch

## 📖 Purpose

Patch Ethernet Link Issue of [Olimex Lime 2 board](https://www.olimex.com/Products/OLinuXino/A20/A20-OLinuXino-LIME2/open-source-hardware).

On some board, the Ethernet port is suffering from paquet loss when speed link is configured to 1Gbps.
Issue can be fixed with CPU register update.

```bash
memtool mw 0x01c20164 0x00000426 
```

This patch set up a service in systemd to run this update at boot (register update is not persistent).

## Usage

..

## 🧑‍🤝‍🧑 Contributors

* [IACA Electronique](https://iaca-electronique.com)
  * Julien FAURE ✉️ julien.faure@iaca-electronique.com