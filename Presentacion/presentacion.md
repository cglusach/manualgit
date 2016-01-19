# Introduccion

## ¿Que es Git?

> - Git fue creado en 2005 por Linus Torvalds como un Sistema Distribuido de Control de Versiones
> - Git fue concebido originalmente para versionar el Kernel de GNU/Linux
> - Git sirve para tener snapshots de cada versión editada del código
> - Git permite a varios programadores colaborar de forma ordenada a la generación de código

## ¿Cómo funciona Git? [1/2]

> - Git se basa en el Modelo Cliente-Servidor para alojar repositorios de código
> - El usuario tiene un repositorio local el cual aloja (dentro
de su PC) diferentes *snapshots* de su código
> - El usuario sube a un repositorio remoto (servidor de Git) sus *snapshots* para ser distribuidas a otros usuarios

## ¿Cómo funciona Git? [2/2]

> - Ejemplos de servidores (públicos) de Git son: *BitBucket* y *GitHub*
> - Los *snapshots* son conocidos en git como *commits*, se identifican por una secuencia de caracteres alfanuméricos denominada *hash*

# Instalación

## Instalación Inicial

### Debian / Ubuntu / Linux Mint
```
sudo apt-get install git kdiff3-qt
```

### Windows
Usar el *complete installer* de GitExtensions:
```
https://gitextensions.github.io/
```

## Configuración en Linux [1/3]

### Establecer Nombre, Email y Mergetool
```
git config --global user.name "Juan Pérez"
git config --global user.email juan.perez@usach.cl
git config --global merge.tool kdiff3
```

## Configuración en Linux [2/3]

### Configurar Llave SSH [1/2]
```
ssh-keygen -t rsa -b 4096 -C "juan.perez@usach.cl"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub
```

## Configuración en Linux [3/3]

### Configurar Llave SSH [2/2]
* Copiar la salida del comando cat, esta es la *llave pública*, la cual debe ser pegada en el servidor de git a usar (BitBucket, GitHub, etc)

# Uso de Git

## Esquema básico de Git

\includegraphics[height=7cm]{imagenes/gitworkflow.png}

## Zonas de Trabajo

> - **Workspace (o Directorio Local):** Es el directorio sobre el cual trabajamos nuestro código
> - **Index (o Índice):** Mantiene una copia observada de los archivos de código editados
> - **Local Repository (o Repo Local):** Agrupa todas las copias observadas del Index en commits
> - **Remote Repository (o Repo Remoto):** Almacena todos los commits transferidos desde el repo remoto y los distribuye a otros usuarios


## Comandos Básicos de Git [1/4]

### Iniciar Repo
	git init

### Añadir Repo Remoto
	git remote add origin [URL]

### Clonar Repo Remoto
	git clone [URL]


## Comandos Básicos de Git [2/4]

### Tirar cambios del Repo Remoto
	git pull [REMOTO] [RAMA]

### Añadir un archivo al Index
	git add [ARCHIVO]

### Añadir todos los archivos al Index
	git add --all


## Comandos Básicos de Git [3/4]

### Crear un *commit* con todos los archivos del Index
	git commit -m "[MENSAJE]"

### Empujar todos los *commits* al Repo Remoto
	git push [REMOTO] [RAMA]


## Comandos Básicos de Git [4/4]

### Ver el estado actual del Repo Local
	git status

### Ver la lista de *commits* recientes
	git log


## Comandos Avanzados de Git [1/2]

### Resetear el Repo Local al último *commit*
	git reset --hard HEAD

### Solucionar manualmente conflictos de fusionado (*merge*)
	git mergetool


## Comandos Avanzados de Git [2/2]

### Crear un nuevo *commit* reversando los cambios de otro
	git revert [HASH]

### Reversar últimos 3 commits guardando cambios en Index
	git revert --no-commit HEAD~3..HEAD


# Conclusión

## Conclusión

* Git es una herramienta eficaz para que múltiples usuarios puedan modificar simultánea y asíncronamente un repositorio de código

## Gracias

\begin{center}
\LARGE{¿Preguntas?}
\end{center}

## Más información

\begin{center}
\large{Recuerda bajar nuestro Manual y Cheatsheet en:}
\LARGE{http://cglusach.github.io/manualgit/}
\end{center}