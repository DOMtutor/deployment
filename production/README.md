Repository containing all infrastructure for the IST DOMjudge instance.

# Deployment

 * Create `domjudge/.env` with:
   ```
   DOMJUDGE_HOST=<public host name>
   MARIADB_ROOT_PASSWORD=<secure password>
   MARIADB_DOMJUDGE_PASSWORD=<secure password>
   ```
 * Run `docker-compose up -d`
 * Note the judgehost secret
 * Add to `.env`:
   ```
   JUDGEDAEMON_PASSWORD=<judgehost secret>
   ```
 * Run `docker-compose up -d`

