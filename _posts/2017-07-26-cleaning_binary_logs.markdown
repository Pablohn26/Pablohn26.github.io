---
layout: post
tags: [ til, mysql,mariadb, spanish ]
title: Limpiando logs binarios de MySQL
---

{% capture column_left %}

El log binario es un log que utiliza la sincronización de MySQL/MariaDB para guardar los cambios que hay tanto en la estructura de la base de datos como en los datos de la misma.

La idea es que mediante ese log los diferentes componentes de la sincronización se ponen de acuerdo en los cambios que hay. Hay mucha más información en este enlace: https://mariadb.com/kb/en/mariadb/binary-log/ .

{% endcapture %}



{% capture column_right %}

<div class="thumbnail centered-text" markdown="1">

![MySQL](https://upload.wikimedia.org/wikipedia/commons/thumb/0/06/Mysql-dolphin-square.svg/2000px-Mysql-dolphin-square.svg.png)

<p>

[MySQL logo]

</p>

</div>

{% endcapture %}

{% include two_columns.html %}

<!-- more -->

#### Cómo limpiar los logs binarios.

El log binario se va guardando indefinidamente cuando la variable _expire_logs_days_ no está definida. El problema es que con el paso del tiempo estos logs van ocupando un espacio que es casi inútil debido a que en el momento en el que rotan estos logs no van a ser utilizados (salvo en caso de desastre).

En [esta magnífica](https://dba.stackexchange.com/a/41054/131416) entrada de StackOverflow se explica cómo utilizar el comando [PURGE BINARY LOGS](https://mariadb.com/kb/en/mariadb/sql-commands-purge-logs/)

Yo lo que he utilizado ha sido 

> PURGE BINARY LOGS TO `mysql-bin.000223`;

Previamente había listado todos los logs binarios que había (están en la carpeta raíz de MySQL/MariaDB). He borrado todos los logs de años anteriores (había desde 2012), pero lo más importante es que no borres el log binario que se está utilizando **actualmente** (para saber cuál se está utilizando hay que utilizar el comando *SHOW MASTER STATUS*)
