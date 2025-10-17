
# Evidencias de la unidad 7


## Actividad 01

#### ¿Qué URL de Dev Tunnels obtuviste? ¿Por qué crees que necesitamos usar esta URL en lugar de http://localhost:3000 o la IP local de tu computador para que el celular se conecte?

El motivo por el que se requiere utilizar una URL diferente es por que los computadores disponibles en la universidad tienen un sistema de red privada que prohibe la conexion directa con aparatos externos, por lo que se utiliza una conexion por medio de minecrosoft devtunnel, lo que permite hacer la conexion entre la pagina de mobile y la de desktop

#### Describe brevemente qué hace npm install y npm start.
~~~bash
$ npm install

up to date, audited 89 packages in 1s

14 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities

~~~

~~~ bash
$ npm start

> sfinteractivesocketiodesktopmobile@1.0.0 start
> node server.js

Server is listening on http://localhost:3000
~~~

Como se puede observar la mayor diferencia es la cantidad de paquetes que se installan a comparacion ademas de la diferencia obvia del nombre antes de darle al start, de mientras no se presentan diferencia notables o anteriores

$ npm start

> sfinteractivesocketiodesktopmobile@1.0.0 start
> node server.js

Server is listening on http://localhost:3000

#### ¿Qué mensajes observaste en la terminal del servidor al conectar el cliente de escritorio y el cliente móvil? ¿Eran diferentes los mensajes o identificadores?
~~~ bash
$ npm start

> sfinteractivesocketiodesktopmobile@1.0.0 start
> node server.js

Server is listening on http://localhost:3000
New client connected
New client connected
~~~
#### Describe el comportamiento observado: ¿Funcionó la interacción? ¿Hubo algún retraso (latencia)?

~~~ bash
Received message => { type: 'touch', x: 172.977783203125, y: 176.1777801513672 }
Received message => { type: 'touch', x: 180.44444274902344, y: 172.977783203125 }
Received message => { type: 'touch', x: 185.7777862548828, y: 171.1999969482422 }
Received message => { type: 'touch', x: 171.55555725097656, y: 175.4666748046875 }
Received message => { type: 'touch', x: 164.44444274902344, y: 177.60000610351562 }
Received message => { type: 'touch', x: 171.55555725097656, y: 174.04444885253906 }
Received message => { type: 'touch', x: 190.04444885253906, y: 166.57778930664062 }
Received message => { type: 'touch', x: 207.4666748046875, y: 158.75555419921875 }
Received message => { type: 'touch', x: 218.84445190429688, y: 153.7777862548828 }
~~~
La interaccion funciona completamente tormal por ahora, presenta cierto retraso a la interaccion, ligeramente notable pero no altera su funcionamiento demasiado.

## Actividad 02

#### Explica con tus propias palabras: ¿Por qué es necesario Dev Tunnels en este escenario y cómo funciona conceptualmente?

Dev Tunnels es necesario en este escenario porque permite que el servidor local que corre en localhost:3000 sea accesible desde cualquier dispositivo, incluso si no está en la misma red. Esto es útil cuando se quiere probar una aplicación web desde un celular o compartirla con otros sin exponer directamente la IP local ni configurar el router. Conceptualmente, Dev Tunnels crea una URL pública que actúa como intermediario seguro entre Internet y el servidor local, reenviando las solicitudes entrantes al puerto correspondiente en la máquina del desarrollador.

#### Describe la función de touchMoved() y por qué se usa la variable threshold en el cliente móvil.

La función touchMoved() en p5.js se ejecuta continuamente mientras el usuario mantiene el dedo sobre la pantalla y lo mueve. Es útil para capturar gestos táctiles en tiempo real, como trazos o desplazamientos. La variable threshold se utiliza para evitar enviar datos por cada pequeño movimiento, lo que optimiza el rendimiento y reduce el tráfico de red. Solo se envía información si el cambio en la posición del toque supera cierto umbral, lo que indica un movimiento significativo y evita saturar la conexión con datos innecesarios.

#### Compara brevemente Dev Tunnels con simplemente usar la IP local. ¿Cuáles son las ventajas y desventajas de cada uno?

Usar la IP local permite acceder al servidor desde otro dispositivo solo si ambos están conectados a la misma red y no hay bloqueos por firewall. Es una solución rápida pero limitada a entornos privados. Dev Tunnels, en cambio, ofrece una URL pública accesible desde cualquier lugar, lo que facilita pruebas remotas y colaboración. La ventaja de Dev Tunnels es su accesibilidad global y seguridad integrada, mientras que su desventaja es la dependencia de servicios externos y posibles restricciones de velocidad o disponibilidad.

#### Coloca en tu bitácora capturas de pantalla del sistema completo funcionando. Esto lo puedes hacer abriendo tanto el mobile como el desktop en tu computador y tomando una captura de pantalla de todos los involucrados (celular, computador y terminal).
<img width="352" height="428" alt="image" src="https://github.com/user-attachments/assets/c80a8271-b101-4a3f-beee-33210878ee36" />

![Imagen de WhatsApp 2025-10-16 a las 20 49 20_4cec64ba](https://github.com/user-attachments/assets/639d03be-9431-47f0-ba93-e81f8a8aef49)

<img width="583" height="375" alt="image" src="https://github.com/user-attachments/assets/d4a4d011-3e3b-46ee-b9b9-40347b8a53c7" />

## Actividad 03

#### ¿Cuál es la función principal de express.static(‘public’) en este servidor? ¿Cómo se compara con el uso de app.get(‘/ruta’, …) del servidor de la Unidad 6?

express.static('public') sirve automáticamente todos los archivos de la carpeta public/ manteniendo su estructura (ej: public/index.html → /index.html), mientras que app.get('/page1', ...) define rutas explícitas y personalizadas donde tú decides qué URL sirve qué archivo específico (ej: /page1 → views/page1.html). La diferencia clave es que static es automático y expone toda la carpeta, mientras que app.get() te da control manual sobre cada ruta permitiéndote crear URLs limpias sin extensiones y agregar lógica adicional. En EntangledTest se usan ambos: static para servir assets generales de la carpeta views/ y app.get() para crear rutas específicas y legibles como /page1 y /page2 en lugar de /page1.html.

#### Explica detalladamente el flujo de un mensaje táctil: ¿Qué evento lo envía desde el móvil? ¿Qué evento lo recibe el servidor? ¿Qué hace el servidor con él? ¿Qué evento lo envía el servidor al escritorio? ¿Por qué se usa socket.broadcast.emit en lugar de io.emit o socket.emit en este caso?

Cuando un usuario mueve su dedo sobre la pantalla del móvil, se dispara el evento touchMoved() de p5.js. Este evento verifica que el movimiento supere el umbral mínimo de 5 píxeles para evitar enviar demasiados mensajes, y luego crea un objeto con las coordenadas del toque. Una vez preparado, el cliente móvil lo envía al servidor usando socket.emit con el canal message, que es el nombre del evento personalizado que definimos para esta comunicación.

El servidor recibe este evento message mediante su handler socket.on y captura los datos del toque. Aquí es donde entra la diferencia crucial en los métodos de emisión: usa socket.broadcast.emit para retransmitir el mensaje a todos los clientes conectados excepto al que lo envió. Si usara socket.emit, solo devolvería el mensaje al móvil creando un eco inútil. Si usara io.emit, lo enviaría a todos incluyendo el móvil original, lo cual sería redundante. Con broadcast, el mensaje viaja exclusivamente a los otros clientes, que en este caso es el escritorio, quien actualiza las coordenadas del círculo rojo con los valores recibidos.

#### Si conectaras dos computadores de escritorio y un móvil a este servidor, y movieras el dedo en el móvil, ¿Quién recibiría el mensaje retransmitido por el servidor? ¿Por qué?

Si conectaras dos computadores de escritorio y un móvil a este servidor, y movieras el dedo en el móvil, ambos computadores de escritorio recibirían el mensaje retransmitido por el servidor porque socket.broadcast.emit envía el mensaje a todos los clientes conectados excepto al emisor original, que en este caso es el móvil. El servidor no distingue entre tipos de clientes ni tiene lógica para filtrar destinatarios específicos, simplemente retransmite a todos los demás sockets conectados identificados por sus IDs únicos. Por lo tanto, ambos computadores verían el círculo rojo moviéndose simultáneamente en la misma posición, creando una experiencia sincronizada entre todos los clientes que no sean el emisor original.

#### ¿Qué información útil te proporcionan los mensajes console.log en el servidor durante la ejecución?

Los mensajes console.log en el servidor proporcionan información vital para monitorear el estado y la actividad de las conexiones en tiempo real. Cuando un cliente se conecta, el servidor registra su ID único y el número total de conexiones activas, permitiéndote saber cuántos dispositivos están conectados y detectar problemas de conectividad. Durante la transmisión de mensajes, los logs muestran exactamente qué datos están viajando, verificando que las coordenadas del toque se envían correctamente. Cuando un cliente se desconecta, el servidor registra qué socket se desconectó y la razón, lo cual es crucial para diagnosticar si fueron desconexiones normales o errores de red.

#### Actividad 04

#### Realiza un diagrama donde muestres el flujo completo de datos y eventos entre los tres componentes: móvil, servidor y escritorio. Puedes ilustrar con un ejemplo de coordenadas táctiles (x, y) y cómo viajan a través del sistema.

#### Actividad 05

<img width="4500" height="3000" alt="image" src="https://github.com/user-attachments/assets/cb61f964-0275-43cc-b25c-17a22bd8b8d5" />
<img width="558" height="371" alt="image" src="https://github.com/user-attachments/assets/a6d1669f-23aa-41a7-8e96-77165ce57b38" />
<img width="669" height="447" alt="image" src="https://github.com/user-attachments/assets/238ba2af-90e6-4051-afe7-d3b59d7b3539" />

La base de la aplicacion esta completamente basada en la cancion [Look a Like](https://youtu.be/ZK82EmKzXEk?list=RDZK82EmKzXEk) de la Ova de sonic de 1996, El plan es usar el coro de la cancion en la que canta repetidamente "On a sunday riding my bike, I notice, I notice, Diferent things that look a like" Tomando literalmente a un muchacho montando una bicicleta con un fondo el cual puede ser modificado dividiendo el mobile en 3 secciones, manejando suave, manejando medio, y manejando rapido, haciendo que el fondo cambie mientras mas rapido va.
Todo el fondo debe estar haciendo bouncing al ritmo de la cancion
Desktop
~~~ js
let socket;
let currentSpeed = 0;
let targetSpeed = 0;
let roadRotation = 0;
let pedalAngle = 0;
let leftLegAngle = 0;
let rightLegAngle = 0;
let backgroundY = 0;
let newBackgroundY = -600;
let isTransitioning = false;
let transitionProgress = 0;
let previousMode = 'medium';
let currentMode = 'medium';
let song;
let fft;
let amplitude;
let buildings = [];
let trees = [];
let waveOffset = 0;
let sunRayAngle = 0;
let beatCounter = 0;
let lastBeatTime = 0;

function preload() {
    song = loadSound('BikeSong.mp3');
}

function setup() {
    createCanvas(400, 600);
    socket = io();
    
    fft = new p5.FFT(0.8, 256);
    amplitude = new p5.Amplitude();
    
    // Edificios
    for (let i = 0; i < 12; i++) {
        buildings.push({
            x: (width / 12) * i + random(-10, 10),
            y: 0,
            w: width / 12 + random(5, 15),
            h: random(200, 450),
            baseY: 0
        });
    }
    
    // Árboles
    for (let i = 0; i < 15; i++) {
        trees.push({
            x: random(-100, width + 100),
            y: 400, // ligeramente más abajo
            baseX: 0,
            swayAngle: random(TWO_PI),
            swayOffset: random(0, TWO_PI)
        });
    }

    socket.on('connect', () => {
        console.log('Connected to server');
        userStartAudio();
        if (song && !song.isPlaying()) {
            song.loop();
            song.setVolume(0.5);
        }
    });

    socket.on('message', (data) => {
        if (data && data.type === 'speed') {
            targetSpeed = data.speed;
        }
    });

    socket.on('disconnect', () => {
        console.log('Disconnected from server');
    });
}

function draw() {
    let level = amplitude.getLevel();
    let spectrum = fft.analyze();
    let bass = fft.getEnergy("bass");
    let treble = fft.getEnergy("treble");
    let mid = fft.getEnergy("mid");
    
    currentSpeed = lerp(currentSpeed, targetSpeed, 0.1);
    
    if (currentSpeed < 0.2) {
        currentMode = 'slow';
    } else if (currentSpeed < 0.7) {
        currentMode = 'medium';
    } else {
        currentMode = 'fast';
    }
    
    if (currentMode !== previousMode) {
        previousMode = currentMode;
        isTransitioning = true;
        transitionProgress = 0;
        backgroundY = 0;
        newBackgroundY = -600;
    }
    
    if (isTransitioning) {
        transitionProgress += 0.03;
        if (transitionProgress >= 1) {
            isTransitioning = false;
            transitionProgress = 0;
            backgroundY = 0;
            newBackgroundY = -600;
        }
    }
    
    push();
    translate(0, backgroundY);
    drawBackground(previousMode, level, bass, treble, mid);
    pop();
    
    if (isTransitioning) {
        push();
        translate(0, newBackgroundY + transitionProgress * 600);
        drawBackground(currentMode, level, bass, treble, mid);
        pop();
        backgroundY += 15;
    }
    
    drawRoad(currentSpeed);
    drawCyclist(currentSpeed, level);
}

function drawBackground(mode, level, bass, treble, mid) {
    if (mode === 'slow') {
        background(150, 200, 255);
        
        let musicPush = map(bass, 0, 255, -40, 40);
        
        for (let building of buildings) {
            fill(80 + random(-10, 10), 80 + random(-10, 10), 80 + random(-10, 10));
            stroke(60);
            strokeWeight(2);
            
            let buildingY = height - building.h + musicPush;
            rect(building.x, buildingY, building.w, building.h);
            
            let windowCols = floor(building.w / 25);
            let windowRows = floor(building.h / 45);
            
            for (let w = 0; w < windowCols; w++) {
                for (let h = 0; h < windowRows; h++) {
                    if (random() > 0.3) {
                        fill(255, 255, 150, 150);
                        rect(building.x + 5 + w * 25, buildingY + 10 + h * 45, 15, 30);
                    }
                }
            }
        }
    } 
    
    else if (mode === 'medium') {
        background(135, 206, 235);

        // 🌳 Árboles más grandes e inclinándose desde la base
        let tiltAmount = map(mid, 0, 255, -15, 15);
        
        for (let tree of trees) {
            tree.swayAngle += 0.05;
            let tilt = sin(tree.swayAngle + tree.swayOffset) * tiltAmount;

            push();
            translate(tree.x, tree.y);
            rotate(radians(tilt));
            
            // Pivot visual en la base
            translate(0, -100);

            // Tronco más grande
            fill(139, 69, 19);
            noStroke();
            rect(-10, 0, 20, 120);

            // Copas más grandes
            fill(255, 140, 0);
            circle(0, -60, 130);
            circle(-40, -80, 90);
            circle(40, -80, 90);

            pop();

            // Movimiento lateral
            tree.x -= 1 + currentSpeed * 2;
            if (tree.x < -100) {
                tree.x = width + 100;
            }
        }
    } 
    
    else if (mode === 'fast') {
        background(135, 206, 250);
        
        // ☀️ Sol estático con rayos suaves
        fill(255, 255, 150);
        noStroke();
        circle(width - 80, 100, 140);

        // 🌊 Mar restaurado al estado original (sin reacción al audio)
        fill(0, 0, 139);
        noStroke();
        beginShape();
        vertex(0, 350);
        for (let x = 0; x <= width; x += 10) {
            let y = 350 + sin(x * 0.05 + waveOffset) * 40; // altura fija
            vertex(x, y);
        }
        vertex(width, height);
        vertex(0, height);
        endShape(CLOSE);

        fill(0, 0, 180);
        beginShape();
        vertex(0, 380);
        for (let x = 0; x <= width; x += 10) {
            let y = 380 + sin(x * 0.04 + waveOffset + 2) * 30; // altura fija
            vertex(x, y);
        }
        vertex(width, height);
        vertex(0, height);
        endShape(CLOSE);

        waveOffset += 0.08; // velocidad constante
    }
}

function drawRoad(speed) {
    push();
    translate(width / 2, height + 160);
    rotate(roadRotation);
    
    fill(60);
    noStroke();
    circle(0, 0, 800);
    
    stroke(255, 255, 0);
    strokeWeight(15);
    noFill();
    for (let i = 0; i < 12; i++) {
        let angle = (TWO_PI / 12) * i;
        arc(0, 0, 770, 770, angle, angle + PI / 16);
    }
    
    pop();
    
    roadRotation += 0.005 + speed * 0.1;
}

function drawCyclist(speed, musicLevel) {
    push();
    translate(width / 2, height - 320);
    
    let bodyY = -sin(pedalAngle) * 3;
    
    stroke(120, 140, 150);
    strokeWeight(4);
    line(-35, 60, 5, 30);
    line(5, 30, 35, 60);
    line(-15, 45, 15, 45);
    line(5, 30, 5, 10);
    
    noStroke();
    fill(50);
    circle(-35, 60, 50);
    circle(35, 60, 50);
    
    fill(255, 255, 0);
    circle(-35, 60, 20);
    circle(35, 60, 20);
    
    fill(100, 70, 50);
    ellipse(5, 10, 35, 12);
    
    leftLegAngle = pedalAngle;
    rightLegAngle = pedalAngle + PI;
    
    let leftPedalX = cos(leftLegAngle) * 18;
    let leftPedalY = sin(leftLegAngle) * 18;
    let rightPedalX = cos(rightLegAngle) * 18;
    let rightPedalY = sin(rightLegAngle) * 18;
    
    stroke(0, 200, 0);
    strokeWeight(12);
    line(0, 20 + bodyY, leftPedalX, 45 + leftPedalY);
    line(0, 20 + bodyY, rightPedalX, 45 + rightPedalY);
    
    stroke(0);
    strokeWeight(3);
    line(5, 45, leftPedalX, 45 + leftPedalY);
    line(5, 45, rightPedalX, 45 + rightPedalY);
    
    fill(0);
    noStroke();
    circle(leftPedalX, 45 + leftPedalY, 10);
    circle(rightPedalX, 45 + rightPedalY, 10);
    
    pedalAngle += 0.02 + speed * 0.15;
    
    noStroke();
    fill(0, 255, 0);
    
    if (speed < 0.3) {
        ellipse(0, 10 + bodyY, 50, 70);
    } else if (speed < 0.7) {
        ellipse(0, 0 + bodyY, 50, 70);
    } else {
        push();
        translate(5, 5 + bodyY);
        rotate(radians(15));
        ellipse(0, 0, 60, 45);
        pop();
    }
    
    fill(245, 220, 180);
    strokeWeight(10);
    stroke(245, 220, 180);
    
    if (speed < 0.7) {
        line(0, 15 + bodyY, 25, 25);
    } else {
        line(5, 10 + bodyY, 35, 15);
    }
    
    noStroke();
    fill(245, 220, 180);
    circle(0, -25 + bodyY, 45);
    
    fill(0);
    ellipse(-8, -28 + bodyY, 4, 6);
    ellipse(8, -28 + bodyY, 4, 6);
    
    if (speed > 0.7) {
        arc(0, -20 + bodyY, 18, 12, 0, PI);
    } else {
        arc(0, -18 + bodyY, 15, 10, 0, PI);
    }
    
    pop();
}

function mousePressed() {
    userStartAudio();
    if (song && !song.isPlaying()) {
        song.loop();
        song.setVolume(0.5);
    }
}

function keyPressed() {
    if (key === ' ') {
        if (song && song.isPlaying()) {
            song.pause();
        } else if (song) {
            song.loop();
            song.setVolume(0.5);
        }
    }
}
~~~ 
Mobile
~~~ js
let socket;
let centerX, centerY;
let previousAngle = null;
let angularVelocity = 0;
let speedValue = 0;
let touches = [];

function setup() {
    createCanvas(400, 600);
    centerX = width / 2;
    centerY = height / 2;
    
    socket = io();

    socket.on('connect', () => {
        console.log('Connected to server');
    });

    socket.on('message', (data) => {
        console.log('Received message:', data);
    });

    socket.on('disconnect', () => {
        console.log('Disconnected from server');
    });

    socket.on('connect_error', (error) => {
        console.error('Socket.IO error:', error);
    });
}

function draw() {
    background(40);
    
    angularVelocity *= 0.85;
    speedValue = constrain(angularVelocity * 15, 0, 1);
    
    if (!touches.length) {
        speedValue *= 0.9;
    }
    
    fill(60);
    noStroke();
    circle(centerX, centerY, 280);
    
    stroke(100);
    strokeWeight(2);
    noFill();
    for (let i = 0; i < 12; i++) {
        let angle = (TWO_PI / 12) * i;
        let x1 = centerX + cos(angle) * 120;
        let y1 = centerY + sin(angle) * 120;
        let x2 = centerX + cos(angle) * 140;
        let y2 = centerY + sin(angle) * 140;
        line(x1, y1, x2, y2);
    }
    
    let speedColor = lerpColor(
        color(100, 100, 255),
        color(255, 50, 50),
        speedValue
    );
    fill(speedColor);
    noStroke();
    circle(centerX, centerY, 240);
    
    fill(255);
    textAlign(CENTER, CENTER);
    textSize(32);
    text('Gira el dedo', centerX, centerY - 40);
    textSize(24);
    text('para acelerar', centerX, centerY);
    
    let speedPercent = int(speedValue * 100);
    textSize(48);
    fill(255, 255, 100);
    text(speedPercent + '%', centerX, centerY + 50);
    
    fill(socket && socket.connected ? 0 : 255, socket && socket.connected ? 255 : 0, 0);
    noStroke();
    circle(30, 30, 20);
    
    textAlign(LEFT, TOP);
    textSize(14);
    fill(200);
    text(socket && socket.connected ? 'Conectado' : 'Desconectado', 55, 22);
}

function touchStarted() {
    touches = [];
    for (let i = 0; i < touches.length; i++) {
        touches.push({x: touches[i].x, y: touches[i].y});
    }
    previousAngle = null;
    return false;
}

function touchMoved() {
    if (socket && socket.connected) {
        let dx = mouseX - centerX;
        let dy = mouseY - centerY;
        let distance = dist(mouseX, mouseY, centerX, centerY);
        
        if (distance > 40 && distance < 140) {
            let currentAngle = atan2(dy, dx);
            
            if (previousAngle !== null) {
                let angleDiff = currentAngle - previousAngle;
                
                if (angleDiff > PI) angleDiff -= TWO_PI;
                if (angleDiff < -PI) angleDiff += TWO_PI;
                
                angularVelocity = abs(angleDiff) * 0.5;
                speedValue = constrain(angularVelocity * 15, 0, 1);
                
                let speedData = {
                    type: 'speed',
                    speed: speedValue
                };
                
                socket.emit('message', speedData);
            }
            
            previousAngle = currentAngle;
        }
    }
    return false;
}

function touchEnded() {
    touches = [];
    previousAngle = null;
    
    if (socket && socket.connected) {
        let speedData = {
            type: 'speed',
            speed: 0
        };
        socket.emit('message', speedData);
    }
    return false;
}

function mousePressed() {
    touchStarted();
    return false;
}

function mouseDragged() {
    touchMoved();
    return false;
}

function mouseReleased() {
    touchEnded();
    return false;
}
~~~
El codigo funciona, pues este detecta la velocidad con la que se da vueltas en el mobile, reaccionando ante la velocidad y cambiando el escenario, el escenario reacciona a diferentes partes de la cancion los edificios a el Bass subiendo y bajando, Los arboles reaccionan inclinandose al ritmo del middle y el mar reacciona a el treable.

## Autoevaluacion

#### Actividad 01:
Como la parte mas crucial de esta unidad yo creo que la hice correctamente completa y creo que mi aprendizaje en esta unidad fue bastante alto 5/5
#### Actividad 02:
Esta tambien la siento muy bien explicada y sobretodo completa en cuanto a la manera en la que respondi a las preguntas, considero otra bastante lograda 5/5
#### Activiad 03:
Aunque mas resumida que la anterior considero que esta esta tambien bastante lograda los conceptos quedaron claros en mi cabeza y siento que se consiguio la meta 4/5
#### Actividad 04:
no realizada 0/5
#### Actividad 05:
Con esta tengo un problema personal, pues siento que el resultado tan impresinonante que salio de la unidad anterior tenia que ser superado por esta, pues no siento que lo que hice cumpla con mis estandares a pesar de funcionar con lo que se me requirio y correr correctamente, considero que pudo a ver sido mucho mejor de mi parte, sobre todo en el diseño 4/5
