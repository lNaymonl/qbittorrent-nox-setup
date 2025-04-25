# qbittorrent-nox-setup
This is a small guide to install qbittorrent-nox on a ubuntu system. It pretty much follows the quide in the [official documentation](https://github.com/qbittorrent/qBittorrent/wiki/Running-qBittorrent-without-X-server-(WebUI-only,-systemd-service-set-up,-Ubuntu-15.04-or-newer)) just a little more compact.

## Requirements
- Ubuntu Installation
- sudo access

## Setup
### Installation
```bash
sudo add-apt-repository ppa:qbittorrent-team/qbittorrent-stable
sudo apt install -y qbittorrent-nox
```

### Create a user
```bash
sudo adduser qbtuser
sudo su qbtuser # Inititialize user
exit # Logout
sudo usermod -s /usr/sbin/nologin qbtuser # Disable login
```

### Systemd
```bash
sudo systemctl enable --now qbittorrent-nox@qbtuser
```
