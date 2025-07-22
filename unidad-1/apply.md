# Unidad 1

## 🛠 Fase: Apply

## Actividad 5
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
