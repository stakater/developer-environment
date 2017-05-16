# AGENT MACHINE

---
## SSH setup for git
The SSH key file is to be placed in `agent/shared/gocd-data/ssh-key` folder by the name `id_rsa`.

For now, the `gocd-agent` service, copies the file to another location (`/home/core/docker-volumes/ssh-key/`), and changes its owner to user with ID `1001` (hardcoded ID for user `go` inside `stakater/gocd-agent` and `stakater/gocd-server` image), before starting the gocd-agent & gocd-server docker containers. The location `/home/core/docker-volumes/ssh-key/` is then mapped inside the gocd-agent  & gocd-server containers so that it is accessible by the `go` user in order to perform git operations.

The reason to copy the file in another location (`/home/core/docker-volumes/ssh-key/`) is that we aren't allowed to change permissions of the file which is shared b/w the host machine and vagrant machine. So we copy it to another locaiton, change the file permissions and then map that volume inside the docker containers/


## ELASTICSEARCH

To check the cluster health:

```
http://172.17.9.101:9200/_cluster/health
```

And this endpoint as well:

```
http://172.17.9.101:9200/_cat/health?v
```

---

## KIBANA

### HEALTHCHECK

Machine readable kibana healthcheck is following:

```
http://172.17.9.101:5601/api/status
```

Sample output; it should be GREEN!

```
overall: {
state: "red",
title: "Red",
nickname: "Danger Will Robinson! Danger!",
icon: "danger",
since: "2017-03-07T19:02:19.293Z"
}
```

### UI

```
http://172.17.9.101:5601/app/kibana#?_g=()
```

---

## LOGSTASH

### HEALTHCHECK

```
http://172.17.9.101:9600/
```

More can be read here: `https://www.elastic.co/guide/en/logstash/current/monitoring.html`

