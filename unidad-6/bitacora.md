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

## Actividad 05
Inspirandome de la serie animada jujutsu kaisen y la tecnica Vacio purputa que se ve de la siguiente manera:
https://tenor.com/qfF7VFtilrY.gif
Plantee lo siguiente

<img width="3910" height="915" alt="image" src="https://github.com/user-attachments/assets/479f222e-62a2-408e-bdac-85f1c7678587" />

Aprovechando que ambas esferas estan conectadas constantemente por una vara en la mitad, se puede usar el codigo que determina el tamaño de esta vara como base para medir la distancia de las dos esferas.
<img width="3949" height="727" alt="image" src="https://github.com/user-attachments/assets/11723b0b-c439-454d-aa3a-fa179cc3d98f" />

<img width="2593" height="715" alt="image" src="https://github.com/user-attachments/assets/a93629dc-af22-4ae9-819d-51581ca4e1e2" />

<img width="4308" height="3000" alt="image" src="https://github.com/user-attachments/assets/d4e95302-9a69-43a0-b6eb-eb62eaebc048" />

El programa tiene que funcionar de la siguiente manera, las esferas cuando esten a una distancia aplia van no van a interactuar de ninguna manera, cuando esten relativamente mas cerca van a empezar a mandarse entre ellas particulas de su respectivo color hacia el centro y cuando esten una encima de la otra estas se van a convinar en una sola esfera y esta va a disparar rayos purpuras y particulas del mismo color, ademas que entre mas cerca esten mas oscuro se va a ver el fondo para efectos dramaticos


~~~ js
let currentPageData = {
    x: window.screenX,
    y: window.screenY,
    width: window.innerWidth,
    height: window.innerHeight
}

let previousPageData = {
    x: window.screenX,
    y: window.screenY,
    width: window.innerWidth,
    height: window.innerHeight
};

let remotePageData = { x: 0, y: 0, width: 100, height: 100 };
let point1 = [currentPageData.width / 2, currentPageData.height / 2];
let socket;
let isConnected = false;
let hasRemoteData = false;
let isFullySynced = false;

// Sistema de partículas
let particles = [];
let lightningBolts = [];

// Configuración de distancias (en píxeles)
const DISTANCE_FAR = 800;      // Lejos: no hace nada
const DISTANCE_MEDIUM = 400;   // Medio: empieza a lanzar partículas
const DISTANCE_CLOSE = 150;    // Cerca: fusión y explosión

function setup() {
    createCanvas(windowWidth, windowHeight);
    frameRate(60);
    socket = io();

    socket.on('connect', () => {
        console.log('Connected with ID:', socket.id);
        isConnected = true;
        socket.emit('win1update', currentPageData, socket.id);
        
        setTimeout(() => {
            socket.emit('requestSync');
        }, 500);
    });

    socket.on('getdata', (response) => {
        if (response && response.data && isValidRemoteData(response.data)) {
            remotePageData = response.data;
            hasRemoteData = true;
            console.log('Received valid remote data:', remotePageData);
            socket.emit('confirmSync');
        }
    });

    socket.on('fullySynced', (synced) => {
        isFullySynced = synced;
        console.log('Sync status:', synced ? 'SYNCED' : 'NOT SYNCED');
    });

    socket.on('peerDisconnected', () => {
        hasRemoteData = false;
        isFullySynced = false;
        particles = [];
        lightningBolts = [];
        console.log('Peer disconnected, waiting for reconnection...');
    });

    socket.on('disconnect', () => {
        isConnected = false;
        hasRemoteData = false;
        isFullySynced = false;
        particles = [];
        lightningBolts = [];
        console.log('Disconnected from server');
    });
}

function isValidRemoteData(data) {
    return data && 
           typeof data.x === 'number' && 
           typeof data.y === 'number' && 
           typeof data.width === 'number' && data.width > 0 &&
           typeof data.height === 'number' && data.height > 0;
}

function checkWindowPosition() {
    currentPageData = {
        x: window.screenX,
        y: window.screenY,
        width: window.innerWidth,
        height: window.innerHeight
    };

    if (currentPageData.x !== previousPageData.x || currentPageData.y !== previousPageData.y || 
        currentPageData.width !== previousPageData.width || currentPageData.height !== previousPageData.height) {

        point1 = [currentPageData.width / 2, currentPageData.height / 2]
        socket.emit('win1update', currentPageData, socket.id);
        previousPageData = currentPageData;
    }
}

// Calcular distancia entre las dos esferas
function calculateDistance(x1, y1, x2, y2) {
    return dist(x1, y1, x2, y2);
}

// Clase para partículas individuales
class Particle {
    constructor(x, y, targetX, targetY, col, isExplosion = false) {
        this.pos = createVector(x, y);
        this.col = col;
        this.alpha = 255;
        this.size = random(3, 8);
        this.isExplosion = isExplosion;
        
        if (isExplosion) {
            // Partículas de explosión: dirección aleatoria hacia afuera
            let angle = random(TWO_PI);
            let speed = random(3, 8);
            this.vel = createVector(cos(angle) * speed, sin(angle) * speed);
            this.life = 255;
        } else {
            // Partículas normales: van hacia el objetivo
            this.target = createVector(targetX, targetY);
            let direction = p5.Vector.sub(this.target, this.pos);
            direction.normalize();
            direction.mult(random(2, 4));
            this.vel = direction;
        }
    }
    
    update() {
        this.pos.add(this.vel);
        
        if (this.isExplosion) {
            this.life -= 3;
            this.alpha = this.life;
        } else {
            this.alpha -= 2;
        }
    }
    
    display() {
        noStroke();
        fill(this.col.levels[0], this.col.levels[1], this.col.levels[2], this.alpha);
        circle(this.pos.x, this.pos.y, this.size);
        
        // Glow effect
        fill(this.col.levels[0], this.col.levels[1], this.col.levels[2], this.alpha * 0.3);
        circle(this.pos.x, this.pos.y, this.size * 2);
    }
    
    isDead() {
        if (this.isExplosion) {
            return this.life <= 0;
        }
        return this.alpha <= 0;
    }
}

// Clase para rayos de luz
class LightningBolt {
    constructor(x, y) {
        this.pos = createVector(x, y);
        let angle = random(TWO_PI);
        let length = random(100, 250);
        this.endX = x + cos(angle) * length;
        this.endY = y + sin(angle) * length;
        this.segments = [];
        this.life = 255;
        this.generateSegments();
    }
    
    generateSegments() {
        let steps = 10;
        for (let i = 0; i <= steps; i++) {
            let t = i / steps;
            let x = lerp(this.pos.x, this.endX, t) + random(-10, 10);
            let y = lerp(this.pos.y, this.endY, t) + random(-10, 10);
            this.segments.push(createVector(x, y));
        }
    }
    
    update() {
        this.life -= 15;
    }
    
    display() {
        stroke(150, 50, 200, this.life);
        strokeWeight(3);
        noFill();
        beginShape();
        for (let seg of this.segments) {
            vertex(seg.x, seg.y);
        }
        endShape();
        
        // Glow
        stroke(200, 100, 255, this.life * 0.5);
        strokeWeight(6);
        beginShape();
        for (let seg of this.segments) {
            vertex(seg.x, seg.y);
        }
        endShape();
    }
    
    isDead() {
        return this.life <= 0;
    }
}

function draw() {
    // Fondo dinámico según distancia
    let bgColor = 220;
    
    if (!isConnected) {
        background(bgColor);
        showStatus('Conectando al servidor...', color(255, 165, 0));
        return;
    }
    
    if (!hasRemoteData) {
        background(bgColor);
        showStatus('Esperando conexión de la otra ventana...', color(255, 165, 0));
        return;
    }
    
    if (!isFullySynced) {
        background(bgColor);
        showStatus('Sincronizando datos...', color(255, 165, 0));
        return;
    }

    checkWindowPosition();
    
    // Calcular posiciones
    let vector1 = createVector(currentPageData.x, currentPageData.y);
    let vector2 = createVector(remotePageData.x, remotePageData.y);
    let resultingVector = createVector(vector2.x - vector1.x, vector2.y - vector1.y);
    
    let remoteX = resultingVector.x + remotePageData.width / 2;
    let remoteY = resultingVector.y + remotePageData.height / 2;
    
    // Calcular distancia entre esferas
    let distance = calculateDistance(point1[0], point1[1], remoteX, remoteY);
    
    // Oscurecer fondo según la cercanía
    if (distance < DISTANCE_CLOSE) {
        let darkness = map(distance, DISTANCE_CLOSE, 0, 220, 20);
        bgColor = darkness;
    }
    
    background(bgColor);
    
    // ESTADO 1: LEJOS - No hace nada
    if (distance > DISTANCE_FAR) {
        drawSphere(point1[0], point1[1], color(255, 0, 0), 75);
    }
    // ESTADO 2: DISTANCIA MEDIA - Lanzar partículas
    else if (distance > DISTANCE_CLOSE && distance <= DISTANCE_FAR) {
        drawSphere(point1[0], point1[1], color(255, 0, 0), 75);
        
        // Generar partículas rojas hacia la otra esfera
        if (frameCount % 5 === 0) {
            particles.push(new Particle(point1[0], point1[1], remoteX, remoteY, color(255, 0, 0)));
        }
    }
    // ESTADO 3: MUY CERCA - Fusión y explosión
    else {
        // Calcular punto medio para la fusión
        let midX = (point1[0] + remoteX) / 2;
        let midY = (point1[1] + remoteY) / 2;
        
        // Dibujar esfera morada fusionada
        drawSphere(midX, midY, color(150, 50, 200), 100);
        
        // Generar partículas de explosión moradas
        if (frameCount % 2 === 0) {
            for (let i = 0; i < 3; i++) {
                particles.push(new Particle(midX, midY, 0, 0, color(150, 50, 200), true));
            }
        }
        
        // Generar rayos de luz morados
        if (frameCount % 8 === 0) {
            lightningBolts.push(new LightningBolt(midX, midY));
        }
    }
    
    // Actualizar y dibujar partículas
    for (let i = particles.length - 1; i >= 0; i--) {
        particles[i].update();
        particles[i].display();
        if (particles[i].isDead()) {
            particles.splice(i, 1);
        }
    }
    
    // Actualizar y dibujar rayos
    for (let i = lightningBolts.length - 1; i >= 0; i--) {
        lightningBolts[i].update();
        lightningBolts[i].display();
        if (lightningBolts[i].isDead()) {
            lightningBolts.splice(i, 1);
        }
    }
    
    // Mostrar info de debug
    fill(255);
    noStroke();
    textSize(12);
    textAlign(LEFT, TOP);
    text(`Distancia: ${distance.toFixed(0)}px`, 10, 10);
    text(`Partículas: ${particles.length}`, 10, 25);
    text(`Rayos: ${lightningBolts.length}`, 10, 40);
}

function showStatus(message, statusColor) {
    textSize(24);
    textAlign(CENTER, CENTER);
    noStroke();
    fill(0, 0, 0, 150);
    rectMode(CENTER);
    let textW = textWidth(message) + 40;
    let textH = 40;
    rect(width / 2, height / 6, textW, textH, 10);
    fill(statusColor);
    text(message, width / 2, height / 6);
}

function drawSphere(x, y, col, size) {
    // Glow exterior
    for (let i = 3; i > 0; i--) {
        noStroke();
        fill(col.levels[0], col.levels[1], col.levels[2], 30 / i);
        ellipse(x, y, size * (1 + i * 0.3), size * (1 + i * 0.3));
    }
    
    // Esfera principal
    fill(col);
    noStroke();
    ellipse(x, y, size, size);
    
    // Brillo interior
    fill(255, 255, 255, 100);
    ellipse(x - size * 0.15, y - size * 0.15, size * 0.3, size * 0.3);
}

function windowResized() {
    resizeCanvas(windowWidth, windowHeight);
}
~~~

~~~ js
let currentPageData = {
    x: window.screenX,
    y: window.screenY,
    width: window.innerWidth,
    height: window.innerHeight
}

let previousPageData = {
    x: window.screenX,
    y: window.screenY,
    width: window.innerWidth,
    height: window.innerHeight
};

let remotePageData = { x: 0, y: 0, width: 100, height: 100 };
let point2 = [currentPageData.width / 2, currentPageData.height / 2];
let socket;
let isConnected = false;
let hasRemoteData = false;
let isFullySynced = false;

// Sistema de partículas
let particles = [];
let lightningBolts = [];

// Configuración de distancias (en píxeles)
const DISTANCE_FAR = 800;      // Lejos: no hace nada
const DISTANCE_MEDIUM = 400;   // Medio: empieza a lanzar partículas
const DISTANCE_CLOSE = 150;    // Cerca: fusión y explosión

function setup() {
    createCanvas(windowWidth, windowHeight);
    frameRate(60);
    socket = io();

    socket.on('connect', () => {
        console.log('Connected with ID:', socket.id);
        isConnected = true;
        socket.emit('win2update', currentPageData, socket.id);
        
        setTimeout(() => {
            socket.emit('requestSync');
        }, 500);
    });

    socket.on('getdata', (response) => {
        if (response && response.data && isValidRemoteData(response.data)) {
            remotePageData = response.data;
            hasRemoteData = true;
            console.log('Received valid remote data:', remotePageData);
            socket.emit('confirmSync');
        }
    });

    socket.on('fullySynced', (synced) => {
        isFullySynced = synced;
        console.log('Sync status:', synced ? 'SYNCED' : 'NOT SYNCED');
    });

    socket.on('peerDisconnected', () => {
        hasRemoteData = false;
        isFullySynced = false;
        particles = [];
        lightningBolts = [];
        console.log('Peer disconnected, waiting for reconnection...');
    });

    socket.on('disconnect', () => {
        isConnected = false;
        hasRemoteData = false;
        isFullySynced = false;
        particles = [];
        lightningBolts = [];
        console.log('Disconnected from server');
    });
}

function isValidRemoteData(data) {
    return data && 
           typeof data.x === 'number' && 
           typeof data.y === 'number' && 
           typeof data.width === 'number' && data.width > 0 &&
           typeof data.height === 'number' && data.height > 0;
}

function checkWindowPosition() {
    currentPageData = {
        x: window.screenX,
        y: window.screenY,
        width: window.innerWidth,
        height: window.innerHeight
    };

    if (currentPageData.x !== previousPageData.x || currentPageData.y !== previousPageData.y || 
        currentPageData.width !== previousPageData.width || currentPageData.height !== previousPageData.height) {

        point2 = [currentPageData.width / 2, currentPageData.height / 2]
        socket.emit('win2update', currentPageData, socket.id);
        previousPageData = currentPageData; 
    }
}

// Calcular distancia entre las dos esferas
function calculateDistance(x1, y1, x2, y2) {
    return dist(x1, y1, x2, y2);
}

// Clase para partículas individuales
class Particle {
    constructor(x, y, targetX, targetY, col, isExplosion = false) {
        this.pos = createVector(x, y);
        this.col = col;
        this.alpha = 255;
        this.size = random(3, 8);
        this.isExplosion = isExplosion;
        
        if (isExplosion) {
            // Partículas de explosión: dirección aleatoria hacia afuera
            let angle = random(TWO_PI);
            let speed = random(3, 8);
            this.vel = createVector(cos(angle) * speed, sin(angle) * speed);
            this.life = 255;
        } else {
            // Partículas normales: van hacia el objetivo
            this.target = createVector(targetX, targetY);
            let direction = p5.Vector.sub(this.target, this.pos);
            direction.normalize();
            direction.mult(random(2, 4));
            this.vel = direction;
        }
    }
    
    update() {
        this.pos.add(this.vel);
        
        if (this.isExplosion) {
            this.life -= 3;
            this.alpha = this.life;
        } else {
            this.alpha -= 2;
        }
    }
    
    display() {
        noStroke();
        fill(this.col.levels[0], this.col.levels[1], this.col.levels[2], this.alpha);
        circle(this.pos.x, this.pos.y, this.size);
        
        // Glow effect
        fill(this.col.levels[0], this.col.levels[1], this.col.levels[2], this.alpha * 0.3);
        circle(this.pos.x, this.pos.y, this.size * 2);
    }
    
    isDead() {
        if (this.isExplosion) {
            return this.life <= 0;
        }
        return this.alpha <= 0;
    }
}

// Clase para rayos de luz
class LightningBolt {
    constructor(x, y) {
        this.pos = createVector(x, y);
        let angle = random(TWO_PI);
        let length = random(100, 250);
        this.endX = x + cos(angle) * length;
        this.endY = y + sin(angle) * length;
        this.segments = [];
        this.life = 255;
        this.generateSegments();
    }
    
    generateSegments() {
        let steps = 10;
        for (let i = 0; i <= steps; i++) {
            let t = i / steps;
            let x = lerp(this.pos.x, this.endX, t) + random(-10, 10);
            let y = lerp(this.pos.y, this.endY, t) + random(-10, 10);
            this.segments.push(createVector(x, y));
        }
    }
    
    update() {
        this.life -= 15;
    }
    
    display() {
        stroke(150, 50, 200, this.life);
        strokeWeight(3);
        noFill();
        beginShape();
        for (let seg of this.segments) {
            vertex(seg.x, seg.y);
        }
        endShape();
        
        // Glow
        stroke(200, 100, 255, this.life * 0.5);
        strokeWeight(6);
        beginShape();
        for (let seg of this.segments) {
            vertex(seg.x, seg.y);
        }
        endShape();
    }
    
    isDead() {
        return this.life <= 0;
    }
}

function draw() {
    // Fondo dinámico según distancia
    let bgColor = 220;
    
    if (!isConnected) {
        background(bgColor);
        showStatus('Conectando al servidor...', color(255, 165, 0));
        return;
    }
    
    if (!hasRemoteData) {
        background(bgColor);
        showStatus('Esperando conexión de la otra ventana...', color(255, 165, 0));
        return;
    }
    
    if (!isFullySynced) {
        background(bgColor);
        showStatus('Sincronizando datos...', color(255, 165, 0));
        return;
    }

    checkWindowPosition();
    
    // Calcular posiciones
    let vector2 = createVector(remotePageData.x, remotePageData.y);
    let vector1 = createVector(currentPageData.x, currentPageData.y);
    let resultingVector = createVector(vector2.x - vector1.x, vector2.y - vector1.y);
    
    let remoteX = resultingVector.x + remotePageData.width / 2;
    let remoteY = resultingVector.y + remotePageData.height / 2;
    
    // Calcular distancia entre esferas
    let distance = calculateDistance(point2[0], point2[1], remoteX, remoteY);
    
    // Oscurecer fondo según la cercanía
    if (distance < DISTANCE_CLOSE) {
        let darkness = map(distance, DISTANCE_CLOSE, 0, 220, 20);
        bgColor = darkness;
    }
    
    background(bgColor);
    
    // ESTADO 1: LEJOS - No hace nada
    if (distance > DISTANCE_FAR) {
        drawSphere(point2[0], point2[1], color(0, 100, 255), 75);
    }
    // ESTADO 2: DISTANCIA MEDIA - Lanzar partículas
    else if (distance > DISTANCE_CLOSE && distance <= DISTANCE_FAR) {
        drawSphere(point2[0], point2[1], color(0, 100, 255), 75);
        
        // Generar partículas azules hacia la otra esfera
        if (frameCount % 5 === 0) {
            particles.push(new Particle(point2[0], point2[1], remoteX, remoteY, color(0, 100, 255)));
        }
    }
    // ESTADO 3: MUY CERCA - Fusión y explosión
    else {
        // Calcular punto medio para la fusión
        let midX = (point2[0] + remoteX) / 2;
        let midY = (point2[1] + remoteY) / 2;
        
        // Dibujar esfera morada fusionada
        drawSphere(midX, midY, color(150, 50, 200), 100);
        
        // Generar partículas de explosión moradas
        if (frameCount % 2 === 0) {
            for (let i = 0; i < 3; i++) {
                particles.push(new Particle(midX, midY, 0, 0, color(150, 50, 200), true));
            }
        }
        
        // Generar rayos de luz morados
        if (frameCount % 8 === 0) {
            lightningBolts.push(new LightningBolt(midX, midY));
        }
    }
    
    // Actualizar y dibujar partículas
    for (let i = particles.length - 1; i >= 0; i--) {
        particles[i].update();
        particles[i].display();
        if (particles[i].isDead()) {
            particles.splice(i, 1);
        }
    }
    
    // Actualizar y dibujar rayos
    for (let i = lightningBolts.length - 1; i >= 0; i--) {
        lightningBolts[i].update();
        lightningBolts[i].display();
        if (lightningBolts[i].isDead()) {
            lightningBolts.splice(i, 1);
        }
    }
    
    // Mostrar info de debug
    fill(255);
    noStroke();
    textSize(12);
    textAlign(LEFT, TOP);
    text(`Distancia: ${distance.toFixed(0)}px`, 10, 10);
    text(`Partículas: ${particles.length}`, 10, 25);
    text(`Rayos: ${lightningBolts.length}`, 10, 40);
}

function showStatus(message, statusColor) {
    textSize(24);
    textAlign(CENTER, CENTER);
    noStroke();
    fill(0, 0, 0, 150);
    rectMode(CENTER);
    let textW = textWidth(message) + 40;
    let textH = 40;
    rect(width / 2, height / 6, textW, textH, 10);
    fill(statusColor);
    text(message, width / 2, height / 6);
}

function drawSphere(x, y, col, size) {
    // Glow exterior
    for (let i = 3; i > 0; i--) {
        noStroke();
        fill(col.levels[0], col.levels[1], col.levels[2], 30 / i);
        ellipse(x, y, size * (1 + i * 0.3), size * (1 + i * 0.3));
    }
    
    // Esfera principal
    fill(col);
    noStroke();
    ellipse(x, y, size, size);
    
    // Brillo interior
    fill(255, 255, 255, 100);
    ellipse(x - size * 0.15, y - size * 0.15, size * 0.3, size * 0.3);
}

function windowResized() {
    resizeCanvas(windowWidth, windowHeight);
}
~~~
[Video demostratativo](https://youtu.be/QGAP57zoyMA)
