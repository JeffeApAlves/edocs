---
title: Linux
keywords: [service, supervisor, runworker]
summary: "Inicializando toda aplicação django através do Supervisor."
sidebar: linux_sidebar
tags: [django, supervisor]
toc: true
permalink: linux_service.html
folder: linux
---

## Instalação do Supervisor

1. Instalar os pacotes abaixo

   ```shell
   $ sudo apt-get install supervisor
   ```

2. Utilitário para visualizar os nomes dos serviçõs

   ```shell
   $ sudo aptitude install python-dev
   $ pip install setproctitle
   ```


## Configuração 

1. Editar arquivo 

    ```shell
    $ nano /etc/supervisor/supervisord.conf
    ```

2. Adicionar o caminho do diretorio que possui os conf's e scripts de inicialização 

    ```shell
    files = /etc/supervisor/conf.d/*.conf  <caminho do diretorio startup>/*.conf
    ```

## Arquivos *.conf
  
1. Criar os arquivos conf no diretório que foi configurado no item anterior e indicar o script de inicialização

   ```
   [program:daphne]
   command=<path/script_de_inicializacao_do_daphne.sh>
   user=<webuser>
   stdout_logfile=<path/log_file>
   redirect_stderr=true
   autostart=true
   autorestart=true
   ```
   ```
   [program:<app_django>]
   command=<path/script_de_inicialização_do_app.sh>
   user=<webuser>
   stdout_logfile=<path/log_file>
   redirect_stderr=true
   autostart=true
   autorestart=true
   ```
   ```
   [program:<app_django>-runworker]
   command=<path/script_de_inicialização_do_runworker.sh>
   directory=<WEB_HOME>
   numprocs=4
   process_name=%(program_name)s_%(process_num)02d
   user=<webuser>
   stdout_logfile=<path/log_file>
   redirect_stderr=true
   autostart=true
   autorestart=true
   ```

2. Verificar os scripts e re-start com as novas configurações

   ```shell
   $ sudo supervisorctl reread
   $ sudo supervisorctl update
  ```


## Gerenciamento de serviços

### Comandos básicos

```shell
$ sudo supervisorctl COMMAND <nome_do_processo>
```
Commands:

status | stop | start | restart

ou

```shell
$ sudo service <serviço> COMMAND
```
Command:

status | start | stop | restart

Exemplo:

```shell
$ sudo service postgresql status
```
### Lista serviços

```shell
$ ps axf
```
### Recarregar o servicos
```shell
$ sudo systemctl daemon-reload
```

Referências:

[Inicializando serviços](http://www.bosontreinamentos.com.br/linux/16-inicializacao-init-runlevels-init-d-inittab-e-telinit-linux/)

{% include links.html %}
