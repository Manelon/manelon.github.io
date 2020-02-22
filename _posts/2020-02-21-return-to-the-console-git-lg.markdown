---
layout: post
title:  "Back to the console... git lg "
date:   2020-02-21 23:47:41 +0000
categories: git
tags: [git, nocompila]
---
Una cosa que hecho en falta cada vez que instalo git en una máquina nueva es ver las ramas de los proyectos de una manera cómoda y entendible.  
Por defecto si sobre un repositoio le haces git log verás una cosa como esta
``` shell
$ git log
commit a699088fa10ade490fcba3df377e0a400dd36978 (HEAD -> master, origin/master)
Merge: 8ccc924 bf28f20
Author: Manel <usuario@correo.com>
Date:   Thu Feb 20 23:50:57 2020 +0000

    Merge pull request #1 from Manelon/develop
    
    First post

commit bf28f204ef3dc7199fee927f4ccd4f3548f5b62c (origin/develop, develop)
Author: Manel <usuario@correo.com>
Date:   Thu Feb 20 23:47:50 2020 +0000

    First post

commit 8ccc924f4b49096c9cdbfa383853bb3ca541a5c2
Author: Manel <usuario@correo.com>
Date:   Wed Feb 19 23:55:09 2020 +0000

    Set theme jekyll-theme-hacker

commit cd413d42fbd2315dbaa20174cff1cb71fef840f0
Author: Manel <usuario@correo.com>
Date:   Wed Feb 19 23:50:27 2020 +0000

    WIP
```
Pero la salida del comando log por defecto es... poco práctica..., vamos que se puede mejorar.  
En vez de escapar a un cliente gráfico, se puede ver me una manera mucho mejor por la consola. Por ejemplo:
``` shell
$ git lg
*   a699088 - (23 hours ago) Merge pull request #1 from Manelon/develop- Manel (HEAD -> master, origin/master)
|\  
| * bf28f20 - (23 hours ago) First post- Manel (origin/develop, develop)
|/  
* 8ccc924 - (2 days ago) Set theme jekyll-theme-hacker- Manel
* cd413d4 - (2 days ago) WIP- Manel
```

Esta opción es más compacta, informativa y además se ve claramente las ramas. Aunque git lg no está disponible por defecto, puedes añadirlo facilmente a tu consola.  
Hay un montón de post en internet donde te explican como hacer esto. Yo uso la respuesta de [Slipp Thompson](https://stackoverflow.com/users/177525/slipp-d-thompson) en [stack overflow](https://stackoverflow.com/a/34467298/1003288) y que se recojen en este [post](https://www.jacobtomlinson.co.uk/quick%20tip/2016/01/18/pretty-git-logs-with-git-lg/).

Lo único que tienes que hacer es añadir estos alias fichero .gitconfig que encontrarás en tu home
``` shell	
[alias]
    lg = !"git lg1"
    lg1 = !"git lg1-specific --all"
    lg2 = !"git lg2-specific --all"
    lg3 = !"git lg3-specific --all"
 
    lg1-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)'
    lg2-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n''          %C(white)%s%C(reset) %C(dim white)- %an%C(reset)'
    lg3-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset) %C(bold cyan)(committed: %cD)%C(reset) %C(bold yellow)%d%C(reset)%n''          %C(white)%s%C(reset)%n''          %C(dim white)- %an <%ae> %C(reset) %C(dim white)(committer: %cn <%ce>)%C(reset)'
```
Con esto tendrás tres git lgs, cada uno con más detallado que el anterior, aunque usarás git lg que por defecto apunta al menos verboso.   Muy recomendable que lo tengas en tu configuración. 


Por cierto, este post lo publiqué originalmente en [nocompila.com](https://www.nocompila.com/2020/02/back-to-console-git-lg.html) pero creo que puede ser interesante tenerlo aquí también.