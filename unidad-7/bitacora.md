
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
