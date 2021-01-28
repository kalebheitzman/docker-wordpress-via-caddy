# WordPress via Caddy Docker Stack

This is a WordPress via Caddy Docker stack that can be deployed in development, staging, and/or production environments. Copy the ```.env-sample``` file to ```.env``` and update the values for your needs.

## Quickstart Sample Workflow

**Step 1:** Install Docker Desktop on your development machine. 

This will give you access to the ```docker-compose up``` command on the command line. 

**Step 2:** Fork this repository and tweak it for your own needs. 

**Step 3:** Clone your forked repository to your development machine. There is no need to copy the ```.env-sample``` to ```.env``` because default values are already provided in the [docker-compose.yml](docker-compose.yml) file for a development environment.

Simply issue the following command and everything will be set up for you.

```bash
docker-compose up -d
```

**Step 4:** Set up a staging environment.

**Step 5:** Set up a production environment.

## Caddyfile

This stack uses Caddy to serve WordPress. Create a Caddyfile in your environment using the following syntax. This example is for intercepting all port :80 traffic. Change :80 to your domain, for example https://example.com.

```
:80 {
    root * /var/www/html
    php_fastcgi wordpress:9000
    file_server
}
```