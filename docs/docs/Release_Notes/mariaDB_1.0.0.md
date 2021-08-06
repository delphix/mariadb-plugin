# MariaDB Plugin 1.0.0

To install dxi, refer to [Plugin Installation](/PluginInstallation/index.html)

###New Features

-  Selecting Databases : Ability to select specific databases in the Source MariaDB server when creating a dSource.
-  Delphix generated config file : If a my.cnf file is not provided while creating a dSource, Delphix now creates one. 
-  New Exit Return Codes : MariaDB Plugin 1.0.0 introduces more granular exit codes for errors. 

###Breaking Changes 
-  Removed Simple Tablespace Backup: MariaDB Plugin does not support the Simple Tablespace Backup option for Linking. This option may be supported in the future.

###Supported versions

The current release supports  

- All MariaDB versions greater than 10.2.39
- RHEL 6.9 / 7.x / 8.x
- Delphix Engine 6.0.4 and above

Future releases may add support for additional versions.

Questions?
----------------
If you have questions, bugs or feature requests reach out to us via the [MariaDB Github](https://gitlab.delphix.com/mouhssine.saidi/mariadb_linux/) or
at [Delphix Community Portal](https://community.delphix.com/home)
