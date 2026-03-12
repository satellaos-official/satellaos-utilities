# 🟣 SatellaOS ToolBox

> **One-click utility toolbox for SatellaOS (Debian-based systems)**

SatellaOS ToolBox is a shell-based utility that brings together configuration tools, system helpers, and program installers under a single interface. It focuses on simplicity, safety, and user control, making common system tasks faster without hiding what happens in the background.

---

## 🚀 Quick Start

Run the following commands to download and launch the SatellaOS ToolBox:

```bash
echo "Downloading SatellaOS ToolBox..."

mkdir -p "$HOME/satellaos"

wget "https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/refs/heads/main/toolbox.sh" \
  -O "$HOME/satellaos/toolbox.sh"

chmod +x "$HOME/satellaos/toolbox.sh"

"$HOME/satellaos/toolbox.sh"
```

---

## 🧩 Included Features

* GPU drivers (AMD / Intel)
* Bluetooth setup
* Touchpad configuration
* Program installer (Deb & Flatpak)
* Beginner-safe defaults

---

## 🖥️ Drivers

### 🔴 AMD GPU

```bash
sudo apt update
sudo apt install -y \
  firmware-amd-graphics \
  mesa-vulkan-drivers \
  mesa-va-drivers \
  mesa-vdpau-drivers
```

### 🔵 Intel GPU

```bash
sudo apt update
sudo apt install -y \
  firmware-misc-nonfree \
  intel-media-va-driver \
  i965-va-driver \
  mesa-vulkan-drivers \
  mesa-va-drivers \
  mesa-vdpau-drivers
```

### 🔷 Bluetooth

```bash
sudo apt update
sudo apt install -y bluetooth bluez blueman

sudo systemctl enable bluetooth
sudo systemctl start bluetooth

systemctl status bluetooth
```

### 🖱️ Touchpad (libinput)

Enables **tap-to-click** for laptops:

```bash
sudo mkdir -p /etc/X11/xorg.conf.d

sudo tee /etc/X11/xorg.conf.d/40-libinput.conf > /dev/null <<EOF
Section "InputClass"
  Identifier "libinput touchpad catchall"
  MatchIsTouchpad "on"
  MatchDevicePath "/dev/input/event*"
  Driver "libinput"
  Option "Tapping" "on"
EndSection
EOF
```

---

## 📦 Programs

> **Note:** All programs are installed using the **SatellaOS Program Installer Tool** inside SatellaOS ToolBox.

Programs are listed **alphabetically** to reduce errors and keep maintenance simple.

The **first 5 entries are web browsers** by design.

---

### 🌐 Browsers (Priority)

| Program       | Package | Screenshot                                                                                                           |
| ------------- | ------- | -------------------------------------------------------------------------------------------------------------------- |
| Brave Browser | Deb     | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/04-Brave.png)       |
| Firefox ESR   | Deb     | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/05-Firefox-ESR.png) |
| Google Chrome | Deb     | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/01-Chrome.png)      |
| Opera         | Deb     | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/02-Opera.png)       |
| Vivaldi       | Deb     | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/03-Vivaldi.png)     |

---

### 📃 All Programs (Alphabetical)

| Program               | Package       | Screenshot                                                                                                                     |
| --------------------- | ------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Baobab                | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/31-baobab.png)                |
| Free Download Manager | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/07-Free-Download-Manager.png) |
| Galculator            | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/26-Galculator.png)            |
| GIMP                  | Deb / Flatpak | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/13%7C14-GIMP.png)             |
| GNOME Disk Utility    | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/22-Gnome-Disk-Utility.png)    |
| GNOME Software        | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/28-Gnome-Software.png)        |
| GParted               | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/21-GParted.png)               |
| Grub Customizer       | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/25-GRUB-Customizer.png)       |
| Gucharmap             | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/27-Gucharmap.png)             |
| KDiskMark             | Deb / Flatpak | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/10%7C11-KDiskMark.png)        |
| LibreOffice           | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/32-Libreoffice.png)           |
| LocalSend             | Deb / Flatpak | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/08%7C09-LocalSend.png)        |
| MenuLibre             | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/17-MenuLibre.png)             |
| Mintstick             | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/29-Mintstick-1.png)           |
| Mission Center        | Flatpak       | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/20-Mission-Center.png)        |
| Pinta                 | Flatpak       | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/15-Pinta.png)                 |
| PowerISO              | Flatpak       | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/16-PowerISO.png)              |
| qBittorrent           | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/24-qBittorrent.png)           |
| Steam                 | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/06-steam.png)                 |
| Sublime Text          | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/18-Sublime-Text.png)          |
| VirtualBox 7.2.4      | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/12-VirtualBox.png)            |
| VLC                   | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/23-VLC.png)                   |
| Warp VPN              | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/30-Warp-VPN.png)              |
| WineHQ                | Deb           | ![](https://raw.githubusercontent.com/satellaos-official/satellaos-debian-utilities/main/app-png/19-WineHQ.png)                |
