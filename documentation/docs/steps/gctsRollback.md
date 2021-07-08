# ${docGenStepName}

## ${docGenDescription}

## Prerequisites

This step performs a rollback of commit(s) in a local ABAP system repository. If a `commit` parameter is specified, it will be used as the target commit for the rollback. If no `commit` parameter is specified and the remote repository domain is 'github.com', the last commit with status 'success' will be used for the rollback. Otherwise, gctsRollback will rollback to the previously active commit in the local repository.
Learn more about the SAP git-enabled Central Transport System (gCTS) [here](https://help.sap.com/viewer/4a368c163b08418890a406d413933ba7/201909.001/en-US/f319b168e87e42149e25e13c08d002b9.html). With gCTS, ABAP developments on ABAP servers can be maintained in Git repositories.

## ${docGenParameters}

## ${docGenConfiguration}

## ${docJenkinsPluginDependencies}

## Example

Example configuration for the use in a Jenkinsfile.

```groovy
gctsRollback(
  script: this,
  host: "https://abap.server.com:port",
  client: "000",
  abapCredentialsId: 'ABAPUserPasswordCredentialsId',
  repository: "myrepo"
  )
```

Example for the use in a YAML configuration file (such as `.pipeline/config.yaml`).

```yaml
steps:
  <...>
  gctsRollback:
    host: "https://abap.server.com:port"
    client: "000"
    abapCredentialsId: 'ABAPUserPasswordCredentialsId'
    repository: "myrepo"
```