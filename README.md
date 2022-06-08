# Что делает playbook

`Playbook` установит три приложения:
* jdk
* elasticsearch
* kibana

Дистрибутив JDK в `.tar.gz` нужно предварительно [скачать](https://www.oracle.com/ru/java/technologies/javase/jdk11-archive-downloads.html) и поместить в каталог `/files`.

# Какие у него есть параметры 

[group_vars/all:](group_vars/all/vars.yml)
* jdk_distr_type: remote/local
* java_jdk_version - версия Java.
* java_oracle_jdk_package - дистрибутив JDK в каталоге `/files`.
* java_home - директория установки Java.

[group_vars/elasticsearch:](group_vars/elasticsearch/vars.yml)
* elastic_version - версия Elasticsearch и Kibana. 
* elastic_home/kibana_home - директории установки Elasticsearch и Kibana.

# Какие у него есть теги

* java
* elastic
* kibana

# Как запустить

1. Задать хосты [prod.yml](inventory/prod.yml)
1. Можно настроить переменные в [all.yml](group_vars/all/vars.yml) и [elasticsearch.yml](group_vars/elasticsearch/vars.yml).
1. Запустить плейбук
    ```bash
    ansible-inventory -i inventory/prod.yml site.yml
    ```