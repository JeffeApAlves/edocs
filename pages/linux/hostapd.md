---
title: Hostapd
tags: [getting_started, troubleshooting]
keywords:
summary:
toc: true
hide_sidebar: true
permalink: hostapd.html
folder: linux
---

## Instalação

1. Instalar os pacotes

    ```shell
    $ sudo apt-get update
    $ sudo apt-get install hostapd isc-dhcp-server
    ```

## Configuração do DHCP

1. Fazer o backup do arquivo dhcp.conf


     ```shell
     $ sudo cp /etc/dhcp/dhcpd.conf /etc/dhcp/dhcpd.conf.default
     ```

2. Editar o arquivo dhcp.conf

     ```shell
     $ sudo nano /etc/dhcp/dhcpd.conf
     ```

3. No arquivo comente as linhas conforme indicado abaixo

     ```
     #option domain-name "example.org";
     #option domain-name-servers ns1.example.org, ns2.example.org;
     ```

3. No arquivo retire o coment´ario da linha, conforme indicado abaixo

    ```
    authoritative;
    ```

4. No fim do arquivo adicione as linhas abaixo

    ```
    subnet 192.168.42.0 netmask 255.255.255.0 {
         range 192.168.42.10 192.168.42.50;
         option broadcast-address 192.168.42.255;
         option routers 192.168.42.1;
         default-lease-time 600;
         max-lease-time 7200;
         option domain-name "local";
         option domain-name-servers 8.8.8.8, 8.8.4.4;
    }
    ```

5. Edite o arquivo abaixo

    ```shell
    sudo nano /etc/default/isc-dhcp-server
    ```

6. Adicione ou edite a linha conforme indicado

    ```shell
    INTERFACES="wlan0"
    ```

## Configuração da interface

1. Editar o arquivo interfaces

    ```shell
    sudo ifdown wlan0
    sudo cp /etc/network/interfaces /etc/network/interfaces.backup
    sudo nano /etc/network/interfaces
    ```

2. Conteúdo do arquivo

    ```
    auto lo
    iface lo inet loopback

    auto eth0
    iface eth0 inet dhcp

    allow-hotplug usb0
    iface usb0 inet dhcp

    auto wlan0
    iface wlan0 inet static
    address 192.168.42.1
    netmask 255.255.255.0
    network 192.168.42.0

    ```

## Configuração Hostapd

1. Copiar o conteudo abaixo para o arquivo indicado.


    ```shell
    $ sudo nano /etc/hostapd/hostapd.conf
    ```

2. Conteúdo do arquivo

    ```
    interface=wlan0
    driver=nl80211
    ssid=WiPi
    hw_mode=g
    channel=7
    wmm_enabled=0
    macaddr_acl=0
    auth_algs=1
    ignore_broadcast_ssid=0
    wpa=2
    wpa_passphrase=xyz301081
    wpa_key_mgmt=WPA-PSK
    wpa_pairwise=TKIP
    rsn_pairwise=CCMP
    ```

## Configuração sys

1. Configurar para 1 a propriedade *_net.ipv4.ip_forward*


    ```shell
    $ sudo nano /etc/sysctl.conf
    net.ipv4.ip_forward=1
    ```
ou        
    ```shell
    $ sudo sh -c "echo 1 > /proc/sys/net/ipv4/ip_forward"
    ```

## Configuração firewall

1. Realizar a configuração do firewall conforme este [procedimento][iptables]

{% include links.html %}
