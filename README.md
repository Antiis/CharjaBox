# CharjaBox

<img src='docs/img/mascot.png' alt='CharjaBox mascot' width="100"/>

Work in progress Ansible based Homeserver setup using Docker.

Inspired by [Ansible NAS](https://github.com/davestephens/ansible-nas) and [HomelabOS](https://gitlab.com/NickBusey/HomelabOS)

## What is this?

In the future this maybe could be a simple solution to quickly deploy a homeserver using Ansible and Docker.
At the moment it can share files via SMB and create a Portainer container for managing Docker containers. But this is only the beginning.
I will add more information, documentation and features soon

## Features

* Samba Sharing
* Manual container management using Portainer
* Home Media Streaming with Plex

### Applications

* [Plex](https://www.plex.tv/) - Your very own personal streaming service
* [Portainer](https://portainer.io/) - Web Interface for managing Docker containers

## Installation

1. Make sure all [Requirements](requirements.md) are met
2. Clone the repository and `cd` into the directory
3. Copy `settings.template` to `settings` and [configure](configuration.md) everything
4. Create an `inventory` file and add your server's IP/Hostname/Domain
4. Install needed roles: `ansible-galaxy install -r requirements.yml`
5. Run the playbook: `ansible-playbook -i inventory -u $USER charjabox.yml`

## Special Thanks

* Thanks to [DysphoricUnicorn](https://github.com/DysphoricUnicorn) for designing our beautiful mascot.
