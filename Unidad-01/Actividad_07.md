# ACTIVIDAD 07

## ✨ Etapa 1: ideación

🌱 **`Idea inicial:`** Al principio investigué temáticas de festivales específicamente enfocados en tecnología y creatividad. La gran mayoría de temáticas tendían hacia temas ecológicos y de justicia social... lo cuál es chévere, pero no me inspiraba demasiado. Mi mente se fue de inmediato al comportamiento animal como algoritmo, y la manera en la que la presencia (o ausencia) humana influye sobre él. Empecé a buscar qué cosas eran técnicamente posibles dentro de p5.js: detección de humanos, objetos, blob tracking... como inputs que alteraran el comportamiento de un animalito virtual en pantalla. La idea me pareció chévere, pero no veía mucho más que explotarle... simplemente era una forma divertida de explorar todas esas bibliotecas. Cuando le conté al profe (hola profe) me recordó que puede ser un poco más interesante trabajar por medio de una abstracción más profunda y limitación de herramientas. me pareció un desafío interesante, por lo que me decidí por el tema `PURE ABSTRACTION` de Art Fluent.  
  
Mi proceso creativo depende COMPLETAMENTE de la música, el silencio y la capacidad de dar vuelticas mientras pienso, por lo que decidí dejar de rumiarle al proyecto y concentrarme en algo más hasta que pudiera salir de la clase y seguir mi workflow preferido.    
  
⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹
  
🌿 **`Segunda propuesta`** Inmediátamente salí del salón, me puse audífonos y me despedí de mis amistades, todo empezó a fluir con MUCHA más facilidad. Llevo ya aproximádamente un mes dándole vueltas a la misma pregunta:  
> ¿por qué creamos? ¿qué mueve al humano a crear? ¿y qué lo influye en el proceso?   
  
Es algo que he estado tocando desde múltiples perspectivas: psicología, sociología, espitirualismo, biología, etc. No he encontrado ninguna respuesta sólida, y creo que jamás será posible encontrarla. TODAS las personas a las que les he preguntado responden siempre desde una perspectiva limitada a su área de expertise, lo cual también me parece muy curioso. Es como que el campo que te apasiona influencia por completo también tu visión del mundo y lo que te rodea.  
  
Me quedé con lo del comportamiento como algoritmo, y con esas diferencias escenciales sobre la motivación core del ser humano para crear desde su área (matemática, filosofía, artes, psicología, etc). 
Y a partir de eso... surgió mi segunda propuesta:

Una obra de arte colectiva generada por partículas pequeñitas, que spawneen con una predisposición a crear ciertos tipos de patrones, y se vean afectadas por su entorno y las tendencias de las demás partículas participantes.  
  
⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹  
 
## ✨ Etapa 2: refinación

Ya teniendo una idea que sí me entusiasmaba, empecé a considerar todos los posibles parámetros que alteran esos procesos creativos y cómo podría representarlo en el algoritmo. Esta es la lista que se me ocurrió: 
Una abstracción del proceso creativo y la manera en la que se ve influenciado por el entorno, a pesar de la predisposición natural del ser humano.  

🌱 **`Atributos de comportamiento de las partículas:`** 
> *`color`* el color con el que las partículas van a dejar rastros y patrones en el canvas. Es el "tag" que muestra esa disposición interna que los mueve subconscientemente durante sus procesos creativos.  
> ⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹  
> *`inclinación`* define el tipo de patrones que la partícula dibujará en el canvas.  
> ⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹  
> *`sugestibilidad:`* qué tan probable es que una partícula abandone su inclinación original para adoptar el de las partículas cercanas que la rodean. Valores que tiendan a 0 son firmes en su programación, valores intermedios lo abandonan temporalmente para luego regresar a su comportamiento original, y valores más altos los abandonan completamente para evolucionar constantemente. En todo momento, las partículas retienen su color base, representando que aunque su motivación cambie, hay una predisposición interna que afecta su interacción con el mundo.  
> ⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹  
> *`influencia:`* valores altos de influencia aumenta la probabilidad de "infectar" partículas con sugestibilidad media y alta, provocando que más partículas copien su comportamiento durante su recorrido.  
> ⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹    
> *`curiosidad`* valores más cercanos a 1 tienen mayor probabilidad de realizar saltos más grandes en su recorrido, abandonando rápidamente la zona donde spawnean. Valores cercanos a 0 tienden a dar pasos muchos más pequeños y mantenerse dentro de la misma zona.    
> ⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹    
> *`observación`*: determina cómo cambia su comportamiento al ser observado por partículas cercanas.  
> ⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹   
> *`estado:`* determina si está en estado de creación, observación, crisis o reposo. Cada partícula realizará los métodos con velocidades e intervalos diferentes.   

___

🌿 **`Tipos de partículas:`** se me ocurren los siguientes tipos:

1) `PARTÍCULA SENSIBLE:`
   - **Color**: azul y aguamarina claro, semitraslúcido.  
   - **Inclinación**: patrones redondeados, lentos, cíclicos... como alguien que se queda rumiando toda la noche y se pierde en escenarios ficticios en su cabeza. Usa círculos.  
   - **Sugestibilidad:** alta. Son el tipo de personas que funcionan como esponjitas: las emociones de los demás las sienten como propias, y los consumen fácilmente.  
   - **Influencia:** baja. Cuando están inspirados, su sensibilidad logra llegar a los demás e inspirarlos... pero eso solo sucede cuando logran superar la timidez e interactuar con otras.  
   - **Curiosidad:** baja. Tienden a quedarse en su zona de confort. En lugar de perseguir lo desconocido, lo desconocido viene a ellos.  
   - **Observación:** al ser observados, se vuelven tímidos y nerviosos. Sus movimientos son un poquito más erráticos, como si temblaran, y más lentos porque están pensando cada movimiento antes de actuar.
     
⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹  
  
2) `PARTÍCULA CURIOSA:`
   - **Color**: amarillos y naranjas completamente opacos.  
   - **Inclinación**: mezcla de patrones angulares y redondeados. Rápido y completamente impredescible. Se deja emocionar fácilmente y cambia de rumbo constantemente. Usa círculos y triángulos.  
   - **Sugestibilidad:** muy alta. Todo le interesa, y todo lo quiere probar. Abandona completamente sus ideas anteriores para probar unas nuevas.   
   - **Influencia:** media. Para algunos resulta inspirador su espíritu, pero para otras es demasiado cansona.    
   - **Curiosidad:** súper alta. No es capaz de quedarse en un solo lugar por mucho tiempo.  
   - **Observación:** al ser observados, sus colores se vuelven más intensos y sus movimientos más grandes. Son amantes de la atención, y les entusiasma mucho mostrar lo que saben hacer mejor.
  
⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹  
  
3) `PARTÍCULA METICULOSA:`
   - **Color**: negro, gris. Completamente opaco.
   - **Inclinación**: líneas rectas, con algunos cuadrados en medio. Avanza con un paso constante, ni muy rápido ni muy lento. Todo está fríamente calculado.  
   - **Sugestibilidad:** muy baja. Son tercos y tienen una visión clara de su objetivo, y casi nadie puede hacerlos cambiar de opinión.     
   - **Influencia:** alta. Tienen una personalidad tan fuerte que se vuelve natural en su proceso creativo el marcar tendencias.  
   - **Curiosidad:** media. Les gusta explorar y aprender, pero están cómodos en su espacio.    
   - **Observación:** al ser observados, su comportamiento no cambia. Completamente centrados en sus metas.
  
⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹  
  
Podría hacer más, pero siento que ya está todo muy complejo y no quiero que la IA me colapse.  
___

🍃 **`Estados de las partículas:`** 
> *`creación`* la partícula recorre el canvas y dibuja patrones en él.  
> ⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹  
> *`observación`*: la partícula se acerca a otras partículas cercanas, se detiene a observarlas por un momento, y continúa su exploración. Si está en modo de observación, su atributo de influencia es nulo pero permanece susceptible a la influencia de la partícula observada.  
> ⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹   
> *`crisis:`* en lugar de dibujar con su color asignado, la partícula dibuja sobre su zona con el color del fondo, borrando su progreso y el de los demás.   
> ⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹  
> *`reposo`* luego de un periodo de crisis, la partícula se detiene en su lugar hasta que otra partícula se acerque lo suficiente como para influenciarla y reiniciar su proceso de creación.  
___

☘️ **Inicio de vida de la partícula:** estaba pensando en la manera en la que las haditas nacen en TinkerBell. Ahí, la risa de un niño crea una hadita con una personalidad y talento ligado a ella. Mirando la biblioteca de `ml5.js`, vi que hay una opción para tomar un string de texto e identificar el sentimiento con un valor que oscila entre 0 (negativo) a 1 (positivo), entrenado con reviews de películas. Se me ocurre que haya una sola partícula spawneada al inicio, y se entregue en pantalla una zona de input de texto donde los usuarios puedan escribir una palabra o frase corta que cree una nueva partícula, cuya predisposición es influenciada por la emoción identificada. Valores más cercanos a 0 crean partículas sensibles, valores más cercanos a 1 crean partículas curiosas, y valores intermedios crean partículas meticulosas.  

___

🍂 **REGLAS DE LA SIMULACIÓN:**  
1) Si en algún momento más del 80% de las partículas comparten la misma inclinación, aparecerán 2 partículas más de los tipos restantes para equilibrar la población un poco. Representa que cuando hay una moda o estándar en las comunidades creativas, siempre aparecerá una nueva corriente rebelde para innovar.  
2) Cada partícula hará uso del algoritmo de `random walk` y `lévy flight`, modificándolo de acuerdo a sus atributos, para los recorridos en su estado de creación.   
3) Se hará uso de `perlin noise` para darle una sensación más orgánica y menos aleatoria a los patrones dibujados por las partículas.  
4) Los colores base con los que pintará cada partícula, junto a los atributos de las formas que usen para hacerlo, tendrán leves variaciones por medio de una distribución normal.  
5) Los valores de inclinación, sugestibilidad, influencia y curiosidad se generarán semi-aleatoriamente con distribución normal que tienda hacia el rango establecido por su tipo, permitiendo que cada partícula sea única.  
6) El usuario no modifica el resultado, solo mueve un poco las posibilidades al agregar nuevos tipos de partículas con su input escrito. Todas las demás decisiones son tomadas por las probabilidades y las predisposiciones de las partículas.
7) Al ser influenciado por la inclinación de otra partícula, adopta por completo sus figuras y patrones (todo lo descrito).  

  
⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹  
 
## ✨ Etapa 3: Primeros prototipos
  
Mi guess es que la idea va a ser inicialmente muy compleja para la IA y el alcance de p5.js. Maybe no me de los resultados tal cuál como me gustarían al inicio. Voy a darle el prompt a gemini, chatGPT y claude, todos en modo deep think, para comparar resultados. Como se supone que ya ni siquiera nosotros debemos escribir los prompts, le pasé toda esta bitácora a ChatGPT y le pedí que me devolviera el prompt detallado. Este fue el resultado:  
___

# Prompt

You are an expert creative coding engineer specialized in **p5.js**, **ml5.js**, generative art, particle systems, and emergent simulations.

Your task is to build a **complete, production-quality p5.js project**, not pseudocode.

The output must be fully runnable.

Use:

* p5.js
* ml5.js Sentiment library
* the MovieReviews sentiment model

Use exactly this library:

[https://docs.ml5js.org/#/reference/sentiment](https://docs.ml5js.org/#/reference/sentiment)

The project must include complete code for:

* index.html
* sketch.js

The HTML must load:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.11.10/p5.min.js"></script>
<script src="https://unpkg.com/ml5@1/dist/ml5.min.js"></script>
```

The sentiment model must be initialized exactly like the ml5 example:

```javascript
sentiment = ml5.sentiment("MovieReviews");
```

Do not omit any implementation.

Do not leave TODOs.

Do not write pseudocode.

Write the full project.

---

# Project concept

The sketch is an artistic simulation representing how creativity evolves inside communities.

Particles represent people.

Each particle has an innate personality that influences the kind of creative marks it leaves behind.

The simulation should become an emergent ecosystem where behaviors spread, mutate and compete.

The canvas should slowly become filled with generative artwork created entirely by the particles.

The user has very little control.

The system itself should evolve naturally.

---

# Architecture

Organize the code cleanly.

Create:

* Particle class
* ParticleType definitions
* Utility functions
* Simulation manager if necessary

Avoid giant functions.

Comment the code well.

Use constants whenever possible.

---

# Particle attributes

Every particle stores:

```javascript
type
baseColor
currentColor

inclination

susceptibility

influence

curiosity

observationBehavior

state

position

velocity

noiseOffset

energy

age
```

Each particle permanently remembers its original type.

Even after changing its inclination, it keeps its original base color.

---

# Particle types

Implement three types.

---

## Sensitive particle

Color

light blue

cyan

slightly transparent

Behavior

Creates rounded flowing patterns.

Mostly circles.

Moves slowly.

Frequently revisits previous areas.

Uses smooth Perlin movement.

Susceptibility

High.

Easily adopts behaviors from nearby particles.

Influence

Low.

Curiosity

Low.

Prefers remaining near its spawn location.

Observation behavior

When another particle watches it:

movement slows

slight trembling

small random jitter

becomes more hesitant

---

## Curious particle

Color

yellow

orange

opaque

Behavior

Chaotic.

Uses circles and triangles.

Frequently changes direction.

Moves quickly.

Large Lévy jumps.

Very dynamic.

Susceptibility

Very high.

Completely adopts nearby behaviors.

Influence

Medium.

Curiosity

Very high.

Rarely stays in one area.

Observation behavior

When observed:

colors become brighter

movement becomes faster

shapes become larger

---

## Meticulous particle

Color

black

gray

opaque

Behavior

Straight paths.

Occasional squares.

Constant speed.

Very geometric.

Uses minimal randomness.

Susceptibility

Very low.

Influence

High.

Curiosity

Medium.

Observation behavior

No visible change.

---

# Particle states

Each particle can be in one of four states.

---

## Creation

Default state.

Moves and draws.

Uses random walk mixed with Perlin noise.

Occasionally performs Lévy flights according to curiosity.

---

## Observation

Particle temporarily stops drawing.

Moves toward another nearby particle.

Pauses briefly while observing.

While observing:

cannot influence others

can still be influenced

Returns to creation afterwards.

---

## Crisis

Instead of drawing with its own color,

draw using the background color.

This erases existing artwork.

Both its own and nearby marks disappear.

Remain in crisis for a random duration.

Then transition into Rest.

---

## Rest

Particle stops moving.

Does not draw.

Waits until another nearby particle influences it.

Then returns to Creation.

---

# Movement

Movement combines:

Random Walk

Lévy Flight

Perlin Noise

Every particle always uses all three.

The weights depend on its personality.

Curiosity controls:

probability of Lévy jumps

average jump length

Perlin noise should make movement feel organic.

Avoid robotic movement.

---

# Drawing behavior

Particles leave permanent marks.

Do NOT clear the canvas every frame.

Background is drawn only once.

Each particle draws according to its inclination.

Examples:

Sensitive

soft circles

spirals

arcs

slow loops

Curious

circles

triangles

explosive clusters

quick direction changes

Meticulous

lines

rectangles

grids

precise geometry

Drawing sizes should vary slightly.

Opacity should vary slightly.

Use Gaussian random values.

---

# Randomness

Use randomGaussian() extensively.

Apply Gaussian variation to:

colors

shape sizes

movement speed

curiosity

susceptibility

influence

inclination strength

Every particle should be unique.

No two particles should behave identically.

---

# Social interaction

Particles constantly search nearby particles.

If another particle enters an interaction radius:

they may influence one another.

Influence probability depends on:

source influence

target susceptibility

distance

current state

When influence succeeds:

the target completely adopts the inclination and drawing behavior of the source.

It does NOT change:

base color

particle type

Only behavioral inclination changes.

---

# Population balancing

Continuously monitor the dominant inclination.

If over 80% of particles currently share the same inclination:

spawn

2 particles

from the remaining personality types.

This represents new artistic movements emerging against conformity.

Do not spawn endlessly.

Use a cooldown.

---

# Initial population

Begin with exactly one particle.

---

# Creating particles using sentiment analysis

The page must include:

a text input

a submit button

When the user submits text:

run

```javascript
sentiment.predict(...)
```

using ml5.

Interpret confidence value as follows:

0.00–0.33

Sensitive particle

0.34–0.66

Meticulous particle

0.67–1.00

Curious particle

Create one new particle of the corresponding type.

Display the sentiment score beside the input.

Do not remove previous particles.

The simulation should continue forever.

---

# Visual requirements

1080 x 1920 canvas.

Dark background.

Particles leave trails, but patterns slowly dissappear over time.

No UI except:

text input

submit button

sentiment score

optional particle count

The artwork should slowly become dense and beautiful.

The simulation should feel alive.

---

# Performance

The sketch should comfortably handle at least

150 particles

without significant slowdown.

Avoid unnecessary allocations.

Reuse objects where possible.

---

# Code quality

Write readable code.

Use descriptive variable names.

Separate logic into methods.

Comment important algorithms.

Avoid duplicate code.

Do not use external libraries besides:

p5.js

ml5.js

---

# Deliverables

Return:

1. Complete index.html

2. Complete sketch.js

Both must be fully implemented and immediately runnable without requiring any additional code.

Do not summarize.

Do not explain.

Only output the complete source code.

___

## ✨ RESULTADOS INICIALES:

🌱 **`ChatGPT:`** sin pro no sirve para nada, literal no corrió. Flop.  
  
🌱 **`Claude:`** corrió correctamente, pero es menos bonito que gemini. Se influencian correctamente entre ellas, y logran rotar entre los distintos estados. No me termina de convencer... algo en el de Gemini lo hacía sentir más vivo. Su comportamiento era mucho más orgánico. Creo que voy a continuar con el código de gemini, y pulir su estética.    
<img width="680" height="580" alt="image" src="https://github.com/user-attachments/assets/afa39dbe-4ea5-4317-9d2f-ceca1f8d084e" />  
  
🌱 **`Gemini:`** interesante :o    
Funciona correctamente. Pude ver cómo se contagiaban algunas partículas (por ejemplo, una sensible que adoptó el comportamiento de una meticulosa. También pude ver una partícula curiosa que fue observada y se volvió medio loquita de la emoción. Todo parece funcionar correctamente. Además, vi como una partícula sensible entró en crisis y borró un espacio. Entran y salen correctamente de cada estado. Me sorprendió que pudiera lidiar con tanta info.    
<img width="379" height="671" alt="image" src="https://github.com/user-attachments/assets/5024d463-5f20-4c66-8582-1f9768cee7e7" />
<img width="386" height="672" alt="image" src="https://github.com/user-attachments/assets/5586cecd-32a7-4afd-b1b3-e30c1b269f12" />
<img width="188" height="300" alt="image" src="https://github.com/user-attachments/assets/8fd091fe-5b65-44fa-9bd7-1990ec8a6ba5" />
<img width="373" height="658" alt="image" src="https://github.com/user-attachments/assets/0f9974cb-cf3c-428a-9be0-51e849e74c64" />


# Código:
🌻html:
```.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Emergent Art Ecosystem</title>
    <!-- p5.js -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.11.10/p5.min.js"></script>
    <!-- ml5.js -->
    <script src="https://unpkg.com/ml5@1/dist/ml5.min.js"></script>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #0d0d12;
            color: #d1d1e0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
            overflow-x: hidden;
        }

        #ui-container {
            width: 100%;
            max-width: 1080px;
            padding: 15px 20px;
            box-sizing: border-box;
            display: flex;
            gap: 15px;
            align-items: center;
            justify-content: center;
            background: rgba(15, 15, 20, 0.9);
            border-bottom: 1px solid #333;
            z-index: 10;
            flex-wrap: wrap;
        }

        input[type="text"] {
            flex-grow: 1;
            max-width: 400px;
            padding: 10px 15px;
            border: 1px solid #444;
            border-radius: 20px;
            background: #1a1a24;
            color: #fff;
            outline: none;
            transition: border 0.3s;
        }

        input[type="text"]:focus {
            border-color: #5ab0ff;
        }

        button {
            padding: 10px 20px;
            border: none;
            border-radius: 20px;
            background: #5ab0ff;
            color: #000;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.3s, transform 0.1s;
        }

        button:hover {
            background: #7cc0ff;
        }

        button:active {
            transform: scale(0.95);
        }

        .status-badge {
            background: #2a2a35;
            padding: 8px 15px;
            border-radius: 15px;
            font-size: 0.9rem;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        #canvas-container {
            flex-grow: 1;
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100%;
            padding: 20px;
            box-sizing: border-box;
        }

        canvas {
            box-shadow: 0 0 30px rgba(0, 0, 0, 0.8);
            border-radius: 4px;
            max-width: 100%;
            max-height: 85vh;
            object-fit: contain;
        }
        
        .accent {
            color: #5ab0ff;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div id="ui-container">
        <input type="text" id="textInput" placeholder="Enter text to spawn a new creative entity..." autocomplete="off">
        <button id="submitBtn" disabled>Loading Model...</button>
        <div class="status-badge" id="sentimentDisplay">
            Sentiment: <span id="sentimentValue" class="accent">N/A</span>
        </div>
        <div class="status-badge">
            Population: <span id="populationValue" class="accent">1</span>
        </div>
    </div>
    
    <div id="canvas-container"></div>

    <script src="sketch.js"></script>
</body>
</html>
```
🌻 sketch:

```.js
// --- Constants & Configurations ---
const CANVAS_W = 1080;
const CANVAS_H = 1920;
const BG_COLOR = [13, 13, 18];

const PARTICLE_TYPES = {
    SENSITIVE: 'Sensitive',
    CURIOUS: 'Curious',
    METICULOUS: 'Meticulous'
};

const STATES = {
    CREATION: 'Creation',
    OBSERVATION: 'Observation',
    CRISIS: 'Crisis',
    REST: 'Rest'
};

// --- Global Variables ---
let sentiment;
let particles = [];
let spawnCooldown = 0;
let modelReadyFlag = false;

// UI Elements
let textInput, submitBtn, sentimentValue, populationValue;

// --- Setup & Initialization ---
function setup() {
    let canvas = createCanvas(CANVAS_W, CANVAS_H);
    canvas.parent('canvas-container');
    background(BG_COLOR[0], BG_COLOR[1], BG_COLOR[2]);

    // Initialize ml5 Sentiment Model
    sentiment = ml5.sentiment("MovieReviews", modelLoaded);

    // Bind UI Elements
    textInput = document.getElementById('textInput');
    submitBtn = document.getElementById('submitBtn');
    sentimentValue = document.getElementById('sentimentValue');
    populationValue = document.getElementById('populationValue');

    submitBtn.addEventListener('click', handleTextInput);
    textInput.addEventListener('keypress', (e) => {
        if (e.key === 'Enter') handleTextInput();
    });

    // Initial Population: Exactly one particle
    particles.push(createParticle(PARTICLE_TYPES.SENSITIVE, width / 2, height / 2));
}

function modelLoaded() {
    modelReadyFlag = true;
    submitBtn.innerText = "Spawn Particle";
    submitBtn.disabled = false;
    sentimentValue.innerText = "Ready";
}

// --- Main Loop ---
function draw() {
    // Fading effect: patterns slowly disappear over time
    // We use a very low opacity rectangle drawn every frame
    noStroke();
    fill(BG_COLOR[0], BG_COLOR[1], BG_COLOR[2], 4);
    rect(0, 0, width, height);

    // Update and display particles
    let currentObserved = new Set();

    // First pass: identify who is being observed this frame
    for (let p of particles) {
        if (p.state === STATES.OBSERVATION && p.targetParticle) {
            currentObserved.add(p.targetParticle);
        }
    }

    // Second pass: process logic
    for (let i = 0; i < particles.length; i++) {
        let p = particles[i];
        p.isObserved = currentObserved.has(p);
        p.update(particles);
        p.display();
    }

    // Social Interaction & Balance
    manageInteractions();
    balancePopulation();

    // Update UI
    populationValue.innerText = particles.length;
}

// --- Interaction & Simulation Management ---
function manageInteractions() {
    // Every frame, check proximity for influence
    // O(N^2) approach is acceptable for < 200 particles
    for (let i = 0; i < particles.length; i++) {
        for (let j = i + 1; j < particles.length; j++) {
            let p1 = particles[i];
            let p2 = particles[j];
            
            // Interaction radius
            let d = dist(p1.position.x, p1.position.y, p2.position.x, p2.position.y);
            if (d < 60) {
                attemptInfluence(p1, p2, d);
                attemptInfluence(p2, p1, d);
            }
        }
    }
}

function attemptInfluence(source, target, distance) {
    // Cannot influence if source is observing or resting
    if (source.state === STATES.OBSERVATION || source.state === STATES.REST) return;
    
    // Calculate influence probability based on stats and distance
    let distFactor = map(distance, 0, 60, 1, 0.1);
    let probability = source.influence * target.susceptibility * distFactor * 0.05; // 0.05 scaling for frame-rate iteration
    
    if (random() < probability) {
        // Success: target adopts source's inclination
        target.inclination = source.inclination;
        target.observationBehavior = getObservationBehavior(target.inclination);
        
        // If target was resting, it awakens to create
        if (target.state === STATES.REST) {
            target.state = STATES.CREATION;
        }
    }
}

function balancePopulation() {
    if (spawnCooldown > 0) {
        spawnCooldown--;
        return;
    }

    if (particles.length === 0) return;

    // Monitor dominant inclination
    let counts = {};
    for (let p of particles) {
        counts[p.inclination] = (counts[p.inclination] || 0) + 1;
    }

    let dominantType = null;
    let maxRatio = 0;

    for (let type in counts) {
        let ratio = counts[type] / particles.length;
        if (ratio > maxRatio) {
            maxRatio = ratio;
            dominantType = type;
        }
    }

    // If over 80% share the same inclination, spawn 2 from remaining types
    if (maxRatio > 0.8 && particles.length < 250) { // Safety cap
        let availableTypes = Object.values(PARTICLE_TYPES).filter(t => t !== dominantType);
        
        // Spawn first minority
        let type1 = availableTypes[0];
        particles.push(createParticle(type1, random(width), random(height)));
        
        // Spawn second minority (if available, else duplicate first)
        let type2 = availableTypes.length > 1 ? availableTypes[1] : availableTypes[0];
        particles.push(createParticle(type2, random(width), random(height)));

        spawnCooldown = 300; // 5 seconds at 60fps
    }
}

// --- Text Input & Sentiment Spawning ---
function handleTextInput() {
    if (!modelReadyFlag) return;
    
    let txt = textInput.value.trim();
    if (!txt) return;

    // Reset input
    textInput.value = '';
    
    // Predict sentiment
    sentiment.predict(txt, (result) => {
        // ml5 v1 sentiment returns result.score or result.confidence
        let score = result.score !== undefined ? result.score : (result.confidence !== undefined ? result.confidence : 0.5);
        
        sentimentValue.innerText = score.toFixed(3);
        
        // Map confidence value to particle type
        let newType;
        if (score <= 0.33) {
            newType = PARTICLE_TYPES.SENSITIVE;
        } else if (score <= 0.66) {
            newType = PARTICLE_TYPES.METICULOUS;
        } else {
            newType = PARTICLE_TYPES.CURIOUS;
        }

        // Spawn particle in center with small offset
        particles.push(createParticle(newType, width/2 + randomGaussian(0, 50), height/2 + randomGaussian(0, 50)));
    });
}

// --- Particle Factory & Configuration ---
function createParticle(type, x, y) {
    let baseColor, susceptibility, influence, curiosity;

    switch (type) {
        case PARTICLE_TYPES.SENSITIVE:
            baseColor = color(135 + randomGaussian(0, 20), 206 + randomGaussian(0, 20), 235 + randomGaussian(0, 20), 120); // Cyan-ish, slightly transparent
            susceptibility = constrain(randomGaussian(0.85, 0.1), 0, 1);
            influence = constrain(randomGaussian(0.2, 0.1), 0, 1);
            curiosity = constrain(randomGaussian(0.2, 0.1), 0, 1);
            break;
            
        case PARTICLE_TYPES.CURIOUS:
            baseColor = color(255 + randomGaussian(0, 10), 165 + randomGaussian(0, 20), 0 + randomGaussian(0, 20), 240); // Yellow/Orange, opaque
            susceptibility = constrain(randomGaussian(0.95, 0.05), 0, 1);
            influence = constrain(randomGaussian(0.5, 0.1), 0, 1);
            curiosity = constrain(randomGaussian(0.9, 0.1), 0, 1);
            break;
            
        case PARTICLE_TYPES.METICULOUS:
            let gray = 150 + randomGaussian(0, 30);
            baseColor = color(gray, gray, gray, 255); // Gray/Black, opaque
            susceptibility = constrain(randomGaussian(0.1, 0.05), 0, 1);
            influence = constrain(randomGaussian(0.8, 0.1), 0, 1);
            curiosity = constrain(randomGaussian(0.5, 0.1), 0, 1);
            break;
    }

    return new Particle({
        type: type,
        x: x,
        y: y,
        baseColor: baseColor,
        susceptibility: susceptibility,
        influence: influence,
        curiosity: curiosity
    });
}

function getObservationBehavior(inclination) {
    // Returns a function defining how the particle reacts when observed based on its CURRENT inclination
    return function(particle) {
        if (!particle.isObserved) return;

        switch (inclination) {
            case PARTICLE_TYPES.SENSITIVE:
                // Slows down, trembling, hesitant
                particle.velocity.mult(0.6);
                particle.position.x += randomGaussian(0, 1.5);
                particle.position.y += randomGaussian(0, 1.5);
                break;
            case PARTICLE_TYPES.CURIOUS:
                // Faster, larger, brighter
                particle.velocity.mult(1.4);
                // Brighter color handled in display()
                break;
            case PARTICLE_TYPES.METICULOUS:
                // No visible change
                break;
        }
    };
}

// --- Particle Class ---
class Particle {
    constructor(config) {
        // Core Identity
        this.type = config.type;
        this.baseColor = config.baseColor;
        this.currentColor = this.baseColor;
        
        // Behavioral Traits
        this.inclination = config.type; 
        this.susceptibility = config.susceptibility;
        this.influence = config.influence;
        this.curiosity = config.curiosity;
        this.observationBehavior = getObservationBehavior(this.inclination);
        
        // State Machine
        this.state = STATES.CREATION;
        this.stateTimer = 0;
        this.targetParticle = null;
        this.isObserved = false;
        
        // Physics & Metrics
        this.position = createVector(config.x, config.y);
        this.velocity = p5.Vector.random2D().mult(random(1, 3));
        this.noiseOffset = createVector(random(1000), random(1000));
        this.energy = 100;
        this.age = 0;
        
        // Specific drawing states
        this.meticulousDirection = random([0, PI/2, PI, 3*PI/2]); // For strict geometric movement
    }

    update(allParticles) {
        this.age++;
        
        // Occasional State Transitions
        if (this.state === STATES.CREATION && random() < 0.005) {
            // Chance to observe someone
            let potentialTargets = allParticles.filter(p => p !== this && dist(this.position.x, this.position.y, p.position.x, p.position.y) < 200);
            if (potentialTargets.length > 0) {
                this.state = STATES.OBSERVATION;
                this.targetParticle = random(potentialTargets);
                this.stateTimer = floor(randomGaussian(100, 20));
            }
        } else if (this.state === STATES.CREATION && random() < 0.001) {
            // Very rare chance for Crisis
            this.state = STATES.CRISIS;
            this.stateTimer = floor(randomGaussian(60, 15));
        }

        // State Execution
        switch (this.state) {
            case STATES.CREATION:
                this.moveCreative();
                break;
                
            case STATES.OBSERVATION:
                if (!this.targetParticle || this.stateTimer <= 0) {
                    this.state = STATES.CREATION;
                    this.targetParticle = null;
                } else {
                    // Move towards target and stop drawing
                    let dir = p5.Vector.sub(this.targetParticle.position, this.position);
                    if (dir.mag() > 30) {
                        dir.normalize().mult(1.5);
                        this.position.add(dir);
                    }
                    this.stateTimer--;
                }
                break;
                
            case STATES.CRISIS:
                this.stateTimer--;
                // Slight chaotic movement during crisis
                this.position.add(p5.Vector.random2D().mult(randomGaussian(2, 1)));
                if (this.stateTimer <= 0) {
                    this.state = STATES.REST;
                }
                break;
                
            case STATES.REST:
                // Stops moving, waits for influence (handled externally)
                break;
        }

        // Apply observation behaviors (if someone is observing this particle)
        this.observationBehavior(this);

        // Keep within bounds (Wrap around creates a continuous ecosystem)
        this.wrapBounds();
    }

    moveCreative() {
        // Base movement logic based on inclination
        let noiseScale = 0.01;
        let speed = 2;
        
        switch (this.inclination) {
            case PARTICLE_TYPES.SENSITIVE:
                // Smooth Perlin movement, revisits areas
                let angleSen = noise(this.noiseOffset.x) * TWO_PI * 2;
                this.velocity.lerp(p5.Vector.fromAngle(angleSen).mult(1.5), 0.1);
                this.noiseOffset.x += 0.005;
                break;
                
            case PARTICLE_TYPES.CURIOUS:
                // Fast, chaotic
                let angleCur = noise(this.noiseOffset.x) * TWO_PI * 4;
                this.velocity.lerp(p5.Vector.fromAngle(angleCur).mult(3.5), 0.2);
                this.noiseOffset.x += 0.02;
                break;
                
            case PARTICLE_TYPES.METICULOUS:
                // Straight paths, constant speed
                if (random() < 0.02) { // Occasionally change direction strictly by 90 degrees
                    this.meticulousDirection += random([-PI/2, PI/2]);
                }
                let targetVel = p5.Vector.fromAngle(this.meticulousDirection).mult(2.5);
                this.velocity.lerp(targetVel, 0.5); // Fast adaptation to strict angle
                break;
        }

        // Lévy Flight implementation (Heavy-tailed random jumps based on curiosity)
        if (random() < this.curiosity * 0.03) {
            // Inverse transform sampling for pareto-like distribution
            let jumpLength = pow(random(0.01, 1), -1.5) * 5; 
            jumpLength = min(jumpLength, 150); // Cap jump length
            let jumpDir = p5.Vector.random2D().mult(jumpLength);
            this.position.add(jumpDir);
        }

        // Apply Velocity
        this.position.add(this.velocity);
    }

    display() {
        // Crisis State erases artwork
        if (this.state === STATES.CRISIS) {
            noStroke();
            fill(BG_COLOR[0], BG_COLOR[1], BG_COLOR[2], 200); // Mostly opaque background color
            let eraseSize = abs(randomGaussian(60, 20));
            ellipse(this.position.x, this.position.y, eraseSize, eraseSize);
            return; // Do not draw normal artwork
        }
        
        // Rest and Observation states do not draw
        if (this.state === STATES.REST || this.state === STATES.OBSERVATION) return;

        // Visual setup based on original color and current inclination
        push();
        translate(this.position.x, this.position.y);
        
        // Adjust color if curious and observed
        let drawColor = this.baseColor;
        if (this.isObserved && this.inclination === PARTICLE_TYPES.CURIOUS) {
            colorMode(HSB);
            let h = hue(this.baseColor);
            let s = saturation(this.baseColor);
            let b = brightness(this.baseColor);
            drawColor = color(h, s * 0.8, min(b * 1.5, 100), alpha(this.baseColor));
            colorMode(RGB);
        }

        noFill();
        stroke(drawColor);
        
        let sizeMod = (this.isObserved && this.inclination === PARTICLE_TYPES.CURIOUS) ? 2.5 : 1.0;
        let baseSize = abs(randomGaussian(10, 4)) * sizeMod;

        // Draw based on inclination
        switch (this.inclination) {
            case PARTICLE_TYPES.SENSITIVE:
                strokeWeight(abs(randomGaussian(1, 0.5)));
                if (random() < 0.1) {
                    arc(0, 0, baseSize * 2, baseSize * 2, random(TWO_PI), random(TWO_PI) + PI);
                } else {
                    ellipse(0, 0, baseSize, baseSize);
                }
                break;
                
            case PARTICLE_TYPES.CURIOUS:
                strokeWeight(abs(randomGaussian(1.5, 0.8)));
                if (random() < 0.5) {
                    ellipse(0, 0, baseSize, baseSize);
                } else {
                    let r = baseSize;
                    triangle(
                        0, -r,
                        r * 0.866, r * 0.5,
                        -r * 0.866, r * 0.5
                    );
                }
                
                // Explosive clusters
                if (random() < 0.05) {
                    for(let i=0; i<3; i++) {
                        let offX = randomGaussian(0, baseSize*1.5);
                        let offY = randomGaussian(0, baseSize*1.5);
                        point(offX, offY);
                    }
                }
                break;
                
            case PARTICLE_TYPES.METICULOUS:
                strokeWeight(abs(randomGaussian(2, 0.2)));
                rotate(this.meticulousDirection);
                if (random() < 0.1) {
                    rect(-baseSize/2, -baseSize/2, baseSize, baseSize);
                } else {
                    line(-baseSize, 0, baseSize, 0);
                }
                break;
        }
        pop();
    }

    wrapBounds() {
        if (this.position.x < 0) this.position.x = width;
        if (this.position.x > width) this.position.x = 0;
        if (this.position.y < 0) this.position.y = height;
        if (this.position.y > height) this.position.y = 0;
    }
}
```

___

## ✨ PROTOTIPO 2:

La verdad es que el de Gemini está SÚPER bien. Muy cercano a lo que quería!!!
Un problema que noté al correrlo por un tiempo es que al disminuir el tamaño de la pantalla a 360x640px, las partículas tenían menos espacio para recorrer y por ende entraban más fácilmente en estado de observación. No me molesta mucho... se ve chévere... pero sí se vuelve un poco monótono porque Gemini no agregó mucha diferencia en la velocidad de las partículas. Voy a pedirle que realentice más las partículas sensibles, que agrege un poco de variación a las formas (están saliendo todas con la misma rotación), y que lo haga ver un poco más estéticamente atractivo (tengo curiosidad de ver qué se le ocurre).

**`PROMP 2:`**

## Follow-up Prompt

Keep the existing architecture and codebase. Do **not** rewrite the project from scratch.

Modify the current implementation while preserving all existing mechanics, particle types, and sentiment integration.

Implement the following improvements:

### 1. Make Sensitive particles noticeably slower

Sensitive particles should feel calm, hesitant and contemplative.

Reduce their average movement speed significantly compared to the other types.

They should spend more time exploring a small area instead of constantly drifting away.

Their movement should feel gentle and deliberate rather than simply having a lower velocity.

Increase the influence of Perlin noise on their movement so they appear to "wander thoughtfully."

---

### 2. Add more variation to the generated artwork

Currently many shapes are drawn with nearly identical orientations, making the artwork feel repetitive.

Introduce controlled randomness using Gaussian variation and Perlin noise to create much richer compositions.

For example, vary:

* rotation
* scale
* aspect ratio
* stroke weight
* opacity
* spacing between repeated marks
* curvature
* offsets from the movement path

Every particle should develop its own visual "handwriting."

Avoid completely random results; the variations should remain coherent with each particle's personality.

---

### 3. Improve the overall aesthetics

Without changing the conceptual rules of the simulation, make the resulting artwork feel significantly more beautiful and organic.

You are encouraged to creatively improve the visual design.

Possible ideas include:

* smoother transitions
* layered transparent marks
* richer color blending
* more elegant trail composition
* subtle fading instead of harsh overlaps
* improved balance between empty and dense regions
* more expressive particle paths
* more interesting combinations of primitive shapes

Use your own artistic judgment to enhance the appearance while keeping the simulation minimalist and generative.

The goal is for the canvas to resemble an evolving piece of generative art rather than a technical demonstration.

---

### 4. Shorten the Crisis state

Particles currently remain in Crisis for too long.

Adjust the state machine so that:

* Crisis never lasts more than approximately **15 seconds**.
* Most Crisis periods should be shorter than the maximum.
* After Crisis, particles should transition into Rest briefly and then be able to return to Creation naturally.
* The simulation should not accumulate large numbers of inactive particles.

The creative process should recover more quickly after destructive periods.

---

### 5. Slow down Meticulous particles

Meticulous particles currently move too quickly.

Reduce their movement speed so they feel:

* patient
* deliberate
* precise
* methodical

They should still draw straight, geometric paths, but with a slower, more intentional rhythm.

---

### 6. Preserve all existing behavior

Do **not** remove or simplify any existing mechanics.

Keep:

* sentiment analysis
* particle interactions
* influence system
* susceptibility system
* Gaussian variation
* Perlin noise
* Lévy flights
* creation, observation, crisis, and rest states
* population balancing rule

Only refine and improve the current implementation.

Focus on polish, visual quality, and more expressive behavior rather than introducing entirely new systems.

____

### ⭐ RESULTADO FINAL:
  
Me gusta!! :0  
Se siente muy arte moderno. Me quedé observando por un rato, y pasó por muchas fases distintas. Hubo un momento donde eran principalmente meticulosas, y unos segundos después habían puras sentimentales. El sistema solito se ve equilibrando, y siguen spawneando partículas aunque nadie influya. También vi cómo salían algunas partículas que eran figuritas muy chiquitas, haciendo que se vieran como manchitas de polvo!!  otros que era semi-círculos. Me gustó esa cantidad de variación. Sí es MUY evidente cuando todos están tomando una tendencia, y de repente sale una y TUN, rompe con los patrones hasta que todos vuelven a medio reiniciarse. También es genial que cuando ya llegó un punto donde habían más de 100 partículas, las curiosas entraban muy seguido en estado de observación y empezaban a correr por todos lados como luchando por atención. Me dio la sensación de que estaban intentando resaltar entre los demás y decir HOLA MÍRAME AQUÍ ESTOY!!!!!!  
También me pareció chévere que la primera vez que lo probé, la primera partícula meticulosa que spawneó tenía forma de cruz... entonces siguieron habiendo MUCHAS cruces en el canvas; pero la segunda vez, esa primera meticulosa salió como un cuadradito, y por ende hubo muchos más cuadraditos que cruces.  
Estoy súper satisfecha con el resultado!!! :DDD  
Es justo lo que me imaginaba.  

<img width="370" height="639" alt="image" src="https://github.com/user-attachments/assets/d1287461-89b4-4a3e-aa81-d7d2da261e93" />
<img width="376" height="648" alt="image" src="https://github.com/user-attachments/assets/63491d36-221b-4b72-85f7-bc44ebfcf309" />
<img width="354" height="643" alt="image" src="https://github.com/user-attachments/assets/fbd24b29-ff09-4f57-8e8d-c94c1b4a2d94" />
<img width="367" height="643" alt="image" src="https://github.com/user-attachments/assets/8a894e3f-589b-4e48-a11c-c43acc297f5c" />
  
Link: https://editor.p5js.org/EsTorrente/sketches/ibQwv8rRU

