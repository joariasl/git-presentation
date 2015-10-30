# Apunte de comandos Git
<sup style="float:right;display:block;text-align:right;">[Source Markdown](https://github.com/joariasl/git-presentation/blob/master/apuntes-git.md)</sup>

By [Jorge Arias](www.jorgearias.cl).

## Tabla de contenidos
<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Obtener Ayuda](#obtener-ayuda)
- [Configurar](#configurar)
- [Agregar al Staging Area](#agregar-al-staging-area)
- [Comprobar cambios](#comprobar-cambios)
- [Comparar cambios](#comparar-cambios)
- [Commit](#commit)
- [Log](#log)
- [Ramas](#ramas)
  - [Branch](#branch)
  - [Checkout](#checkout)
  - [Merge](#merge)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Obtener Ayuda
```sh
git <command> --help
```
```sh
git help <command>
```
```sh
man git-<command>
```

## Configurar
```sh
git config --global user.name "John Doe" # Definir nombre global de Git
```
```sh
git config --global user.email johndoe@example.com # Definir email global de Git
```
```sh
git config --list # Listar parámetros de configuración
```
```sh
git config --global core.editor vim # Configurar editor predeterminado
```
```sh
git config --global merge.tool vimdiff # Configurar herramienta para resolver conflictos
```

Nota: Configuración global se guarda en ~/.gitconfig. Si no se define --global la configuración será para el repositorio y se guardará en .git/config.

## Agregar al Staging Area
```sh
git add [file|folder] ...
```
```sh
git add -u [file|folder] ... # Agrega automáticamente archivos con seguimiento
```
```sh
git rm [file|folder] ... # Remover archivos de git y disco
```
```sh
git rm --cached [file|folder] ... # Remover del staging area
```

## Comprobar cambios
```sh
git status
```
```sh
git status -v # Mostrar con detalle de modificaciones
```

## Comparar cambios
```sh
git diff [--cached|--staged] # Preparados contra último commit
```
```sh
git diff <commit1> <commit2> # Entre dos commits
```
```sh
git diff --check # Mostrar espacios agregados que pueden causar problemas. Se recomienda excluir espacios redundantes en líneas.
```

## Commit
```sh
git commit # Agregar commit a la historia
```
```sh
git commit -m 'Message' # Agregar con mensaje directamente
```
```sh
git commit --amend # Agregar commit a la historia
# Equivale a git reset --soft HEAD^ y luego git commit -c ORIG_HEAD
```
```sh
git commit [-a|--all] # Agrega todos los archivos agregados y modificados y luego confirma
```
```sh
git commit [-v|--verbose] # Muetra el diff en el editor
```

Nota: Los commits no se eliminan implícitamente

## Log
```sh
git log # Mostrar historial de commits
```
```sh
git log --stat # Mostrar con detalle de dirferencias de archivos
```
```sh
git log --since=2.weeks # Mostrar commits más recientes hasta indicado
git log --since=12.hours
```
```sh
git log <branch1>..<branch2> # Mostrar cambios introducidos desde <branch1> a <branch2>
```
```sh
git log <branch1> --not <branch2> # Muestra commits de <branch1> excluyendo los que pertenecen a <branch2>
```
```sh
git log --oneline # En una línea hash y subject
```
```sh
git log --decorate # Incluyendo posición de referencias (ramas/tags)
```
```sh
git log --graph # Mostrar representación gráfica de historia
```
```sh
git log --all # Mostrar todos los commits con referencia
```

## Ramas
### Branch
```sh
git branch # Mostrar ramas
```
```sh
git branch -vv # Mostrar ramas con SHA1 y commit subject line
```
```sh
git branch <nombre> # Crear rama con puntero a posición actual
```
```sh
git branch -d <nombre> # Eliminar rama (--delete)
```
```sh
git branch -D <nombre> # Forzar eliminar rama (--delete --force)
```
```sh
git branch --merged # Mostrar ramas fusionadas a la actual. Con * si aún no se incorporan últimos cambios
```
```sh
git branch --no-merged # Mostrar ramas que no han sido incorporadas a la actual
```
### Checkout
```sh
git checkout <rama> # Cambiar a rama
```
```sh
git checkout -b <rama> # Cambiar a rama y crear si no existe
```
### Merge
```sh
git merge <rama> # Fusionar <rama> con posición actual
```
