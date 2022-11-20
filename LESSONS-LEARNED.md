# Key learnings

The current Liferay versions (7.x) seem to be a mediocre sh*thole or at least a work-in-progress in some regards.
This page is about some of the odd stuff I faced while working on this example.


## General UX

One needs to be aware of that there are (at least) 2 scope of configurations:
* system scope configuration
* instance scope configuration

with at times incomprehensible differences in general behaviour and available options.

This might be related about how things are working under the hood, but like...seriously?


### Export of configuration

I really do like automating the stuff I'm implementing. So why the hell can I only export my settings when configuring on a system scope?

The documentation shallowly (is this a word?) refers to the new _.config_ based system giving only a few examples.
Or maybe I wasn't just able to find the proper documentation yet...

_Edit 2022-11-19 1_: Ok, it seems one can export something at the top level of instance scope. Something means: Not everything I changed. Well
at least I was able to export the LDAP instance scope configs for now (still need to find a way to fill the password field in the confs tho).

_Edit 2022-11-20 1_: Found a way to add the passwords to the config files. Not the best way yet, but we are getting there. 
The configuration file for the general LDAP export settings still doesn't work yet (the instance scope LDAPServer config works...).

_Edit 2022-11-20 2_: Ok, I found the problem with the general LDAP export settings. The config file was missing the identifier (demarked by using ~<identifier>)
the LDAPServer had. Rechecked if I did something wrong, but it seems exporting the settings via UI omits an idenfitier for the import/export config file).

### LDAP Server Configuration

When I tried to configure the sync of Liferay users to a LDAP server I repeatedly searched particular UI pages at the wrong place. 
More precisely, setting up an instance level LDAP server looks a lot different then on the system level.
The major difference being, that you are able to check the connection (and therefore the validity of your configuration) on an instance level only.
