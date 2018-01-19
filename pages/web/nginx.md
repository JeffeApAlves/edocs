---
title: Nginx
tags: [getting_started, troubleshooting]
keywords: nginx
summary:
sidebar: web_sidebar
hide_sidebar: false
toc: true
permalink: nginx.html
folder: web
---

## Preparação do repositório de arquivos estáticos

1. Coletar do projeto os arquivos estáticos para que o nginx possa servi-los

    ```shell
    $ cd <SITE_HOME>
    $ python manage.py collectstatic
    ```

2. Na existencia copiar os demais arquivos estáticos para o mesmo repositório

    ```shell
    $ cp -r <SITE_HOME>/personal/static/* <STATIC_DIR>
    ```

## Instalação do nginx

1. Instalar o pacote nginx

    ```shell
    $ sudo aptitude install nginx
    ```

## Configuração nginx

1. Criar um arquivo de configuração para a aplicação

     ```shell
     $ sudo nano /etc/nginx/sites-available/<app.conf>
     ```

2. Configurar o path dos arquivos estáticos 

3. Habilitar o site colocando um link simbólico do arquivo de configuração em sites-enable.

    ```shell
    $ cd  /etc/nginx/sites-enable
    $ ln -s /etc/nginx/sites-available/<app.conf> <app_name> 
    ```

## Informações adicionais

Arquivo do serviço do nginx

```shell
$ sudo nano /lib/systemd/system/nginx.service
```


## Link úteis

[Configurando ambiente de produção](http://tutos.readthedocs.io/en/latest/source/ndg.html)

[Configurando ambiente de produção](http://pythonclub.com.br/configurando-um-servidor-de-producao-para-aplicacoes-python.html) 

[Configurando ambiente de produção](http://docs.gunicorn.org/en/latest/run.html)

[Configurando ambiente de produção](https://www.youtube.com/watch?v=G1U6rQa8x1s)

[Configurando ambiente de produção](http://uwsgi-docs.readthedocs.io/en/latest/Nginx.html)

[Configurando ambiente de produção](http://michal.karzynski.pl/blog/2013/06/09/django-nginx-gunicorn-virtualenv-supervisor/) 

{% include links.html %}
