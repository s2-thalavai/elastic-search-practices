# Docker Compose for ES and Kibana

## Check docker version

```bash
s2tha@thalasi-windows MINGW64 /d/Infosys
$ docker-compose --version
Docker Compose version v2.40.3-desktop.1

s2tha@thalasi-windows MINGW64 /d/Infosys
$
```


## Start containers

```bash
docker compose up -d
```

## Check status


```bash
docker compose ps

s2tha@thalasi-windows MINGW64 /d/Infosys/Elasticsearch/elasticsearch-course/01-elastic-setup (main)
$ docker compose ps
NAME            IMAGE                                                 COMMAND                  SERVICE   CREATED              STATUS          PORTS
elasticsearch   docker.elastic.co/elasticsearch/elasticsearch:9.0.2   "/bin/tini -- /usr/l…"   elastic   About a minute ago   Up 19 seconds   0.0.0.0:9200->9200/tcp, [::]:9200->9200/tcp
kibana          docker.elastic.co/kibana/kibana:9.0.2                 "/bin/tini -- /usr/l…"   kibana    About a minute ago   Up 19 seconds   0.0.0.0:5601->5601/tcp, [::]:5601->5601/tcp


s2tha@thalasi-windows MINGW64 /d/Infosys/Elasticsearch/elasticsearch-course/01-elastic-setup (main)
$
```

## ES and kibana

### ES URL: http://localhost:9200/

```json
{
  "name": "c10008b60f04",
  "cluster_name": "docker-cluster",
  "cluster_uuid": "gb2_WkgUSya-hTawobC1XQ",
  "version": {
    "number": "9.0.2",
    "build_flavor": "default",
    "build_type": "docker",
    "build_hash": "0a58bc1dc7a4ae5412db66624aab968370bd44ce",
    "build_date": "2025-05-28T10:06:37.834829258Z",
    "build_snapshot": false,
    "lucene_version": "10.1.0",
    "minimum_wire_compatibility_version": "8.18.0",
    "minimum_index_compatibility_version": "8.0.0"
  },
  "tagline": "You Know, for Search"
}
```

### Kibana URL: http://localhost:5601/app/home#/


### View logs

```bash
docker compose logs elastic
docker compose logs kibana
```

### Stop containers
```bash
docker compose down
```

### Stop and remove data volume

```bash
docker compose down -v
```

