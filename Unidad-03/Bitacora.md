## 🌿 IDEACIÓN INICIAL + PROCESO CON IA  
Escuchando la canción, lo que me imaginaba todo el tiempo era una fábrica industrial construyendo robotcitos, rodeada de fuego y chispitas. Desde el inicio, ya tenía claro que ese era el concepto por el que me quería ir. Mi objetivo era utilizar partículas con fuerzas y colores que le dieran la apariencia de fuego, acompañado de robots bailando en patrones simétricos. Busqué entre los ejemplos que nos mostraste para comprender cómo usar los modelos, y encontré uno de un robot que ya tenía incluída las animaciones de baile y caminar. Perfecto, por ahí comencé.  
   
Lo primero que hice fue tomar el código de ese ejemplo y dárselo a la IA, pidiendo que me confirmara que era posible implementarlo, si sería demasiado pesado, y que hiciera una prueba con el proyecto original (antes de tocar las partículas). Me dijo que sí, ejecutó la prueba, y corría a +70 fps con 100 robots + un nivel intermedio de partículas.  
Teniendo esa base, me concentré en agregar la iluminación para los modelos. Inicialmente, intenté que las partículas fueran las que emitieran luz... pero no se veía bien; los modelos se veían como de una serie para niños y no daba esa sensación edgy industrial que buscaba. En lugar de eso, decidí irme por una sola luz roja intensa debajo de ellos y una luz azul muy tenue encima. Ahora sí, se ajustaba un poco más a mi visión.
    
Teniendo esa base, empecé a pedirle a la IA que creara 5 patrones (desde tecla 6 a tecla 0) para la organización de los robots. La primera que se me ocurrió era una pared de robots, donde caminaran en hileras en direcciones opuestas, unas sobre otras. También pensé en formación de triángulo, como si fuera un ejército... y en formaciones de líneas sencillas, como si estuvieran pasando por esos conveyor belt de las fábricas. Le pedí también que agregara un switch entre la animación de caminar y la animación de bailar. Los patrones de líneas simples no me terminaban de convencer mucho, pero pasé a concentrarme primero en las funciones de las partículas.
  
Comencé por pedirle las fuerzas que lo hicieran parecer fuego. Primero, definí que las partículas iban a ser atraídas por los robots, pero los robots iban a ejercer repulsión sobre ellas; así, habría un campito de fuerza alrededor de ellos. Luego, definí que las partículas se iban a repeler un poquito entre ellas, para que no se convirtieran en un amalgama. Ya teniendo eso definido, le dije a la IA que generara unas fuerzas en las teclas del 1 al 4 con los siguientes patrones: 1) Fuego fluido viniendo desde arriba y abajo, como intentando alcanzar a los robots en el medio. 2) El fuego llega a los robots, pero las ondas de calor del centro las empujan hacia afuera como un campo de fuerza. 3) Corrientes onduladas, como un fuego más tranquilo y fluido que pudiera avanzar entre los robots. 4) Una variación del 2 donde las partículas no sean empujadas con tanta fuerza hacia afuera. Los resultados me gustaron MUCHÍSIMO, pero las formaciones seguían sin convencerme...  
  
Por eso, me senté a mirar cositas de mandalas y así para buscar patrones. Haciendo eso, se me ocurrieron patrones circulares donde ellos pudieran bailar. También se me ocurrió uno donde llenaran toda la cajita, porque estaban dejando demasiado espacio vacío. Y por último, como se veía intimidante, se me ocurrió formarlos en X. Esas combinaciones me gustaron bastante. También se me ocurrió jugar con el tamaño de las partículas, y me di cuenta de que había algunos momentos de la música y patrones que quedaban mejor con tamaños chiquitos, y otros con tamaños grandes que los hacía ver más como una masa que partículas individuales. Agregué un toggle entre los dos.  
  
Ya teniendo los patrones formados, lo siguiente que le pedí a la IA es que me ayudara a construir los controles que me iban a ayudar a que se viera armonioso con la música. Estos ya los tenía súper claros, porque los imaginaba desde que escuché la canción por primera vez.  
  
| Control | Acción |
|---------|--------|
| 1 | Modo de fuerza grid (fuego fluido de arriba y abajo) |
| 2 | Modo de fuerza atractor (ondas de calor) |
| 3 | Modo de fuerza flow diagonal (fuego tranquilo) |
| 4 | Modo de fuerza vortex normal (variación del 2) |
| 5 | Toggle de tamaño de partículas (entre 0.05 y 0.21)|
| 6 | Formación robots en triángulo |
| 7 | Formación robots en cuadrado |
| 8 | Formación robots en círculos |
| 9 | Formación robots en X |
| 0 | Formación robots en pared (caminando en distintas direcciones |
| Z, X, Y | Rotación de cámara alrededor de ese eje |
| C | Aumento de velocidad de la rotación de cámara |
| v | Disminución de velocidad de rotación cámara | 
| Flechita arriba | Un pulso (cambia fondo a amarillo, aumenta bloom de partículas, hace zoom desde el POV de la cámara, aumenta las grid lines) |
| Flechita abajo | Intercambio de color azul <-> rojo | 
| Flechita derecha | Acelera tiempo de simulación e incrementa vibración de partículas para hacerlas erráticas |
| Flechita izquierda | Desacelera tiempo de simulación y detiene movimientos para parecer en cámara lenta |
| H | Esconder menú |
| F | Pantalla completa |
| Mouse posición en Y | Fuerza de repulsión que ejercen los robots sobre las partículas (más bajito o más alto) |
  
Y las fuerzas quedaron así:

| Fuerza | Descripción |
|--------|-------------|
| Modo de fuerza grid (fuego fluido de arriba y abajo) | Utiliza ondas de seno y coseno basadas en la posición vec3(sin(y), cos(z), sin(x)). Esto crea un flujo en ondas, similar a una cuadrícula, en el que las partículas se desplazan a través de pasillos 3D invisibles. |
| Modo de fuerza atractor (ondas de calor) | Calcula la distancia desde el centro p.length() y crea una fuerza de atracción que alterna entre hacia adentro y hacia afuera, basada en una onda de seno que se propaga hacia afuera con el tiempo: sin(r * 0.8 - tiempo * 6.0). | 
| Modo de fuerza flow diagonal (fuego tranquilo) | Una onda de una sola dirección que fluye en diagonal a través del cuadro de límite, modulada por el tiempo. |
| Modo de fuerza vortex normal (variación del 2) | Combina un vector de giro vec3(-z, 0, x) con una onda expansiva que se mueve hacia afuera desde el centro. Esto crea un vórtice giratorio. |
| Fuerza de agrupación de robots (atracción/repulsión) | Se recorre en bucle las 50 posiciones de los robots y calcula la distancia r a cada uno. La fuerza de repulsión se vuelve más fuerte cuando están más cerca, empujándolas más lejos. |
| Micro turbulencia | Para evitar que las partículas se muevan en líneas matemáticas perfectamente estériles, se agrega una capa de ruido 3D de alta frecuencia. Con ondas de seno que se cruzan —sin(x * 5.0 + y * 3.0)—, se crean remolinos chiquitos. Esto les da a las partículas un comportamiento de enjambre orgánico y fluido. |
| Vibración | A diferencia de la turbulencia, que está ligada a la posición espacial, la vibración está relacionada con el tiempo uTime.mul(150.0). Cuando aumenta el uVibrationLevel, se inyecta una fluctuación masiva y rápida, fotograma a fotograma, en el vector de velocidad, lo que hace que las partículas parezcan vibrar con intensa energía. |
| Amortiguación de estabilidad | La línea force.addAssign(v.mul(-1.5)) actúa como resistencia atmosférica (fricción). Aplica una fuerza directamente opuesta a la velocidad actual de la partícula, creando una velocidad terminal y asegurando que la simulación se mantenga estable. | 
  
Ya estando satisfecha con el comportamiento de las partículas y de los robots, me concentré en trabajar en la estética. Comencé a buscar efectos que podrían hacerlo ver más tecnológico, edgy, misterioso. Se me ocurrió agregar una capa de fog en el suelo, un efecto de scan lines, el bloom que siempre hace que todo se vea mejor, y un shake al cambiar a la animación de baile para que se sintiera como que los robots tienen peso. Le pedí primero que me diera sliders para poder jugar con todos estos parámetros y encontrar exactamente la versión que más me gustaba, y ya con eso le dije cuáles valores debía dejar como default.  

___
## 🌿EVIDENCIAS FOTOGRÁFICAS DE ITERACIÓN

<img width="1506" height="930" alt="image" src="https://github.com/user-attachments/assets/bc4b2650-a65b-40e6-ac87-0293e50a0cce" />

<img width="1515" height="947" alt="image" src="https://github.com/user-attachments/assets/6e5f9fd8-42b6-4a56-a85e-d625c212744b" />

<img width="1437" height="916" alt="image" src="https://github.com/user-attachments/assets/eeff4d53-6ce4-49f6-8f32-5b786e759b82" />

<img width="1468" height="939" alt="image" src="https://github.com/user-attachments/assets/fb6c5b43-e762-4b18-af15-01187e4ba98e" />

<img width="917" height="814" alt="image" src="https://github.com/user-attachments/assets/309167a9-1f59-47e2-8042-c6ae204e5074" />
<img width="926" height="752" alt="image" src="https://github.com/user-attachments/assets/7698efaa-8ed8-4103-8211-0abaa1719a0d" />
<img width="767" height="656" alt="image" src="https://github.com/user-attachments/assets/0e95224a-e7d0-4649-b052-37060d74b63e" />

<img width="1295" height="724" alt="image" src="https://github.com/user-attachments/assets/d960a2e8-f05b-4be0-9e8c-bb73b50fa43a" />
<img width="845" height="733" alt="image" src="https://github.com/user-attachments/assets/925e2847-1fec-46aa-abe1-00576ff7e17f" />
<img width="1208" height="771" alt="image" src="https://github.com/user-attachments/assets/c71dcf0b-092e-4df7-b136-b64a7d47f740" />
<img width="1215" height="751" alt="image" src="https://github.com/user-attachments/assets/a27b9690-2f1a-41b4-8de8-891483bc4876" />
<img width="1849" height="967" alt="image" src="https://github.com/user-attachments/assets/ba6eefed-bbe9-4238-ab50-47a7cb81af9b" />

<img width="1786" height="889" alt="image" src="https://github.com/user-attachments/assets/be8dc8af-ba8a-47a5-a377-11ce3a54c539" />
<img width="1189" height="779" alt="image" src="https://github.com/user-attachments/assets/4df462b0-3f6d-46bc-9fe2-9ac9ecfa48eb" />
<img width="1130" height="823" alt="image" src="https://github.com/user-attachments/assets/a0a61094-594e-47cf-8ac3-e49c4cf98465" />

___
# 🌿 ENTREGABLES

## [1. Instrumento funcional y publicado](https://estorrente.github.io/SIM-Forces-Instrument-MarTorrente/)

## 2. Mapa del sistema

### Estado del sistema

| Componente | Variables de estado | Ubicación en código | Tipo de dato |
|------------|---------------------|---------------------|--------------|
| **Partículas** | Posición (`p`) | `positionBuffer` en `createSimulation.js` | `vec3` por partícula |
| | Velocidad (`v`) | `velocityBuffer` en `createSimulation.js` | `vec3` por partícula |
| **Robots** | Posición (x,y,z) | `robots[i].position` en `main.js` | `THREE.Vector3` por robot |
| | Rotación (y) | `robots[i].rotation.y` en `main.js` | `float` por robot |
| | Animación actual | `robotActions[i]` en `main.js` | `AnimationAction` por robot |
| **Cámara** | Posición | `camera.position` en `main.js` | `THREE.Vector3` |
| | FOV | `camera.fov` en `main.js` | `float` |
| | Modo de auto-rotación | `autoRotateAxis` en `main.js` | `string \| null` |
| **UI** | Visibilidad | `uiVisible` en `main.js` | `boolean` |
| | Sliders activos | `slidersContainer` en `main.js` | `DOMElement` |
| **Luz** | Posición de luces | `particleLights[i].position` en `main.js` | `THREE.Vector3` por luz |
| | Color de luces | `particleLights[i].color` en `main.js` | `THREE.Color` por luz |

### Fuerzas del sistema

| Fuerza | Ecuación/Descripción | Parámetros | Archivo |
|--------|---------------------|------------|---------|
| **Fuerza Grid (Modo 1)** | `F = (sin(y·1.5), cos(z·1.5), sin(x·1.5)) · 40` | Ninguno | `createSimulation.js` |
| **Fuerza Atractor (Modo 2)** | `F = normalize(p) · sin(|p|·0.8 - t·6.0) · 60` | `uTime` | `createSimulation.js` |
| **Fuerza Diagonal (Modo 3)** | `F = (sin(z·0.5+t), sin(x·0.5-t), cos(y·0.5+t)) · 50` | `uTime` | `createSimulation.js` |
| **Vórtice (Modo 4)** | `F = spin + expand` <br> `spin = (-z, 0, x)·1.5` <br> `expand = normalize(x,0.8y,z)·sin(r²·0.01 - t·5.0)·25` | `uTime` | `createSimulation.js` |
| **Repulsión/Atracción de Robots** | `F = Σ (dir · (A/r - R/r²))` <br> A = 15.0 (atracción) <br> R = `uRepulsion` (repulsión) | `uRepulsion` (350-1500) | `createSimulation.js` |
| **Micro-turbulencia** | `F = (sin(5x+3y), sin(5y+3z), sin(5z+3x)) · 10` | Ninguno | `createSimulation.js` |
| **Vibración** | `F = (sin(150t+50x), cos(160t+50y), sin(170t+50z)) · vibración · 30` | `uVibrationLevel` | `createSimulation.js` |
| **Amortiguamiento** | `F = -v · 1.5` | Ninguno | `createSimulation.js` |
| **Limitador de velocidad** | `if [v] > maxSpeed: v = normalize(v) · maxSpeed` | `maxSpeed` (5.0) | `createSimulation.js` |

### Integración de fuerzas

| Etapa | Método | Parámetro | Archivo |
|-------|--------|-----------|---------|
| **Cálculo de fuerzas** | Suma vectorial de todas las fuerzas | `dt = 1/60 · timeScale · speedFactor` | `createSimulation.js` |
| **Integración de velocidad** | Euler explícito: `v += F · dt` | `dt` calculado | `createSimulation.js` |
| **Integración de posición** | Euler explícito: `p += v · dt` | `dt` calculado | `createSimulation.js` |
| **Confinamiento** | Módulo en caja: `p = mod(p + bounds/2, bounds) - bounds/2` | `uBounds` | `createSimulation.js` |
| **Limitación de velocidad** | Si `[v] > maxSpeed`: normalizar | `maxSpeed` (5.0) | `createSimulation.js` |

**Orden exacto de ejecución por frame:**

1. Actualizar uTime, uVibrationLevel, uSpeedFactor, uPulseFactor
2. Cálculo de fuerzas
3. Fuerza total = Sumatoria de ( fuerza_modo + robot_pool + turbulencia + vibración + amortiguamiento )
4. v += fuerza_total · dt
5. Si |v| > maxSpeed: v = normalize(v) · maxSpeed
6. p += v · dt
7. p = mod(p + bounds/2, bounds) - bounds/2
8. Actualizar posiciones de robots (movimiento independiente)
9. Renderizar

### Render

| Elemento | Técnica | Ubicación |
|----------|---------|-----------|
| **Partículas** | `InstancedMesh` con `SpriteNodeMaterial` | `createSimulation.js` |
| **Color de partículas** | Node en TSL: `mix(color_azul, color_rojo, colorMode) · velocidad` | `createSimulation.js` |
| **Tamaño de partículas** | Node en TSL: `uParticleSize · (1 + uPulseFactor·1.5)` | `createSimulation.js` |
| **Robots** | `GLTFLoader` + `AnimationMixer` con `SkeletonUtils.clone()` | `main.js` |
| **Fog** | `Mesh` con `MeshBasicNodeMaterial` y TSL para densidad | `main.js` |
| **Bloom** | Post-processing vía TSL `bloom(scenePass, uBloomStrength, 0.5, 0.1)` | `main.js` |
| **Scanlines** | Post-processing TSL: `sin(uv.y · innerHeight · 1.5) · 0.12 · intensidad` | `main.js` |
| **Viñeta** | Post-processing TSL: `(distancia_al_centro · 0.35)²` | `main.js` |
| **Cámara** | Perspectiva con auto-rotación opcional y shake | `main.js` |

### Controles

| Control | Acción | Tipo | Archivo |
|---------|--------|------|---------|
| **Teclas 1-4** | Cambiar modo de fuerza | Teclado | `main.js` |
| **Tecla 5** | Toggle tamaño de partículas (0.05 ↔ 0.21) | Teclado | `main.js` |
| **Teclas 6-9, 0** | Cambiar formación de robots | Teclado | `main.js` |
| **Tecla W** | Toggle baile/caminar de robots | Teclado | `main.js` |
| **Flechas arriba/abajo** | Pulso / Cambio de color | Teclado | `main.js` |
| **Flechas derecha/izquierda** | Acelerar / Cámara lenta | Teclado | `main.js` |
| **Z, X, Y** | Auto-rotación de cámara (eje) | Teclado | `main.js` |
| **C, V** | Velocidad auto-rotación (↑/↓) | Teclado | `main.js` |
| **H** | Ocultar/mostrar UI | Teclado | `main.js` |
| **F** | Pantalla completa | Teclado | `main.js` |
| **Mouse (Y)** | Control de repulsión de robots (0-1500) | Mouse | `main.js` |
| **Wheel** | Zoom (solo en auto-rotación) | Mouse | `main.js` |
| **Sliders UI** | 6 sliders: escala, repulsión, tamaño, bounds X/Y/Z | UI | `main.js` |

___

## FICHA DE FUERZAS

### FUERZA 1: MODO GRID (Fuego fluido de arriba y abajo)

| Propiedad | Descripción |
|-----------|-------------|
| **Nombre** | Fuerza Grid (Fuego normal) |
| **Tecla** | `1` |
| **Ecuación** | `F = (sin(p.y · 1.5), cos(p.z · 1.5), sin(p.x · 1.5)) · 40` |
| **Direccionalidad** | Crea pasillos 3D invisibles usando senos y cosenos en cada eje. Las partículas se mueven en patrones de onda, creando un flujo similar a una cuadrícula. |
| **Parámetros** | Ninguno (fija) |
| **Parámetros que la afectan** | `dt`, `speedFactor` (escala temporal) |
| **Efecto visual** | Cuando las partículas son pequeñitas, se ven como un tipo de tendrils que intentan acercarse a los robots desde arriba y abajo; cuando son grandes, se ven como llamas enormes de fuego porque las partículas se mezclan como una sola masa visualmente. En el color azul y tamaño pequeño, es delicado y bonito; en el color rojo y grandes, son intensas. |

**Predicciones:**
- Como la mayoría de formaciones se extienden hacia los lados y los robots ejercen repulsión sobre ellas, las partículas se van a concentrar en la zona de arriba y abajo; la excepción a esta regla sería, creo, en la formación de pared, donde se moverían a lado y lado de ellos.    
- Aumentar el `speedFactor` haría que las partículas recorran el grid más rápido.  
- Si se aumenta `uBounds` , el grid se estira y los patrones de onda cubren más espacio.  

**Decisiones de diseño:** 
- Diseñada para que se vea bien desde todos los ángulos y formaciones.   
- Multiplicador de 40 para que sea lo suficientemente fuerte pero no domine sobre las otras fuerzas.  
- Sin parámetros para que sea predecible, porque será utilizada en muchas de las secciones y en conjunto con las demás fuerzas para jalarlas a los bordes del bound.  

___

### FUERZA 2: MODO ATRACTOR (Ondas de calor)

| Propiedad | Descripción |
|-----------|-------------|
| **Nombre** | Fuerza Atractor/Onda de calor |
| **Tecla** | `2` |
| **Ecuación** | `F = normalize(p) · sin([p] · 0.8 - t · 6.0) · 60` |
| **Direccionalidad** | Fuerza radial desde el centro que alterna entre atracción y repulsión en forma de onda expansiva. La onda se propaga desde el centro hacia afuera con el tiempo. |
| **Parámetros** | `uTime` (tiempo de simulación) |
| **Parámetros que la afectan** | `dt`, `speedFactor`, `uTime` |
| **Efecto visual** | Las partículas pulsan rítmicamente hacia adentro y afuera del centro, como las ondas de calor que distorsionan la imagen cuando uno está en un lugar demasiado caliente. |

**Predicciones:**
- Si la partícula está en una zona de atracción, se mueve hacia el centro.
- Si la partícula está en una zona de repulsión, se aleja del centro.
- Si `speedFactor` aumenta, la frecuencia de pulsación aumenta.
- Si `uTime` avanza, el patrón de ondas se mueve radialmente.

**Decisiones de diseño:**
- Frecuencia `0.8` para que el patrón de ondas sea visible pero no demasiado denso.
- El diseño de este patrón está pensado para verse bien desde todos los ángulos, usarse en conjunto con el primer patrón de fuerzas, y reforzar los momentos de bass fuerte con la herramienta de pulsación de la flechita hacia arriba. No busca transmitir tanto la sensación de fuego, sino reforzar la musicalidad; es por esto que se usará alternando entre los demás patrones que sí están diseñados para parecer llamas.     

___

### FUERZA 3: MODO FLOW DIAGONAL (Fuego tranquilo)

| Propiedad | Descripción |
|-----------|-------------|
| **Nombre** | Fuerza Flow Diagonal |
| **Tecla** | `3` |
| **Ecuación** | `F = (sin(z·0.5 + t), sin(x·0.5 - t), cos(y·0.5 + t)) · 50` |
| **Direccionalidad** | Onda 3D que se mueve en diagonal a través del espacio. Cada componente depende de una coordenada diferente, creando un flujo complejo y menos caótico. |
| **Parámetros** | `uTime` |
| **Parámetros que la afectan** | `dt`, `speedFactor`, `uTime` |
| **Efecto visual** | Flujo suave y ondulante, como una corriente de aire caliente que se desplaza lentamente entre los robots. Las partículas se mueven en trayectorias curvas y orgánicas. En lugar de verse como un fuego que está intentando buscar activamente a los robots, debe verse como un fuego tranquilo de ambiente.|

**Predicciones:**
- Si `speedFactor` aumenta, el flujo se acelera.
- Si la partícula está en una posición específica, la fuerza depende de esa posición.
- Si aumento `uTime`, el frente de onda avanza.

**Decisiones de diseño:**
- Usada para momentos **más tranquilos** de la música.
- Menor multiplicador (50) que los modos 1 y 2 para un efecto más sutil.
- Diseñado para repulsiones más bajas, permitiendo que los flujos atraviesen los espacios entre los robots y no se apachurren en las esquinas de los bounds.  

___

### FUERZA 4: VÓRTICE (Variación del modo 2)

| Propiedad | Descripción |
|-----------|-------------|
| **Nombre** | Fuerza Vórtice |
| **Tecla** | `4` |
| **Ecuación** | `spin = (-z, 0, x) · 1.5` <br> `expand = normalize(x, 0.8y, z) · sin(x²+z² · 0.01 - t · 5.0) · 25` <br> `F = spin + expand` |
| **Direccionalidad** | Combina un giro constante alrededor del eje Y (`spin`) con una expansión/contracción radial (`expand`). Las partículas orbitan mientras pulsan hacia adentro y afuera. |
| **Parámetros** | `uTime` |
| **Parámetros que la afectan** | `dt`, `speedFactor`, `uTime` |
| **Efecto visual** | Vórtice giratorio con ondas de presión que se expanden desde el centro, similar a un remolino de fuego industrial. |

**Predicciones:**
- Si la partícula está lejos del centro, la fuerza de giro (`spin`) domina.
- Si la partícula está cerca del centro, la fuerza de expansión/contracción es más notable.
- Si `speedFactor` aumenta, el vórtice gira y pulsa más rápido.

**Decisiones de diseño:**
- `expand` usa `0.01` para que el radio de onda sea grande y visible.
- Multiplicador de `25` para que la expansión sea notable sin dominar el giro.
- Está pensada para acompañar la formación en círculo de los robots, permitiendo que la cámara gire junto a la formación y las partículas y genere ese efecto trippy tipo mandala.  

___

### FUERZA 5: REPULSIÓN/ATRACCIÓN DE ROBOTS

| Propiedad | Descripción |
|-----------|-------------|
| **Nombre** | Fuerza de Agrupación de Robots |
| **Ecuación** | `F = sumatoria de (dir · (A/r - R/r²))` <br> donde: <br> `dir = (robot_pos - p)/r` <br> `r = [robot_pos - p]` <br> `A = 15.0` (constante de atracción) <br> `R = uRepulsion` (constante de repulsión) |
| **Direccionalidad** | **Atracción** a larga distancia (r grande): partículas tienden hacia los robots. <br> **Repulsión** a corta distancia (r pequeña): partículas son expulsadas violentamente. |
| **Parámetros** | `uRepulsion` (350-1500, controlado por mouse) |
| **Parámetros que la afectan** | `uRepulsion`, `dt`, `speedFactor`, posiciones de robots |
| **Efecto visual** | Las partículas crean un "aura" alrededor de cada robot. A mayor repulsión, más grande y definida es la aura de vacío alrededor de los robots. |

**Predicciones:**
- Si `uRepulsion` es alto, las partículas se alejan demasiado y se concentran en las esquinas del boundary.
- Si `uRepulsion` es bajo, las partículas logran pasar entre los robots.
- Los cambios de concentración de robotcitos en las formaciones harán que las partículas se concentren algunas veces en los techos y suelos, y otras en las paredes laterales. 

**Decisiones de diseño:**
- Atracción débil (15.0) para que las partículas sigan a los robots sin volverse estáticas.
- Repulsión variable (mouse) para dar control interpretativo en tiempo real.
- Recorre los 50 robots en el shader (eficiente en GPU).
- Todas las partículas sienten todos los robots, porque es un espacio pequeño y comprimido.
- El propósito de esta fuerza es que las partículas no oculten por completo a los robots y siempre haya un ángulo desde dónde verlos, además de crear mayor variación en el comportamiento de estas. 

___

### FUERZA 6: MICRO-TURBULENCIA

| Propiedad | Descripción |
|-----------|-------------|
| **Nombre** | Micro-turbulencia |
| **Ecuación** | `F = (sin(5x+3y), sin(5y+3z), sin(5z+3x)) · 10` |
| **Direccionalidad** | Ruido suave basado en la posición, con frecuencias medias. Crea remolinos pequeños y orgánicos. |
| **Parámetros** | Ninguno (fija) |
| **Parámetros que la afectan** | Solo la posición de la partícula |
| **Efecto visual** | Las partículas nunca se mueven en líneas perfectamente rectas. Tienen un "temblor orgánico" que evita que se vea repetitivo y estéril. |

**Predicciones:**
- Si las partículas están quietas, la turbulencia las hace vibrar ligeramente.
- Si aumento `speedFactor`, la turbulencia escala con el tiempo (porque se aplica cada frame).

**Decisiones de diseño:**
- Frecuencias 5 y 3 para remolinos de tamaño medio (ni microscópicos ni gigantes).
- Multiplicador 10 para que sea sutil pero visible.
- Sin parámetros para mantener la consistencia.
- La uso porque el movimiento del fuego y el humo no es matemáticamente exacto, sino más orgánico y fluido.

___

### FUERZA 7: VIBRACIÓN

| Propiedad | Descripción |
|-----------|-------------|
| **Nombre** | Vibración |
| **Ecuación** | `F = (sin(150t+50x), cos(160t+50y), sin(170t+50z)) · uVibrationLevel · 30` |
| **Direccionalidad** | Ruido de alta frecuencia temporal. Depende del tiempo y la posición, creando un movimiento errático. |
| **Parámetros** | `uVibrationLevel` (0-1+) |
| **Parámetros que la afectan** | `uVibrationLevel`, `uTime`, `speedFactor`, posición |
| **Efecto visual** | **Nivel bajo:** Las partículas vibran sutilmente. <br> **Nivel alto:** Las partículas explotan, como si la fábrica estuviera en crisis o el ruido fuera muy alto. |

**Predicciones:**
- Si `uVibrationLevel = 0`, no hay vibración más allá de la turbulencia chiquita.
- Si mantengo presionada la flechita derecha, la vibración sube gradualmente.
- Si suelto la flechita derecha, la vibración vuelve a 0 rápido (pero con un smooth).
- Si `speedFactor` es alto, la vibración se aplica con más frecuencia (más frames por segundo).

**Decisiones de diseño:**
- Frecuencias altas (150, 160, 170) para un temblor rápido, no una onda lenta.
- Multiplicador 30 para amplificar el efecto.
- Se acumula gradualmente (interpolación en `main.js`) para transiciones suaves.
- La idea es usarlo en cada beat para dar ese efecto como de visualizador (SIN SER UN VISUALIZADOR!!!!!!!!!!!!!!!!!!!), y mantenerlo presionado en la parte de la canción donde el synth se vuelve más brillante (no sé cómo explicarlo? pero hace como un shuuuuuUUUUUUUUUUUUUU!U!UU!U!U!UU!U!U!UU!M)  

____

### FUERZA 8: AMORTIGUAMIENTO

| Propiedad | Descripción |
|-----------|-------------|
| **Nombre** | Fricción |
| **Ecuación** | `F = -v · 1.5` |
| **Direccionalidad** | Siempre opuesta a la velocidad actual. |
| **Parámetros** | Ninguno (fijo: 1.5) |
| **Parámetros que la afectan** | `v` (velocidad actual) |
| **Efecto visual** | Las partículas alcanzan una velocidad terminal. Sin esto, las partículas acelerarían indefinidamente y explotarían. |

**Predicciones:**
- Si `v` es grande, la amortiguación es fuerte (frena rápido).
- Si `v` es pequeña, la amortiguación es débil.
- Si las fuerzas son constantes, las partículas alcanzan equilibrio (velocidad terminal).

**Decisiones de diseño:**
- La necesito para mantener el sistema estable en GPU compute.
- Combinada con el limitador de velocidad para seguridad.

___

### FUERZA 9: LIMITADOR DE VELOCIDAD

| Propiedad | Descripción |
|-----------|-------------|
| **Nombre** | Limitador de Velocidad |
| **Ecuación** | `if |v| > maxSpeed: v = normalize(v) · maxSpeed` |
| **Direccionalidad** | Conserva la dirección, reduce la magnitud. |
| **Parámetros** | `maxSpeed` (5.0 fijo) |
| **Parámetros que la afectan** | `v` (velocidad actual) |
| **Efecto visual** | Las partículas nunca se mueven demasiado rápido, incluso con fuerzas muy altas. |

**Predicciones:**
- Si la partícula está muy acelerada, se limita a maxSpeed.
- Si la partícula está en reposo, no afecta.
- Si aumento `speedFactor`, la partícula alcanza maxSpeed más rápido.

**Decisiones de diseño:**
- `maxSpeed = 5.0` elegido con pruebas para que el movimiento sea visible pero no borroso.

___

## PRUEBAS AISLADAS DE CADA FUERZA
  
### MODOS DE FUERZAS  
    
Fuerza 1 (no se ve muy bonita sola porque la repulsión es lo que hace que se note el patrón):  
<img width="927" height="894" alt="image" src="https://github.com/user-attachments/assets/82e8025d-e9a6-41e4-9100-81bc6e6bc727" />
    
Fuerza 2:  
<img width="1018" height="938" alt="image" src="https://github.com/user-attachments/assets/68ce01d4-96ed-4cd6-9a72-c427abbc7921" />  
    
Fuerza 3:  
<img width="919" height="913" alt="image" src="https://github.com/user-attachments/assets/2b80bb35-cc42-4f46-ae06-94e8a32647d1" />
  
Fuerza 4 (no se puede ver en la imagen, pero van pulsando y rotando):  
<img width="869" height="808" alt="image" src="https://github.com/user-attachments/assets/0bb6186a-ffc8-4109-b790-4a381d146466" />
  
  
### FUERZAS DE ROBOTS
  
Formación 6:  
<img width="935" height="853" alt="image" src="https://github.com/user-attachments/assets/a89282a7-565a-4085-8406-39d55f9da1ab" />
  
Formación 7:  
<img width="880" height="676" alt="image" src="https://github.com/user-attachments/assets/4b1e05c2-2e90-4fb2-8612-3103d17bf6e0" />
  
Formación 8:  
<img width="839" height="855" alt="image" src="https://github.com/user-attachments/assets/2bae6e8a-fa72-439e-a0f0-495fb4243455" />
  
Formación 9:  
<img width="918" height="780" alt="image" src="https://github.com/user-attachments/assets/984e1501-2a80-4f35-b35f-5a565e2d8206" />
  
Formación 0:  
<img width="939" height="885" alt="image" src="https://github.com/user-attachments/assets/cb2ffbcb-43b7-4eee-9b07-64e69565f4d4" />
  
### MICRO TURBULENCIAS  
<img width="950" height="780" alt="image" src="https://github.com/user-attachments/assets/00f47d00-b2f8-49e3-be61-2ffeaeff0c0b" />
  
### VIBRACIÓN  
<img width="783" height="802" alt="image" src="https://github.com/user-attachments/assets/d125d91a-1a8f-4aa2-adf3-95b9f117237a" />
  
### DAMPING (quedan estáticas)  
<img width="869" height="804" alt="image" src="https://github.com/user-attachments/assets/57ad93d0-510e-43cd-ac0f-8903ad2c6561" />
  
### COMBINACIÓN  
<img width="918" height="878" alt="image" src="https://github.com/user-attachments/assets/206e8198-dbb6-419b-a5c8-060d98378366" />

___

## SCORE VISUAL



