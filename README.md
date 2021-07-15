Repository containing all infrastructure for the IST DOMjudge instance.

# TODO

 * Backup for mariadb

# Folders

 * `domjudge`: Contains docker-compose and related for the publicly reachable DOMjudge instance
 * `judgehost`: Separate docker-compose for judgehosts (to allow deployment to a different machine)


# Local Instance

  * `export DOMJUDGE_HOST=<hostname>` a name that resolves to your machine (needed for judgehost -> domjudge communication)
  * Run `docker-compose --env-file .env.dev up -d` inside the folder to start a local instance.
    Judgehost and admin password are printed by domjudge.
    Run
    ```
      docker exec -it domserver cat /opt/domjudge/domserver/etc/initial_admin_password.secret
      docker exec -it domserver cat /opt/domjudge/domserver/etc/restapi.secret
    ```
    to obtain the secrets later.
  * Run `DOMJUDGE_PROTOCOL=http JUDGEDAEMON_PASSWORD=<judgehost secret> docker-compose up -d judgehost-<number>` to start a local instance


# Deployment

 * Create protected `domjudge/.env` with:
   ```
   DOMJUDGE_HOST=<public host name>
   MARIADB_ROOT_PASSWORD=<secure password>
   MARIADB_DOMJUDGE_PASSWORD=<secure password>
   ```
 * Run `docker-compose up -d` in `domjudge`
 * Note the judgehost secret
 * Create protected `judgehost/.env` with:
   ```
   DOMJUDGE_HOST=<url of domjudge>
   JUDGEDAEMON_PASSWORD=<judgehost secret>
   ```
 * Run `docker-compose up -d`

