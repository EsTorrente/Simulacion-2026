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

  
⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹  
 
## ✨ Etapa 3: Primeros prototipos















https://docs.ml5js.org/#/reference/bodypose

https://cc.acm.org/2026/
