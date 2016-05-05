OpenShift New Relic Agent cartridge
===================================

An embedded cartridge to enable New Relic Monitoring for Java applications deployed on OpenShift JBoss cartridges.

The cartridge include the version 3.11.0 of the Java Agent, property of New Relic. To see detailed information about usage conditions see https://docs.newrelic.com/docs/licenses/licenses

Requirements
------------

- A [New Relic](http://www.newrelic.com/) account.
- OpenShift JBoss AS/EAP/EWS as primary cartridge.


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

Known Issues
------------

* Non-writable '/var/lib/<GEAR_UUID>/.env/user_vars/JAVA_OPTS_EXT' found.

  If you used the command `rhc set-env` to define the `JAVA_OPTS_EXT` 
  environment variable, then this will have been created with `root` as the
  owner of the corresponding file.
  
  As a workaround you could take note of the current value of the variable and
  then remove it with:
  
  ```
  rhc env unset JAVA_OPTS_EXT -a <ypur_app_name>
  ```
  
  Once the cartridge is installed, you could copy back the remaining values to 
  the variable through a login session:
  
  ```
  rhc ssh -a <your_app_name>
  vim .env/user_vars/JAVA_OPTS_EXT
  ```
