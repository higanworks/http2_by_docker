# http2_by_docker

## start

### h2o

```
$ sudo docker build -t local/h2o .
$ sudo docker run -t --rm -p 443:8080 -v `pwd`/conf:/conf local/h2o /conf/h2o.conf
```

### trusterd

```
$ sudo docker build -t local/trusterd .
$ sudo docker run -t --rm -p 443:8080 -v `pwd`/conf:/conf -t local/trusterd /conf/trusterd.conf
```

