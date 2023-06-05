# docker-registry

after that get reposity from github

you must run this command

```
docker-compose up -d
```

after that you must run this command for generate user and password for docker registry

```
docker run --entrypoint htpasswd httpd:2 -Bbn testuser testpassword > auth/htpasswd
```

you can see list of docker registry with whis command
```
curl -X GET https://myregistry:5000/v2/_catalog
```

after that if use to another host for pull and push image from docker registry 

you must this command and create on every host

nano /etc/docker/daemon.json

~~~~
{
     "insecure-registries":["http://your-ip:5000"]
}
~~~~
afetr that you must run these command
~~~~
systemctl stop docker
systemctl start docker
~~~~

docker registry can map on port 80

and you must forwarding this port but ui for docker registry ist not work

you must create and setting secure domain on this host for secure host and set domain for easy way for use this docker registery

source
- virgool [Docker Registry with shiva]([[https://hub.docker.com/_/postgres/](https://virgool.io/@shivaganji/%D8%AF%D8%A7%DA%A9%D8%B1-%D8%B1%D8%AC%DB%8C%D8%B3%D8%AA%D8%B1%DB%8C-%D8%A7%D8%B6%D8%A7%D9%81%D9%87-%DA%A9%D8%B1%D8%AF%D9%86-%D8%B5%D9%81%D8%AD%D9%87-ui-hf4hdilkmpzc)](salam))
