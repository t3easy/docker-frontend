# Usage

1.  Copy over either `.examples/docker-compose.override.host.yml` or `.examples/docker-compose.override.local.yml` to `docker-compose.override.yml`.
1.  Add certificates to `certs` folder for local, or to `/etc/ssl/private/` on the docker host.  
    If you use docker-machine to interact with your docker host, you can use it to copy your certs:
    `docker-machine scp -r certs/. docker-host:/etc/ssl/private/`
