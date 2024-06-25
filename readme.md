# Mysql

### .env

```
ROOT_DIR=<set to a location where the database will be stored>
HOSTNAME=<>
```

### deploy

```
docker compose up -d
```

NOTE: change default password for `root` user after installation.

### set healthcheck credentials

Redo if container gets recreated since this setup is ephimeral on purpose.

- Log into the container shell
    ```
    docker exec -it mysql-1 bash
    ```
- Setup credentials. Will propmt for password.
    ```
    mysql_config_editor set --login-path=ping --user=<type user here> --host=127.0.0.1 -p
    ```
- Restart container.
    ```
    docker restart mysql-1
    ```

### Update mysql config

You can change or add new config files in [./config](./config). After any modification, restart the container.