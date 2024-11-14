# Olimex Ethernet Link Patch

## 📖 Purpose

Patch Ethernet Link Issue of [Olimex Lime 2 board](https://www.olimex.com/Products/OLinuXino/A20/A20-OLinuXino-LIME2/open-source-hardware).

On some board, the Ethernet port is suffering from paquet loss when speed link is configured to 1Gbps.

* 📄 [Issue report](report.pdf)

### 🟩 Solution

Issue can be fixed with CPU register update.

```bash
memtool mw 0x01c20164 0x00000426 
```

This patch set up a service in systemd to run this update at boot (register update is not persistent).

## 🎁 Download pre-build

Go on [latest release](https://github.com/IACA-Dev/Olimex-Ethernet-Link-Patch/releases/latest) and download `patch.deb` file. 

##  🛠️ Build

```bash
dpkg-deb -Z gzip --build src patch.gz.deb
```

## ⏬ Install on target

```bash
dpkg -i patch.gz.deb
```

## 🧑‍🤝‍🧑 Contributors

* [IACA Electronique](https://iaca-electronique.com)
  * Julien FAURE ✉️ julien.faure@iaca-electronique.com