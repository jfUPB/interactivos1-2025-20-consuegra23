<img width="550" height="213" alt="image" src="https://github.com/user-attachments/assets/3ffddb52-af5f-46ae-9cbd-cef8c6fc22fa" />
# Evidencias de la unidad 6

<img width="1664" height="908" alt="Captura de pantalla 2025-09-23 105634" src="https://github.com/user-attachments/assets/8f144230-99a3-4da3-b702-299d45e62278" />

## Actividad 1

#### ¿Qué ocurrió en la terminal cuando ejecutaste npm install? ¿Cuál crees que es su propósito?
$ npm install

added 120 packages, and audited 121 packages in 3s

17 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities

npm notice

npm notice New major version of npm available! 10.2.0 -> 11.6.0

npm notice Changelog: <https://github.com/npm/cli/releases/tag/v11.6.0>

npm notice Run `npm install -g npm@11.6.0` to update!

npm notice
El proposito de esta funcion es instalar las dependencias necesarias ademas de colocar las funciones necesarias en el index

#### ¿Qué mensaje específico apareció en la terminal después de ejecutar npm start? ¿Qué indica este mensaje?

$ npm start

> nodejs-test-1@1.0.0 start

> node server.js

Server is listening on http://localhost:3000

A user connected - ID: 46W9gfDv5PvIkIANAAAB

El servidor empieza a escuchar y revisar la existencia de las paginas, esto se puede comprobrar si se inicia el link que esta disponible pues se esta esperando una conexion.

#### Describe lo que ves inicialmente en page1 y page2 en tu navegador.

Cuando se colocan cualquiera de las dos paginas se inicia a buscar si la otra pagina ya esta abierta y mientras tanto muestra que se esta esperando la conexion, despues de que se inicie la segunda pagina y el servidor este funcionando estas muestran una esfera en cada pagina conectadas por medio de una linea que siempre conecta ambas.

#### ¿Qué mensajes aparecieron en la terminal del servidor cuando abriste page1 y page2?

en el servidor se empiezan a mandar los datos del centro donde esta la esfera en la pagina y se actualiza solo cuando las paginas se mueven.

## Actividad 2
#### Piensa en cómo te conectas a Internet en casa o en la Universidad. ¿Usas Wi-Fi? ¿Un cable de red? Eso es simplemente tu “rampa de acceso” a la gran red de carreteras. ¿Qué pasaría si esa rampa se corta? 

Yo pienso que el internet funciona como una red grandisima de barcos y al momento de conectarme es como si yo me montara en mi propio barco, lo que me permite navegar las aguas libremente encontrando islas como paginas web, juegos online, etc. o otros barcos con los que puedo intercambiar informacion por medio de intermediarios como discord, whatsapp o otros medios, me imagino que si se "corta la rampa" seria como si algo de mi barco se dañara fuera la vela que me permite navegar mas rapido a mi destino, la carga que tenia perdiendo la informacion o la rampa para poder subir datos propios o bajarlos.

#### ¿Puedes identificar otros ejemplos de relaciones Cliente-Servidor en tu vida diaria (no necesariamente digitales)? Por ejemplo, al pedir comida en un restaurante. ¿Quién es el cliente y quién el servidor? ¿Qué se pide y qué se entrega?

Un ejemplo cotidiano de relación cliente-servidor es cuando vas a una cafetería. Tú eres el cliente porque haces una solicitud, como pedir un café, y el barista actúa como servidor al recibir tu pedido, prepararlo y entregártelo.

Otro caso es en una biblioteca. El usuario solicita un libro específico (cliente) y el bibliotecario busca y entrega el material (servidor). En ambos ejemplos, hay una petición clara, una respuesta concreta y una entrega de servicio.

#### Toma la URL de tu sitio web favorito. Intenta identificar el protocolo, el nombre de dominio y la ruta (si la hay). ¿Qué crees que pasa si solo escribes el nombre de dominio (ej. www.google.com) sin una ruta específica? ¿Qué “página por defecto” crees que te envía el servidor?

Tomando como ejemplo la URL https://www.wikipedia.org/wiki/Colombia, el protocolo es https, el nombre de dominio es www.wikipedia.org y la ruta es /wiki/Colombia. El protocolo indica cómo se transmite la información, el dominio identifica el servidor y la ruta señala el recurso específico dentro del sitio.

Si solo se escribe el dominio, como www.wikipedia.org, el servidor normalmente envía una página por defecto, que suele ser la página principal o de inicio del sitio. Esta página sirve como punto de entrada para navegar hacia otros contenidos.

#### Compara HTTP con los protocolos seriales que usaste.

#### ¿Qué similitudes encuentras? ¿Qué diferencias clave ves?

Como similitudes la verdad no identifico mucho si no casi nada, seria mas o menos como responde el HTTP que se asemeja a los mensajes de consola que mandaba el micro:bit.
Como diferencias varias pues el sistema de pregunta y respuesta que utiliza es bastante diferente al sistemas de analisis de datos generados por Inputs, pues en este caso podemos controlar completamente que datos esta recibiendo el clinte y el servidor lo que debe permitir filtrarlos y tambien evitar su robo

#### ¿Por qué crees que HTTP necesita ser más complejo que un simple envío de bytes como hacías con el micro:bit?
Asumo que requieren de esta complejidad tanto como por que deben necesitar mandar muchisimos datos y deben saber donde ponerlos y como usarlos tanto como para proteger los datos del cliente y solo utilizar lo necesario o para lo que se le dio permiso

#### Piensa en una página web simple, como un formulario de login.

#### ¿Qué parte crees que es HTML (ej. los campos de texto, el botón)?
#### ¿Qué parte es CSS (ej. el color del botón, el tipo de letra)?
#### ¿Qué parte es JavaScript (ej. la comprobación de si escribiste algo antes de enviar, el mensaje de “contraseña incorrecta” que aparece sin recargar la página)?

Una pagina para hacer login que es de una tienda de videojuegos que usaria HTML para los textos de ingresar correo electronico, ingresar contraseña, el boton para iniciar sesion, otro para decir olvidar contraseña.
Con CSS que el boton de iniciar sesion sea azul, el de contraseña olvidada sea rojo y tenga un tipo de letra menos llamativo.
JavaScript va a comprobar que el usuario y contraseña sean correctos, mandar la señal de que esta equivocado algun dato, enviar a el cliente a la pagina despues de inicar sesion o a la pagina de contraseña olvidada.

#### Compara el bucle draw() de p5.js con este modelo de “esperar a que algo pase y reaccionar”.

#### ¿Qué ventajas crees que tiene el modelo basado en eventos para una interfaz de usuario web?
Este modelo debe ser mucho menos consumidor de recursos al solo reaccionar cuando se le indica y demas que es mas organizado pues se puede facilitar el comprobar errores pues no hay acciones inesperadas que se pueden conectar entre ellas.
#### ¿Sería eficiente tener un bucle draw() redibujando toda la página 60 veces por segundo si nada ha cambiado?

Esto seria completamente ineficiente pues el estar actualizando constantemente la pagina consumiria una cantidad de recursos ridicula pues el comprobar constantemente si los datos que estan ahi se estan actualizando, es completamente inecesesario demas que causaria errores, pues muchas paginas borran las lineas escritas si por ejemplo la contraseña y el usuario esta malo, si se actualizara y comprobara todo constantemente estaria borrando todo el tiempo el usuario pues nadie es capaz de escribir lo suficientemente rapido,

#### ¿Por qué crees que podría ser útil usar JavaScript tanto en el cliente (navegador) como en el servidor? ¿Se te ocurre alguna ventaja para los desarrolladores?

Usar JavaScript tanto en el cliente como en el servidor es útil porque permite mantener un solo lenguaje en todo el desarrollo de una aplicación. Esto simplifica el trabajo, ya que los desarrolladores no necesitan aprender diferentes lenguajes para manejar el frontend y el backend. Además, se pueden reutilizar funciones y estructuras, lo que ahorra tiempo y reduce errores.

Otra ventaja es que facilita la colaboración entre equipos, ya que todos trabajan bajo una misma lógica. También mejora el rendimiento de las aplicaciones, permitiendo validaciones rápidas en el navegador y procesamiento más complejo en el servidor, sin necesidad de recargar la página constantemente.

#### Resume con tus propias palabras la diferencia fundamental entre una comunicación HTTP tradicional y una comunicación usando WebSockets/Socket.IO. ¿En qué tipo de aplicaciones has visto o podrías imaginar que se usa esta comunicación en tiempo real?

La diferencia fundamental entre HTTP y WebSockets/Socket.IO está en cómo se comunican el cliente y el servidor. HTTP es una comunicación de tipo petición-respuesta: el cliente pide algo y el servidor responde, pero no hay conexión constante. En cambio, WebSockets y Socket.IO permiten una conexión abierta y continua, donde ambos pueden enviarse mensajes en tiempo real sin necesidad de recargar la página.

Este tipo de comunicación se usa en aplicaciones como chats en línea, videojuegos multijugador, transmisiones en vivo, tableros colaborativos o sistemas de monitoreo. En estos casos, la velocidad y la actualización instantánea son clave para una buena experiencia de usuario.

## Actividad 4
#### cambiar la ruta de page1 a pagina_uno
el programa funciona completamente bien y sin ningun problema o variacion, lo que muestra que la ruta no es lo mas primordial al momento de iniciar el programa y solo nos ayuda a iniciar la pagina y puede ser modificada sin ningun problema mayor
#### Seguir los pasos mientras se observa el servidor
Received win1update from ID: oJdzmHDxeO__tgF8AAAB Data: { x: 1001, y: 156, width: 492, height: 593 }
Debug - Connected clients: 1, Page1: 1, Page2: 0, Synced: 0
Sync status: pages=false, synced=false, clients=1
Debug - Connected clients: 1, Page1: 1, Page2: 0, Synced: 1
Sync status: pages=false, synced=true, clients=1
Esto es lo que se ve cuando se inicia la pagina uno individualmente sin inicar la pagina dos, ni moverla de su lugar, muestra que en un dato booleano tiene que si la pagina esta activa y es capaz de medir su ubicacion en la pantalla.
Received win2update from ID: AOTPzaymCVyH3MUZAAAD Data: { x: 499, y: 154, width: 492, height: 591 }
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 1
Sync status: pages=true, synced=false, clients=2
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 1
Sync status: pages=true, synced=false, clients=2
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Received win2update from ID: AOTPzaymCVyH3MUZAAAD Data: { x: 499, y: 154, width: 492, height: 625 }
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Received win1update from ID: oJdzmHDxeO__tgF8AAAB Data: { x: 1001, y: 156, width: 492, height: 625 }
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Al iniciar la segunda pagina vuelve a comprobar la ubicacion de ambas y ahora muestra que las dos estan activadas mas no sincronizadas pues solo hay un Synced,  ya despues de eso vuelve  a hacer el analizis y ya ambas estan Synced y funcionando con normalidad
User disconnected - ID: oJdzmHDxeO__tgF8AAAB
User disconnected - ID: AOTPzaymCVyH3MUZAAAD
Estos fueron los mensajes enviados por el programa al desconectar respectivamente pagina 1 y pagina 2 simplemente se desconectan y dejan de hacer la busqueda enseguida
como conclusion delos Id puedo ver que varian usualmente cuando se haee un cambio en el servidor y cada uno de los ID parece representar cada uno a una de las paginas pues cada ID da coordenadas diferentes y se muestra el mismo cuando se desconecta su pagina respectiva
#### Analizis de Winupdate
Received win1update from ID: RFziBF8MEg-_9gyIAAAB Data: { x: 526, y: 186, width: 492, height: 625 }
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Received win2update from ID: iTb5B_3tvr-AJJkPAAAD Data: { x: 1045, y: 143, width: 492, height: 625 }
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Se puede ver que cada pagina se actualiza individualmente en su propio update y muestra solo sus datos junto con su id como dije en el pasado
Received win1update from ID: P8NUU74rQjI86n7HAAAD Data: { x: 607, y: 119, width: 492, height: 625 }
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Despues de hacer los camios dados no note una diferencia notable en el win1update
#### Cambiar el numero del port
<img width="1648" height="782" alt="image" src="https://github.com/user-attachments/assets/31550d1a-4310-434a-977a-17215bae41ee" />
Server is listening on http://localhost:3001
A user connected - ID: SOVMfGBfVqYo_sk4AAAB
Received win2update from ID: SOVMfGBfVqYo_sk4AAAB Data: { x: 1227, y: 348, width: 492, height: 593 }
Debug - Connected clients: 1, Page1: 0, Page2: 1, Synced: 0
Sync status: pages=false, synced=false, clients=1
Debug - Connected clients: 1, Page1: 0, Page2: 1, Synced: 1
Sync status: pages=false, synced=true, clients=1
A user connected - ID: AGPZ7aVIalgIbpK7AAAD
Received win2update from ID: AGPZ7aVIalgIbpK7AAAD Data: { x: 856, y: 147, width: 492, height: 591 }
Debug - Connected clients: 2, Page1: 0, Page2: 2, Synced: 1
Sync status: pages=false, synced=false, clients=2
Debug - Connected clients: 2, Page1: 0, Page2: 2, Synced: 1
Sync status: pages=false, synced=false, clients=2
Debug - Connected clients: 2, Page1: 0, Page2: 2, Synced: 2
Sync status: pages=false, synced=true, clients=2
Parece que la pagina no inicia correctamente como se muestra en la imagen pero los datos de incio funcionan correctamente,pero al nuna iniciar no puedo comprbar si estos pueden detectar los movimientos de la pestaña
<img width="1640" height="714" alt="image" src="https://github.com/user-attachments/assets/1be90a97-a4a3-48c0-943a-c4b7b7f37791" />
User disconnected - ID: AGPZ7aVIalgIbpK7AAAD
A user connected - ID: NZcAn2p64E_H6LYPAAAF
Received win1update from ID: NZcAn2p64E_H6LYPAAAF Data: { x: 0, y: 0, width: 1920, height: 945 }
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 1
Sync status: pages=true, synced=false, clients=2
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 1
Sync status: pages=true, synced=false, clients=2
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Received win2update from ID: SOVMfGBfVqYo_sk4AAAB Data: { x: 1284, y: 201, width: 492, height: 625 }
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Received win2update from ID: SOVMfGBfVqYo_sk4AAAB Data: { x: 1284, y: 192, width: 492, height: 625 }
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Received win2update from ID: SOVMfGBfVqYo_sk4AAAB Data: { x: 1283, y: 189, width: 492, height: 625 }
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Debug - Connected clients: 2, Page1: 1, Page2: 1, Synced: 2
All clients are fully synced
Por alguna razon despues de comprobar que intentar entrar con el port en 3000 no servia y volver a abrir el 3001 en un navegador diferente empezo a fucnionar de la nada y sin motivo aparente, esto rompe todo lo que creia del funionanmiento del port haciendo que no fuera un numero arbitrario, pero parece que si lo haz pues no modifico el funcionamiento

## Actividad 04

<img width="541" height="331" alt="image" src="https://github.com/user-attachments/assets/76ec3fcb-bb50-428f-bce1-df51d78aa84b" />

Al seguir las instrucciones sin reinciar la pgaina llega hasta este punto ahi se ve claramente que genera un error por que no se puede conectar ya mas a nada y se queda esperando.

<img width="550" height="213" alt="image" src="https://github.com/user-attachments/assets/1f00efac-0227-4c97-a043-ca09bc20242a" />


<img width="547" height="251" alt="image" src="https://github.com/user-attachments/assets/613742a5-7af7-4974-b5a7-5256564c8096" />

Despues de reiniciar y despues de reiniciar el servidor y reiniciar la pagina respectivamente, se puede ver que sin iniciar el servidor todavia presenta el mismo error de codigo por lo que se asume que ese error es que no es capaz de encontrar el servidor por el que funciona. y al iniciar el servidor luego funciona normalmente y no presenta errores.

