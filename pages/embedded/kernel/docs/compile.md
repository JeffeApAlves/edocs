---
title: Kernel compile
keywords: embarcado kernel compile
sidebar: embedded_sidebar
toc: true
permalink: kernel_compile.html
folder: embedded
---

## Configurar/verificar ambiente de desenvolvimento

1. Editar o arquivo “~/.bashrc” ativando a PATH do toolchain conforme a figura abaixo. Adicionar as variáveis de ambiente que será utilizado na compilação do

[path do toolchain][path_toolchain]

## Código fonte

1. Fazer o clone do código fonte do kernel em uma workspace local. Para isso utilizar o comando no local onde se deseja fazer a clonagem.

    ```shell 
    git clone --depth=1 https://github.com/raspberrypi/linux
    ```

[Clonagem código fonte][clone_sourcecode]


Periodicamente usar o comando abaixo, para manter o código atualizado com o repositório.

    ```shell 
    git pull
    ```

## Configuração da compilação

1. Entrar no diretório onde foi feita a clonagem

    ```shell 
    cd <diretorio_clone>
    ```

2. Definir a configuração inicial para Raspberry PI 0W

    ```shell
    make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf-bcmrpi_defconfig
    ```

[Configuração][config]

### Menu configuração

Quando necessário utilizar o comando make menuconfig para ter acesso as configurações e alterá-las conforme a necessidade.

[Menu de configuração][menuconfig]

## Compilação

1. Para compilar usar o comando abaixo

    ```shell
    make -j8 zImage modules dtbs 2>&1 | tee build.log
    ```

O comando tee irá criar um arquivo com a saída da compilação e mostrar na tela simultaneamente.

[Inicio compilação][start_compile]


Fim compilação

[Fim compilação][end_compile]

## Preparação do SD-Card

1. Iremos atualizar apenas o Kernel e os módulos. Por isso iremos utilizar uma imagem de uma versão anterior para copiar os demais.

    ```shell
    unzip -p 2017-11-29-raspbian-stretch.zip | sudo dd of=/dev/sdX bs=4M conv=fsync
    ```

2. Executando o commando lsblk é possível verificar as partições boot e rootfs


    ```shell
    lsblk
    ```
[resultado lsbk][lsbk_result]

## Verificando original

Realizando o boot com essa instalação temos a seguinte versão do Kernel original

Versão 4.9.59 Data Sun Oct 29 2017 11:47:10

Verificando a data do arquivo original

[file explorer original][file_explorer_original]

Prompt da versão original do kernel

    ```shell
    uname -a
    ```

[result original][result_original]


## Instalação do Kernel compilado

1. Para facilitar o trabalho montamos as partições nos seguintes diretórios

    ```shell
    mkdir mnt
    mkdir mnt/fat32
    mkdir mnt/ext4
    sudo mount /dev/sdb1 mnt/fat32
    sudo mount /dev/sdb2 mnt/ext4
    ```

2. Realizamos a instalação dos módulos com o seguinte comando


    ```shell
    sudo make ARCH=arm NSTALL_MOD_PATH=mnt/ext4 modules_install
    ```

Instalando os módulos

[instação dos modulos][install_modules]

3. Para instala o Kernel realizar a cópia de alguns arquivos seguindo a sequência abaixo. O comando da primeira linha faz um backup do kernel original.

   ```shell
   sudo cp mnt/fat32/$KERNEL.img mnt/fat32/$KERNEL-backup.img
   sudo cp arch/arm/boot/zImage mnt/fat32/$KERNEL.img
   sudo cp arch/arm/boot/dts/*.dtb mnt/fat32/
   sudo cp arch/arm/boot/dts/overlays/*.dtb* mnt/fat32/overlays/
   sudo cp arch/arm/boot/dts/overlays/README mnt/fat32/overlays/
   ```

[Copia dos arquivos][copy_files]

## Verificando compilado

Verificando a data do arquivo compilado

[file explorer original][file_explorer_compilado]

Prompt da versão original do kernel

    ```shell
    uname -a
    ```

[result original][result_compilado]


[path_toolchain]: bashrc.png
[clone_sourcecode]: clone_kernel.png
[config]: config.png
[menuconfig]: menu_config.png
[start_compile]: start_compile.png
[end_compile]: end_compile.png
[lsbk_result]: lsbk.png
[file_explorer_original]: file_explorer_original.png
[result_original]: result_original.png
[install_modules]: install_modules.png
[copy_files]: copy_files.png
[file_explorer_compilado]: file_explorer_compile.png
[result_compilado]: result_compile.png