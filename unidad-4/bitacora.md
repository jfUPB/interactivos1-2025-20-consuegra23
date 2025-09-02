# Evidencias de la unidad 4

## Código

[Enlace a la aplicación a modificar](URL)

Código a modificar:

``` js
'use strict';

var tileCount = 10;

var tileWidth;
var tileHeight;
var shapeSize = 50;
var newShapeSize = shapeSize;
var shapeAngle = 0;
var maxDist;
var currentShape;
var shapes;

var sizeMode = 0;

function preload() {
  shapes = [];
  shapes.push(loadImage('data/module_1.svg'));
  shapes.push(loadImage('data/module_2.svg'));
  shapes.push(loadImage('data/module_3.svg'));
  shapes.push(loadImage('data/module_4.svg'));
  shapes.push(loadImage('data/module_5.svg'));
  shapes.push(loadImage('data/module_6.svg'));
  shapes.push(loadImage('data/module_7.svg'));
}

function setup() {
  createCanvas(600, 600);
  imageMode(CENTER);
  // set the current shape to the first in the array
  currentShape = shapes[0];
  tileWidth = width / tileCount;
  tileHeight = height / tileCount;
  maxDist = sqrt(pow(width, 2) + pow(height, 2));
}

function draw() {
  clear();

  for (var gridY = 0; gridY < tileCount; gridY++) {
    for (var gridX = 0; gridX < tileCount; gridX++) {

      var posX = tileWidth * gridX + tileWidth / 2;
      var posY = tileHeight * gridY + tileWidth / 2;

      // calculate angle between mouse position and actual position of the shape
      var angle = atan2(mouseY - posY, mouseX - posX) + (shapeAngle * (PI / 180));

      if (sizeMode == 0) newShapeSize = shapeSize;
      if (sizeMode == 1) newShapeSize = shapeSize * 1.5 - map(dist(mouseX, mouseY, posX, posY), 0, 500, 5, shapeSize);
      if (sizeMode == 2) newShapeSize = map(dist(mouseX, mouseY, posX, posY), 0, 500, 5, shapeSize);

      push();
      translate(posX, posY);
      rotate(angle);
      noStroke();
      image(currentShape, 0, 0, newShapeSize, newShapeSize);
      pop();
    }
  }
}

function keyReleased() {
  if (key == 's' || key == 'S') saveCanvas(gd.timestamp(), 'png');
  if (key == 'd' || key == 'D') sizeMode = (sizeMode + 1) % 3;
  if (key == 'g' || key == 'G') {
    tileCount += 5;
    if (tileCount > 20) {
      tileCount = 10;
    }
    tileWidth = width / tileCount;
    tileHeight = height / tileCount;
  }

  if (key == '1') currentShape = shapes[0];
  if (key == '2') currentShape = shapes[1];
  if (key == '3') currentShape = shapes[2];
  if (key == '4') currentShape = shapes[3];
  if (key == '5') currentShape = shapes[4];
  if (key == '6') currentShape = shapes[5];
  if (key == '7') currentShape = shapes[6];

  if (keyCode == UP_ARROW) shapeSize += 5;
  if (keyCode == DOWN_ARROW) shapeSize = max(shapeSize - 5, 5);
  if (keyCode == LEFT_ARROW) shapeAngle += 5;
  if (keyCode == RIGHT_ARROW) shapeAngle -= 5;
}

```

[Enlace a la aplicación modificada](URL)

Código modificado:

``` js
'use strict';
let c;
let port;
let connectBtn;
let connectionInitialized = false;
let microBitConnected = false;

let microBitX = 0;
let microBitY = 0;
let microBitAState = false;
let microBitBState = false;
let prevmicroBitAState = false;
let prevmicroBitBState = false;

var tileCount = 10;
var tileWidth;
var tileHeight;
var shapeSize = 50;
var newShapeSize = shapeSize;
var shapeAngle = 0;
var maxDist;
var currentShape;
var shapes;
var sizeMode = 0;

// 🔹 Control de lectura y prints
let readTimer = null;
let printCounter = 0;
let printEvery = 5; // imprime 1 de cada 5 lecturas

function preload() {
  shapes = [];
  shapes.push(loadImage('data/module_1.svg'));
  shapes.push(loadImage('data/module_2.svg'));
  shapes.push(loadImage('data/module_3.svg'));
  shapes.push(loadImage('data/module_4.svg'));
  shapes.push(loadImage('data/module_5.svg'));
  shapes.push(loadImage('data/module_6.svg'));
  shapes.push(loadImage('data/module_7.svg'));
}

function setup() {
  createCanvas(600, 600);
  imageMode(CENTER);
  currentShape = shapes[0];
  tileWidth = width / tileCount;
  tileHeight = height / tileCount;
  maxDist = sqrt(pow(width, 2) + pow(height, 2));

  port = createSerial();
  connectBtn = createButton("Connect to micro:bit");
  connectBtn.position(0, 0);
  connectBtn.mousePressed(connectBtnClick);
}

function connectBtnClick() {
  if (!port.opened()) {
    port.open("MicroPython", 115200);
    connectionInitialized = false;
  } else {
    port.close();
  }
}

function startReader() {
  if (readTimer) return;
  readTimer = setInterval(readMicrobit, 100); // lee cada 100 ms
}

function stopReader() {
  if (readTimer) {
    clearInterval(readTimer);
    readTimer = null;
  }
}

function readMicrobit() {
  if (!port.opened()) return;

  if (!connectionInitialized) {
    port.clear();
    connectionInitialized = true;
  }

  if (port.availableBytes() > 0) {
    let data = port.readUntil("\n");
    if (data) {
      data = data.trim();

      let values = data.split(",");
      if (values.length == 4) {
        microBitX = int(values[0]) + width / 2;
        microBitY = int(values[1]) + height / 2;
        microBitAState = values[2].toLowerCase() === "true";
        microBitBState = values[3].toLowerCase() === "true";

        updateButtonStates(microBitAState, microBitBState);
      }
      printCounter++;
    }
  }
}

function updateButtonStates(newAState, newBState) {
  if (newAState === true && prevmicroBitAState === false) {
    shapeSize = random(20, 80);
  }
  if (newBState === false && prevmicroBitBState === true) {
    shapeAngle += 45;
  }
  prevmicroBitAState = newAState;
  prevmicroBitBState = newBState;
}

function draw() {
  // Estado de conexión y arranque/parada del lector
  if (!port.opened()) {
    connectBtn.html("Connect to micro:bit");
    microBitConnected = false;
    stopReader();
  } else {
    microBitConnected = true;
    connectBtn.html("Disconnect");
    startReader();
  }

  clear();
  let controlX = microBitConnected ? microBitX : mouseX;
  let controlY = microBitConnected ? microBitY : mouseY;

  for (var gridY = 0; gridY < tileCount; gridY++) {
    for (var gridX = 0; gridX < tileCount; gridX++) {
      var posX = tileWidth * gridX + tileWidth / 2;
      var posY = tileHeight * gridY + tileWidth / 2;

      var angle = atan2(controlY - posY, controlX - posX) + (shapeAngle * (PI / 180));

      if (sizeMode == 0) newShapeSize = shapeSize;
      if (sizeMode == 1) newShapeSize = shapeSize * 1.5 - map(dist(controlX, controlY, posX, posY), 0, 500, 5, shapeSize);
      if (sizeMode == 2) newShapeSize = map(dist(controlX, controlY, posX, posY), 0, 500, 5, shapeSize);

      push();
      translate(posX, posY);
      rotate(angle);
      noStroke();
      image(currentShape, 0, 0, newShapeSize, newShapeSize);
      pop();
    }
  }
}

function keyReleased() {
  if (key == 's' || key == 'S') saveCanvas('grid', 'png');
  if (key == 'd' || key == 'D') sizeMode = (sizeMode + 1) % 3;
  if (key == 'g' || key == 'G') {
    tileCount += 5;
    if (tileCount > 20) tileCount = 10;
    tileWidth = width / tileCount;
    tileHeight = height / tileCount;
  }
  if (key == '1') currentShape = shapes[0];
  if (key == '2') currentShape = shapes[1];
  if (key == '3') currentShape = shapes[2];
  if (key == '4') currentShape = shapes[3];
  if (key == '5') currentShape = shapes[4];
  if (key == '6') currentShape = shapes[5];
  if (key == '7') currentShape = shapes[6];
  if (keyCode == UP_ARROW) shapeSize += 5;
  if (keyCode == DOWN_ARROW) shapeSize = max(shapeSize - 5, 5);
  if (keyCode == LEFT_ARROW) shapeAngle += 5;
  if (keyCode == RIGHT_ARROW) shapeAngle -= 5;
}
```

## Video

[Video demostratativo](URL)


