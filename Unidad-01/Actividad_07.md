# ACTIVIDAD 07

## Etapa 1: ideación

🌱 **`Idea inicial:`** Al principio investigué temáticas de festivales específicamente enfocados en tecnología y creatividad. La gran mayoría de temáticas tendían hacia temas ecológicos y de justicia social... lo cuál es chévere, pero no me inspiraba demasiado. Mi mente se fue de inmediato al comportamiento animal como algoritmo, y la manera en la que la presencia (o ausencia) humana influye sobre él. Empecé a buscar qué cosas eran técnicamente posibles dentro de p5.js: detección de humanos, objetos, blob tracking... como inputs que alteraran el comportamiento de un animalito virtual en pantalla. La idea me pareció chévere, pero no veía mucho más que explotarle... simplemente era una forma divertida de explorar todas esas bibliotecas. Cuando le conté al profe (hola profe) me recordó que puede ser un poco más interesante trabajar por medio de una abstracción más profunda y limitación de herramientas. me pareció un desafío interesante, por lo que me decidí por el tema `PURE ABSTRACTION` de Art Fluent.  
  
Mi proceso creativo depende COMPLETAMENTE de la música, el silencio y la capacidad de dar vuelticas mientras pienso, por lo que decidí dejar de rumiarle al proyecto y concentrarme en algo más hasta que pudiera salir de la clase y seguir mi workflow preferido.    
  
⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹
  
🌿 **`Segunda propuesta`** Inmediátamente salí del salón, me puse audífonos y me despedí de mis amistades, todo empezó a fluir con MUCHA más facilidad. Llevo ya aproximádamente un mes dándole vueltas a la misma pregunta:  
> ¿por qué creamos? ¿qué mueve al humano a crear? ¿y qué lo influye en el proceso?   
  
Es algo que he estado tocando desde múltiples perspectivas: psicología, sociología, espitirualismo, biología, etc. No he encontrado ninguna respuesta sólida, y creo que jamás será posible encontrarla. TODAS las personas a las que les he preguntado responden siempre desde una perspectiva limitada a su área de expertise, lo cual también me parece muy curioso. Es como que el campo que te apasiona influencia por completo también tu visión del mundo y lo que te rodea.  
  
Me quedé con lo del comportamiento como algoritmo, y con esas diferencias escenciales sobre la motivación core del ser humano para crear desde su área (matemática, filosofía, artes, psicología, etc). 
Y a partir de eso... surgió mi segunda propuesta:

Una obra de arte colectiva generada por partículas pequeñitas, que spawneen con una predisposición a crear ciertos tipos de patrones, y se vean afectadas por su entorno y las tendencias de las demás partículas participantes.  

## Etapa 2: refinación

Ya teniendo una idea que sí me entusiasmaba, empecé a considerar todos los posibles parámetros que alteran esos procesos creativos y cómo podría representarlo en el algoritmo. Esta es la lista que se me ocurrió:  

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

🌿 **`Tipos de partículas:`** se me ocurren los siguientes tipos:

1) PARTÍCULA SENSIBLE:
   

🍃 **`Estados de las partículas:`** 
> *`creación`* la partícula recorre el canvas y dibuja patrones en él.  
> ⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹  
> *`observación`*: la partícula se acerca a otras partículas cercanas, se detiene a observarlas por un momento, y continúa su exploración. Si está en modo de observación, su atributo de influencia es nulo pero permanece susceptible a la influencia de la partícula observada.  
> ⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹   
> *`crisis:`* en lugar de dibujar con su color asignado, la partícula dibuja sobre su zona con el color del fondo, borrando su progreso y el de los demás.   
> ⊹₊˚‧︵‿₊⊱·✶·⊰₊‿︵‧˚₊⊹ 
> *`reposo`* luego de un periodo de crisis, la partícula se detiene en su lugar hasta que otra partícula se acerque lo suficiente como para influenciarla y reiniciar su proceso de creación.  

☘️ **Inicio de vida de la partícula:** estaba pensando en la manera en la que las haditas nacen en TinkerBell. Ahí, la risa de un niño crea una hadita con una personalidad y talento ligado a ella. Mirando la biblioteca de `ml5.js`, vi que hay una opción para tomar un string de texto e identificar el sentimiento con un valor que oscila entre 0 (negativo) a 1 (positivo), entrenado con reviews de películas. Se me ocurre que haya una sola partícula spawneada al inicio, y se entregue en pantalla una zona de input de texto donde los usuarios puedan escribir una palabra o frase corta que cree una nueva partícula, cuya predisposición es influenciada por la emoción identificada.

















https://docs.ml5js.org/#/reference/bodypose

https://cc.acm.org/2026/
