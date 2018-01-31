# Usage

1.  Copy over either `.examples/docker-compose.override.host.yml` or `.examples/docker-compose.override.local.yml` to `docker-compose.override.yml`.
    1.  For local: Copy over `.examples/traefik.toml` to `traefik.toml` and modify it to your needs
    1.  For host: Modify `.examples/traefik.toml` and build your image
1.  Add certificates to `certs` folder, copy the example `certs/.cert.toml.example` to `certs/your-cert.toml` for local, or to `/etc/ssl/private/` on the docker host.  
    If you use docker-machine to interact with your docker host, you can use it to copy your certs:
    `docker-machine scp -r certs/. docker-host:/etc/ssl/private/`
