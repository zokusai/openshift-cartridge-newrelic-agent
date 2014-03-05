Openshift New Relic Agent cartridge
===================================

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
