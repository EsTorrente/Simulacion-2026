# 🌿 IDEACIÓN INICIAL + PROCESO CON IA  
Escuchando la canción, lo que me imaginaba todo el tiempo era una fábrica industrial construyendo robotcitos, rodeada de fuego y chispitas. Desde el inicio, ya tenía claro que ese era el concepto por el que me quería ir. Mi objetivo era utilizar partículas con fuerzas y colores que le dieran la apariencia de fuego, acompañado de robots bailando en patrones simétricos. Busqué entre los ejemplos que nos mostraste para comprender cómo usar los modelos, y encontré uno de un robot que ya tenía incluída las animaciones de baile y caminar. Perfecto, por ahí comencé.  
   
Lo primero que hice fue tomar el código de ese ejemplo y dárselo a la IA, pidiendo que me confirmara que era posible implementarlo, si sería demasiado pesado, y que hiciera una prueba con el proyecto original (antes de tocar las partículas). Me dijo que sí, ejecutó la prueba, y corría a +70 fps con 100 robots + un nivel intermedio de partículas.  
Teniendo esa base, me concentré en agregar la iluminación para los modelos. Inicialmente, intenté que las partículas fueran las que emitieran luz... pero no se veía bien; los modelos se veían como de una serie para niños y no daba esa sensación edgy industrial que buscaba. En lugar de eso, decidí irme por una sola luz roja intensa debajo de ellos y una luz azul muy tenue encima. Ahora sí, se ajustaba un poco más a mi visión.
    
Teniendo esa base, empecé a pedirle a la IA que creara 5 patrones (desde tecla 6 a tecla 0) para la organización de los robots. La primera que se me ocurrió era una pared de robots, donde caminaran en hileras en direcciones opuestas, unas sobre otras. También pensé en formación de triángulo, como si fuera un ejército... y en formaciones de líneas sencillas, como si estuvieran pasando por esos conveyor belt de las fábricas. Los patrones de líneas simples no me terminaban de convencer mucho, pero pasé a concentrarme primero en las funciones de las partículas.
  
Comencé por pedirle las fuerzas que lo hicieran parecer fuego. Primero, definí que las partículas iban a ser atraídas por los robots, pero los robots iban a ejercer repulsión sobre ellas; así, habría un campito de fuerza alrededor de ellos. Luego, definí que las partículas se iban a repeler un poquito entre ellas, para que no se convirtieran en un amalgama. Ya teniendo eso definido, le dije a la IA que generara unas fuerzas en las teclas del 1 al 4 con los siguientes patrones: 1) Fuego fluido viniendo desde arriba y abajo, como intentando alcanzar a los robots en el medio. 2) El fuego llega a los robots, pero las ondas de calor del centro las empujan hacia afuera como un campo de fuerza. 3) Corrientes onduladas, como un fuego más tranquilo y fluido que pudiera avanzar entre los robots. 4) Una variación del 2 donde las partículas no sean empujadas con tanta fuerza hacia afuera. Los resultados me gustaron MUCHÍSIMO, pero las formaciones seguían sin convencerme...  
  
Por eso, me senté a mirar cositas de mandalas y así para buscar patrones. Haciendo eso, se me ocurrieron patrones circulares donde ellos pudieran bailar. También se me ocurrió uno donde llenaran toda la cajita, porque estaban dejando demasiado espacio vacío. Y por último, como se veía intimidante, se me ocurrió formarlos en X. Esas combinaciones me gustaron bastante.  
  
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
  
Y las fuerzas quedaron así:

| Fuerza | Descripción |
|--------|-------------|
| Modo de fuerza grid (fuego fluido de arriba y abajo) | Utiliza ondas sinusoidales y cosinusoidales entrelazadas basadas en la posición vec3(sin(y), cos(z), sin(x)). Esto crea un flujo ondulante, similar a una cuadrícula, en el que las partículas se desplazan a través de pasillos 3D invisibles. |
| Modo de fuerza atractor (ondas de calor) | Calcula la distancia desde el centro p.length() y crea una fuerza de atracción que alterna entre hacia adentro y hacia afuera, basada en una onda sinusoidal que se propaga hacia afuera con el tiempo: sin(r * 0.8 - tiempo * 6.0). | 
| Modo de fuerza flow diagonal (fuego tranquilo) | Una onda unidireccional que fluye en diagonal a través del cuadro delimitador, modulada por el tiempo. |
| Modo de fuerza vortex normal (variación del 2) | Combina un vector de giro vec3(-z, 0, x) con una onda expansiva que se mueve hacia afuera desde el centro. Esto crea un vórtice giratorio. |
| Fuerza de agrupación de robots (atracción/repulsión) | Esta es una fuerza de dirección basada en agentes. Se recorre en bucle las 50 posiciones de los robots y calcula la distancia r a cada uno. Utiliza una ecuación muy inspirada en el potencial de Lennard-Jones (utilizado en dinámica molecular). La fuerza de repulsión se vuelve más fuerte cuando están más cerca, empujándolas más lejos. |
| Micro turbulencia | Para evitar que las partículas se muevan en líneas matemáticas perfectamente estériles, se agrega una capa de ruido 3D de alta frecuencia. Al superponer ondas sinusoidales que se cruzan —sin(x * 5.0 + y * 3.0)—, se crean pequeños remolinos. Esto les da a las partículas un comportamiento de enjambre orgánico y fluido. |
| Vibración | A diferencia de la turbulencia, que está ligada a la posición espacial, la vibración está estrechamente relacionada con el tiempo uTime.mul(150.0). Cuando aumenta el uVibrationLevel, se inyecta una fluctuación masiva y rápida, fotograma a fotograma, en el vector de velocidad, lo que hace que las partículas parezcan vibrar con intensa energía. |
| Amortiguación de estabilidad | La línea force.addAssign(v.mul(-1.5)) actúa como resistencia atmosférica (fricción). Aplica una fuerza directamente opuesta a la velocidad actual de la partícula, creando una velocidad terminal y asegurando que la simulación se mantenga estable. | 
  


___
<img width="1506" height="930" alt="image" src="https://github.com/user-attachments/assets/bc4b2650-a65b-40e6-ac87-0293e50a0cce" />

<img width="1515" height="947" alt="image" src="https://github.com/user-attachments/assets/6e5f9fd8-42b6-4a56-a85e-d625c212744b" />

<img width="1437" height="916" alt="image" src="https://github.com/user-attachments/assets/eeff4d53-6ce4-49f6-8f32-5b786e759b82" />

<img width="1468" height="939" alt="image" src="https://github.com/user-attachments/assets/fb6c5b43-e762-4b18-af15-01187e4ba98e" />

___
<img width="917" height="814" alt="image" src="https://github.com/user-attachments/assets/309167a9-1f59-47e2-8042-c6ae204e5074" />
<img width="926" height="752" alt="image" src="https://github.com/user-attachments/assets/7698efaa-8ed8-4103-8211-0abaa1719a0d" />
<img width="767" height="656" alt="image" src="https://github.com/user-attachments/assets/0e95224a-e7d0-4649-b052-37060d74b63e" />

<img width="1295" height="724" alt="image" src="https://github.com/user-attachments/assets/d960a2e8-f05b-4be0-9e8c-bb73b50fa43a" />
<img width="845" height="733" alt="image" src="https://github.com/user-attachments/assets/925e2847-1fec-46aa-abe1-00576ff7e17f" />
<img width="1208" height="771" alt="image" src="https://github.com/user-attachments/assets/c71dcf0b-092e-4df7-b136-b64a7d47f740" />
<img width="1215" height="751" alt="image" src="https://github.com/user-attachments/assets/a27b9690-2f1a-41b4-8de8-891483bc4876" />
<img width="1849" height="967" alt="image" src="https://github.com/user-attachments/assets/ba6eefed-bbe9-4238-ab50-47a7cb81af9b" />

___

<img width="1786" height="889" alt="image" src="https://github.com/user-attachments/assets/be8dc8af-ba8a-47a5-a377-11ce3a54c539" />
<img width="1189" height="779" alt="image" src="https://github.com/user-attachments/assets/4df462b0-3f6d-46bc-9fe2-9ac9ecfa48eb" />
<img width="1130" height="823" alt="image" src="https://github.com/user-attachments/assets/a0a61094-594e-47cf-8ac3-e49c4cf98465" />
