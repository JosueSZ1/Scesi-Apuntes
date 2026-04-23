# Clases de Git 1
Josue suarez Zabala
## Que es git
Control de Versionamiento
## Como Nacio Git
Linus Tolvads se ardio con un versionamiento de paga y lo creo
## Como instalar git
Mediante el instalador de paquetes de linux apt get o descargando el ejecutable en windows
## Configuraciones Basicas Y todo de git:x
El git init para inicializar proyextos El git status para verificar archivos del repositorio El git log para verificar cambios en el git con fecha hora y quien fue 
# Clase de Git 2
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

