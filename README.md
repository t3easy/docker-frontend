# A preconfigured Traefik service with docker backend

## Usage

1.  Change `.env` `COMPOSE_FILE` to include all necessary compose files.
1.  Modify Traefik config to your needs
    1.  Example for development: `traefik.dev.toml`
    1.  Example for production: `traefik.prod.toml`
1.  If you have/need other certificates than Let's Encrypt:  
    Add certificates to `certs` folder, copy the example `certs/.cert.toml.example` to `certs/your-cert.toml`.
1.  For production, you should build the image with `docker-compose build --pull`
    and push it to your registry `docker-compose push`. 
1.  Start the service `docker-compose up -d`

## Protect the API
Either disable the API in the config or generate basic authentication credentials with escaped `$` and add it to your CI variables as `BASIC_AUTHENTICATION`
```bash
echo $(htpasswd -nb user password) | sed -e s/\\$/\\$\\$/g
```
