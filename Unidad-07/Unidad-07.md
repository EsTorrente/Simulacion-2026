# Bitácora

## 1. IDEACIÓN!q!!!!!

Mi intención con este proyecto es explorar el aspecto colaborativo de la identidad de Meow Wolf. La marca se caracteriza por sus instalaciones inmersivas, sus colores neón y sus escenarios súper trippy y raritos, pero lo que más me interesa es que sus exposiciones son el resultado del trabajo conjunto de muchísimos artistas, diseñadores y técnicos.
Quería representar esa dinámica a través de dos personalidades que trabajan de maneras muy distintas, pero que se necesitan mutuamente para crear algo nuevo: el gato y el lobo.  
El lobo representa a Meow Wolf como organización. Es quien proporciona los materiales, las herramientas y las posibilidades para crear, pero también quien debe esforzarse para conseguirlos. El gato representa a los artistas y técnicos que reciben esos recursos y tienen rienda suelta para interpretarlos y darles su propio toque.
La idea es que ninguno de los dos pueda completar la experiencia por su cuenta. El lobo puede conseguir todos los materiales, pero no decide cómo se utilizan. El gato puede tener toda la creatividad del mundo, pero necesita que el lobo le proporcione las herramientas. Al final, ambos deben ponerse de acuerdo para terminar su creación.

Me interesa que la colaboración no sea simplemente una mecánica obligatoria, sino que se sienta en la manera en la que cada jugador interactúa con el sistema. Cada uno tiene objetivos, limitaciones y responsabilidades diferentes, y el resultado depende de lo que ambos aporten.

## 2. Referentes

### Meow Wolf

Mi referente principal son las instalaciones de Meow Wolf. Toda su identidad visual juega muchísimo con los colores neón, las formas *bold* y los escenarios súper saturados, extraños e inmersivos.

Me interesa especialmente cómo sus espacios parecen tener sus propias reglas y cómo uno puede encontrar cosas inesperadas al explorarlos. No todo tiene que ser inmediatamente comprensible: parte de la experiencia consiste en curiosear, probar cosas y descubrir conexiones.

Quiero llevar esa sensación al sistema tipográfico, tanto en la interfaz como en el resultado final. La idea no es que las letras sean simplemente texto decorado, sino que se conviertan en el punto de partida para construir algo mucho más extraño.

### Los primeros experimentos de arte con inteligencia artificial

Mi segunda referencia son los primeros intentos de generación de imágenes mediante inteligencia artificial, cuando las figuras todavía eran bastante ambiguas y no siempre se entendía exactamente qué estaba pasando.

Me gustan esas imágenes en las que las formas parecen transformarse unas en otras, donde un objeto puede terminar pareciéndose a una criatura y un patrón puede convertirse en un paisaje. También me interesa la saturación de los colores y esa sensación de que todo está a punto de convertirse en algo diferente.

Quiero explorar esa ambigüedad en el mundo que aparece al finalizar la composición tipográfica. En vez de construir un escenario completamente definido desde el principio, me interesa que los colores, las formas y los elementos que los jugadores hayan utilizado generen un entorno que se sienta orgánico, inesperado y un poquito absurdo.

### Los juegos colaborativos de mi infancia

Mi tercer referente son los juegos colaborativos que jugaba de pequeña, especialmente uno de Romeo y Julieta que jugaba con mi mamá.

Me hacía mucha gracia que los niveles estuvieran diseñados de tal manera que Romeo tuviera que atravesar un montón de obstáculos súper complejos, mientras que el jugador de Julieta básicamente oprimía un botón de vez en cuando.

Esa diferencia entre los dos roles se me quedó grabada. Me hizo pensar en la dinámica de personalidades que solemos atribuirles a los perros y los gatos: el perro es el que está emocionadísimo por cumplir tareas y hacer cosas, mientras que el gato parece una mente maestra que observa todo y decide qué hacer con lo que tiene.

Quería recuperar esa diferencia para el proyecto. El lobo tiene que explorar, esquivar enemigos y esforzarse para conseguir recursos, mientras que el gato se dedica a experimentar creativamente con ellos. Aunque las tareas son muy diferentes, ninguna tiene sentido sin la otra.

## 3. Concepto y reglas del sistema

La experiencia se divide en dos roles que se comunican a través de una misma composición tipográfica.

### El lobo

El jugador del lobo explora un laberinto con obstáculos y enemigos. Su objetivo es encontrar y recoger los colores y las pegatinas que después estarán disponibles para el gato.

No se trata simplemente de recoger objetos en un recorrido vacío. Quiero que explorar el laberinto represente el esfuerzo que implica conseguir los recursos necesarios para que otra persona pueda crear.

Los objetos disponibles son limitados, por lo que el jugador debe explorar el espacio y decidir cómo conseguirlos evitando los peligros.

### El gato

El jugador del gato trabaja directamente sobre las letras del logotipo de Meow Wolf. Puede dibujar, experimentar con colores y colocar las pegatinas que el lobo haya desbloqueado.

El gato tiene libertad para decidir cómo utilizar los recursos. Recibir una pegatina no determina automáticamente dónde va ni qué función tendrá dentro de la composición; esa decisión sigue siendo parte del proceso creativo.

Me interesa que el resultado pueda ser diferente en cada partida, dependiendo tanto de los recursos que consiga el lobo como de las decisiones que tome el gato.

### La colaboración

Las acciones de ambos jugadores se reflejan en la misma composición. El lobo consigue los recursos y el gato los transforma en una interpretación visual de la marca.

Para terminar, ambos deben confirmar que están de acuerdo con finalizar la creación. No hay una puntuación ni un ganador: el objetivo es descubrir qué pueden construir juntos.

Una vez terminada la composición, esta se transforma en un entorno generativo influenciado por los colores, los dibujos y las pegatinas que utilizaron. De esta manera, el resultado final no es completamente predeterminado, sino una consecuencia de las decisiones de los dos jugadores.

## 4. Desarrollo y experimentación

### Primera etapa: estructura funcional

Empecé por construir la estructura técnica de la experiencia, antes de intentar desarrollar todos los efectos visuales.

La propuesta necesita funcionar en dos computadores conectados a la misma red, así que tuve que pensar en cómo sincronizar las acciones de ambos jugadores y cómo mantener una única versión compartida de la partida.

En esta etapa me enfoqué en que cada jugador pudiera entrar a su rol, que las acciones del lobo se reflejaran en los recursos disponibles para el gato y que los dibujos realizados por el gato aparecieran también en la pantalla del lobo.

También fue importante establecer reglas para evitar que un mismo objeto pudiera recogerse varias veces o que el gato utilizara recursos que todavía no había desbloqueado.

**Evidencias por agregar:**
- [ ] Captura de las dos pantallas conectadas.
- [ ] Prueba de recolección y desbloqueo de una pegatina.
- [ ] Prueba de sincronización de los dibujos.
- [ ] Prueba de confirmación de ambos jugadores.

### Segunda etapa: composición tipográfica

Una de las decisiones importantes fue utilizar el logotipo de Meow Wolf como base de la experiencia, en lugar de tratar el texto como una palabra escrita con una fuente cualquiera.

La intención es que la forma de las letras sea reconocible y que el jugador pueda intervenir directamente sobre ellas. Por eso, la composición debe conservar las proporciones y los contornos del logotipo original, mientras permite añadir dibujos y pegatinas encima.

También me interesa que el gato pueda ver la composición completa mientras trabaja. Si solo observa una letra a la vez, pierde parte de la posibilidad de entender cómo se relacionan sus decisiones y cómo se ve el conjunto de la palabra.

**Evidencias por agregar:**
- [ ] Imagen del logotipo original.
- [ ] Prueba de extracción de los contornos de las letras.
- [ ] Comparación entre la composición original y la intervenida.
- [ ] Captura de la composición completa dentro de la interfaz.

### Tercera etapa: construcción del mundo final

La última parte de la experiencia consiste en transformar la composición tipográfica en un entorno visual generativo.

La idea es que los elementos que utilizaron los jugadores tengan consecuencias más allá de la apariencia de las letras. Por ejemplo, ciertos colores y pegatinas pueden influir en la aparición de estructuras orgánicas, patrones ramificados, movimientos eléctricos o formas que recuerden al fuego.

Quiero explorar sistemas de partículas y movimientos inspirados en el comportamiento del *Physarum*, donde los agentes dejan rastros, siguen patrones y generan estructuras que evolucionan con el tiempo.

Lo interesante de esta parte es que el mundo final puede funcionar como una representación de la colaboración: cada intervención individual aporta algo al sistema, pero el resultado termina siendo una estructura que ninguno de los jugadores habría creado exactamente de la misma manera por su cuenta.

**Evidencias por agregar:**
- [ ] Primeros experimentos con partículas.
- [ ] Pruebas de movimiento y ramificación.
- [ ] Comparación de resultados con distintas combinaciones de colores y pegatinas.
- [ ] Captura o video de la transición entre el logotipo y el mundo final.

## 5. Decisiones visuales

Quiero que toda la experiencia tenga una identidad visual cercana a la sensación de entrar en una instalación de Meow Wolf: colores muy saturados, luces neón, contrastes fuertes y formas extrañas que parecen pertenecer a un mundo propio.

La segunda referencia, los primeros experimentos de generación de imágenes con inteligencia artificial, también influye en la apariencia del resultado final. Me interesa que las formas no siempre sean completamente literales y que el sistema pueda generar combinaciones inesperadas.

Sin embargo, no quiero que la interfaz sea tan caótica que dificulte jugar. El laberinto debe seguir siendo legible, los enemigos deben distinguirse de los objetos que se pueden recoger y las herramientas del gato deben ser fáciles de entender.

Por eso, hay una diferencia entre la interfaz y el mundo final: la primera necesita organizar la información para que los jugadores puedan actuar; el segundo puede permitirse ser mucho más libre, extraño y visualmente complejo.

## 6. Pruebas y problemas encontrados

Durante el desarrollo, la prioridad inicial fue conseguir que las mecánicas funcionaran correctamente en ambos computadores. Después de eso, empecé a identificar problemas relacionados con la presentación visual y la facilidad de uso.

Entre los aspectos que necesitaban mejorar estaban la escala de la composición tipográfica en la vista del lobo, la representación de las pegatinas y los controles para manipularlas desde la interfaz del gato.

También noté que el primer resultado del mundo final no transmitía la complejidad que tenía en mente. Aunque la estructura generativa funcionaba, la apariencia era demasiado simple y no alcanzaba la sensación de inmersión que buscaba en mis referentes.

Esto me llevó a separar dos objetivos que al principio podían parecer el mismo: que el sistema funcione y que el sistema comunique visualmente lo que quiero expresar. Tener las mecánicas funcionando es un avance importante, pero todavía hace falta que la presentación, la interacción y el resultado visual estén al nivel de la intención original.

**Registro de pruebas:**

| Prueba | Resultado / observaciones |
|---|---|
| Conexión entre dos computadores | [Por completar] |
| Sincronización de dibujos | [Por completar] |
| Desbloqueo y recolección de recursos | [Por completar] |
| Manipulación de pegatinas | [Por completar] |
| Confirmación de ambos jugadores | [Por completar] |
| Transición al mundo final | [Por completar] |
| Relación entre los recursos usados y el mundo generado | [Por completar] |

## 7. Reflexión personal

Lo que más me interesa de este proyecto es que la colaboración no se representa únicamente mediante dos personas trabajando al mismo tiempo, sino mediante dos formas diferentes de relacionarse con un mismo sistema.

El lobo tiene que actuar, explorar y superar obstáculos para conseguir recursos. El gato tiene que observar, interpretar y decidir cómo utilizarlos. Uno no puede sustituir al otro, y el resultado final depende de la relación entre sus decisiones.

También me gusta que el sistema no tenga una única solución correcta. No hay una composición ideal que los jugadores deban alcanzar, porque la gracia está precisamente en lo que cada pareja decide hacer con las posibilidades que tiene.

El proyecto me ha hecho pensar en cómo las reglas de una experiencia pueden comunicar una idea sin necesidad de explicarla directamente. Si cada jugador tiene una función diferente y las consecuencias de sus acciones dependen del otro, la colaboración deja de ser solo el tema del proyecto y se convierte en parte de cómo se juega.

Todavía quiero mejorar la calidad visual y la forma en que el mundo final responde a las decisiones de los jugadores. Mi intención es que esa última transformación se sienta como la creación de algo nuevo a partir de muchos aportes individuales, en lugar de ser simplemente una animación que aparece cuando se termina el juego.

## 8. Autoevaluación

*Completar después de las últimas pruebas y antes de la presentación.*

Considero que el proyecto responde a la intención semántica porque convierte la colaboración en una mecánica central. Cada rol tiene capacidades y responsabilidades diferentes, los recursos que consigue un jugador condicionan las posibilidades del otro y el resultado final depende de las decisiones de ambos.

Como evidencia, puedo mostrar la sincronización entre los dos computadores, el desbloqueo de recursos, la intervención de la composición tipográfica y la transición al mundo generativo.

Uno de los principales logros es haber conseguido que las acciones de los dos jugadores formen parte de una misma experiencia. Sin embargo, todavía debo evaluar hasta qué punto las decisiones visuales y el mundo final comunican esa intención con suficiente claridad.

**Aspectos que considero logrados:**
- [ ] La interacción entre los dos roles es necesaria para completar la experiencia.
- [ ] Las acciones de los jugadores tienen consecuencias visibles.
- [ ] La composición tipográfica permite experimentar en lugar de seguir una única solución.
- [ ] El resultado final responde a las decisiones tomadas durante la partida.
- [ ] La identidad visual es coherente con los referentes elegidos.

**Aspectos que mejoraría:**
- [ ] La claridad y comodidad de los controles.
- [ ] La calidad visual y la profundidad del entorno generativo.
- [ ] La relación perceptible entre los recursos utilizados y el resultado final.
- [ ] [Agregar otro aspecto después de las pruebas.]

En general, creo que el proyecto tiene una base conceptual y técnica sólida, pero su éxito no depende solamente de que funcione. También depende de que las personas puedan descubrir la relación entre sus acciones y el resultado, y de que la experiencia visual haga sentir que están construyendo algo juntas.
