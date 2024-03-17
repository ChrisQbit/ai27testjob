ia27 Poyecto de prueba tecnica
Pasos para instalar y correr.
Descargar el zip/rar y descomprimir en la carpeta deseada
OJO eso se puede trabajar en git con ramas pero me causa conflicto con mi actual configuracion de mi maquina y mis llaves ssh.

REQUISITOS Windows:
Tener instalado node JS
https://nodejs.org/en/download/
Tener instalado npm

En la carpeta raiz correr los siguientes comandos
1.- cd /ai27ChristianPadilla
1.1 - npm init -y
2. - npm install express mongoose body-parser mongodb http axios
2.1- OPCIONAL: Si se quiere comprobar la conexion MongoDB antes ejecutar el comando: 
        node connection.js  (Este arroja un mensaje de exito o error informativo)
3.- Ejecutar el proyecto con el comando:      node server.js 

BASE DE DATOS MongoDB 
** Por defecto la cadena de conexion apunta a mi mongo account para apuntar a tu propio mongo 
cambiar la cadena de conexion de los archivos server.js en la linea 13 y el archivo connection.js 
en la linea 2
el string por defecto es el siguiente:
mongodb+srv://ai27:123456abc@ai27db.rpscjra.mongodb.net/?retryWrites=true&w=majority&appName=ai27DB

Consideraciones:
Recomendamos utilizar nombres bien escritos de pokemon, ya que es el parametro
mas importante para brindarte una respuesta satisfactoria. puedes encontrar 
una lista fiable aqui: 
https://www.pokemon.com/us/pokedex

POSTMAN
este link es el acceso al proyecto postman donde se implementan todos los servicios como ejemplo
copiar y pegar en el navegador.


API Rest Documentacion 
El api levanta un servicio en el local y en el puerto 3000
Este servicio consta de 4 endpoints y nos permite Listar, Crear, Borrar por id y Borrar todo por tipo.
Formato de datos JSON 


// Lista Pokemons 
GET url: http://127.0.0.1:3000/pokemons

**En este endpoint lista los pokemons en base de datos.

// Crear Pokemons 
POST url: http://127.0.0.1:3000/pokemons/Altaria

**En este endpoint el nombre del pokemon debe de ir como parametro en la url y buscara dentro 
de pokeapi , si el pokemon existe, se guarda en base de datos Id, Nombre, Moves y Types de lo 
contrario recibimos un mensaje de pokemon no encontrado.

// Borrar un Pokemon
DELETE url: http://127.0.0.1:3000/pokemons/65f61e247fbd3624df86ee4d

**En este endpoint recibe el ide del pokemon como parametro en la url y elimina el pokemon de la 
base de datos, si el pokemon no existe , no hace nada. 
NOTA IMPORTANTE - el id que se proporciona en la url para borrar es el id de
nuestra base de datos, no el id de pokeapi por lo que para eliminar se debe mandar el id
que tiene el formato _id del json

// Borrar todos los Pokemons
PUT url: http://127.0.0.1:3000/pokemons/dragon

**En este endpoint borra todos los registros y no se puede deshacer. y es de tipo PUT. 
