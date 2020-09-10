# MediaWiki

[MediaWiki](https://www.mediawiki.org) is an extremely powerful, scalable software and a feature-rich wiki implementation that uses PHP to process and display data stored in a database, such as MySQL.


## Introduction

This chart bootstraps a [MediaWiki](https://github.com/wikimedia/mediawiki-docker) deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

It also packages the [MariaDB chart](https://github.com/docker-library/mariadb) which is required for bootstrapping a MariaDB deployment for the database requirements of the MediaWiki application.

mediawiki-chart can deployed to any helm cluster

## Prerequisites

- Kubernetes 1.12+
- Helm 2.12+ or Helm 3.0-beta3+

## Installing the Chart

To install the chart with the release name `my-test`:

Download the package and add it to any private/public helm repo and use helm to install/delete the charts

```console
$ helm install my-test mediawiki-chart
```

The command deploys MediaWiki on the Kubernetes cluster in the default configuration. The [Parameters](#parameters) section lists the parameters that can be configured during installation.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall/delete the `my-test` deployment:

```console
$ helm delete my-test
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

The following table lists the configurable parameters of the MediaWiki chart and their default values.

| Parameter                            | Description                                                                                            | Default                                                      |
|--------------------------------------|--------------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
| `image.svcimage`	               | Docker image registry for mediawiki servide                                                            | `mediawiki`                                                  |
| `image.dbimage`       	       | Docker image registry for mariadb servide                                                              | `mariadb`      					       |
| `mysql.dbname`              	       | Mariadb database name                                                                                  | `my_wiki`                                                    |
| `mysql.dbuser`                       | Mariadb user name                                                                                      | `test`                                                  |
| `mysql.dbpass`                       | Mariadb password                                                                                       | `Hello123`                                          |
| `service.apptype`                    | Service type for kubernetes mediawiki service                                                          | `NodePort`                                                   |
| `service.appPort`                    | Service Port for kubernetes mediawiki service                                                          | `80`                                                         |
| `service.dbtype`                     | Service type for kubernetes db service                                                                 | `NodePort`                                                   |
| `service.dbPort`                     | Service Port for kubernetes db service `                                                               | `3306`                                                       |
| `ReplicaSet`                         | ReplicaSet for mediawiki and mariadb service                                                           | `1`                                                          |
| `service.appNodePort`		       | Service Node Port for kubernetes mediawiki service                                                     | `32625`                                                      |
| `service.dbNodePort`		       | Service Node Port for kubernetes db service                                                            | `32626`                                                      |

