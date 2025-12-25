# 💕 Hyphanet Arch Linux Package 💕

*I-I made this PKGBUILD just for you, okay?! It's not like I wanted to or anything...* (⁄ ⁄>⁄ ▽ ⁄<⁄ ⁄)

An Arch Linux package for Hyphanet (formerly Freenet) ~ 💝

**A-Arch users are so cool... compiling everything from source...** (*/ω\*) 🔪💕

---

## 📦 What's Inside~ OwO

| File | Description | My Love Level 💘 |
|------|-------------|------------------|
| `PKGBUILD` | The build recipe | 💕💕💕💕💕 |
| `hyphanet.install` | Install hooks | 💗💗💗💗💗 |
| `hyphanet.service` | Systemd service | 💗💗💗💗💗 |

*I worked SO hard on these... you'll use them, right? RIGHT?!* ヾ(｡>﹏<｡)ﾉ゙✧

---

## 🔧 Installation~ (Let me help you, senpai!)

### Building from AUR 💝

```bash
# Clone this repo~ 💕
git clone https://github.com/blubskye/hyphanet_arch.git
cd hyphanet_arch

# Build and install (I believe in you!) ✨
makepkg -si
```

### Or with an AUR helper~ 💗

```bash
# Using yay (my favorite~)
yay -S hyphanet

# Using paru
paru -S hyphanet
```

*Once it's in the AUR, that is~* (◕‿◕)♡

---

## 🌸 Post-Installation (Now we're connected forever~)

*After installation, Hyphanet will always be with you... just like me!* (◕‿◕)♡

```bash
# Start Hyphanet 💜
sudo systemctl start hyphanet

# Enable at boot (We'll start together... EVERY. SINGLE. DAY.) 💗
sudo systemctl enable hyphanet
```

🎀 **Access the web interface at:** http://127.0.0.1:8888/ 🎀

*I-I'll be waiting for you there, okay?!* (⁄ ⁄•⁄ω⁄•⁄ ⁄)

---

## ⚙️ Configuration (Customize me however you want~)

Configuration file: `/etc/default/hyphanet`

| Option | Description | Default | 💕 |
|--------|-------------|---------|-----|
| `JAVA_OPTS` | JVM memory settings | `-Xms128m -Xmx1024m` | 💗 |
| `JAVA_EXTRA_OPTS` | Additional JVM arguments | - | 💗 |
| `HYPHANET_DATA` | Data directory | `/var/lib/hyphanet` | 💗 |

*Y-You can change these settings... but you can't change my feelings for you!* (/ω\)

---

## 📜 License

This package is licensed under **AGPL-3.0** 💕

Hyphanet itself is licensed under GPL-2.0-or-later~

*Free software... free love... FREE TO BE WITH YOU FOREVER!!!* 💗🔪💗

---

## 💌 From Me To You

```
╔══════════════════════════════════════════════════════════╗
║                                                          ║
║   I made this PKGBUILD just for you, anon~ 💕            ║
║                                                          ║
║   BTW I use Arch... and now you do too~                  ║
║   We have so much in common! 🔪✨                        ║
║                                                          ║
║   Forever yours,                                         ║
║   Your Package Maintainer 💗                             ║
║                                                          ║
║   P.S. Star this repo or else... (◕‿◕)🔪                ║
║                                                          ║
╚══════════════════════════════════════════════════════════╝
```

---

## 🌐 Other Distros~

*I-I guess I have packages for other distros too... but you chose Arch, so you're clearly superior~* (￣ε￣)

- **Gentoo:** https://github.com/blubskye/hyphanet_gentoo 💚
- **Debian/Ubuntu:** *coming soon~* 💙
- **Fedora/RHEL:** *coming soon~* 💜

---

*~Made with mass amounts of mass love and mass compile time~* 💕✨🔪💕

**GitHub:** https://github.com/blubskye/hyphanet_arch 💝

ღゝ◡╹)ノ♡ *BTW I use Arch~*
