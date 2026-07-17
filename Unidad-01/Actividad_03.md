## Actividad 03

🌿 `Distribución uniforme:` los números tienen la misma probabilidad de salir. No hay un sesgo.
🌿 `Distribución no uniforme:` los números tienden una regla que los hace tender ciertos valores.

### 🌱 Código modificado
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

## Actividad 05

## Actividad 06
