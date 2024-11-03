---
title: Configuración inicial
date: 2024-11-02 20:22:0 -0500
categories: [GIT]
tags: [git]
---

Esto hace que los commits se asocien con un usuario y esta pueda aparecer en plataformas como GitHub.

```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

## Comprobar la configuración inicial de Git

Este comando lo puedes usar antes de los comandos anteriores, esto te permite visualizar cuál es la configuración que tiene Git.

```
git config --list
```

## Alcance de las configuraciones

Existen 3 opciones que puedes utilizar al momento de realizar la configuración inicial, lo cual permite establecer valores que afectarán el comportamiento de Git en distintos niveles:

1. `--global` : Esta opción almacena la configuración en un archivo de configuración global del usuario, la cual se encuentra en `.gitconfig`. Esta configuración se aplican a todos los repositorios de la cuenta de usuario actual, por lo cual, se mantiene en todos los proyectos.

2. `--local` : Esta opción almacena la configuración en `.git/config`, la cual se encuentra dentro del repositorio. Esta configuración solo se aplica al repositorio en el que se está trabajando, ignorando las configuraciones globales; esto es útil si se desea que el usuario o email sean diferentes para un proyecto en particular.

    ```
    git config --local user.name "Otro Nombre"
    git config --local user.email "otro_email@example.com"
    ``` 

3. `--system` : Esta opción es de mayor alcance y afecta a todos los usuarios del sistema. Generalmente se encuentra en /etc/gitconfig para sistemas UNIX o en algún directorio específico de Windows. Generalmente se necesitan permisos de administrador.

    ```
    sudo git config --system core.editor "vim"
    ```

Entonces si queremos mostrar nuestra configuración:

- Mostrar la configuración global: 
  `git config --global --list`
- Mostrar la configuración local (si existe):
  `git config --local --list`
- Mostrar la configuración del sistema (si existe):
  `git config --system --list`
