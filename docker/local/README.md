# Running Local Deployment

 * Ensure that `docker` and `docker-compose` is installed
 * `docker-compose up -d`
 * Check admin password of domjudge by `docker logs domjudge` (optional if you set it if you set it via `pyjudge`)
 * Change the password of the `judgehost` user to `judgepassword` in the DOMjudge webinterface
 * Check the log of the judgehost instance for errors with `docker-compose logs judgehost`

 * To stop the docker images, run `docker-compose stop` in this folder

## Cgroup errors

 * On linux, you need to add `cgroup_enable=memory swapaccount=1` to your cmdline (e.g. `/etc/default/grub` and `sudo update-grub2`)
 * It may be needed to add `systemd.unified_cgroup_hierarchy=0` too on some modern system
