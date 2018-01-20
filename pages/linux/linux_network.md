---
title: Linux
keywords: [rede, port, nmap]
summary: "Comandos relacionados a rede"
sidebar: linux_sidebar
permalink: linux_network.html
folder: linux
toc: true
---


### Mapeamento dos hosts

É possível o mapemanento dos hosts, localmente, editando o arquivo 

```shell
$ nano /etc/hosts
```

### Verificação das portas 

Para vericar quais portas estão abertas e escutando

```shell
$ netstat -atp tcp | grep -i "listen"`
```


### Listar quais processos estão utilizando uma determinada porta e protocolo

```shell
$ sudo fuser 80/tcp
```


### Listar quais portas estão abertas para um determindao IP

```shell
$ sudo nmap <IP>
```

```shell
$ ss -tnlp 
```

{% include links.html %}
