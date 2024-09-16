# PI SETUP

This is a repository for [ansible](https://www.ansible.com/) notebook (agent less system configuration tool) to be configure raspberry pi for [komorebi project](https://github.com/dattasaurabh82/komorebi-stick).

When run from a client machine, it sshes into the PI, installs bunch of things, edits the configuration, etc. without using any installation shell script.

## Applied Persisant Changes

- Sets a custom ASCII art Message of the Day (MOTD)
- Updates the apt cache
- Enables the I2C interface in boot config
- Loads the I2C kernel module
- Hides the Raspberry Pi logo during boot and disables it on the top left corner
- Installs required packages (git, tmux, neofetch, vim, vlc)
- Sets the desktop background to black
- Hides all desktop icons (documents, trash, mounts)
- Ensures the LXDE panel configuration directory exists
- Configures the panel to auto-hide

## Pre-requisites

- The image we used to burn on the micro SD card (32GB) is the [32bit Raspberry Pi OS (Legacy) with desktop](https://downloads.raspberrypi.com/raspios_oldstable_armhf/release_notes.txt)
- While using [PI-Imager](https://www.raspberrypi.com/software/) to install this we also made settings changes such as:
  - Give it WiFi credentials (not 5GHz) to auto-connect on the first boot
  - Enable and give it as suitable hostname
  - Give it a suitable user name (I kept `pi`)
  - Give it a suitable password
  - Enable Provide ssh key of the client development machine from which we will often shh into the pi or run the ansible notebooks from.
- Before running the ansible notebook, goes unsaid, make sure that you have [ansible installed](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) on your development client machine.  
- Make Sure to edit the [inventory.ini](inventory.ini) to match pi's host name and user name. For example, my pi's (the one I'm using for the komorebi project) user is `pi` and the hostname is `komorebi.local` (see below).

  ```ini
  [raspberry_pi_2_zero_w]
     komorebi ansible_host=komorebi.local ansible_user=pi
  ```

## Post Installation

### Configure git

TBD

### Run the notebook

TBD
