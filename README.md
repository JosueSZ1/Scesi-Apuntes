# Clases de Git
![Git Logo](https://git-scm.com/images/logos/downloads/Git-Icon-1788C.png)

**Autor:** Josue Suarez Zabala

---
## Índice
- [Clase 1: Introducción a Git](#clase-1-introducción-a-git)
- [Clase 2: Estados de Git](#clase-2-estados-de-git)
- [Clase 3: GitHub y trabajo remoto](#clase-3-github-y-SSH)
- [Clase 4: SSH Multiple y Checkout](#clase-4-github-SSH-multiple-y-checkout)
- [Clase 5: Ramas y Git Flow para principiantes](#clase-5-gitflow-ramas)
- [Clase 6: Merge y sincronización](#clase-6-merge-y-sincronización)
- [Clase 7: Versionamiento de ramas](#clase-7-versionamiento-de-ramas)
- [Clase 8: Pull Request "La libertad de expresion deberas no importa xd"](#clase-8-PullRequest-PR)

---

## Clase 1: Introducción a Git
### Que es git?
Es un Sistema de "Control de Versionamiento"
### Como Nacio Git?
Linus Tolvads se ardio con un versionamiento de paga y lo creo
### Como instalar git?
| Sistema | Método |
|---|---|
| Linux | `sudo apt install git` |
| Windows | Descargar instalador desde [git-scm.com](https://git-scm.com/) |
### Configuraciones Basicas Y todo de git:x
| Comando | Descripción |
|---|---|
| `git init` | Inicializa un repositorio local |
| `git status` | Muestra el estado de los archivos |
| `git log` | Muestra historial de commits (fecha, autor, cambios) |

---

## Clase 2: Estados de Git
## Los Estados de Git
(Modificado) Codigo escrito pero no asegurado
(Stage) Area de espera lo que se planea guardar
(Confirmado) Cambios con un ID (HASH) guardados
(Remoto) Repositorio remoto de git
## Directorio de Trabajo
Git observa los archivos y los cataloga en
Untracked: Archivo nuevo se ve pero no hay un estado previo de el
Modified: Git tiene una version previa del archivo
Nota: Cualquier archivo que no este en gitignore pasa automaticamente a unos de estos estados
## Stage area
Para traer archivos al stage necesitamos 
git add :<archivo> Agrega al archivo 
git add . :agrega todo lo modificado
git restore --staged <archivo> :quita el archivo de stage
git log --online muestra un id resumido
git reset --soft HEAD-1  borra el ultimo commit
## Repositorio Local (confirmado)
Los cambios que estan en staged pasan al historial
git commit -m "Mensaje"
### Buenas practicas
Git atomicos
Los commits deben ser descriptipos y imperativos: ADD Change Fix Remove
No usarpuntos suspensivos
Maximo 50 caracteres
Usar prefijo para los comits: feat fix pert build ci docs refactor style test 
# Clase de git 3
## Git hub
### QUE ES GITHUB
Plataforma en la nube y red social para desarrolladores que permite alojar gestionar y colaborar en proyectos de software utilizando git
### GIT VS GITHUB
Git es un sistema de control de versiones
Git hub Servidor donde se almacenan y se socializan con el mundo
## SSH VS HTTPS
### HTTPS
Si queremos clonar un repo con HTTPS pide autentificacion
### SSH
Configurar pc/laptop con ssh parta comunicarnos con github mediante key
## Configuracciones ssh
ssh-keygen -t ed25519 -C "tu-correo gamil.com"
cat -/.ssh/id_ed25519.pub
ssh -T git github.com
## Crear repositorio en github
## Conectar un repositorio local con uno en github
## Clonar un repo de git
### Cambios
Subir cambios git push origin <rama>
Bajar Cambios git pull origin <rama>
## Manejo de ramas
## Navegacion entre ramas
# Clases de Git 6 
## ¿Qué es Git Merge?
Merge = fusión, entonces git merge nos permite fusionar nuestras ramas en una sola con el fin de que ambas tengan los commits realizados.
Se agrega el <flag –no-ff> que significa <no fast forward>, hace que no se pierda el historial de ramas y fuerza a hacer un commit para el merge sin que se pierda el historial de ramas, aunque la borras
## ¿Qué es git fetch?
Permite ver si hubo cambios en la rama principal y sus ramas hijas, avisa si hubo cambios o no
## ¿Qué es git pull?
Permite traer todos los cambios que tiene el repositorio remoto de esa rama. Se usa también con origin y el nombre de la rama para que no tengas problemas al subirla.
<git pull origin rama>
## ¿Qué es git push?
Es el comando que sube tus cambios al repositorio remoto de esa rama. Se usa también con origin y el nombre de la rama para que no tengas problemas al subirla.
<git push origin rama>
Si no es tu repositorio, la primera vez que hagas git push de tu rama debes hacerlo con el flag -u para que no tenga que pedir permiso para crear la rama.
<git pull origin -u rama>
# Clase de Git 7
Versionamiento de ramas y cosas asi
