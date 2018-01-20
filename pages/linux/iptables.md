---
title: iptables
tags: [firewall]
keywords: [firewall]
summary:
toc: true
sidebar: linux_sidebar
hide_sidebar: false
permalink: iptables.html
folder: linux
---

## Regras para o access point

```shell
$ sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
$ sudo iptables -A FORWARD -i eth0 -o wlan0 -m state --state RELATED,ESTABLISHED -j ACCEPT
$ sudo iptables -A FORWARD -i wlan0 -o eth0 -j ACCEPT
```

## Regras para o postgres

```shell
$ sudo iptables -A INPUT -p tcp -s 0/0 --sport 1024:65535 -d 192.168.42.1  --dport 5432 -m state --state NEW,ESTABLISHED -j ACCEPT
$ sudo iptables -A OUTPUT -p tcp -s 192.168.42.1 --sport 5432 -d 0/0 --dport 1024:65535 -m state --state ESTABLISHED -j ACCEPT
```

## Verificando

```shell
$ sudo iptables -t nat -S
$ sudo iptables -S
```

## Salvando 

```shell
$ sudo sh -c "iptables-save > /etc/iptables.ipv4.nat"
```

## Configuração da interface

1. Editar o arquivo interfaces

    ```shell
    $ sudo ifdown wlan0
    $ sudo cp /etc/network/interfaces /etc/network/interfaces.backup
    $ sudo nano /etc/network/interfaces
    ```

2. Adiconar a linha abaixo no final do arquivo

    ```
    up iptables-restore < /etc/iptables.ipv4.nat
    ```

{% include links.html %}
