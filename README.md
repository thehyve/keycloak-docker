# keycloak_docker
Puppet module to run keycloak with docker-compose

**Prerequirements**

You should have puppet_docker module installed.

**Install module**

Add this module as submodule:
`git submodule add https://github.com/thehyve/keycloak_docker.git`

Parameters:

* keycloak_docker::db_password - required
* keycloak_docker::keycloak_user - required
* keycloak_docker::keycloak_password - required
* keycloak_docker::keycloak_fqdn - required
* keycloak_docker::docker_compose_file_path - default is `/tmp/docker-compose.yml`

**BackUP procedure**

To backup keycloak you need to backup database:
`$ sudo docker exec -it -u postgres $(docker ps | grep postgres | awk '{print $1}') pg_dump -U keycloak keycloak > keycloak.sql`
