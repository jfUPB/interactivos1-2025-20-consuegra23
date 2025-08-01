# Unidad 2

## 🔎 Fase: Set + Seek

### Unidad 1

#### 1.

Este ejemplo funciona haciendo que dos pixeles en la pantalla del micro\:bit parpadeen de manera independiente, para esto se crea una clase llamada Pixel que guarda información sobre la posición del pixel, el estado en el que se encuentra, el tiempo en el que inició y el intervalo que debe esperar antes de cambiar, cuando se inicia el código se crean dos objetos de esta clase, uno en la esquina superior izquierda que parpadea cada segundo y otro en la esquina inferior derecha que parpadea cada medio segundo, luego en el ciclo principal se llama todo el tiempo a la función update de cada pixel para verificar si ya pasó el intervalo de tiempo, si pasó entonces el pixel alterna entre encendido y apagado generando el efecto de parpadeo.

#### 2.

Los estados en el programa son Init y WaitTimeout, Init es cuando el pixel apenas empieza a funcionar, se guarda el tiempo inicial y se enciende el pixel por primera vez, luego pasa al estado WaitTimeout en el que espera hasta que se cumpla el intervalo de tiempo, cuando el intervalo se cumple cambia el estado del pixel entre apagado y encendido y sigue en este mismo estado esperando la siguiente alternancia.

#### 3.
Los eventos o inputs que se manejan en este programa no vienen de botones ni sensores sino del paso del tiempo que se mide en milisegundos, cuando la diferencia de tiempo entre el momento actual y el tiempo de inicio supera el intervalo que tiene definido cada pixel eso se toma como un evento que activa el cambio de estado del pixel.

#### 4.
Las acciones en el programa son prender un pixel con intensidad 9 o apagarlo poniéndolo en intensidad 0 y alternar entre estas dos acciones cada vez que pasa el tiempo de espera, esto se hace para cada pixel por separado logrando que parpadeen de forma independiente en la pantalla del micro\:bit.
### Unidad 2
