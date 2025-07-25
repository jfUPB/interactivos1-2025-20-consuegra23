# Unidad 1

## 🛠 Fase: Apply

## Actividad 5
### explica cómo funciona el sistema físico interactivo que acabamos de crear. 
El sistema funciona por medio de el Micro:bit que en su codigo de Phython constantemente esta preguntanto si se esta precionando el boton a, en caso de lo contrario el mandara una señal N, si este boton fue presionado mandara una señal A, estos son los outputs del programa, como input el programa de p5.js primero forma un canvas y pregunta por el micro:bit al este estar conectado el programa recibira los inputs y analizara que letra se esta enviando, al recibir una N generara un cuadrado de color verde, pero mientras reciba una A este cambiara el anterior por un cuadrado rojo.
## Actividad 6
https://editor.p5js.org/consuegra23/sketches/QZBxIda-D 
~~~ js
let port;
let connectBtn;
let connectionInitialized = false;
let x = 200;
 
function setup() {
  createCanvas(400, 400);
  background(220);
  port = createSerial();
  connectBtn = createButton("Connect to micro:bit");
  connectBtn.position(80, 300);
  connectBtn.mousePressed(connectBtnClick);
}
 
function draw() {
  background(220);
 
  if (port.opened() && !connectionInitialized) {
    port.clear();
    connectionInitialized = true;
  }
 
  if (port.availableBytes() > 0) {
    let dataRx = port.read(1);
    if (dataRx === "A") {
      x -= 20;
    } else if (dataRx === "B") {
      x += 20;
    }
  }
 
  fill("blue");
  circle(x, 200, 50);
 
  if (!port.opened()) {
    connectBtn.html("Connect to micro:bit");
  } else {
    connectBtn.html("Disconnect");
  }
}
 
function connectBtnClick() {
  if (!port.opened()) {
    port.open("MicroPython", 115200);
    connectionInitialized = false;
  } else {
    port.close();
  }
}
~~~
~~~ py
from microbit import *

uart.init(baudrate=115200)
display.show(Image.ARROW_E)
while True:

    if button_a.is_pressed():
        uart.write('A')
    if button_b.is_pressed():
        uart.write('B')
    sleep(100)
~~~
