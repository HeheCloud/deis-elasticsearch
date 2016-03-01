# Deis Elasticsearch

Elasticsearch for use in the [Deis@HeheCloud](http://hehecloud.com/) open source PaaS.

This Docker image is based on the official
[elasticsearch:2.2](https://hub.docker.com/_/elasticsearch/) image.

Please add any [issues](https://github.com/HeheCloud/deis-elasticsearch/issues) you find with this software to the Project.

## Usage

```
ETCD_PATH=/hehe/services/elasticsearch
etcdctl --no-sync set "$ETCD_PATH/hosts/${COREOS_PRIVATE_IPV4}" '{"http_port": 9200, "transport_port": 9300}' --ttl 60
$ docker run --rm -it \
    --name deis-elasticsearch \
    -p 9200:9200 \
    -p 9300:9300 \
    -v /data/elasticsearch/data:/usr/share/elasticsearch/data \
    -e HOST=${COREOS_PRIVATE_IPV4} \
    -e PUBLIC_IPV4=${COREOS_PUBLIC_IPV4} \
    -e PRIVATE_IPV4=${COREOS_PRIVATE_IPV4} \
    -e HTTP_PORT=9200 \
    -e EXTERNAL_PORT_HTTP=9200 \
    -e TRANSPORT_PORT=9300 \
    -e EXTERNAL_PORT_TRANSPORT=9300 \
    daocloud.io/cloudmario/deis-elasticsearch:master-init
```


## Additional Resources

* [HeheCloud](http://hehecloud.com/)
* [Deis中文指南](http://deis.heheapp.com/)
