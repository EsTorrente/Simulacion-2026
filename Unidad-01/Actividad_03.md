## Actividad 03
**En tus propias palabras cuál es la diferencia entre una distribución uniforme y una no uniforme de números aleatorios.***  
🌿 `Distribución uniforme:` los números tienen la misma probabilidad de salir. No hay un sesgo.  
🌿 `Distribución no uniforme:` los números tienden una regla que los hace tender ciertos valores.  
  

⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹  

  
**Modifica el código de la caminata aleatoria para que utilice una distribución no uniforme, favoreciendo el movimiento hacia la derecha.**  
### 🌱 Código modificado

<img width="669" height="312" alt="image" src="https://github.com/user-attachments/assets/1a0f490d-d1d2-4a86-aef2-372f1e0de333" />  

```.js
// The Nature of Code
// Daniel Shiffman
// http://natureofcode.com

let walker;

function setup() {
  createCanvas(640, 240);
  walker = new Walker();
  background(255);
}

function draw() {
  walker.step();
  walker.show();
}

class Walker {
  constructor() {
    this.x = width / 2;
    this.y = height / 2;
  }

  show() {
    stroke('orange');
    fill('red');
    quad(this.x, this.y+40, this.x, this.y-40, this.x+40, this.y, this.x-40, this.y);
    quad(this.x, this.y+20, this.x+20, this.y, this.x, this.y-20, this.x-20, this.y);
  }

  step() {
    const choice = floor(random(6));
    if (choice == 0 || choice >= 4) {
      this.x++;
    } else if (choice == 1) {
      this.x--;
    } else if (choice == 2) {
      this.y++;
    } else {
      this.y--;
    }

    if (this.x >= width)
    {
      this.x = 0;
    }
  }
}


```

## Actividad 04

**Crea un nuevo sketch en p5.js que represente una distribución normal, pero visualizándola de manera diferente a la del ejemplo.**
> Quería hacer algo con cajitas que me dejara contar a ojo cuántas bolitas salían en cada una. Usé la dist. normal para determinar en qué cajita saldrían, y luego para variar un poquito el color del circulito dependiendo de dónde quedó.    
<img width="915" height="336" alt="image" src="https://github.com/user-attachments/assets/f5386f89-7b68-4513-831d-9b19940a4ae2" />  

```.js
function setup() {
  createCanvas(900, 300);
  background(0);
}

function draw() {

  if (millis() > 1500) { // corro solo por 1.5 segundos
    noLoop();
    return;
  }

  // spawnear cada 3 frames
  if (frameCount % 3 == 0) {

    // dist gaussiana focuseada en cuadro del medio (media es index 1)
    let g = randomGaussian(1, 0.6);

    // convertir a index de cajita para ver en cuál spawnea
    let box = constrain(round(g), 0, 2); //round, no floor, para q no lo moche a uno menor

    // pos random en su cajita
    let x = random(box * width/3, (box+1) * width/3);
    let y = random(50, height);

    // color para cada cajita
    let r, gr, b;

    if (box == 0) {
      r = constrain(randomGaussian(220, 40), 0, 255);
      gr = constrain(randomGaussian(60, 40), 0, 255);
      b = constrain(randomGaussian(60, 40), 0, 255);
    }

    if (box == 1) {
      r = constrain(randomGaussian(60, 40), 0, 255);
      gr = constrain(randomGaussian(220, 40), 0, 255);
      b = constrain(randomGaussian(60, 40), 0, 255);
    }

    if (box == 2) {
      r = constrain(randomGaussian(60, 40), 0, 255);
      gr = constrain(randomGaussian(60, 40), 0, 255);
      b = constrain(randomGaussian(220, 40), 0, 255);
    }

    noStroke();
    fill(r, gr, b, 180);
    circle(x, y, 12);
  }

  // ============ UI ENCIMA =================

  stroke(255);
  strokeWeight(2);

  line(width / 3, 0, width / 3, height);
  line(2 * width / 3, 0, 2 * width / 3, height);

  noStroke();
  fill(255);
  textAlign(CENTER);
  textSize(20);

  text("A", width / 6, 30);
  text("B", width / 2, 30);
  text("C", 5 * width / 6, 30);
}
```

## Actividad 05
> Usé esta técnica para adaptarlo porque me pareció muy sencilla e intuitiva. No necesitaba hacerle cambios raros al código original, solamente agregar una variable chiquita que pudiera exagerar un tris la distancia del movimiento del puntico. Lo que espero es que al ejecutarlo siga funcionando con las mismas probabilidades que el original (sigue sacando números enteros del 0 al 3)... lo que cambia es que hay un 5% de veces en las que va a ir más lejos en la dirección que eligió y, por ende, no se pise tanto a sí mismo.    

<img width="649" height="276" alt="image" src="https://github.com/user-attachments/assets/099eacc5-9bfd-456c-8cf1-b51ec0487523" />  
  
```.js
// The Nature of Code
// Daniel Shiffman
// Modified to demonstrate a Lévy Flight

let walker;

function setup() {
  createCanvas(640, 240);
  background(255);

  walker = new Walker();
}

function draw() {
  walker.step();
  walker.show();
}

class Walker {
  constructor() {
    this.x = width / 2;
    this.y = height / 2;
  }

  show() {
    stroke(0);
    point(this.x, this.y);
  }

  step() {
    let stepSize = 1;

    // brinquito lévy flight
    if (random() < 0.05) //num entre 0 y 1 
    {
      stepSize = random(20, 80); //cada frame vuelve a stepSize == 1 y tira prob again
    }

    const choice = floor(random(4));

    if (choice == 0) {
      this.x += stepSize;
    } else if (choice == 1) {
      this.x -= stepSize;
    } else if (choice == 2) {
      this.y += stepSize;
    } else {
      this.y -= stepSize;
    }

    // que no se escape
    this.x = constrain(this.x, 0, width);
    this.y = constrain(this.y, 0, height);
  }
}
```

## Actividad 06
> Quería replicar el efecto wave warp de after effects. Los ejemplos que vi en la biblioteca de p5.js me recordaron mucho al turbulent noise del programa, y me llevó a pensar si podría usarlo para imitar ese efecto :0


```.js
let img;
let t = 0;

// UI
let ampSlider;
let scaleSlider;
let speedSlider;
let sliceSlider;

// valores suavizados
let sAmp = 100;
let sScale = 0.008;
let sSpeed = 0.022;

function preload() {
  img = loadImage("image.png");
}

function setup() {
  createCanvas(img.width, img.height);

  ampSlider = createSlider(0, 180, 100);
  ampSlider.position(15, 15);

  scaleSlider = createSlider(5, 20, 8);
  scaleSlider.position(15, 45);

  speedSlider = createSlider(1, 50, 22);
  speedSlider.position(15, 75);

  sliceSlider = createSlider(1, 6, 1);
  sliceSlider.position(15, 105);

  textSize(14);

  noiseDetail(1, 0.5); // una sola octava para que sea menos detallado
}

function draw() {

  background(255);

  // ====== suavizar cambios de los sliders ======

  let targetAmp = ampSlider.value();
  let targetScale = scaleSlider.value() / 1000;
  let targetSpeed = speedSlider.value() / 1000;

  sAmp = lerp(sAmp, targetAmp, 0.08);
  sScale = lerp(sScale, targetScale, 0.08);
  sSpeed = lerp(sSpeed, targetSpeed, 0.08);

  let fxSlice = sliceSlider.value();

  // ====== distorsión ======

  for (let x = 0; x < img.width; x += fxSlice) {

    // primera capa de ruido
    let n1x = noise(x * sScale, t);
    let n1y = noise(x * sScale + 100, t);

    // segunda capa (más lenta y amplia)
    let n2x = noise(x * sScale * 0.45, t*0.8 + 500);
    let n2y = noise(x * sScale * 0.60 + 300, t*0.8 + 800);

    // combinar ambas capas
    let dx =
      map(n1x, 0, 1, -sAmp, sAmp) +
      map(n2x, 0, 1, -sAmp * 0.5, sAmp * 0.5);

    let dy =
      map(n1y, 0, 1, -sAmp * 0.6, sAmp * 0.6) +
      map(n2y, 0, 1, -sAmp * 0.3, sAmp * 0.3);

    image(
      img,

      x + dx,
      dy,

      fxSlice + 1,
      img.height,

      x,
      0,

      fxSlice,
      img.height
    );
  }

  // avanzar en el tiempo
  t += sSpeed;

  // ========= UI ===============

  noStroke();
  fill(0, 180);
  rect(10, 10, 260, 120, 8);

  fill(255);

  text("Intensidad: " + nf(sAmp, 1, 1), 150, 30);
  text("Escala: " + nf(sScale, 1, 3), 150, 60);
  text("Velocidad: " + nf(sSpeed, 1, 3), 150, 90);
  text("Tamaño slice: " + fxSlice, 150, 120);
}
```
