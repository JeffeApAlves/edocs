---
title: Linux
keywords: [user, visudo]
summary: "Comandos para gerenciamento de usuários"
sidebar: linux_sidebar
permalink: linux_user.html
folder: linux
toc: true
---


### Criando um usuário

```shell
$ adduser -m <nome_usuario>
```

### Habilitando o sudo para o usuário

Executar o visudo

```shell
$ visudo
```
Adicionar a linha abaixo. **NOPASSWD**  faz com que não seja solicitada a senha

```
<usuario> ALL=NOPASSWD: ALL
```

{% include links.html %}
