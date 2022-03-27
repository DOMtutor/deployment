# Running local deployment

 * `docker-compose up -d`
 * Initially, change the password of the `judgehost` user to `judgepass`

## Cgroup errors

 * On linux, you need to add `cgroup_enable=memory swapaccount=1` to your cmdline (e.g. `/etc/default/grub`)
