# Key learnings

The current Liferay versions (7.x) seem to be a giant sh*thole or at least a work-in-progress in some regards.
This page is about some of the odd stuff I faced while working on this example.


## General UX

One needs to be aware of that there are (at least) 2 levels of configurations:
* system level configuration
* instance level configuration

with at times incomprehensible differences in general behaviour and available options.

This might be related about how things are working under the hood, but like...seriously?


### Export of configuration

I really do like automating the stuff I'm implementing. So why the hell can I only export my settings when configuring on a system level?

The documentation shallowly (is this a word?) refers to the new _.config_ based system giving only a few examples.
Or maybe I wasn't just able to find the proper documentation yet...


### LDAP Server Configuration

When I tried to configure the sync of Liferay users to a LDAP server I repeatedly searched particular UI pages at the wrong place. 
More precisely, setting up an instance level LDAP server looks a lot different then on the system level.
The major difference being, that you are able to check the connection (and therefore the validity of your configuration) on an instance level only.
