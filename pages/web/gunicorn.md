---
title: gunicorn
keywords: gunicorn
sidebar: web_sidebar
toc: true
hide_sidebar: false
permalink: gunicorn.html
folder: web
---

## Instalação

```shell
$ pip install gunicorn
```

## Configuração

1. Criar o script de inicialização executando

```shell
$ sudo nano <path_da_solucão_web>/<_script_app_start>.sh
```

## Informações adicionais

Para Finalizar a aplicação é necessário o pid que foi salvo na execução do processo. Arquivo indicado no script 

```shell
$ kill -HUP sudo kill -HUP `cat <web_django.pid>`
$ uwsgi --stop <web_django.pid>
```

{% include links.html %}
