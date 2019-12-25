# General
[Lidarr](https://lidarr.audio/) - Manage your music collection

Set `lidarr_data_directory` to the folder where downloaded `.torrent` files should get stored.

Lidarr uses the path set in `charjabox_music_directory` in `charjabox_general.yml` to access your music collection.

# Variables

| Variable                | Type    | Default                           | Comment                                          |
|-------------------------|---------|-----------------------------------|--------------------------------------------------|
| lidarr_enabled          | Boolean | false                             | Enable/Disable the application                   |
| lidarr_config_directory | String  | "{{ docker_home }}/lidarr/config" | Path were application config should be stored    |
| lidarr_data_directory   | String  | "{{ docker_home }}/lidarr/data"   | Path were application data should be stored      |
| lidarr_traefik_enabled  | Boolean | false                             | Enable/Disable access to application via Traefik |
| lidarr_domain           | String  | "lidarr.{{ charjabox_domain }}"   | Domain used to access the application            |
| lidarr_port             | Int     | 8686                              | Port used to access the application              |
