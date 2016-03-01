# Deis Elasticsearch

Elasticsearch for use in the [Deis@HeheCloud](http://hehecloud.com/) open source PaaS.

This Docker image is based on the official
[elasticsearch:2.2](https://hub.docker.com/_/elasticsearch/) image.

Please add any [issues](https://github.com/HeheCloud/deis-elasticsearch/issues) you find with this software to the Project.

## Usage

```
ETCD_PATH=/hehe/services/elasticsearch
etcdctl set $ETCD_PATH/cluster.name hehe
etcdctl --no-sync set "$ETCD_PATH/hosts/10.171.35.246" '{"IP":"10.171.35.246","HttpPort":9200,"TransportPort":9300}'
$ docker run --rm -it \
    --name deis-elasticsearch \
    -p 9200:9200 \
    -p 9300:9300 \
    -v /data/elasticsearch/data:/usr/share/elasticsearch/data \
    -v /data/elasticsearch/logs:/usr/share/elasticsearch/logs \
    -e HOST=${COREOS_PRIVATE_IPV4} \
    daocloud.io/cloudmario/deis-elasticsearch:master-init
```


## Additional Resources

* [HeheCloud](http://hehecloud.com/)
* [Deis中文指南](http://deis.heheapp.com/)
