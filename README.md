# Clases de Git

<p align="center"><strong>Autor: Josue Suarez Zabala</strong></p>

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
### Los Estados de Git principales

| Estado | Descripción |
|---|---|
| **Modified** | Archivo modificado, aún no preparado para commit |
| **Staged** | Archivo en área de preparación |
| **Committed** | Cambio con un ID (HASH) guardado en el historial local |
| **Remote** | Cambio sincronizado en repositorio remoto |

### Directorio de Trabajo
Git observa los archivos y los cataloga en:
| Tipo | Descripción |
|---|---|
| `Untracked` | Archivo nuevo sin seguimiento |
| `Modified` | Archivo ya versionado con cambios |

> Nota: cualquier archivo no incluido en `.gitignore` entra en alguno de estos estados.

### Stage area (área de preparación)
Para traer archivos al stage necesitamos 
| Comando | Uso |
|---|---|
| `git add <archivo>` | Agrega un archivo al stage |
| `git add .` | Agrega todos los archivos modificados |
| `git restore --staged <archivo>` | Saca un archivo del stage |
| `git log --oneline` | Muestra commits resumidos |
| `git reset --soft HEAD~1` | Revierte el último commit sin perder cambios |

### Repositorio Local (confirmado)
Los cambios que estan en staged pasan al historial:

| git commit -m "Mensaje" |
|---|

### Buenas practicas
| Reglas | Recomendacion |
|---|---|
| Commits atomicos | Un cambio logico por commit |
| Mensaje claro | Usar verbo imperativo: Add, Fix, Remove, Change |
| Longitud | Maximo 50 caracteres |
| Prefijos | feat, fix, perf, build, ci, docs, refactor, style, test |
| Evitar | Puntos suspensivos o mensajes ambiguos |

---

## Clase 3: GitHub y trabajo remoto
### Que es GitHub?
Plataforma en la nube y red social para desarrolladores que permite alojar gestionar y colaborar en proyectos de software utilizando git
### GIT VS GITHUB
| Git | GitHub |
|---|---|
| Sistema de control de versiones | Plataforma para alojar proyectos Git |
| Funciona localmente | Facilita colaboracion remota |
### SSH VS HTTPS
| Protocolo | Caracteristicas |
|---|---|
| HTPS | Suele pedir autenticacion al operar |
| SSH | Usa llaves para autentificacion segura sin contraseña constante |
### Configuracciones ssh
ssh-keygen -t ed25519 -C "tu-correo@gmail.com"
cat ~/.ssh/id_ed25519.pub
ssh -T git@github.com
### Crear repositorio en github
1.Vas a tu apartado de repositorios en https://github.com/Tu-user?tab=repositories y Click en “New”
2.Pones el nombre de tu repositorio, y si quieres una descripción. Y luego click en “Create Repository”
### Conectar un repositorio local con uno en github
| git remote add origin git@github.com:TuUser/TuRepo.git |
|---|
| git branch -M main |
| git push -u origin main |

> Nota: Para usar estos comandos ya tienes que tener inicializado un proyecto git y al menos un commit inicial 
### Clonar un repo de git
Para clonar es necesario ejecutar el codigo
| git clone "linkdelrepoonline"|
|---|
### Cambios
| Subir cambios | git push origin <rama> |
|---|---|
| Bajar Cambios | git pull origin <rama> |

> Nota: push = empujar, pull = traer, oritgin = de donde

---

## Clase 4: SSH Multiple y Checkout
### Git Remote
Comando que nos permite gestionar nuestras conexiones con los repos remotos.
### Comandos utiles
| git remote -v | Permite ver las URLs exactas de donde apunta a nuestro repositorio |
|---|---|
| git remote add <apodo> “url” | Vincula el repo local con uno en la nube |
| git remote set-url <apodo> “url” | Cal la URL donde apunta nuestro repo |

### Multiples SSH
### Configurar multiples SSH
| Generamos el sshkey en con otro nombre: | ssh-keygen -t ed25519 -C "micorreo@gmail.com" -f ~/.ssh/id_miname |
|---|---|
| Creamos un archivo config para que no choquen las key |  # Cuenta del otro correo, Host github-miname, HostName github.com, User git, IdentityFile ~/.ssh/id_miname |
| Para verificar si funciona ejecutamos el comando: | ssh -T git@github-miname |  
### Configuraciones locales
Es decir por repositorio, local se impone a lo global, por lo cula necesitamos hacer
| git config user.name "Mi nuevo Name" | git config user.email "micorreo@gmail.com" |
|---|---|
### Git Checkout
Comando, permite desplazar el HEAD (lector actual) hacia un punto especifico de la historia o una rama distinta
| Para que sirve |  |
|---|---|
| Inspeccionar: | Ver como ere el codigo en un commit antiguo |
| Restaurar: | Recuperar archivos borrados o cambiados |
| Experimentar: | Probar sin tocar la rama principal |
| Cambiar: | saltar de una rama a otra |
### El Estado "Detached HEAD"
Normalmente el HEAD apunta a una rama (que se mueve), En estado desacoplado, el HEAD apunta directamente a un Commit (que es fijo).
### ¿Cómo ir y volver de un commit?
| Comando | Que hace |
|---|---|
| git checkout <hash_antiguo> | Para ir atras |
| git checkout "<rama>" | Para volver al ultimo hash |
| git checkout <hash_commit_creado> | Salvar un commit |
| git checkout -b rama_nueva |  | 
### Buenas Practicas
| No trabajes mucho tiempo en 'Detached HEAD' |
|---|
| Limpia tu Directorio de trabajo |
| Úsalo para aprender |

---
## Clase 5: Ramas y Git Flow para principiantes
La base del trabajo en equipo remoto
### Que son las ramas?
Se trata de una bifurcacion del estado del codigo que crea un nuevo camino de cara a la evolcuion del codigo, se puede trabajar en paralelo a otras ramas
### Git Branch
Comando que nos permite gestionar las ramas que tiene o tendra nuestro proyecto
### Comandos utiles
| git branch | Lista las ramas disponibles y nos muestra nuestro HEAD |
|---|---|
| git branch "<rama>" | Creas una rama a partir de la ramam actual |
| git branch -D "<rama>" | Borra la rama |
### Git Checkout enfocado en ramas
Git checkout tambien sirve para las ramas
| git checkout "<rama>" | Cambiar de rama |
|---|---|
| git checkout -b "<rama>" | Crea un ramma y temueve directamente a ella |

> Nota: No debemos tener nada en modified/untracked o Staged
### Git Checkout vs Git Switch
Git checkout es como una navaja suiza, en cambio git Switch es como un cuchillo simple, cumple pero el checkout sirve mas
### Git flow Basico
Flujo de trabajo, nos permite trabajar de manera ordenada en nuestra ramas
### Como funciona el GitFlow?
| main | La rama por defecto al crear un repo de git, contiene el codigo en produccion |
|---|---|
| develop | Se usa como una rama pre produccion, mayor indice de trabajo |
| ramas de apoyo | Ramas que permiten escribir codigo, pueden ser feature, release y hotfix |
### Ramas de Apoyo
| feature | Nueva caracteristica para el proyecto|
|---|---|
| release | Donde se hacen pruebas |
| hotfix | Para trabajar cambios imprevistos |
### Datos extra
| Rama | Nace | Muere en |
|---|---|---|
| develop | main | Nunca |
| feature | develop | develop |
| release | develop | main y develop |
| hotfix | main | main y develop |

---
## Clase 6: Merge y sincronización
### ¿Qué es Git Merge?
Merge = fusión, entonces git merge nos permite fusionar nuestras ramas en una sola con el fin de que ambas tengan los commits realizados.
Se agrega el <flag –no-ff> que significa "<no fast forward>", hace que no se pierda el historial de ramas y fuerza a hacer un commit para el merge sin que se pierda el historial de ramas, aunque la borras
### ¿Qué es git fetch?
Permite ver si hubo cambios en la rama principal y sus ramas hijas, avisa si hubo cambios o no
### ¿Qué es git pull?
Permite traer todos los cambios que tiene el repositorio remoto de esa rama. Se usa también con origin y el nombre de la rama para que no tengas problemas al subirla.
| "<git pull origin rama>" |
|---|
### ¿Qué es git push?
Es el comando que sube tus cambios al repositorio remoto de esa rama. Se usa también con origin y el nombre de la rama para que no tengas problemas al subirla.
| "<git push origin rama>" |
|---|
Si no es tu repositorio, la primera vez que hagas git push de tu rama debes hacerlo con el flag -u para que no tenga que pedir permiso para crear la rama.
| "<git pull origin -u rama>" |
|---|

---
## Clase 7: Versionamiento de ramas
## Clase 8: Pull Request "La libertad de expresion deberas no importa xd
