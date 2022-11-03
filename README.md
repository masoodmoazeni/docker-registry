# docker-registry

Get "https://host-ip:5000/v2/": http: server gave HTTP response to HTTPS client

nano /etc/docker/daemon.json

~~~~
{
     "insecure-registries":["http://your-ip:5000"]
}
~~~~

~~~~
systemctl stop docker
systemctl start docker
~~~~
