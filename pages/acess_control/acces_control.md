---
title: Access Controls
tags: [getting_started, troubleshooting]
keywords:
summary:
toc: true
sidebar: access_controls_sidebar
permalink: access_control.html
folder: access_control
---

## LDAP

Autenticação e politica de acesso

### Identificação/autorização

```shell
$ sudo nano /etc/phpldapadmin/config.php
```

editar o arquivo

```shell
$ sudo nano /etc/apache2/apache2.conf
```

colocando no final 'Include /etc/phpmyadmin/apache.conf'

### Usuário/grupo da aplicação

```shell
$ sudo groupadd --system webapps
$ sudo useradd --system --gid webapps --shell /bin/bash gtracker
$ sudo usermod -a -G users gtracker
$ sudo chown -R gtracker:users /var/www/gtracker/
$ sudo chmod -R g+w /var/www/gtracker
```

{% include links.html %}
