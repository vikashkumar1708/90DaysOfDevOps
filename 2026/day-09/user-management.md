bash
sudo useradd -m tokyo
sudo useradd -m berlin
sudo useradd -m professor
sudo passwd tokyo
sudo passwd berlin
sudo passwd professor

sudo groupadd developers
sudo groupadd admins

sudo usermod -aG developers tokyo
sudo usermod -aG developers,admins berlin
sudo usermod -aG admins professor

sudo mkdir /opt/dev-project
sudo chgrp developers /opt/dev-project
sudo chmod 775 /opt/dev-project
