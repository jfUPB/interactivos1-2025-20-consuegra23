# Unidad 1

## 🔎 Fase: Set + Seek

## Actividad 01

#### ¿Que es un sistema fisico interactivo?  
Un sistema fisico se caracterisa por el uso de inputs externos lo que permite que se utilizen camaras,microfonos etc. para generar un output con la informacion dada permitiendo al usuario o al artista que la utilice dar una experiencia la cual sea acorde a lo que este haciendo.

#### ¿Como podrias aplicar lo que has visto en tu perfil profesional?
 aprovechando esta clase de sistemas se pueden generar experiencias sensoriales para personas con cierto nivel de discapacidad permitiendoles experimentar por medio de sus sentidos lo que nosotros interpretamos con aquello que ellos no poseen, por ejemplo usando el input de una camara para que le de un pront a una ia que interprete la escena y genere a lo que cree que sonaria esta imagen permitiendo experimentarla a quienes no pueden ver
## Actividad 02

#### ¿que es el diseño/arte generativo? 
El diseño generativo o arte generativo es el uso de algoritmos para la formacion de imagenes las cuales pueden ser variables estar basadas en el mismo pront, las mimsas reglas o algoritmo generando imagenes que pueder ser parecidas pero son unicas en su propia forma al ser el medio incapaz de repetir la misma imagen O no solo variables si no que cambien a tiempo real al modificar la imagen anterior o generar una continuacion a la anterior dando una sensacion parecida al moviemiento como lo que genera la animacion, lo que permite que interactue con otros elementos externos y generen cosas nuevas siempre
¿Como podrias aplicar lo que has visto en tu perfil profesional? 
al utilizar bases de personajes ua hechas se podrian generar un sistema que sea capaz de interactuar con un usuario al ser capaz de esuchar y ver al usuario generando una experiencia unica y constante sin utilizar ningun tipo de base, dando una experiencia unica al usuario

## Actividad 3
#### ¿En este sistemas físico interactivo identifica los inputs, outputs y el proceso? 
Los inputs presentes son aquellos que nos otorga el micro:bit los dos botones que posee el a y el b, ademas del sensor de movimiento y por fuera del micro:bit el boton "give love", los outputs presentes son el canvas en la computadora y los cambios en las esferaz dentro de esta dependiendo del input recibido, y tambien la pantalla de pixeles que esta en el micro:bit que reacciona al boton "give love"

## Actividad 4
https://editor.p5js.org/consuegra23/sketches/rlwyIpbgY
<img width="588" height="506" alt="image" src="https://github.com/user-attachments/assets/1587858b-ac8c-40aa-8fbb-d1b24dae158c" />

``` js
let t = 0;

function setup() {
  createCanvas(600, 600);
  background(0);
  noStroke();
}

function draw() {
  fill(0, 20);
  rect(0, 0, width, height);
  
  translate(width / 2, height / 2);

  for (let i = 0; i < 100; i++) {
    let angle = random(TWO_PI);
    let radius = 200 * sin(t + i * 0.1);
    let x = radius * cos(angle);
    let y = radius * sin(angle);

    fill(
      128 + 127 * sin(t + i),
      128 + 127 * sin(t + i + PI / 3),
      128 + 127 * sin(t + i + PI / 1.5),
      150
    );

    let size = random(5, 20);
    ellipse(x, y, size, size);
  }

  t += 0.01;
}

