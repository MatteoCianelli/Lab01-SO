# Informe Post-Laboratorio: Introducción a Git y GitHub


## 1. Introducción:

### ¿Qué es Git y GitHub?

Git es un sistema de control de versiones distribuido que permite rastrear cambios en archivos y coordinar el trabajo entre múltiples usuarios. Funciona de manera local en cada computadora, creando un historial completo de todos los cambios realizados en un proyecto.

GitHub es una plataforma web que aloja repositorios Git remotos, facilitando la colaboración entre desarrolladores, el seguimiento de problemas, y la implementación de flujos de trabajo profesionales como pull requests y code reviews.

### Objetivo del Laboratorio

El objetivo de este laboratorio es aprender o recordar los conceptos básicos y los comando principales para utilizar Git y GitHub.
- Inicialización de repositorios locales
- Gestión de cambios
- Trabajo con branches
- Integración de repositorios remoto en GitHub

## 2. Desarrollo

- Se creó una carpeta para el laboratorio y se inicializó un repositorio de Git con el comando:
```bash
  git init
  ```

**Descripción:** Este comando inicializa un repositorio Git local, genera un archivo `.git` que contiene la información necesaria.

![alt text](<Captura de pantalla 2026-03-17 191000-1.png>)

- Se creó un archivo `README.md` con el siguiente contenido:
```bash
# Laboratorio de Git y GitHub
Este es un repositorio de prueba para el laboratorio de Sistemas Operativos.
```

- Se prepararon los cambios para el commit:
```bash
git add README.md
```

**Descripción:** El comando `git add` prepara los cambios para hacer un commit. Los archivos se mueven al "staging area".

- Se hace el commit:
```bash
git commit -m "Primer commit: agregado README.md"
```

**Descripción:** El comando `git commit` registra permanentemente los cambios en el repositorio. Con el pámetro `-m` se agrega un mensaje descriptivo al commit. 

![alt text](<Captura de pantalla 2026-03-17 191209.png>)

- Se usa el siguiente comando para ver el historial de commits:
```bash
git log
```

**Descripción:** El comando `git log` muestra el historial de commits realizados.

![alt text](<Captura de pantalla 2026-03-17 191225.png>)

- Se crea una rama con el nombre `develop`:

```bash
git branch develop
```

**Descripción:** El comando `git branch` crea una rama (branch) con el nombre ingresado, tomando como base el último commit. Esto permite trabajar de forma ordenada individualmente o en equipo y mantener los cambios aislado por seguridad.

- Se cambia a la rama `develop`:

```bash
git checkout develop
```

**Descripción:** El comando `git checkout` cambia el area de trabajo a una rama diferente.

![alt text](<Captura de pantalla 2026-03-17 191314.png>)

- Se modificó el archivo `README.md`:

```bash
# Laboratorio de Git y GitHub
Este es un repositorio de prueba para el laboratorio de Sistemas Operativos.
Estos son los cambios de develop.
```

- Luego se confirman los cambios:

```bash
git add README.md
git commit -m "Agregada descripción en develop"
```

![alt text](<Captura de pantalla 2026-03-17 191445.png>)

- Se vuelve a la branch "master" (rama principal) y se llevan los cambios:

```bash
git checkout master
git merge develop
```

**Descripción:** `git checkout main` cambia de vuelta al branch principal. `git merge develop` integra los cambios de la branch "develop" en la branch "master".

![alt text](<Captura de pantalla 2026-03-17 191539.png>)

- Se creó un repositorio en GitHub.

![alt text](<Captura de pantalla 2026-03-17 191539-1.png>)

- Se agrega el repositorio remoto con el siguiente comando:

```bash
git remote add origin <URL_del_repositorio>
```

**Descripción:** Este comnado vincula el repositorio local con un repositorio remoto. "origin" es el nombre por defecto del repositorio remoto.

![alt text](<Captura de pantalla 2026-03-17 191821.png>)

- Por último se suben los cambios al repositorio remoto con el siguinte comando:

```bash
git push -u origin master
```

**Descripción:** El comando `git push` manda los commits locales al repositorio remoto. El parámetro `.u` establece la rama remota como la rama de seguimiento predeterminada.

![alt text](<Captura de pantalla 2026-03-17 191921.png>)

## 3. Conclusiones

### Aprendizajes Principales:
Ya tenía una base de conocimento sobre el uso de Git y GitHub gracias a PII, pero me sirvió bastante para recordar algunos comandos que no utilizaba hace mucho. Algo que nunca había hecho y aprendí en este laboratorio fue a crear primero el repositorio local y luego vincularlo con un repositorio remoto.

### Dificultades Encontradas y Soluciones:
Tube un único problema que surgió al usar Git y VisualStudioCode. El problema fue que al cambiar de de "develop" a "master" luego de hacer el commit, los cambios se mantenian sin hacer el merge. Busqué y logré solucionarlo, lo único que tenia que hacer es guardar los archivos antes de hacer el comit.