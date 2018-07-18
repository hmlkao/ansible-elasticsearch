# ansible-elasticsearch
Ansible role for manage Elasticsearch

## Description
Only one instance is supported.

## Role variables
```
es_config               Values which will be passed to elasticsearch.yml; Default: {cluster.name: my-application}
es_jvm_options          Values which will be passed to jvm.options; Default: {es_heap_size: 1g}
es_templates_fileglob   Files used as Elasticsearch templates, if empty no templates will be added; Default: ""
```
