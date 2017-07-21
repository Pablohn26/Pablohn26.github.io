---
layout: post
tags: [ til, website, spanish ]
title: Cómo he creado este sitio 
---

{% capture column_left %}

Inauguro este espacio explicando cómo se ha creado. Quiero que este espacio sea un lugar para guardar mis notas personales relacionadas con la informática a modo de referencia personal compartida con el resto de la humanidad.

Agradezco a toda la comunidad del software libre, Github y Jekkyl en general y en especial a [Anton Khodakivskiy](https://www.linkedin.com/in/akhodakivskiy/) (por la base) y "a la Mari" (por enseñarme la base y el cómo hacerlo).

Veamos cómo se ha montado esta web

{% endcapture %}



{% capture column_right %}

<div class="thumbnail centered-text" markdown="1">

![Jekyll and Github pages](https://upload.wikimedia.org/wikipedia/commons/4/42/Jekyll_%28software%29_Logo.png)

<p>

[Jekkyl and Github Pages]

</p>

</div>

{% endcapture %}

{% include two_columns.html %}

<!-- more -->

#### ¿Pero esto qué eeeees?

Esto es lo más de lo más. Había un mundo en el que si te querías hacer una web sin conocimientos "informáticos", con Wordpress te podías crear un web de manera muy sencilla ya que la interfaz es amigable. A raíz del auge de Wordpress, se crearon miles de blogs que luego más que blogs eran páginas webs por completo (ya que la plataforma evolucionó también en esa orientación). El resultado fue miles de programadores creando temas (que más que temas eran frameworks web) y millones de usuarios consumiendo esos temas (gratuitos y no gratuitos) y creando webs bastante decentes.

Pero resulta que un día alguien (en realidad varios) pensaron ¿tánto para casi nada?. Muchas personas entendidas veían que para crear una web con 4 secciones, 3 subpáginas y 2 sliders de imágenes no se necesitaba una plataforma tan grande como lo que es Wordpress ahora. Esas personas viajaron en una máquina del tiempo al año 1993 y al volver de viaje se pusieron a facilitar la creación de páginas webs estáticas. Wordpress es una plataforma de páginas web dinámicas. Se llaman dinámicas porque tienen una base de datos en la que se guardan datos y en base a esos datos se genera "al vuelo" (de eso se encarga PHP) un html, que es lo que finalmente se muestra en el navegador. Una página web estática sin embargo no tiene base de datos y no cambia a no ser que se cambie el código. Ventajas de las estáticas: seguridad (no hay base de datos), rendimiento (no hay que generar la web). Desventajas de las estáticas: al no haber base de datos no hay "usuario", todos ven la web de la misma manera. Es decir las páginas estáticas son para webs que cambian poco mientras que las dinámicas están preparadas para que cambien o cada poco o cada vez que quieras filtrar o mostrar ne base a ciertos datos. Si asumes o no necesitas las desventajas de las dinámicas, las estáticas son la auténtica salud.

Esos mismos viajeros del tiempo desarrollaron entonces un generador (un software) para generar páginas web en html cuyo contenido en texto está escrito en Markdown (un lenguaje de marcas creado por [John Gruber](https://daringfireball.net/projects/markdown/) y un tal [Aaron Swartz](https://www.youtube.com/watch?v=mT8FJcIx3HI) ). Ese software se llama [Jekyll](https://jekyllrb.com/) y tiene muy buena pinta. Pero es que además estos viajeros del tiempo son super buenas personas y como hostear una web estática cuesta 1 céntimo mientras que una dinámica cuesta 1 euro, pues han creado otra cosa que se llama [Github Pages](https://pages.github.com/), que es como el sistema, el hosting. Es decir, estos viajerons del tiempo super buenas personas te dan las facilidades para crear una web y además te dan el hosting gratis. ¡Vivan los viajeros del tiempo super buenas personas!

Después de este royo, ya sabes un resumen de qué es esto y cómo hemos llegado aquí. Hasta aquí el pasado, ahora hay que mejorar el futuro. Por eso te voy a contar cómo crear algo parecido a esto. Contaré simplemente la base para esta web pero modificable para ti. Si quieres cambiar luego algo ya te buscas la vida o contratas a un profesional. 

#### ¿Qué necesito?

- Una cuenta en [Github](https://github.com/join). Si no sabes de qué va esto, aquí tienes un pequeño manual sobre [cómo editar en Github](https://docs.google.com/document/d/1RsoBRlH-VZDq61lJ88EEQdqlnGiLUugbIFQPrDf_otY/edit?usp=sharing)

Sí, ya no necesitas nada más (demos gracias de nuevo a los viajeros del tiempo super buenas personas).

#### ¡¡¡¡Al lío!!!!

- Vete al repositorio de Github que es la base de esta web. Es [este](https://github.com/Pablohn26/Pablohn26.github.io)
- Dale a fork (arriba a la derecha). Esto creará una copia del contenido de mi web en tu cuenta personal.
- Una vez dentro de tu repositorio, vete a "Settings" y renombra en "Repository name" el nombre del repositorio a tunombredeusuario.github.io . En mi caso es Pablohn26.github.io , si tu nombre de usuario en Github es pepe123, tendrías que renombrar a pepe123.github.io 
- Comprueba que si entras en tunombredeusuario.github.io ya se ve **TU** página web

¡Y ya está!

#### ¿Ya está? 

Sí y no. Ya hemos solucionado la parte del sistema. Es decir ya hay una web que está mostrando un contenido. El problema es que no es el contenido que tú quieres. A nivel "de configuración" hay muy poco que hacer, como mucho que cambies el archivo \_config.yml y [cambies mis datos por tus datos](https://github.com/Pablohn26/Pablohn26.github.io/commit/86fac96dc63cfe4d05a61d104afcdb7484eb1f31).

Después ya te quedaría toquetear el resto de enlaces e ir poco a poco poniendo tu contenido y tus datos.


#### Añadiendo un dominio personalizado

Esta web la puedes ver tanto en [pablohn26.github.io](https://pablohn26.github.io) como en [til.pablohinojosa.is](http://til.pablohinojosa.is/). Para que la web sea cargada con tu dominio personalizado lo que tienes que hacer es crear un registro DNS de tipo CNAME cuyo contenido sea tunombredeusuario.github.io. En mi caso [pablohn26.github.io](https://www.whatsmydns.net/#CNAME/til.pablohinojosa.is). Una vez creado, tendrías que ir a "Settings", y en el apartado de "GitHub Pages" tendrías que poner tu "Custom domain" y darle a guardar.   


#### Y todavía más

Lo básico ya está hecho. Podrías poner tu dominio personalizado con HTTPS [siguiendo este tutorial](https://hackernoon.com/set-up-ssl-on-github-pages-with-custom-domains-for-free-a576bdf51bc). También podrías cambiar el tema o los colores toqueteando los css, o [cambiar los enlaces](https://github.com/Pablohn26/Pablohn26.github.io/commit/8b6f811f00c7b8995f38302843a8a6f690ba0c5b). 

Pero al menos lo básico ya lo tienes :)

