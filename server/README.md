# server machine

This machine hosts following:

* ETCD
* Consul Server

There is a bug in the official consul docker image and the container fails to start with chown permission issues if you have a mapping like this: `Host(MAC): /host/path => VM(CoreOS): /vagrant/path => Container: /docker/path`

So, one hackish workaround is following:

`sudo chown -R 100:1000 <PATH>/developer-environment/server/shared`

`100:1000` is not always the `user:group` assigned to consul! so, they could be different! you need to ssh into the vagrant vm and check the user/groupdid!