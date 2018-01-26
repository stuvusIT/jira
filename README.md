# jira

This role installs the Atlassian JIRA.
Configuration that is made in configuration files is automatically performed.
Further configuration is only possible through the JIRA administration interface.

## Requirements

Ubuntu and an [Oracle JVM (JIRA 7 needs at least Version 8)](https://github.com/stuvusIT/oracle-java)

## Role Variables

| Name                                  | Default/Required             | Description                                                                                                                                    |
|---------------------------------------|:----------------------------:|------------------------------------------------------------------------------------------------------------------------------------------------|
| `jira_version`                        | :heavy_check_mark:           | Version of JIRA to download and install                                                                                                        |
| `jira_java_home`                      | `/usr/lib/jvm/java-8-oracle` | Home directory of the Java installation to use                                                                                                 |
| `jira_java_opts`                      | `-Xms1024M -Xmx1024M`        | Options to pass to the JVM                                                                                                                     |
| `jira_shutdown_port`                  | `8005`                       | Shutdown port for JIRA's server.xml                                                                                                            |
| `jira_connector_port`                 | `8080`                       | Port to listen on for requests                                                                                                                 |
| `jira_connector_max_threads`          | `150`                        | Maximum threads to Major version number of Java to install use for the connector                                                               |
| `jira_connector_min_spare_threads`    | `25`                         | Minimum amount of spare theads for the connector                                                                                               |
| `jira_connector_connection_timeout`   | `20000`                      | Timeout to wait for requests                                                                                                                   |
| `jira_connector_max_http_header_size` | `8192`                       | Maximum header size for requests                                                                                                               |
| `jira_connector_accept_count`         | `100`                        | Maximum concurrent `accept` syscalls for listening                                                                                             |
| `jira_proxy_name`                     | ` `                          | Name of the proxy to run JIRA behind. This role assumes you use a proxy which offers JIRA with TLS. Unencrypted connections are not supported. |

## Example Playbook

```yml
- hosts: jira
  roles:
  - jira
    jira_version: 7.6.1
    jira_proxy_name: tickets.example.com
```

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/).

## Author Information

- [Janne Heß](https://github.com/dasJ)
