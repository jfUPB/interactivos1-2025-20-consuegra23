# Unidad 2


## 🤔 Fase: Reflect
### Actividad 6
#### Parte 1:
1.Describe con tus palabras qué es una máquina de estados. ¿Cuáles son sus cuatro componentes fundamentales que has utilizado en esta unidad?

Accion, Estado, Evento y Reaccion/Resultado

2.Explica por qué la técnica de máquina de estados es tan útil para gestionar la “concurrencia” (atender un temporizador y botones “al mismo tiempo”) en un dispositivo con un solo hilo de ejecución como el micro:bit. ¿Qué problema soluciona en comparación con usar funciones como sleep()?

Al utlizar una maquida de estados podemos determinar resultados concretos que se apliquen a condiciones especificas y facilitar el planteamiento del codigo, en cunato a que problemas soluciona que sleep no puede hacer, seria por ejemplo realizar acciones simultaneas mientras se espera el resultado, como mostrar pantallas de carga o interacciones mientras se espera al resultado determinado.

3. Imagina que tienes que añadir una nueva funcionalidad a la bomba temporizada: si se agita (shake) el micro:bit mientras la cuenta regresiva está activa, el tiempo se reduce a la mitad. ¿Cómo modificarías tu diagrama de máquina de estados para incluir este nuevo evento y acción?

Pondria una funcion Update que este revisando cada frame si esta siendo agitada la bomba que realizo en caso de eso, se genere un nuevo tick que posea la mitad del tiempo que le faltaba al contador anterior 
   
4. Explica qué es un “vector de prueba” y por qué es una herramienta crucial para verificar que una máquina de estados funciona como se espera.

Esta herramienta que utiliza los diagramas de estados pues formulamos teoricamente lo que supuestamente tiene que hacer el codigo y la manera en la que debe responder, esto es crucial pues nos permite identificar bugs o reaciciones inusuales.
   
#### Parte 2: reflexión sobre tu proceso (Metacognición)

1.¿Qué parte del diseño de la bomba temporizada te resultó más desafiante: crear el diagrama de estados (Actividad 04) o traducir ese diagrama a código MicroPython (Actividad 05)? ¿Por qué?

traducir el diagrama a codigo MicroPython, pues realize que en el codigo mostrara una funcion que llenara una fila de leds mientras estuviera contando, lo que requirio investigacion y planteamiento ademas de aprender a utilizar funcilones que no recorbada y fueron utiles para esto, en este caso el for que no sabia como aplicarlo en phyton

2.Describe un error o “bug” que encontraste al implementar tu programa. ¿Cómo te ayudó pensar en términos de estados, eventos y transiciones a identificar y solucionar el problema?

cuando estaba creando el semaforo tuve un problema al momento de implementar pues debido a la manera en la que se creo el codigo, con intervencion de inteligencia artificial no fui capaz de resolver que pasara de rojo a amarillo a verde, lo que provoco que no usara mas inteligencia artificial despues pues este problema provocaba que las luces parpadearan y se saltaran de un estado a otro incorrectamente.

3.El problema de la bomba era complejo. ¿Qué estrategia usaste para abordarlo? ¿Comenzaste con una versión simple y añadiste funcionalidades poco a poco?

Fue un trabajo de mucho planteamiento y desarrollo, pues una vez diseñado el diagrama el siguiente paso que fue programar fue de estado A a B pues pasaba individualmente en el orden de los estados para formularlos y completarlos al 100% antes de pasar al siguiente.

4.Ahora que entiendes el patrón de máquina de estados, ¿En qué otro tipo de proyecto o sistema de entretenimiento digital crees que podrías aplicarlo?

Veo la maquina de estados muy planteable en sistemas que sean por ejemplo para eventos en vivo pues de las reacciones de la gente digamos en un concierto o en una cancion en especifica se podria cambiar automaticamente de ambiente dando una experiencia mucho mas inmersiva.

Actividad 8

En el diagrama de la bomba planteamos una solucion muy parecida mas mi compañero tuvo una capacidad de organizacion mayor a la que yo tuve, ademas en su codigo el no presento ningun feedback a que la bomba estaba armada como lo hice yo, pero fue un trabajo muy bueno que realizo pues yo opino que es mucho mas efectivo que mi trabajo pues le tomo menos lineas hacer lo mismo.
