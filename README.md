# ansible-elasticsearch
Ansible role for manage 6.x Elasticsearch

## Features
 - Only one instance is supported
 - Simplier than [official Elastic Ansible role for Elasticsearch](https://github.com/elastic/ansible-elasticsearch)
 - Should be as similar as instalation via package manager (allows updates via package manager)

## Role variables
```
es_config               Values which will be passed to elasticsearch.yml; Default: {cluster.name: my-application, path.data: /var/lib/elasticsearch, path.logs: /var/log/elasticsearch}
es_jvm_options          Values which will be passed to jvm.options; Default: {-Xms1g, -Xmx1g}
es_templates_fileblob   Files used as Elasticsearch templates, if empty no templates will be added; Default: ""
```
## Tested environment
 - CentOS 7
 
## TODO
 - Check that needed variables are set and valid
 - Create path.data and path.logs folders
 - Set correct permissions to path.data and path.logs folders
 
