About this Repo
======

This is the Git repo of the official Docker image for [Odoo](https://registry.hub.docker.com/_/odoo/). See the Hub page for the full readme on how to use the Docker image and for information regarding contributing and issues.

The full readme is generated over in [docker-library/docs](https://github.com/docker-library/docs), specifically in [docker-library/docs/odoo](https://github.com/docker-library/docs/tree/master/odoo).


## Steps
Clone this repo 
and goto this link
(local running odoo)[http://localhost:8069/web/database/manager]
```
sudo docker run -d -e POSTGRES_USER=odoo -e POSTGRES_PASSWORD=odoo -e POSTGRES_DB=postgres --name db postgres:15
sudo docker run -v odoo-data:/var/lib/odoo -d -p 8069:8069 --name odoo --link db:db -t odoo
```


```

# Copy the module to the container
sudo docker cp extra-addons/pos_restrict_product_stock/ odoo:/mnt/extra-addons

# Verify the module is in the container
sudo docker exec -it odoo ls /mnt/extra-addons

# Restart the Odoo container
sudo docker restart odoo

```
Now install via UI
Via Odoo UI:

Log in to your Odoo instance.
Go to Apps.
Click on the Update Apps List button.
Find your module in the list and install it.

### Via Command line 
# Update modules list and install the new module

```
sudo docker exec -it odoo /bin/bash -c "odoo -u all -d your_database_name"
```
