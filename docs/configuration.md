# Configuration

Configuration is done by overwriting the defaults that are set in `group_vars/all/*`. Do not change files in this folder, as it is tracked by git.

To do this, create variable files (or folders) in either `group_vars/`or `host_vars`. These can either be files called `$GROUPNAME.yml`/`$HOSTNAME.yml` or folders called `$GROUPNAME`/`$HOSTNAME` with any number of `.yml` files inside.
Then, overwrite variables in the form of `$VARIABLE: $VALUE`.

If you use CharjaBox to set up multiple servers, you can use different settings for every server, by having multiple groups and/or hosts with different variables in your inventory.

## General

`charjabox_general.yml` includes all general configuration about your server, like Hostnames, Timezones, etc.

`charjabox_ports.yml` includes all the ports for the applications in one place.

## Application Settings

Every application has it's own variables, where you can enable the Application and apply App-specific configuration.

## Customizing the Docker containers

For everything that is not covered by existing variables, there is the option to add additional port bindings, volumes, environment variables and labels to Docker containers. 

Only use this function if you understand how Docker and docker-compose work.

Those additional values are set in list variables with the following names:

```
$appName_additional_env: []
$appName_additional_labels: []
$appName_additional_ports: []
$appName_additional_volumes: []
```

Just exchange `$appName` with the internal name of the app (see the prefix of other variables for that name) and add the lines, just as you would add them to the docker-compose file, as a list of strings.

For example:

```
$appName_additional_env:
  - "foo: bar"
  - "bar: foo"
$appName_additional_ports:
  - "8080:80"
  - "4443:443"
$appName_additional_volumes:
  - "/etc/somepath/:/somepath/
```

## Example configuration

I have a local server currently running Portainer, Heimdall, Nginx and Plex. I called the group `production` to differentiate it from a testing server. 

The inventory file looks like this:

```
[production]
192.168.1.22
[testing]
192.168.1.33
[someothergroup]
192.168.1.42

```

The group name `production` tells Ansible to look for the file `group_vars/production.yml` or the folder `group_vars/production`, which looks like this:

```
charjabox_hostname: "charjabox_production"
charjabox_domain: "charjabox.production"

portainer_enabled: true

nginx_enabled: true
nginx_http_port: 10080
nginx_https_port: 10443

firefly_enabled: true

firefly_db_password: "[REDACTED]"
firefly_app_key: "[REDACTED]"
```
