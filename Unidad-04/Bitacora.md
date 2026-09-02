# 🌱 PROCESO IDEACIÓN
  
**IDEA PRINCIPAL:**  
varios elementos con distintos sonidos y bpm. Se pueden sincronizar para formar una canción armoniosa, y volver a enredarse.

**POSIBLES REFERENTES:**
- [Manos?](https://youtu.be/WC8QrR72UTM?si=-8CvzvpGUw_Mu5FM&t=145). Me gusta esta estética.
- [Edición de video?](https://youtu.be/E_sY1PgQ5p4?si=1QzQ3p66wr0xWK9u). [Videos son afectados por distintos parámetros de post procesado. Cada grupito de pixel tiene su reloj interno de kuramoto](https://youtu.be/DKHYfwcx028?si=XrQTAwd1T3ZfLr7a) con la posibilidad de [sincronizarse](https://youtu.be/4JunL8aPS8Q?si=Hsz7GVJq0x3DPblt). Cada uno de ellos emite sonidos con distinto BPM.
- [Flocks de pájaros.](https://p5js.org/examples/Classes-And-Objects-Flocking/)

Inspo de cosas chéveres:
- Nada qué ver, pero [esto está cool](https://p5js.org/sketches/2213463/)
- [Shaders p5.js](https://p5js.org/tutorials/intro-to-p5-strands/)
- [Caminantes?](https://github.com/tetunori/BMWalker.js)

___

# 🌱 IDEA FINAL

La idea final del proyecto es una experiencia audiovisual interactiva en tiempo real que utiliza los sonidos y la identidad visual de los pajaritos que vemos a diario en la ciudad (menos el barranquero, ese fue un capricho) para convertir un sistema de osciladores acoplados mediante el modelo de Kuramoto en un instrumento audiovisual.

La intención inicial era crear un proyecto que le permitiera a los usuarios aprender a identificar los sonidos de estas aves entre el caos diario de la ciudad y ruidos de otros animales. La idea surgió porque estuve escuchando unas grabaciones que hice de cantos de pájaros, y me di cuenta de que a pesar de que todos cantaban en tonalidades y ritmos distintos, se acoplaban para sonar como una melodía unificada.  

El usuario puede construir una pequeña composición utilizando ocho aves diferentes. Cada pista del secuenciador representa un agente del sistema y tiene asociada una especie de ave, un sonido y una personalidad audiovisual. El usuario puede activar o desactivar las casillas de la secuencia y, al reproducirla, una línea recorre cada pista individualmente y activa los sonidos correspondientes.

Debajo de la secuencia existe un sistema de 8 osciladores de Kuramoto que determina la fase y la relación entre los agentes. Por lo tanto, cada ave tiene su propio estado dentro del sistema dinámico y las relaciones entre ellas producen diferentes niveles de organización.

La experiencia busca que el usuario pueda pasar de un estado de desorden, donde las aves se comportan de manera relativamente independiente, a una organización parcial y finalmente a una organización estable, modificando el acoplamiento del sistema. También puede perturbar agentes individuales para romper temporalmente esa organización y observar cómo el colectivo responde.

Sobre este comportamiento se construye la capa visual. El estado del sistema alimenta una simulación inspirada en la [ecuación de Kuramoto–Sivashinsky](https://www.youtube.com/watch?v=OWYz3bVKl6k), que genera un campo fluido y cambiante. Este campo funciona como la base de la visualización audiovisual y se combina con los videos de las aves para producir una imagen generativa que cambia a medida que cambia el sistema.

___

## Proceso de creación

Desde el principio entendí que intentar pedirle a una IA que construyera toda la experiencia en un solo prompt probablemente produciría un proyecto demasiado complejo y difícil de controlar. Por eso decidí separar el desarrollo en diferentes fases, construyendo primero cada sistema de manera relativamente independiente y luego conectándolos.

Esto también me permitió probar cada parte antes de agregar otra, en lugar de tener que corregir al mismo tiempo problemas de audio, interacción, simulación y visualización.

### 1. Primer prototipo: secuenciador + Kuramoto

Primero me concentré en construir la parte más cercana a la interacción musical.

La primera meta fue tener un secuenciador de ocho pistas donde cada pista pudiera representar un agente y donde el usuario pudiera activar diferentes momentos de reproducción. Aún no agregué cambios de pitch ni nada muy complejo; simplemente buscaba asegurarme de que el audio funcionara. Al inicio, no lo hizo... pero tras un poco de debugging y cambio de los métodos de reproducción, todo funcionó correctamente.  

A partir de ahí incorporé el modelo de Kuramoto. Cada una de las ocho aves pasó a tener una fase propia `θ`, una frecuencia natural `ω` y una relación de acoplamiento con las otras aves.

También incorporé el cálculo del **parámetro de orden de Kuramoto `R`**, que permite medir qué tan sincronizado está el colectivo.
En la experiencia, `R` se utiliza para distinguir entre diferentes estados colectivos.

<img width="829" height="755" alt="image" src="https://github.com/user-attachments/assets/b86ac3c7-c57e-4920-b6f4-a0ce928fe409" />  
  

En esta primera etapa el objetivo no era que se viera bonito. Quería comprobar que el sistema dinámico funcionara y que los agentes realmente pudieran sincronizarse.

___

## 2. Segundo proyecto: Kuramoto–Sivashinsky

Después de tener funcionando el sistema de Kuramoto y el secuenciador, decidí trabajar la parte visual en un proyecto separado.

En lugar de intentar integrar inmediatamente una simulación compleja con toda la interfaz, le pedí a la IA que recreara el comportamiento de una implementación de Kuramoto–Sivashinsky basada en el repositorio:

[RichtersFinger/Fortran2dETDRK4](https://github.com/RichtersFinger/Fortran2dETDRK4)

El repositorio implementa un esquema ETDRK4 pseudo-espectral en dos dimensiones, utilizando FFTW para trabajar espacialmente en el dominio de Fourier. También incluye versiones amortiguadas de la ecuación de Kuramoto–Sivashinsky. Este fue el resultado obtenido:

<img width="595" height="596" alt="image" src="https://github.com/user-attachments/assets/17fa991e-6c00-4e39-8369-fe4be9b4e7b2" />  
  
Esta parte requirió bastante iteración porque la primera versión del campo terminaba rápidamente concentrándose en un color. Al observar el repositorio, entendí que necesitaba introducir un damping para evitar que los valores de la simulación crecieran hasta consumir visualmente todo el campo.

Por eso añadí un término de amortiguación a la dinámica. En la implementación final aparece como:

```javascript
float damp = damping * uC;
```

y se resta dentro de la actualización del campo.

___

## 3. Evolución visual del campo

Una vez conseguí que la simulación pudiera mantenerse estable, empecé a trabajar la apariencia.

Quería que el campo se sintiera menos como una representación científica y más como una especie de fluido y células. Por eso experimenté con la forma en que sus valores eran interpretados visualmente y pedí que el `hue` cambiara con el tiempo.
La intención era que la simulación no fuera solamente una imagen estática coloreada, sino una superficie en movimiento continuo.

También incorporé efectos audiovisuales como cambios de intensidad, perturbaciones y bloom para que el sistema pudiera reaccionar a lo que estaba ocurriendo en la experiencia. En el código, por ejemplo, el nivel de audio modifica diferentes parámetros visuales y se utilizan varias pasadas de shader para la simulación y el procesamiento final.

___

## 4. Unión de ambos proyectos

Cuando los dos sistemas funcionaban por separado, pedí que fueran integrados.
De esta manera, el comportamiento colectivo de los agentes afecta directamente a la evolución del campo visual. Pedí que refinara el UI y agregara unas tarjetas con los nombres de las palomas en cada lado de la pantalla, además de darme una opción de ocultar el secuenciador para poder admirar las visuales.

Una vez que la parte central estaba funcionando, empecé a concentrarme menos en la simulación y más en cómo se experimentaba el sistema.
Definí los distintos tipos de personalidades y su impacto en el las visuales del fondo, y le di al usuario la opción de cambiarlos al hacer clic en él.  


- `Cantor (0, 1):` Fuerte impacto en el sistema. Cuando cantan, crean "huecos" enormes en el campo visual.  
- `Temblorosos (2, 3):` Rebeldes. Se resisten al acoplamiento de Kuramoto (sensibilidad reducida a K), lo que hace que "tiemblen" entrando y saliendo de fase antes de sucumbir finalmente al grupo.  
- `Planeadores (4, 5):` Fluidos. Su frecuencia de reproducción de audio sube y baja dinámicamente en tiempo real según la velocidad instantánea de su agente mientras son arrastrados por el grupo.   
- `Resonadores (6, 7):` Recursivos. Generan orgánicamente un eco secundario y más silencioso exactamente 150 ms después de su impacto principal, llenando el espacio.  
  
  
<img width="1600" height="782" alt="image" src="https://github.com/user-attachments/assets/d646ca16-b3b9-4f0f-ab1e-afde3caa3d06" />
<img width="1600" height="789" alt="image" src="https://github.com/user-attachments/assets/85b137b0-255c-4fb5-846b-f743e96e0fdd" />
<img width="1600" height="790" alt="image" src="https://github.com/user-attachments/assets/714752bf-406d-48d7-9995-def89e84649b" />
  
Agregué un ícono de rayo al lado derecho de cada track que permitiera perturbar la fase de cada agente.  

Para que la utilización del programa fuera mucho más sencilla, agregué la posibilidad de arrastrar las aves desde los laterales hacia las pistas del secuenciador.
Esto hace que cambiar la composición sea más parecido a organizar un conjunto de agentes que a editar parámetros de un programa.
Las tarjetas de las aves contienen su imagen, nombre y nombre científico, y pueden ser arrastradas directamente hacia una pista.

Además, modifiqué el secuenciador para que cada una de las ocho posiciones del secuenciador esté asociada a una relación de pitch diferente. De esta manera, las aves no solamente representan diferentes timbres, sino que pueden ocupar distintas posiciones dentro de una escala musical. La reproducción mantiene como base la grabación real del ave y modifica su `playbackRate` de acuerdo con la pista y la personalidad del agente. Para mí era importante que el usuario pudiera seguir escuchando el sonido en su tono original, así que definí que en el botón para aislar la pista se pausaría el efecto del pitch.

___

## 8. Tutorial y producto final

Finalmente agregué un tutorial para que el sistema pudiera ser explorado sin necesidad de explicar previamente el funcionamiento.

El tutorial explica:

1. cómo elegir las aves;
2. cómo cambiar su personalidad;
3. cómo activar las casillas musicales;
4. cómo utilizar mute y solo;
5. cómo modificar el acoplamiento;
6. cómo comenzar la experiencia.

También incluye una explicación sencilla del fenómeno de sincronización de Kuramoto para que el usuario pueda entender intuitivamente lo que está pasando.

<img width="1898" height="912" alt="image" src="https://github.com/user-attachments/assets/525984e4-be4a-4600-9cef-5a7cfb03c0b6" />
<img width="1869" height="919" alt="image" src="https://github.com/user-attachments/assets/b82c42cc-7673-46ad-8cc9-569afc6f7de7" />

___

# 🌱 Herramientas e IA utilizadas

Para desarrollar el proyecto utilicé principalmente IA generativa como herramienta de programación y prototipado, pero no le pedí que resolviera todo el proyecto en un único prompt.

Probé diferentes modelos y terminé utilizando principalmente Gemini Pro en distintas cuentas, porque dentro del tier gratuito me pareció que ofrecía el mejor equilibrio entre calidad visual, capacidad de programación y cantidad de iteraciones posibles.

La estrategia fue dividir el trabajo en fases:

1. Kuramoto básico + secuenciador
2. Simulación Kuramoto–Sivashinsky
3. Integración de ambos sistemas
4. Interacción y audiovisual
5. Información, tutorial y pulido de UI

Esto fue especialmente importante porque los problemas que aparecían en una etapa podían resolverse antes de introducir otra capa de complejidad.

___

# 🌱 JUSTIFICACIONES

| Variable / concepto                     | ¿Qué representa en Kuramoto?                                                                                                                                                                                   | ¿Qué representa en mi proyecto?                                                                                                                                                                                                                           | ¿Cómo afecta la experiencia?                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Número de agentes — `N`**             | Es la cantidad de osciladores que participan en el sistema.                                                                                                                                                    | `N = 8` y representa las **ocho aves** que participan simultáneamente. Cada una tiene su propia fase y está conectada con los otros siete agentes.                                                                                                        | Determina el tamaño del colectivo. Las ocho aves pueden influirse entre sí y formar diferentes estados de organización.                                                                                                                                                                                                                                                                                                                                                                 |
| **Fase — `θᵢ`**                         | Representa el estado actual de cada oscilador dentro de su ciclo.                                                                                                                                              | Representa el **estado de fase de cada ave** dentro de su ciclo.                                                                                                                                                                                          | La fase determina la posición del agente dentro del ciclo temporal del secuenciador. Al avanzar la fase, el agente recorre las posiciones de la secuencia y puede activar los sonidos correspondientes. Por esto, el playhead no es simplemente un reloj externo: está vinculado a la evolución de las fases de los agentes. En el código: `this.theta += this.instVelocity * deltaTime;` Posteriormente, la fase se convierte en una posición dentro de los 16 pasos del secuenciador. |
| **Frecuencia natural — `ωᵢ`**           | Es la velocidad natural a la que cada oscilador tiende a avanzar cuando no existe acoplamiento.                                                                                                                | Cada ave tiene una frecuencia natural diferente, construida a partir del BPM y de una dispersión particular de cada agente. <br><br>`javascript<br>let baseOmega = (bpm / 60.0) / 4.0 * TWO_PI;<br>let myOmega = baseOmega + (this.offset * spread);<br>` | Hace que las aves tengan inicialmente diferentes ritmos o tendencias de movimiento. La variable `spread` determina cuánto se diferencian estas frecuencias naturales entre sí.                                                                                                                                                                                                                                                                                                          |
| **Acoplamiento — `K`**                  | Determina la **fuerza con la que los osciladores se influyen entre sí**.                                                                                                                                       | Representa la fuerza con la que las **aves se afectan entre sí**. Es una de las variables que el usuario puede modificar en tiempo real.                                                                                                                  | Cuando `K` aumenta, las diferencias de fase tienen mayor influencia sobre la evolución de los agentes, haciendo que el sistema tienda hacia una mayor sincronización. Cuando `K` disminuye, las aves tienen mayor libertad para mantener sus propias frecuencias. Esto permite al performer provocar deliberadamente cambios en la organización del colectivo.                                                                                                                          |
| **Diferencia de fase — `sin(θⱼ − θᵢ)`** | Determina la influencia que tiene el oscilador `j` sobre el oscilador `i` dependiendo de qué tan diferentes sean sus fases.                                                                                    | Representa la relación temporal entre una ave y las demás. Una ave puede estar adelantada o atrasada respecto a las otras.                                                                                                                                | Esta diferencia determina cuánto debe modificarse la velocidad de cada agente. En conjunto, estas influencias producen el comportamiento colectivo. En el código: <br><br>`javascript<br>sum += sin(agents[j].theta - this.theta);<br>`<br><br>y posteriormente:<br><br>`javascript<br>let coupling = (effectiveK / N) * sum;<br>`                                                                                                                                                      |
| **Velocidad instantánea — `dθᵢ/dt`**    | Es la velocidad con la que cambia la fase de un oscilador. Resulta de combinar su frecuencia natural con la influencia de los demás agentes: <br><br>\(\dot{\theta_i} = \omega_i + \text{acoplamiento}\)       | Representa la velocidad con la que cambia el estado de cada ave dentro de su ciclo.                                                                                                                                                                       | Determina cómo evoluciona la fase de cada agente y, por lo tanto, cuándo avanza dentro de su secuencia. La velocidad no depende únicamente de su ritmo individual: también cambia como consecuencia de las demás aves.                                                                                                                                                                                                                                                                  |
| **Parámetro de orden — `R`**            | Mide el **nivel de sincronización del colectivo**. Su valor se encuentra entre `0` y `1`. <br><br>• `R ≈ 0` → fases desordenadas<br>• `R` intermedio → organización parcial<br>• `R ≈ 1` → alta sincronización | Representa qué tan organizadas o sincronizadas están las ocho aves en un momento determinado.                                                                                                                                                             | Permite identificar los tres estados colectivos de la experiencia: **DESORDEN**, **ORGANIZACIÓN PARCIAL** y **ORGANIZACIÓN ESTABLE**. Además, el valor de `R` se utiliza para modificar aspectos de la visualización, haciendo que la sincronización tenga una consecuencia perceptible. En el código: <br><br>`javascript<br>R = sqrt(sumCos * sumCos + sumSin * sumSin) / N;<br>`                                                                                                     |

___

### ¿Cómo producen estas variables el comportamiento observado?

El comportamiento de la experiencia aparece de la interacción entre todas estas variables.
Al comenzar, cada ave tiene una fase y una frecuencia propia. Por lo tanto, si el acoplamiento `K` es bajo, las aves tienden a moverse de manera relativamente independiente.
Al aumentar `K`, la influencia entre las fases aumenta. Esto hace que las diferencias individuales comiencen a reducirse y aparezcan patrones colectivos.

Lo importante es que estos estados no están escritos como una animación predeterminada. El estado se determina a partir de `R`, que a su vez depende de las fases reales de los ocho agentes.

Además, el usuario puede introducir una perturbación individual.

Cada pista tiene un botón de perturbación que modifica directamente la fase del agente:

```javascript
agents[row].theta += random(PI, TWO_PI);
```

___

## Modificación y extensión del modelo

La implementación parte del modelo original de Kuramoto, pero incorpora una variación relacionada con las personalidades de los agentes.

Una de las personalidades utiliza un acoplamiento reducido:

```javascript
let effectiveK = (pType === 1) ? K * 0.35 : K;
```

Esto significa que el valor global de `K` sigue siendo controlado por el usuario, pero determinados agentes presentan una respuesta diferente al acoplamiento.

La intención de esta modificación es evitar que las ocho aves se comporten como copias idénticas y utilizar la estructura matemática del modelo como base para crear identidades audiovisuales diferentes.

___

## Relación entre Kuramoto, sonido e imagen

Una de las partes más importantes del proyecto fue evitar que Kuramoto se convirtiera simplemente en "un algoritmo que existe por detrás".

En la experiencia, sus efectos aparecen en diferentes niveles.

### En el tiempo

La fase `θᵢ` de cada agente determina su posición dentro del ciclo del secuenciador.

### En el sonido

Cuando un agente alcanza una determinada posición de su ciclo y existe un evento activo en esa posición, se reproduce el sonido real de su ave.

Además, las personalidades pueden modificar la forma en que se reproduce ese sonido.

### En el estado colectivo

`R` determina si el sistema se encuentra en desorden, organización parcial, u organización estable.

### En la visualización

El estado colectivo modifica parámetros utilizados por la simulación visual. Por ejemplo:

```javascript
damping = lerp(0.3, 0.04, R);
```

Esto crea una conexión entre la organización del sistema de agentes y el comportamiento del campo visual.

Por lo tanto, Kuramoto no puede eliminarse simplemente y reemplazarse por un reloj global sin modificar la experiencia. Un reloj podría decirnos **cuándo** reproducir algo, pero no produciría la misma relación dinámica entre las ocho aves, el estado colectivo, las perturbaciones y la visualización.

___

# Cumplimiento de los objetivos de la unidad

# ✅ Cumplimiento de los objetivos de diseño

| Requisito                                                    | Estado         | Implementación en Bird Sync                                                                                                                                                                                                                                |
| ------------------------------------------------------------ | -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **8 agentes simultáneos**                                    | ✅ | El sistema utiliza `N = 8` y crea ocho instancias de `Agent`. Cada una tiene su propia fase y participa en el acoplamiento colectivo.                                                                                                                      |
| **4 personalidades audiovisuales diferentes**                | ✅ | Se definieron cuatro personalidades: **Cantor, Tembloroso, Planeador y Resonador**. Estas modifican el comportamiento de los agentes y su manifestación sonora y visual, en lugar de limitarse a cambiar su apariencia.                                    |
| **Manifestación visual y sonora de cada agente**             | ✅ | Cada agente está relacionado con una **especie de ave, una grabación sonora, una pista, una personalidad, una representación visual y un video**. De esta manera, la identidad de cada ave se mantiene a través de las diferentes capas de la experiencia. |
| **Modificar al menos 2 variables del modelo en tiempo real** | ✅ | El usuario puede modificar `K`, que representa el acoplamiento entre los agentes, y `spread`, que controla la dispersión de sus frecuencias naturales. Además, el **BPM** permite modificar el ritmo general de la experiencia.                            |
| **2 formas diferentes de interacción performativa**          | ✅ | Existe una **interacción global**, mediante la modificación de `K` y `spread`, que afecta al colectivo completo; y una **interacción individual**, mediante la cual el usuario puede intervenir agentes específicos.                                       |
| **Mecanismo de perturbación**                                | ✅ | El botón `⚡` permite modificar directamente la fase de un agente. Esto altera su estado dentro del sistema y permite observar posteriormente cómo el colectivo responde a la perturbación.                                                                 |
| **3 estados colectivos reconocibles**                        | ✅ | El sistema reconoce tres estados a partir del parámetro de orden `R`: **DESORDEN, ORGANIZACIÓN PARCIAL y ORGANIZACIÓN ESTABLE**.                                                                                                                           |
| **Comunicación perceptible del estado colectivo**            | ✅ | El estado colectivo aparece explícitamente en la interfaz junto con el valor de `R`. Además, el nivel de sincronización produce consecuencias audiovisuales en la experiencia.                                                                             |

___

# ✨ LINK: https://editor.p5js.org/EsTorrente/full/QfsI6zugU
