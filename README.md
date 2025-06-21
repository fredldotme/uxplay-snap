## uxplay-snap
[![uxplay](https://snapcraft.io/uxplay/badge.svg)](https://snapcraft.io/uxplay)

[Upstream Project Link](https://github.com/FDH2/UxPlay) 

**NOTE:** X11 is not supported by this snap.

UxPlay is a AirPlay Unix mirroring server.

It lets you mirror your iPhone, iPad or Mac desktop screen to your desktop, where it appears in a floating window that can be shared with other apps, like Discord and OBS Studio.

UxPlay is a screen mirror only. You can't interact with what you see on the screen.

This snap is not affiliated with the upstream project in any way. If you encounter any issues, please kindly report it here.

[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)](https://snapcraft.io/uxplay)

## Requirements

[Snap installed](https://snapcraft.io/docs/installing-snapd)

## Install

```bash
$ sudo snap install uxplay
```

## Usage

see: [Official Docs](https://github.com/FDH2/UxPlay?tab=readme-ov-file#usage)


## Data & Config file location

Due to the packaging with Snap, the default paths are different.

- Default data directory: /home/$Your_User_Name/snap/uxplay/current/
- Default config directory: /home/$Your_User_Name/snap/uxplay/current/.config/uxplay

## Enable Service (Running uxplay in 'monitor' mode in background)

[What is Monitor Mode?](https://github.com/abraunegg/onedrive/blob/master/docs/usage.md#ongoing-synchronisation-operational-mode-monitor-mode)

```bash
$ mkdir -p ~/.config/systemd/user/
$ wget https://raw.githubusercontent.com/boukendesho/uxplay-snap/main/uxplay.service -O ~/.config/systemd/user/uxplay.service
$ systemctl --user daemon-reload
$ systemctl --user enable --now uxplay.service
# check service status
$ systemctl --user status uxplay.service
# check service log
$ journalctl --user-unit uxplay.service
