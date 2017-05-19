# AGENT MACHINE

---

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

