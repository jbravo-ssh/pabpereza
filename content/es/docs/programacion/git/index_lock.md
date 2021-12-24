
---
title: "Index lock"
linkTitle: "Index lock"
weight: 5
tags: [git, errores]
description: >
   Error index lock 
---

Git tiene un sistema de funcionamiento muy estricto para evitar conflictos y ayudarnos a mantener nuestro bien versionado.
Para ello, solo a un proceso realziar cambios a la vez para mantener la integridad de la informaci�n.

Cuando realizamos cualquier tarea en git, un commit, push, pull... este genera un archivo llamado "index.lock" y lo guarda
dentro de la carpeta ".git" en la raiz del repositorio.

Este archivo bloquea el repositorio ante cualquier otro acceso o proceso simult�neo que quiera realizar cambios. En algunos casos,
poco frecuentes, puede pasar que una acci�n o tarea nunca termine ( por fallo del SO u otros) y el repositorio se quede bloqueado.

Si tenemos claro lo que estamos haciendo, podr�amos borrar simplemente este archivo con el comando:
``` bash
rm .git/index.lock
```

As� de simple conseguir�amos quitar el bloqueo de git pero *atenci�n* que no tengamos otro proceso ejecutando alguna tarea sobre git
o podr�amos corromper datos del repositorio.
