# Description

This is a sample project showing how to sync user-infos
from a LiferayDXP instance to a LiferayCE instance via an LDAP-enabled server.

# What this example wants to achieve?

As part of a migration I needed to sync the users of a LiferayDXP instance to a LiferayCE instance via a LDAP server.  
The LiferayDXP instance acts as a (write) primary while the LiferayCE instance will be a (read) secondary.

(Image follows)

# How it is achieved?

An OpenLdap container and a LiferayDXP container are spun up in docker-compose network.
The LiferayDXP container is configured via Liferay osgi-config files (Apache Felix notation IIRC) 
mounted into the container, pointing to the LDAP DN within the OpenLDAP container where the users should be synced to.


# Current WIP:
Running something like "ldapadd -H ldap://localhost:1389 -D cn=admin,dc=liferay,dc=ldap,dc=example,dc=org -w adminpassword" 
with the DN infos passed via STDIN after OpenLDAP container startup will be too hacky. 
So I'll setup a more complex directory structure via a LDIF file provided to the OpenLDAP container. 

# Usage

compose.yaml currently contains a simple setup with only one liferay container (for systems with less then 10 GB of RAM available)

(compose-full.yaml with the full setup for systems with more then 10 GB of RAM will follow soon)

# Lessons Learned

If you like to read rants of random tech guys the [Lessons Learned Page](LESSONS-LEARNED.md) might be worth a read for you.
