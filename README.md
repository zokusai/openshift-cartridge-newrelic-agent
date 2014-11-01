OpenShift New Relic Agent cartridge
===================================

An embedded cartridge to enable New Relic Monitoring for Java apps deployed on OpenShift JBoss AS 7 or JBoss EAP 6.

The cartridge include the version 3.4.2 of the newrelic java agent, property of New Relic. To see detailed information about usage conditions see https://docs.newrelic.com/docs/licenses/licenses

Requirements
------------

- A [New Relic](http://www.newrelic.com/) account.  
- OpenShift JBoss AS or JBoss EAP as primary cartridge.


Install
-------

- Install the cartridge from GitHub.

```
  rhc add-cartridge -a <your_app_name> \ 
    -e OPENSHIFT_NEWRELIC_LICENSE_KEY=<your_new_relic_key> \  
    -c https://raw.github.com/zokusai/openshift-cartridge-newrelic-agent/latest/metadata/manifest.yml
```

- Restart your application.

```
  rhc app restart <your_app_name>
```
      
Remove
------

```
  rhc cartridge-remove newrelic -a <your_app_name>
```
