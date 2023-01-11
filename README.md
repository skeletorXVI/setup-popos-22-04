# Pop!Os 22.04 Setup

Instructions, scripts and to set up Pop!Os 22.04 LTS installations.

## Setup

1. Install Ansible
   ```shell
   sudo apt install python3-pip \
   && sudo pip install ansible
   ```
2. Download repository containing playbook
   ```shell
   mkdir ~/Repositories \
   && cd ~/Repositories \
   && git clone https://github.com/skeletorXVI/popos22-04_setup.git
   ```
3. Setup system
   ```shell
   ansible-playbook \
    --user "$USER" \
    --inventory ~/Repositories/popos22-04_setup/inventory \
    --connection=local \
    --ask-become-pass \
    ~/Repositories/popos22-04_setup/setup.yml
   ```
4. Add user bin path
   ```shell
   echo 'export PATH="/home/fabian/.local/bin:$PATH"' >> ~/.bashrc
   ```
5. Enable extended keyboard layouts
   ```shell
   gsettings set org.gnome.desktop.input-sources show-all-sources true
   ```
6. Select the `English (US)` > `German, Swedish and Finnish (US)`
