# MariaDB_Linux

## What Does a Delphix Plugin Do?

Delphix is a data management platform that provides the ability to securely copy and share datasets. Using virtualization, you will ingest your data sources and create virtual data copies, which are full read-write capable database instances that use a small fraction of the resources a normal database copy would require. The Delphix engine has built-in support for interfacing with certain types of datasets, such as Oracle, SQL Server and ASE.

The Delphix virtualization SDK (https://github.com/delphix/virtualization-sdk) provides an interface for building custom data source integrations for the Delphix Dynamic Data Platform. The end users can design/implement a custom plugin which enable them to use custom data source like MariaDB, MongoDB, Cassandra, MariaDB or something else similar to as if they are using a built-in dataset type with Delphix Engine.

## MariaDB Plugin

MariaDB plugin is developed to virtualize MariaDB data source leveraging the following built-in MariaDB technologies:
Features:

- Environment Discovery: MariaDB plugin can discover environments where MariaDB server is installed.
- Ingesting Data: Create a dSource using differnt methods specified below.
- VDB Creation: Single node MariaDB VDB can be provisioned from the dsource snapshot.

Different Ways to Ingest Data ( Dsource creation )

- Replication with Delphix initiated Backup: Delphix takes an initial backup from source DB to ingest data and create a dSource. Delphix also sets up a master-slave replication to keep this dSource in sync with the source database. User can select the databases they want to virtualize
- Replication with User Provided Backup: User provides a backup file from source DB to ingest data and create a dSource. Delphix sets up a master-slave replication to keep this dSource in sync with your source database.
- User Provided Backup with no Replication: User provides a backup file from source DB to ingest data and create a dSource. When a new backup is available, user initiates a resync of the dSource to ingest data from the new backup.
- Manual Backup Ingestion: Delphix creates an empty seed datanase and User manually ingests a backup to create a dSource.

MariaDB Plugin documentation can be found at TDB

### <a id="upload-plugin"></a>Steps to build, upload and run unit tests for plugin

1. Build the source code. It generates the build with name `artifacts.json`:

```bash
    dvp build
```

dvp version 2.1 required.

2. Upload the `artifacts.json` ( generated in step 1 ) on Delphix Engine:

```bash
    dvp upload -e <Delphix_Engine_Name> -u <username> --password <password>
```

### <a id="run_unit_test_case"></a>Download plugin logs

#### Plugin Logs:

Download the plugin logs using below command:

`dvp download-logs -c plugin_config.yml -e <Delphix_Engine_Name> -u admin --password <password>`

### <a id="tested-versions"></a>Tested Versions

- Delphix Engine: 6.0.8.0 and above
- MariaDB Versions 10.2.x, 10.3.x above 10.4.
- Linux Version: RHEL 7.x, 8.x

### <a id="support-features"></a>Supported Features

- MariaDB Replication
- MariaDB Manual Backup Ingestion

### <a id="unsupported-features"></a>Unsupported Features

- MariaDB Clusters
- Sharded MariaDB Databases

### <a id="contribute"></a>How to Contribute

Please read [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the pull requests process.

### <a id="statement-of-support"></a>Statement of Support

This software is provided as-is, without warranty of any kind or commercial support through Delphix. See the associated license for additional details. Questions, issues, feature requests, and contributions should be directed to the community as outlined in the [Delphix Community Guidelines](https://delphix.github.io/community-guidelines.html).

### <a id="license"></a>License

This is code is licensed under the Apache License 2.0. Full license is available [here](./LICENSE).
