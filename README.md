# developer-environment

A developer environment based on:

* Vagrant
* CoreOS
* Docker

Vagrant will run CoreOS guest machine which will host docker'ized apps.

## TODOs

- [x] Create Repo
- [ ] Fix logstash API endpoint
- [ ] Create a diagram
- [ ] ETCD + CONSUL + Elastic Stack (ELK + F)
- [ ] Script to run both vagrant files sequentially; so, run one command to bring up whole stack
- [ ] Script to modify the permission of shared folder in host machine for consul data mapping to work (so, that defined key/value pairs survive restart)
- [x] Given user option to cherry pick services to start. ANS: The best solution is to comment out the services which are not required.
- [ ] Map /backup/data/ to host machine as well! Currently get these errors `chown: changing ownership of '/var/lib/mysql/': Operation not permitted`
- [x] Run GoCD (server + agents) as systemd units
