# Troubleshooting

If you run into an error while using the MariaDB plugin and have an exit code in the error, 
refer to [ExitCodes](/References/ExitCodes/index.html) for further information. 

## Logs

There are 2 sets of logs for the MariaDB plugin

1. Plugin Logs
   
    Plugin logs are part of the Delphix Engine. Refer to [How to Retrieve Logs] (https://developer.delphix.com/References/Logging/#how-to-retrieve-logs) 
    to find out how to get the Delphix Plugin Logs. 
   
2. MariaDB Shell Operation Logs
   
    When the plugin performs certain operations ( such as Take backup, Link, Provision etc), 
    logs are written to log files on the staging or target host under the *Delphix Toolkit* directory

    Following are the logs to review

    - delphix_mysql_debug.log 
    - delphix_mysql_info.log
    - delphix_mysql_error.log


## Common MariaDB Commands 

1. Connecting to a MariaDB instance

    ```commandline
    delphixos> /usr/bin/mysql -uUserName -pPassword --protocol=TCP --port=1234
    ```
   
2. List databases in MariaDB
   ```jql
   mysql> show databases;
   ```
   
3. Check replication status in MariaDB
   ```jql
   mysql> show slave status;
   ```

4. Check binary logging
   ```jql
   mysql> SHOW VARIABLES LIKE 'log_bin';
   ```

5. Check user permissions
    ```jql
    mysql> show grants for 'delphixdb'@'%';
    ```
