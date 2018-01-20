---
title: Linux
keywords: [ssh]
summary: "Comandos relativos a conexões utilizando SSH."
sidebar: linux_sidebar
permalink: linux_ssh.html
folder: linux
toc: true
---

### Gerando uma chave

```shell
$ ssh-keygen -t rsa
```

### Copiando a chave para o computador remoto

```shell
$ ssh-copy-id <usuariossh>r@<ip-machine>
```
ou

```shell
$ scp /home/usuário/.ssh/id_rsa.pub <usuariossh>@<ip-machine>:/tmp
$ ssh <usuariossh>@<ip-machine>
$ cat /tmp/id_rsa.pub >> ~/.ssh/authorized_keys2
```

{% include links.html %}


### Conectando a um dispositivo

```shell
$ ssh <usuariossh>@<ip-machine>
```

