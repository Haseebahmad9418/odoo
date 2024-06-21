About this Repo
======

This is the Git repo of the official Docker image for [Odoo](https://registry.hub.docker.com/_/odoo/). See the Hub page for the full readme on how to use the Docker image and for information regarding contributing and issues.

The full readme is generated over in [docker-library/docs](https://github.com/docker-library/docs), specifically in [docker-library/docs/odoo](https://github.com/docker-library/docs/tree/master/odoo).


## Steps
Clone this repo 
and goto this link
[local running odoo](http://localhost:8069/web/database/manager)
```
sudo docker run -d -e POSTGRES_USER=odoo -e POSTGRES_PASSWORD=odoo -e POSTGRES_DB=postgres --name db_new postgres:15
sudo docker run -v odoo-data-new:/var/lib/odoo -d -p 8070:8069 --name odoo_new --link db_new:db -t odoo
```
