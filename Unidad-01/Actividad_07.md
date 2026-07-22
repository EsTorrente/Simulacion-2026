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

✨ # RESULTADOS INICIALES:

   
