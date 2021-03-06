# Instructions #
This document describes how to configure pipeline before first deploy.

## Jenkinsfile ##
At the beginning of Jenkinsfile there are variables you must adjust as necessary:
* APP_NAME 
* COMPANY_NAME
* REGISTRY
* DEVELOP_NAMESPACE
* RELEASE_NAMESPACE
* PROD_NAMESPACE
* DEVELOP_ENV
* RELEASE_ENV
* PROD_ENV

## Helm default values ##
There is a file with default values for every environment, and they must be adjusted as necessary:
* DEV environment = helm3/appchart/values-dev.yaml
* HML environment = helm3/appchart/values-hml.yaml
* PRD environment = helm3/appchart/values-prd.yaml


## Agents ##
There are container's agents examples in directory `agents` that are used on pipeline steps, and they can be customised as necessary.
If you prefer you can use it inline instead of a separated file.

Example of external file agent declaration:

```groovy 
agent {
    kubernetes {
        cloud 'local'
        yamlFile 'pipeline/agents/gcpdeploy.yml'
    }
}  
```

