# Installation

1. Make sure all [Requirements](requirements.md) are met
2. Clone the repository and `cd` into the directory
3. Override all relevant variables by adding `.yml` files to either `settings/charjabox` or a custom folder per group/host. See [configuration](https://cherrykitten.github.io/CharjaBox/#configuration/) for details.
4. Create an `inventory` file and add your server's IP/Hostname/Domain
5. Install needed roles: `ansible-galaxy install -r requirements.yml`
6. Run the playbook: `ansible-playbook -i inventory -u $USER charjabox.yml`

You can use the playbook `charjabox/scripts/initialize.yml` to skip part of steps 3 and 4. This playbook asks you about your server IP, group name and settings folder and creates the files for you automatically.

You still need to do it manually if you want to use multiple servers for now. This functionality will be added to the script in the future.
