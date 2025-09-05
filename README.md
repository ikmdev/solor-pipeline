# SOLOR Pipeline

This project builds SOLOR, a harmonized terminology database comprising the following datasets:
* SNOMED-CT International
* LOINC
* RxNorm
* GUDID (Subset or Full)
* GMDN
* DeX

SOLOR is composed of Maven plugin dependencies originating from its component pipelines.

Before building this project, clone the repos below and follow the READMEs to perform a local 'clean install':
* https://github.com/ikmdev/snomed-ct-data
* https://github.com/ikmdev/loinc-data
* https://github.com/ikmdev/rxnorm-data
* https://github.com/ikmdev/gudid-data

After all of the plugin artifacts have been built locally, run the SOLOR pipeline:

```
mvn clean install -U -Dmaven.build.cache.enabled=false
```

To deploy data artifacts to Nexus:
```
mvn deploy -f solor-export -DdeployToNexus=true -Dmaven.deploy.skip=true -Dmaven.build.cache.enabled=false
```