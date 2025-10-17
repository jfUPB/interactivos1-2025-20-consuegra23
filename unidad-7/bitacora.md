
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
La base de la aplicacion esta completamente basada en la cancion https://www.youtube.com/watch?v=ZK82EmKzXEk&list=RDZK82EmKzXEk&start_radio=1
