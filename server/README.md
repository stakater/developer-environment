# server machine

This machine hosts following:

* ETCD
* Consul Server

---

## Getting Started

* Once in the server folder run `vagrant up`
* Then run `vagrant status` and find the name
* Then run `vagrant ssh <name>`


---

## CONSUL

To check the consul status:

```
http://172.17.8.101:8500/v1/health/service/consul?pretty
```

---

## Troubleshooting

#### Persist consul data during restarts

There is a bug in the official consul docker image and the container fails to start with chown permission issues if you have a mapping like this: `Host(MAC): /host/path => VM(CoreOS): /vagrant/path => Container: /docker/path`. You might be wondering what is the need of doing it; this is just to persist data of consul during restarts

So, one hackish workaround is following:

`sudo chown -R 100:1000 <PATH>/developer-environment/server/shared`

`100:1000` is not always the `user:group` assigned to consul! so, they could be different! you need to ssh into the vagrant vm and check the user/groupid!

