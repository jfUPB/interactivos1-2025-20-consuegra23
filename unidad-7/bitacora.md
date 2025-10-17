
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

#### Explica con tus propias palabras: ¿Por qué es necesario Dev Tunnels en este escenario y cómo funciona conceptualmente?

Dev Tunnels es necesario en este escenario porque permite que el servidor local que corre en localhost:3000 sea accesible desde cualquier dispositivo, incluso si no está en la misma red. Esto es útil cuando se quiere probar una aplicación web desde un celular o compartirla con otros sin exponer directamente la IP local ni configurar el router. Conceptualmente, Dev Tunnels crea una URL pública que actúa como intermediario seguro entre Internet y el servidor local, reenviando las solicitudes entrantes al puerto correspondiente en la máquina del desarrollador.

#### Describe la función de touchMoved() y por qué se usa la variable threshold en el cliente móvil.

La función touchMoved() en p5.js se ejecuta continuamente mientras el usuario mantiene el dedo sobre la pantalla y lo mueve. Es útil para capturar gestos táctiles en tiempo real, como trazos o desplazamientos. La variable threshold se utiliza para evitar enviar datos por cada pequeño movimiento, lo que optimiza el rendimiento y reduce el tráfico de red. Solo se envía información si el cambio en la posición del toque supera cierto umbral, lo que indica un movimiento significativo y evita saturar la conexión con datos innecesarios.

#### Compara brevemente Dev Tunnels con simplemente usar la IP local. ¿Cuáles son las ventajas y desventajas de cada uno?

Usar la IP local permite acceder al servidor desde otro dispositivo solo si ambos están conectados a la misma red y no hay bloqueos por firewall. Es una solución rápida pero limitada a entornos privados. Dev Tunnels, en cambio, ofrece una URL pública accesible desde cualquier lugar, lo que facilita pruebas remotas y colaboración. La ventaja de Dev Tunnels es su accesibilidad global y seguridad integrada, mientras que su desventaja es la dependencia de servicios externos y posibles restricciones de velocidad o disponibilidad.

#### Coloca en tu bitácora capturas de pantalla del sistema completo funcionando. Esto lo puedes hacer abriendo tanto el mobile como el desktop en tu computador y tomando una captura de pantalla de todos los involucrados (celular, computador y terminal).
