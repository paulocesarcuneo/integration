# integration
docker-compose git submodule hello world

El objetivo de este repositorio es mostrar como integrar un sistema de aplicaciones dockerizadas,
cada una con su propio repositorio, y ejecutar el sistema usando docker-compose.
Los submodules son el equivalente de symlinks a repositorios, esto nos permite tener un repo por app, 
y al mismo tiempo tener repo con todas las apps.

* https://git-scm.com/book/en/v2/Git-Tools-Submodules
* https://docs.docker.com/compose/

## Init - Clone de repositorios
Al clonarse el repo por primera vez deben ejecutarse init y update de los submodulos.
Esto solo necesario hacerlo una vez.
```

git clone "..." # clona el contenido del padre.
git submodule init # inicializa las carpetas de los submodulo
git submodule update # clona los submodulos de cero

```

Luego de esto cada carpeta submodule actua como un repositorio git aislado, es decir, con su propia historia, branches, commit, etc. 
Por lo cual cuando se pushea dentro de un submodulo, unicamente se esta pushean a ese submodulo.

## Pull/Fetch de repositorios
Se puede hacer pull desde el mismo submodulo, o masivamente.

```

git submodule foreach git pull # hace git pull para cada.
cd <submodule>
git pull # hace pull dentro del modulo

```
## Ejecutar localmente con Docker 🚀
Ejecutar el siguiente comando.

```

docker-compose --build up

```

## Agregado de submodules
Para agregar mas submodules se usar el siguiente comando:

```

git submodule add <url del repo>

```
