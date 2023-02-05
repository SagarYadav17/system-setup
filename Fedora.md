#system-setup #linux

Add this lines to `/etc/dnf/dnf.conf` file

```
fastestmirror=True
max_parallel_downloads=20
```

Update the System

```bash
sudo dnf update
sudo dnf upgrade -y
```

Add Visual Studio Code and Docker Repo

```bash
# vscode
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'

# docker
sudo dnf -y install dnf-plugins-core
sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
```

Download [Docker Desktop](https://docs.docker.com/desktop/install/fedora/)

Install Basic Programs

```bash
sudo dnf install wget curl git zsh neofetch code -y
```

Add flatpak

```bash
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

Download Miniconda, Chrome

```bash
wget -b -P ~/Downloads -O miniconda.sh https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
wget -b -P ~/Downloads -O google-chrome.rpm https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm
```

To check status

```bash
tail -f wget-log
```

Install Flatpak Application

```
flatpak install flathub com.getpostman.Postman
flatpak install flathub org.videolan.VLC
flatpak install flathub com.stremio.Stremio
flatpak install flathub org.blender.Blender
flatpak install flathub md.obsidian.Obsidian
```
