# Wordpress behind a Proxy with Let's Encrypt using Docker

Wordpress blog with MySQL database behind a Nginx proxy with SSL certificates by Let's Encrypt.

## Requisites

[Docker](https://www.docker.com/get-docker) installed on the host.

## For local development

Clone this repo and run the following commands:

* Read the this [guide](https://medium.com/@francoisromain/set-a-local-web-development-environment-with-custom-urls-and-https-3fbe91d2eaf0) to setup your machine, like `/etc/hosts/`, certificates.
* To start Nginx proxy, from the root of the project, run this command:

```bash
docker-compose -f docker-compose-dev.yml up -d
```

* Go to `wordpress` folder and create a file called `.env` with the following content (update values as needed):

```
MYSQL_ROOT_PASSWORD=mysqlrootpassword
WORDPRESS_DB_PASSWORD=wordpressdbpassword
```

* Start Wordpress by running:

```
docker-compose -f docker-compose.yml -f docker-compose-dev.yml up -d
```

## For production
Refer to this [guide](https://medium.com/@francoisromain/host-multiple-websites-with-https-inside-docker-containers-on-a-single-server-18467484ab95).

## Acknowledgments

Thanks to [François Romain](https://medium.com/@francoisromain) for the excellent guides.
