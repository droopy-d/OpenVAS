# 1. Install docker
```
sudo apt install docker.io
```

# 2. Install OpenVAS container from dockerhub.
```
docker run -d -p 443:443 --name openvas mikesplain/openvas
```
OpenVAS will be configured and available to use once you navigate to https://127.0.0.1 in your preferred web browser.

```
Username: admin
Password: admin
```

# Script to reinstall Docker and OpenVAS with each reboot (if needed)
https://taksshack.com/forums/topic/openvas-gvm-vulnerability-scanner-install-parrot-os/
```
#! /bin/bash
echo “Uninstalling Docker.io”
sudo apt remove --purge docker.io -y
sudo rm -rf /etc/docker
sudo apt autoremove -y
echo "Reinstalling Docker.io"
sudo apt install docker.io -y
echo "Installing OpenVAS container"
docker run -d -p 443:443 --name openvas mikesplain/openvas
echo "OpenVas Container Installed."
echo "Open with https://127.0.0.1"
echo "User is admin."
echo "Password is admin."
```
