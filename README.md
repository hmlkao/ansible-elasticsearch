# ansible-elasticsearch
Ansible role for manage 6.x Elasticsearch

## Features
 - Only one instance is supported
 - Simplier than [official Elastic Ansible role for Elasticsearch](https://github.com/elastic/ansible-elasticsearch)
 - Should be as similar as instalation via package manager (allows updates via package manager)

## Tested environment
 - CentOS 7

## Role variables
```
es_config               Values which will be passed to elasticsearch.yml; Default: {path.data: /var/lib/elasticsearch, path.logs: /var/log/elasticsearch}
es_heap_size                    Defines a heap size; Default: 1g
es_templates_fileglob   Files used as Elasticsearch templates; Default: ""
es_update                       Update Logstash to the latest version from repository; Default: false
es_version                      Version of logstash which will be installed, used only if ls_update is false; Default: empty
es_restart_on_change            Service will be restarted when some changes appear; Default: true
java_update                     Update Java to the latest version from repository; Default: false
```

## Templates
If you want to install indices templates, you shouldn't set `es_templates` role variable first time you run the role, it is because templates are installed via API and require running Elasticsearch which will be run after configuration.

## Troubleshooting

### Templates are not installed
This role installs templates only if they were copied to remote host. If some problem during template installation occur (eg. ES is not running yet and installation fails) templates are not installed even if you run role again (because they were already copied).

## TODO
 - Create path.data and path.logs folders (?)
 - Set correct permissions to path.data and path.logs folders (?)
 - Remove templates on remote host if installation fails

