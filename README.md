# ansible-slow-query-log-digest

Digest slow query logs and persist them in database which is used by [anemometer](https://github.com/box/Anemometer)

## Requirements

This role requires Ansible 2.8 or higher and platform requirements are listed in the metadata file.

## Role variables

|Name|Default value|Description|
|--|--|--|
|`slow_query_log_digest_image`|`"perconalab/percona-toolkit:3.0.6"`|Image that it is used for digesting slow logs|
|`slow_query_log_digest_network`|**NONE**|(REQUIRED)Networks list to attach to|
|`slow_query_log_digest_slowlog_path`|`"var/log/mysql/mariadb-slow.log"`|Path to slow log file|
|`slow_query_log_digest_database_host`|`localhost`|Database host|
|`slow_query_log_digest_database_port`|`3306`|Database port|
|`slow_query_log_digest_database_user`|`root`|Database user|
|`slow_query_log_digest_database_pass`|`pass`|Database password|
|`slow_query_log_digest_database_name`|`slow_query_log`|Database name|
|`slow_query_log_digest_database_review_table`|`global_query_review`|Database review table name|
|`slow_query_log_digest_database_review_history_table`|`global_query_review_history`|Database review history table name|

## Example playbook

```
- name: Provision servers
  hosts: all
  become: true
  roles:
    - ansible-slow-query-log-digest
  vars:
    slow_query_log_digest_image: "perconalab/percona-toolkit:3.0.6"
    slow_query_log_digest_slowlog_path: "/var/log/mysql/mariadb-slow.log"
    slow_query_log_digest_network:
      - name: foo_network
      - name: bar_network
    slow_query_log_digest_database_host: localhost
    slow_query_log_digest_database_port: 3306
    slow_query_log_digest_database_user: root
    slow_query_log_digest_database_pass: pass
    slow_query_log_digest_database_name: slow_query_log
    slow_query_log_digest_database_review_table: global_query_review
    slow_query_log_digest_database_review_history_table: global_query_review_history
```
