
# Evidencias de la unidad 5

## Actividad 01
¿Cómo se están comunicando el micro:bit y el sketch de p5.js?

La comunicación entre el micro:bit y el sketch de p5.js se realiza mediante un puerto serial utilizando UART a 115200 baudios. El micro:bit envía datos en formato ASCII cada 100 milisegundos, y el sketch de p5.js los recibe, interpreta y utiliza para generar visuales en pantalla. Esta estructura permite que ambos sistemas trabajen de forma concurrente, ya que mientras se dibuja en pantalla, también se están leyendo datos y respondiendo a eventos físicos como la inclinación del dispositivo o la presión de botones.

¿Que datos envia el micro:bit?

El micro:bit constantemente esta enviando 4 datos xValue,yValue,aState,bState que determinan su posicion por medio del acelerometro en Y y en X ademas del estado de los botones A y B si estan presionados o no

¿Cómo es la estructura del protocolo ASCII usado?

El protocolo es una cadena de texto con formato CSV (valores separados por comas), terminada en salto de línea. Ejemplo:
-123,456,True,False\n
Este formato permite que el sketch de p5.js pueda dividir fácilmente la cadena en partes, convertir los valores a números o booleanos, y usarlos para controlar la visualización gráfica.

¿Cómo se lee y transforma la información en p5.js?

En el bloque draw() del sketch de p5.js, se encuentra el siguiente fragmento:
~~~ js
if (port.availableBytes() > 0) {
  let data = port.readUntil("\n");
  if (data) {
    data = data.trim();
    let values = data.split(",");
    if (values.length == 4) {
      microBitX = int(values[0]) + windowWidth / 2;
      microBitY = int(values[1]) + windowHeight / 2;
      microBitAState = values[2].toLowerCase() === "true";
      microBitBState = values[3].toLowerCase() === "true";
      updateButtonStates(microBitAState, microBitBState);
    }
  }
}
~~~

Aquí se realiza lo siguiente:

En el sketch de p5.js, la lectura de datos desde el micro:bit se realiza dentro del ciclo draw(), donde se verifica si hay bytes disponibles en el puerto serial. Cuando se detecta una línea completa, se elimina cualquier espacio innecesario y se divide la cadena en cuatro partes usando la coma como separador. Los dos primeros valores, correspondientes al eje X e Y del acelerómetro, se convierten en coordenadas de pantalla al sumarse con la mitad del ancho y alto de la ventana, lo que permite centrar el sistema de referencia. Los dos últimos valores, que indican el estado de los botones A y B, se transforman en booleanos reales comparando si el texto recibido es "true". Finalmente, se llama a la función updateButtonStates() para procesar los cambios de estado y generar los eventos correspondientes.

¿Cómo se generan los eventos A pressed y B released en p5.js?

Los eventos se generan mediante una comparación entre el estado actual y el estado anterior de los botones A y B. En la función updateButtonStates(), si el botón A está presionado y en el ciclo anterior no lo estaba, se interpreta como un evento de "A pressed", lo que activa acciones como definir una nueva longitud para el módulo gráfico y registrar la posición actual del micro:bit. Por otro lado, si el botón B deja de estar presionado y en el ciclo anterior sí lo estaba, se genera el evento "B released", que cambia el color del trazo a uno aleatorio. Esta lógica basada en transiciones permite detectar eventos de forma precisa y mantener una interacción fluida entre el micro:bit y el entorno gráfico, sin detener la ejecución general del programa.
<img width="559" height="448" alt="image" src="https://github.com/user-attachments/assets/b7e07e1f-7135-4031-ad00-614aeb3e2e31" />
<img width="559" height="511" alt="image" src="https://github.com/user-attachments/assets/e3d005f1-e2f6-41a3-a2e0-6fd3d36eedbb" />

## Actividad 2
Al momento de ver el serial y compararlo con otros serial de otros codigos, puedo observar enseguida que a pesar de tener limitado el volumen de datos a 115200 baudios no sabria describir el por que siento que la informacion se manda a una mayor velocidad, asumo pues no soy yo una computadora que pueda analizar estos datos, que al ser binario o hexadecimal reduce la cantidad de procesos que tiene que hacer el pc pues no tiene que traducir los datos que esta recibiendo para poder utilizarlos.

como desventaja inmediata es la incapacidad de leer los datos, sobre todo durante el primer codigo pues el barraje de mensajes con numeros que no entendia eran indecifrables, ya con el segundo puedo minimo entender los paquetes de informacion que esta mandando pues se ven que son 6 bytes de informacion por paquete al hacer la accion de shake y asumo que se pueden traducir pero debido a que yo no se nada de hexadecimal no soy capaz de decodificarlos

¿Cuántos bytes se están enviando por mensaje?

Se están enviando 6 bytes por cada mensaje.

Esto se debe al uso de la función struct.pack con el formato '>2h2B', que empaqueta los datos en binario de acuerdo con el siguiente desglose:

>: indica que los datos se codifican en big-endian (orden de bytes más significativo primero).
2h: dos valores tipo short (entero de 16 bits, 2 bytes cada uno).
2B: dos valores tipo unsigned char (entero de 8 bits, 1 byte cada uno).
Entonces:

2h → 2 × 2 bytes = 4 bytes
2B → 2 × 1 byte = 2 bytes
Total: 4 + 2 = 6 bytes
¿Qué significa cada uno de los bytes que se envían?

Cada mensaje contiene los siguientes datos:

Bytes 0-1: valor del eje X del acelerómetro (xValue) como entero de 16 bits.
Bytes 2-3: valor del eje Y del acelerómetro (yValue) como entero de 16 bits.
Byte 4: estado del botón A (aState) como entero de 8 bits (0 o 1).
Byte 5: estado del botón B (bState) como entero de 8 bits (0 o 1).
Estos datos se envían en formato binario, lo que permite una transmisión más eficiente que el uso de texto ASCII, especialmente útil cuando se requiere velocidad o se trabaja con recursos limitados.

A pesar de las desventajas mencionadas las ventajas son claras, binario es infintamente mas rapido, pues manda los datos muchisimo mas rapido y pesando infinitamente menos, pues los 6 bytes que utilizamos en enviarlo son 21 bytes o mas cuando lo hacemos en ascii me gustaria probar si aquel programa que hice la unidad pasada seria mucho mas rapido si los datos se enviaran en binario pues este tenia problemas de rendimiento
## Actividad 3
