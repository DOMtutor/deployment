# Running local deployment

 * `docker-compose up -d`
 * Check admin password of domjudge by `docker logs domjudge` (optional if you set it if you set it via `pyjudge`)
 * Change the password of the `judgehost` user to `judgepassword`

## Cgroup errors

 * On linux, you need to add `cgroup_enable=memory swapaccount=1` to your cmdline (e.g. `/etc/default/grub`)
