---
title: Bootloader
tags: [linux, Embedded_system]
keywords: embarcado bootloader
sidebar: embedded_sidebar
toc: true
permalink: bootloaders_compare.html
folder: embedded
---

## Bottloader

A escolha de um bootloader deve ser feita baseada em requisitos técnicos
do sistema onde será utilizado.
No Quadro abaixo desse [link](https://en.wikipedia.org/wiki/Comparison_of_boot_loaders#Notes), estão listados bootloaders e algumas das suas
principais características.
Dentre as opções de bootloader para plataforma ARM e fazendo uma
análise generalista( sem nenhum requisito especifico) e considerando apenas essas
informações o Das U-Boot apresenta uma vantagem. Em sua lista de
sistemas operacionais suportados existe a presença de até RTOS como é o
caso do Artos, mas não tem suporte ao Windows. Caso isso seja um
requisito do sistema, em desenvolvimento, a solução poderia ser feita
através do grub2. Possui um número bem satisfatório de sistemas de
arquivos e arquiteturas, isso ajuda no caso da necessidade de migração de
plataformas. Por ter um foco em sistemas embarcados, uma outra
característica do Das U-boot é não ter suporte ao UEFI

Referências:

[Comparação](https://en.wikipedia.org/wiki/Comparison_of_boot_loaders#Notes)

[UEFI](https://elinux.org/images/6/69/Marrying_U-Boot,_UEFI_and_grub.pdf)

[Redboot and u-boot](http://rts.lab.asu.edu/web_438/project_final/Talk%2010%20Redboot.pdf)
