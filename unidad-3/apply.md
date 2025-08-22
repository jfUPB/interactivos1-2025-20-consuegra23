# Unidad 3


## 🛠 Fase: Apply

### Actividad 5

#### codigo en p5.sj

~~~ js
let Tiempo = 20;
let estado = 'config';
let startMillis;
let CON = ['A', 'B', 'A'];
let index = 0;
let CONIN = [];
let comandosRecibidos = [];
let btnA, btnB, btnS, btnT;

function setup() {
  createCanvas(400, 400);
  textSize(32);
  textAlign(CENTER, CENTER);

  btnA = createButton('A');
  btnA.position(80, 300);
  btnA.mousePressed(() => comandosRecibidos.push('A'));

  btnB = createButton('B');
  btnB.position(350, 300);
  btnB.mousePressed(() => comandosRecibidos.push('B'));

  btnS = createButton('S');
  btnS.position(200, 300);
  btnS.mousePressed(() => comandosRecibidos.push('S'));

  btnT = createButton('T');
  btnT.position(200, 50);
  btnT.mousePressed(() => comandosRecibidos.push('T'));
}

function draw() {
  background(220);

  while (comandosRecibidos.length > 0) {
    let comando = comandosRecibidos.shift(); // Leer y eliminar el primero
    console.log(comando);

    if (estado === 'config') {
      if (comando === 'A') Tiempo = min(60, Tiempo + 1);
      else if (comando === 'B') Tiempo = max(10, Tiempo - 1);
      else if (comando === 'S') {
        estado = 'armed';
        startMillis = millis();
      }
    } else if (estado === 'armed') {
      if (comando === 'A' || comando === 'B') {
        CONIN.push(comando);
        index++;
        if (index === 3) {
          if (JSON.stringify(CONIN) === JSON.stringify(CON)) {
            estado = 'config';
            CONIN = [];
            index = 0;
          }
        } else if (index > 3) {
          CONIN.splice(0, 1);
          index = 3;
        }
      }
    } else if (estado === 'exploted') {
      if (comando === 'T') {
        estado = 'config';
      }
    }
  }

  // Mostrar estado
  if (estado === 'config') {
    text('Configuración: ' + nf(Tiempo, 2), width / 2, height / 2);
  } else if (estado === 'armed') {
    let elapsed = floor((millis() - startMillis) / 1000);
    let remaining = max(Tiempo - elapsed, 0);
    text('Explotará: ' + nf(remaining, 2), width / 2, height / 2);
    if (remaining === 0) {
      estado = 'exploted';
    }
  } else if (estado === 'exploted') {
    text('¡¡¡EXPLOTÓ!!!', width / 2, height / 2);
    Tiempo = 20
  }
}

function keyPressed() {
  let tecla = key.toUpperCase();
  if (['A', 'B', 'S', 'T'].includes(tecla)) {
    comandosRecibidos.push(tecla);
  }
}
~~~
