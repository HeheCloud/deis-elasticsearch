# Deis Elasticsearch

Elasticsearch for use in the [Deis@HeheCloud](http://hehecloud.com/) open source PaaS.

This Docker image is based on the official
[elasticsearch:2](https://hub.docker.com/_/elasticsearch/) image.

Please add any [issues](https://github.com/HeheCloud/deis-elasticsearch/issues) you find with this software to the Project.

## Usage

```
$ docker run --rm \
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
    elasticsearch:2.2
```


## Additional Resources

* [HeheCloud](http://hehecloud.com/)
* [Deis中文指南](http://deis.heheapp.com/)
