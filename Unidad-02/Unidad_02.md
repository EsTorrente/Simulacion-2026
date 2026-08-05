# 🌱 ACTIVIDAD 04

## 🌿 **1) Ideación**
Al ver los conjuntos de partículas creadas en los ejemplos, y con base en mi trabajo anterior, quedó en mí un asombro por lo fácil que es simular comportamientos complejos a partir de reglas muy simples. Basta con asignar pequeñas fuerzas de atracción, repulsión o movimiento para que aparezcan dinámicas que parecen tener intención propia. Me gusta mucho esa idea de que, al final, somos una colección de predisposiciones interactuando entre sí.  
  
Desde el primer momento que se mencionó el concepto de tensión, lo primero que vino a mi mente fue el movimiento de las mareas. El mar nunca está completamente quieto; constantemente empuja y luego devuelve. Nosotros parecemos seguir el mismo patrón: algo nos impulsa a buscar, investigar y perseguir aquello que queremos... y luego una palabra, una interacción, una presencia o un error nos hace retroceder.  

Es un proceso por el que paso con demasiada frecuencia. Un día estoy pensando en grande, imaginando proyectos ambiciosos, sintiendo la alegría de crear... y luego Juanferfranco vuelve a hablar de la IA y me achicopalo un poquito. Empiezo a dudar de la viabilidad, del concepto, del tiempo, de mi valor como artista, del valor del arte como tal, del público, de mi propósito, de mi utilidad... y bueno, la idea queda atrás (hasta que una semana después vuelve a empezar).  

Quiero representar esa contradicción.  
  

# 🌿 **2) Definición**

**`Intención:` ¿Qué transformación, sensación, tensión o idea debe experimentar quien observa?**

> Quiero que quien observe perciba cómo las partículas que fluyen parecen atorarse a veces y ser consumidas por otras. Que hay una tensión entre aquellas que avanzan y aquellas que se estancan, y tratan al mismo tiempo de hundir a las demás.


**`Entidades:` ¿Qué elementos existen? / `Relaciones:` ¿Cómo se afectan?**

> El sistema está compuesto por cinco especies de partículas que representan distintos impulsos internos. 

* **Miedos:** partículas que viajan en dirección contraria a la corriente principal. Se desplazan de manera errática, buscan acercarse a las almas y forman redes al conectarse entre sí. También se adhieren a los pulsos de muerte, utilizando estas partículas como puntos de anclaje. A medida que la red crece, aumenta su capacidad para atrapar y matar otras partículas.

* **Anhelos:** partículas que siguen el flujo de la corriente principal. Se desplazan suavemente intentando avanzar junto a las almas y los pulsos de vida. Cuando entran en contacto con una red de miedos, desaparecen, representando la manera en que las dudas pueden extinguir una posibilidad antes de que llegue a materializarse.

* **Pulsos de vida:** partículas que acompañan el movimiento de los anhelos. Su comportamiento refuerza la corriente principal y generan conexiones visuales que representan momentos de impulso, motivación o creatividad.

* **Pulsos de muerte:** partículas completamente inmóviles que funcionan como arrecifes. No persiguen nada ni cambian con el tiempo, pero sirven como puntos donde los miedos pueden sujetarse y extender sus redes, convirtiéndose en obstáculos permanentes dentro del paisaje.

* **Almas:** representan a cada organismo del sistema. Son las partículas alrededor de las cuales se organizan los demás impulsos. Avanzan siguiendo la corriente principal mientras son constantemente perseguidas por los miedos.


**`Matriz:`**
<img width="513" height="119" alt="image" src="https://github.com/user-attachments/assets/30cc5584-bbde-4957-b30c-96f46c6673d5" />

  
* Los miedos buscan a los anhelos (0.5), pero los anhelos también buscan a los miedos (0.7). Eso refleja que cuanto más importante es un sueño, más espacio ocupa también el miedo a fracasar. No es una persecución unilateral.  
* Los pulsos de vida no persiguen los anhelos (0), pero los anhelos sí buscan los pulsos de vida (0.8). La motivación no siempre aparece cuando la buscamos; somos nosotros quienes intentamos aferrarnos a esos momentos de inspiración cuando aparecen.  
* El alma busca intensamente los pulsos de vida (1.0), mientras que los pulsos de vida no necesitan perseguir al alma (0). La vida sucede, y la persona es quien intenta sostenerla.  
  
**`Entradas:` ¿Qué alimenta el sistema?**
  
> El sistema evoluciona principalmente a partir del tiempo y de las interacciones entre partículas. Sobre estas dinámicas actúa una corriente marina global que empuja constantemente a la mayoría de especies en una dirección, mientras los miedos avanzan en sentido contrario.
  
> El participante puede intervenir utilizando el mouse para alterar localmente estas corrientes, generando pequeños remolinos que modifican temporalmente el recorrido de las partículas. No controla directamente a ninguna de ellas; únicamente altera el flujo que las transporta.
  
  
**`Reglas:` ¿Cómo cambia el estado de un frame al siguiente?**
  
> En cada actualización, las partículas calculan las fuerzas ejercidas por las demás mediante una matriz de atracción y repulsión. A esto se suma una corriente global que desplaza a casi todas las especies hacia un mismo lado del espacio, mientras los miedos se resisten avanzando en dirección opuesta.
  
> Los miedos generan conexiones entre sí cuando se encuentran suficientemente cerca, formando redes que pueden apoyarse sobre los pulsos de muerte. Si un anhelo entra en contacto con una de estas redes, desaparece. Las almas continúan intentando avanzar mientras son perseguidas continuamente por los miedos.
  

**`Invariantes:` ¿Qué debe permanecer para conservar la identidad del sistema?**
  
> Siempre deben existir corrientes claramente identificables moviéndose en sentidos opuestos. Los miedos deben conservar la capacidad de formar redes, los pulsos de muerte deben permanecer completamente inmóviles y las almas deben continuar desplazándose dentro de la corriente principal mientras son perseguidas.
  
> Aunque cambien los parámetros del sistema, estas relaciones deben mantenerse para preservar la tensión entre avanzar y desistir.
  

**`Variabilidad:` ¿Qué puede cambiar sin destruir esa identidad?**
  
> Puede variar la cantidad de partículas, el número de almas presentes, la intensidad de la corriente, el alcance de las fuerzas de atracción, el tamaño de las partículas, la longitud de los rastros y los valores de la matriz de interacción.
  
> Además, los colores cambian lentamente con el paso del tiempo. Ninguna especie conserva un color fijo, obligando al observador a identificar los comportamientos antes que los colores. Esto busca representar cómo las emociones rara vez son completamente distinguibles; suelen confundirse entre sí hasta que prestamos atención a los patrones que generan.
  

**`Curaduría y reflexión:` ¿Qué resultado es significativo y cuál es solo un accidente interesante?**

> El resultado significativo es la aparición de corrientes que constantemente intentan avanzar mientras otras fuerzas construyen obstáculos capaces de detenerlas. También lo es la formación espontánea de redes de miedo alrededor de los arrecifes y la desaparición gradual de los anhelos cuando quedan atrapados por ellas.  
  
> En cambio, las formas exactas que adoptan las redes, las trayectorias particulares de cada organismo y las composiciones visuales que aparecen en cada ejecución son accidentes emergentes. No fueron diseñadas directamente, sino que nacen de la interacción entre reglas simples.  

___

# 🌱 ACTIVIDAD 5

🌿 **Formula la tensión:**  
Quiero explorar la tensión entre `los anhelos` y `los miedos`.  
  
🌿 **Describe brevemente cómo esperas que se manifieste en el comportamiento del sistema.**  
    
Espero que esta tensión se manifieste como un flujo constante de corrientes que avanzan en direcciones opuestas. La mayor parte del sistema intentará desplazarse siguiendo una misma marea, mientras los miedos nadarán contra ella, buscando tanto a las almas como a los arrecifes formados por los pulsos de muerte.  
  
La contradicción está incorporada en las reglas del sistema. Los anhelos, los pulsos de vida y las almas favorecen el movimiento continuo, mientras que los miedos construyen redes que nacen de los arrecifes y bloquean ese avance. Cuando un anhelo queda atrapado por una de estas redes desaparece, representando cómo una posibilidad puede extinguirse antes de llegar a realizarse.  
   
Ninguna de las dos fuerzas domina completamente el sistema. Las corrientes nunca dejan de avanzar, pero tampoco dejan de encontrar obstáculos.  


🌿 **Diseño del sistema**

1) `Tipos de partículas`

Seleccioné cinco tipos de partículas (alma, anhelos, miedos, pulsos de vida y pulsos de muerte) porque quiero hacer perceptible que un estado emocional complejo puede surgir de la interacción entre varios impulsos simples y no de una única fuerza dominante. Espero que produzca un sistema donde el comportamiento global emerja de las relaciones entre especies, permitiendo que aparezcan momentos de estabilidad, conflicto y reorganización sin necesidad de reglas específicas para cada situación.  
  
2) `Cantidad de partículas de cada tipo`
  
* 4 Almas (configurable)
* Aproximadamente 45 % Miedos
* Aproximadamente 35 % Anhelos
* Aproximadamente 20 % Pulsos de Vida
* Cantidad variable de Pulsos de Muerte (configurable)

**Justificación:**
Seleccioné una mayor proporción de miedos y anhelos porque quiero hacer perceptible que el conflicto principal ocurre entre estas dos fuerzas, mientras que la vida y la muerte actúan como influencias que modifican ese equilibrio. Espero que produzca una tensión constante en la que ninguna de las dos fuerzas desaparezca completamente y donde pequeñas variaciones puedan alterar el comportamiento colectivo.  

---

🌿 `Matriz de atracción, repulsión e indiferencia`
<a name="matrix"></a>
<img width="513" height="119" alt="image" src="https://github.com/user-attachments/assets/b2d75afd-ba37-453d-b38e-f83dce107f31" />

  
**Justificación:**
  
Seleccioné relaciones asimétricas entre algunas especies porque quiero representar que las influencias emocionales no siempre son recíprocas. En muchos casos una emoción puede afectar profundamente a otra sin recibir el mismo efecto de regreso.  
  
Algunas partículas persiguen aquello que desean, otras buscan aquello que las amenaza y otras simplemente permanecen inmóviles permitiendo que aparezcan nuevas dinámicas.  
  
🌿 `Intensidad y alcance de cada relación`

**Miedos**
   
* Atracción fuerte hacia pulsos de muerte y almas.  
* Atracción moderada hacia otros miedos y anhelos.  
* Repulsión frente a los pulsos de vida.  
  
**Anhelos**
  
* Atracción fuerte hacia pulsos de vida.  
* Atracción moderada hacia almas.  
* Ligera cohesión entre ellos.
* Evitan los pulsos de muerte.
  
**Pulsos de vida**
  
* Repelen los miedos.
* Debilitan la influencia de los pulsos de muerte.
  
**Pulsos de muerte**
  
* Permanecen inmóviles.
* Funcionan como arrecifes que atraen a los miedos y repelen la vida.

**Almas**
  
* Buscan la vida y los anhelos.
* Evitan los miedos y los pulsos de muerte.

**Justificación**
  
Seleccioné distintas intensidades porque quiero que algunas relaciones dominen el comportamiento del sistema mientras otras únicamente introduzcan pequeñas desviaciones. De esta manera aparecen corrientes generales claramente reconocibles sin eliminar la complejidad local del movimiento. También porque quiero que los miedos sean como especies aisladas de la corriente principal, intentando acercarse a las demás, pero atorándose en sus pulsos de muerte.  
  
🌿 `Distancias de interacción`
  
Cada partícula puede interactuar dentro de un radio configurable que determina hasta dónde alcanza su influencia sobre las demás.  
  
**Justificación:**
  
Seleccioné un radio de interacción compartido porque quiero que el comportamiento global dependa principalmente de las relaciones entre especies y no de diferencias arbitrarias en la distancia. Esto facilita que aparezcan estructuras colectivas como las redes de miedo o las corrientes de partículas.  
  
  
🌿 `Fricción y velocidad máxima`

|           | Miedos | Anhelos | Vida  | Muerte | Alma  |
| --------- | ------ | ------- | ----- | ------ | ----- |
| Velocidad | Alta   | Media   | Media | Cero   | Baja  |
| Fricción  | Media  | Media   | Media | Total  | Media |


**Justificación:**

Seleccioné una velocidad máxima compartida para los miedos, los anhelos y los pulsos de vida porque quiero hacer perceptible que sus diferencias de comportamiento provienen de las fuerzas que los afectan y de sus interacciones, y no de una ventaja física inherente. Espero que produzca un sistema donde cada especie exprese un movimiento característico únicamente como consecuencia de la matriz de atracción, las corrientes y las reglas emergentes.  
  
Seleccioné una velocidad máxima menor para las almas porque quiero hacer perceptible que actúan como núcleos estables que organizan a las demás partículas en lugar de perseguirlas activamente. Espero que produzca organismos con un centro relativamente constante alrededor del cual puedan reorganizarse los anhelos, los miedos y los pulsos de vida.  
  
Seleccioné una velocidad nula para los pulsos de muerte porque quiero hacer perceptible que representan obstáculos permanentes dentro del entorno y no agentes móviles. Espero que produzca puntos de influencia fijos que modifiquen el recorrido de las demás partículas y favorezcan la formación de regiones dominadas por el miedo.  
  
Seleccioné una fricción global para todas las partículas móviles porque quiero hacer perceptible que todas están sometidas al mismo medio, como si compartieran una misma corriente oceánica. Espero que produzca movimientos suaves y continuos, evitando aceleraciones indefinidas y permitiendo que las diferencias entre especies surjan principalmente de sus relaciones e interacciones, en lugar de parámetros físicos distintos.  
  
🌿 `Distribución inicial`

Las almas aparecen distribuidas en distintos puntos del espacio. Alrededor de ellas se generan anhelos, miedos y pulsos de vida. Los pulsos de muerte aparecen dispersos por el escenario.  
  
**Justificación:**
  
Seleccioné una distribución inicial organizada alrededor de las almas porque quiero hacer perceptible que cada organismo comienza con un equilibrio interno antes de enfrentarse a las influencias externas. Espero que produzca varios núcleos independientes que evolucionen de forma distinta y que el comportamiento final dependa de las interacciones del sistema y no de posiciones completamente aleatorias.  

### **Justificación**

Seleccioné una distribución inicial agrupada alrededor de las almas porque quiero que desde el primer instante existan pequeños organismos que posteriormente sean transformados por las corrientes y por las interacciones entre especies.

---

🌿 `Parámetros constantes y variables`

| Constantes                                                                                                                        | Variables                                                                                                                                        |
| --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| Tipos de partículas, reglas de interacción, dirección general de las corrientes, comportamiento estático de los pulsos de muerte. | Cantidad de partículas, número de almas, intensidad de la corriente, matriz de atracción, tamaño de partículas, colores, alcance de interacción. |

### **Justificación**

Seleccioné estos parámetros porque quiero mantener una identidad reconocible entre ejecuciones mientras permito que cada simulación produzca configuraciones distintas. Aunque cambien las formas, las trayectorias o los colores, siempre debe percibirse el mismo conflicto entre avanzar con la corriente y quedar atrapado por las redes del miedo.

---

🌿 `Todo completito`

Quiero explorar la tensión entre **los anhelos** y **los miedos**.
  
Quiero representar esa tensión como el flujo de corrientes marinas. Mientras las almas, los anhelos y los pulsos de vida avanzan siguiendo la corriente, los miedos nadan en sentido contrario, persiguen a las almas y construyen redes sobre arrecifes inmóviles formados por los pulsos de muerte. Cuando un anhelo queda atrapado en una de estas redes desaparece, mostrando cómo las dudas pueden extinguir una posibilidad antes de que llegue a convertirse en realidad.
  
Mi intención es que esta contradicción no se explique mediante símbolos, sino que sea visible en el comportamiento emergente del sistema: las corrientes representan el impulso de avanzar, mientras las redes muestran cómo el miedo puede convertir el movimiento en estancamiento. Los colores cambian continuamente para recordar que las emociones rara vez son completamente claras; sólo al observar sus patrones de interacción es posible distinguirlas.
<a name="particulas"></a>
| **Característica**             | **Miedos**                                      | **Anhelos**                           | **Pulsos de vida**                  | **Pulsos de muerte**               | **Almas**                                                          |
| ------------------------------ | ----------------------------------------------- | ------------------------------------- | ----------------------------------- | ---------------------------------- | ------------------------------------------------------------------ |
| **Forma**                      | Círculo pequeño que puede crecer y formar redes | Círculo pequeño con pulsación suave   | Dos círculos concéntricos pulsantes | Círculo compacto                   | Núcleo brillante con halo pulsante                                 |
| **Movimiento**                 | Rápido y errático                               | Fluido y estable                      | Fluido y estable                    | Inmóvil                            | Lento y estable                                                    |
| **Velocidad máxima (`maxSp`)** | **1.7** (Alta)                                  | **1.7** (Alta)                        | **1.7** (Alta)                      | **0.0** (Nula)                     | **0.7** (Baja)                                                     |
| **Fricción**                   | **0.900**  (modificable)                                     | **0.900**                             | **0.900**                           | No aplica (estático)               | **0.900**                                                          |
| **Comportamiento**             | Se agrupan, forman redes y persiguen anhelos    | Buscan vida y almas; evitan la muerte | Atraen anhelos y repelen miedos     | Actúan como obstáculos permanentes | Funcionan como núcleos alrededor de los cuales surge el ecosistema |
| **Rol simbólico**              | Miedo y pensamientos negativos que se propagan  | Esperanza, metas y deseos             | Energía vital y crecimiento         | Estancamiento o desesperanza       | El ser vivo o la conciencia que da origen al sistema               |

  
___

# 🌱 DESARROLLO

Comencé por pedirle a cada una de las IAs que me entregara un sistema de particle life para p5.js que simulara el movimiento de olas o corrientes.  
  
**Resultado inicial de DeepSeek:**
<img width="919" height="878" alt="image" src="https://github.com/user-attachments/assets/214ee728-4e33-4f69-a2f6-8802dc55a8fa" />
  
**Resultado inicial de Gemini:**
<img width="921" height="786" alt="image" src="https://github.com/user-attachments/assets/ad910934-8dbe-4290-aec6-951a9ff517dc" />
  
**Resultado inicial de ChatGPT:**
<img width="917" height="785" alt="image" src="https://github.com/user-attachments/assets/c2c568fc-1841-4935-b218-f75242d83567" />
  
**Resultado inicial de Claude:**
<img width="1101" height="916" alt="image" src="https://github.com/user-attachments/assets/9a5b65fd-a42e-4185-9850-4f9116bdcb6f" />

___
  
Me voy a ir con Gemini y claude de nuevo. Ahora le pedí que agregaran la interacción del mouse a ella.  
  
**Segundo resultado de Gemini:**
<img width="920" height="793" alt="image" src="https://github.com/user-attachments/assets/681f394f-9bfc-4b57-8bf2-ded7e0bd0869" />

**Resultado inicial de Claude:**
<img width="1101" height="916" alt="image" src="https://github.com/user-attachments/assets/9a5b65fd-a42e-4185-9850-4f9116bdcb6f" />

___

**Tercer resultado de Gemini:**
<img width="917" height="778" alt="image" src="https://github.com/user-attachments/assets/bd62ce75-019e-412d-a567-c7bac252c5d3" />

**Intento de gemini de replicar el de Claude:**
<img width="1186" height="782" alt="image" src="https://github.com/user-attachments/assets/3694c1f6-912c-47d4-ba17-a7d2d701e26a" />

___

Aquí ya sentí que no estaban cuadrando las cosas. Se estaban perdiendo las corrientes y el propósito inicial del modelo. Sentía que se veían mucho como células y no como corrientes:


<img width="1187" height="784" alt="image" src="https://github.com/user-attachments/assets/ea3a16f5-f58a-4031-834d-5a6e02c0f5fd" />

<img width="1187" height="766" alt="image" src="https://github.com/user-attachments/assets/62572c69-944e-4a13-83d0-0a1cdadab06c" />

<img width="907" height="916" alt="image" src="https://github.com/user-attachments/assets/0ad4e660-17a6-4f55-915b-1dad426b4de2" />

<img width="887" height="902" alt="image" src="https://github.com/user-attachments/assets/fbe69e6e-243b-465e-845f-2b24eafa29dd" />
  
Por lo que volví a intentar, modificando los parámetros hasta que conseguí algo más similar a lo que buscaba inicialmente:  

<img width="838" height="758" alt="image" src="https://github.com/user-attachments/assets/a6d2aaab-9d05-4ff5-bd67-37c0f0341fd4" />

<img width="838" height="780" alt="image" src="https://github.com/user-attachments/assets/c32648b6-3355-42d2-a128-ae82eb6667c1" />
  
Comencé a iterar sobre el diseño estético para generar esa sensación de un océano profundo.  

<img width="839" height="777" alt="image" src="https://github.com/user-attachments/assets/7e806da7-d6cb-418c-8145-e3b5edfde3f9" />

<img width="942" height="543" alt="image" src="https://github.com/user-attachments/assets/04a3c020-bdf0-4424-bfa9-46bc0fbbc6d6" />

<img width="940" height="536" alt="image" src="https://github.com/user-attachments/assets/d1b0a234-6dff-4596-b37d-f766503a5ca2" />
  
Y finalmente, llegué a este resultado:

<img width="848" height="541" alt="image" src="https://github.com/user-attachments/assets/086f2460-c473-4416-b4d2-3f3f5e880501" />

<img width="847" height="531" alt="image" src="https://github.com/user-attachments/assets/19181a7e-05ad-4c3f-9b43-1137c38dcaad" />

<img width="922" height="531" alt="image" src="https://github.com/user-attachments/assets/179a6a9f-f416-4b8a-bdb9-54456c25a884" />

Ya por último, le agregué la variación con el tiempo de colores. Este fue el resultado final:

### ⭐ LINK AL SKETCK:
[Clic aquí.](https://editor.p5js.org/EsTorrente/full/KTPeq_rUd)

| Requisito                                                    | ¿Cumple? | Evidencia                                                                                                                                                                                                                                                            |
| ------------------------------------------------------------ | :------: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Posición, velocidad y aceleración**                        |     ✅    | Cada partícula tiene `px`, `py` (posición), `vx`, `vy` (velocidad). La aceleración no se almacena explícitamente, pero se calcula cada frame acumulando fuerzas (`fx`, `fy`) y luego se integra a la velocidad: `vx += fx`, `vy += fy`. |
| **Varias poblaciones de partículas**                         |     ✅    | [Hay cinco poblaciones:](#particulas) **Miedos**, **Anhelos**, **Vida**, **Muerte** y **Almas**.                                                                                                                                                                 |
| **Interacciones dependientes de la distancia**               |     ✅    | Todas las fuerzas sólo se aplican si la distancia es menor que `maxR`. Además la intensidad depende de la distancia mediante `forceFn()`.                                                                                                                            |
| **Relaciones de atracción, repulsión o indiferencia**        |     ✅    | [Matriz](#matrix)                                                                                                                                                                             |
| **Al menos una relación asimétrica**                         |     ✅    | No todas las relaciones son recíprocas. [Matriz](#matrix)                                                                                      |
| **Variabilidad entre ejecuciones**                           |     ✅    | Las almas aparecen en posiciones aleatorias, las demás partículas se distribuyen aleatoriamente alrededor de ellas y además sus velocidades iniciales también son aleatorias. Cada ejecución comienza distinta.                                                      |
| **Comportamientos emergentes, no trayectorias predefinidas** |     ✅    | Ninguna partícula sigue un camino programado. El movimiento surge de la combinación de la corriente, las fuerzas entre partículas, la fricción, las conexiones y la aleatoriedad.                                                                                    |
| **Una identidad reconocible entre diferentes resultados**    |     ✅    | Aunque cambien las posiciones iniciales, siempre aparecen los mismos patrones: redes de miedos, agrupaciones alrededor de almas, corrientes de vida hacia la derecha, arrecifes de muerte y anhelos siguiendo la corriente.                                          |
| **Las partículas pueden ser círculos o puntos**              |     ✅    | Todas las partículas son círculos, no se utilizan otras figuritas.                                                                                                                                                                                     |
# ⭐ ENTREGABLES 
  
⭐ `LINK AL SKETCK:` [Clic aquí.](https://editor.p5js.org/EsTorrente/full/KTPeq_rUd)
  
___

## FICHA TÉCNICA:

**Tensión**

El sistema representa la lucha constante el miedo y los anhelos.

**Intención**

Hacer perceptible el conflicto emocional común de ser controlado y limitado por nuestros miedos, representando visualmente la dinámica entre estas inclinaciones internas. Se hace uso de las corrientes marinas como metáfora para representar el avance de los seres, limitado por las redes de miedo que se atascan en los pulsos de muerte.  


**Tipos y cantidades**

| Tipo             |                Cantidad |
| ---------------- | ----------------------: |
| Almas            |        4 (configurable) |
| Miedos           |              aprox 45 % |
| Anhelos          |              aprox 35 % |
| Pulsos de vida   |              aprox 20 % |
| Pulsos de muerte | Variable (configurable) |

Los miedos y los anhelos constituyen la mayor parte del sistema porque representan el conflicto principal. Las almas funcionan como núcleos organizadores, mientras que los pulsos de vida y muerte modifican continuamente la dinámica general.


**Reglas principales**

* Las partículas interactúan mediante fuerzas de atracción, repulsión o indiferencia.
* Las interacciones dependen de la distancia.
* Los miedos forman redes entre sí.
* Los pulsos de vida pueden romper esas redes.
* Los anhelos buscan la vida y las almas.
* Los miedos son atraídos por la muerte.
* Las almas buscan la vida y los anhelos mientras evitan el miedo y la muerte.
* Una corriente global desplaza los miedos hacia un lado y la vida junto con los anhelos hacia el contrario.
* Los pulsos de muerte permanecen inmóviles.


**Matriz de relaciones**

<img width="513" height="119" alt="image" src="https://github.com/user-attachments/assets/fa08830f-5509-4579-b86f-028233569c39" />


La matriz incorpora relaciones asimétricas para representar que algunas influencias emocionales no son necesariamente recíprocas. Las principales relaciones son:  
* Los miedos buscan a los anhelos (0.5), pero los anhelos también buscan a los miedos (0.7). Eso refleja que cuanto más importante es un sueño, más espacio ocupa también el miedo a fracasar. No es una persecución unilateral.  
* Los pulsos de vida no persiguen los anhelos (0), pero los anhelos sí buscan los pulsos de vida (0.8). La motivación no siempre aparece cuando la buscamos; somos nosotros quienes intentamos aferrarnos a esos momentos de inspiración cuando aparecen.  
* El alma busca intensamente los pulsos de vida (1.0), mientras que los pulsos de vida no necesitan perseguir al alma (0). La vida sucede, y la persona es quien intenta sostenerla.  


**Parámetros principales y justificación**

| Parámetro            | Valor                                |
| -------------------- | ------------------------------------ |
| Radio de interacción | 61 px                                |
| Velocidad máxima     | 1.7 (excepto almas: 0.7 y muerte: 0) |
| Fricción             | 0.900                                |
| Corriente global     | 1.40                                 |
| Espaciado inicial    | 1.90                                 |
| Tamaño base          | 1.5                                  |

**Justificación**

Los parámetros fueron seleccionados para favorecer la aparición de estructuras colectivas en la forma de las corrientes. La velocidad limita movimientos excesivos, la fricción suaviza las trayectorias (sin ser muy alta, para que igual parezca que están flotando y siendo llevadas por la marea) y el radio de interacción permite que las relaciones locales se conviertan en patrones globales. El parámetro de la corriente es lo principal, pues sin él se perdería la mayor parte del significado.  


**Invariantes**

Siempre permanecen constantes:
* Cinco tipos de partículas.
* Reglas de interacción.
* Relaciones de la matriz.
* Corrientes principales.
* Pulsos de muerte inmóviles.
* Existencia de al menos un conflicto entre miedo, vida y anhelos.
  
**Variables**
Pueden modificarse:

* Cantidad total de partículas.
* Número de almas.
* Cantidad de pulsos de muerte.
* Intensidad de la corriente.
* Alcance de interacción.
* Valores de la matriz.
* Tamaño de partículas.
* Fricción.
* Velocidad máxima.
* Distribución inicial.

___

## Variaciones del sistema:
<img width="957" height="549" alt="image" src="https://github.com/user-attachments/assets/45b992e5-0fc5-4a66-a11f-37dcc5fb53c8" />
<img width="954" height="523" alt="image" src="https://github.com/user-attachments/assets/5e5664da-9ac3-4120-bf0c-9bc08f9b0884" />
<img width="958" height="536" alt="image" src="https://github.com/user-attachments/assets/eb213f2f-a71d-4dbf-bbaf-dc068b93a153" />
<img width="952" height="530" alt="image" src="https://github.com/user-attachments/assets/40901afa-0c6b-4d8c-a074-71ad39733ed0" />



## Autoevaluación:

| Criterio                                                                          |   Peso   | Valoración (/100) |   Aporte  |
| --------------------------------------------------------------------------------- | -------- | ----------------- | --------- |
| La intención es clara y perceptible en el comportamiento.                         |    20%   |       **98**      |  **19.6** |
| Los tipos, cantidades, matriz y parámetros están justificados desde la intención. |    25%   |       **100**      |  **25** |
| Comprendo y puedo modificar el funcionamiento técnico del sistema.                |    20%   |       **85**      |  **17** |
| El sistema produce variaciones con una identidad reconocible.                     |    15%   |       **100**      | **15** |
| Experimenté, comparé, seleccioné y descarté con criterios claros.                 |    10%   |       **100**      |  **10**  |
| Puedo distinguir y sustentar lo diseñado y lo emergente.                          |    10%   |       **100**      |  **10**  |
| **Total**                                                                         | **100%** |                   | **96.6** |

`NOTA:` 4.8
