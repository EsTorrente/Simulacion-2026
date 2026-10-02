# 🌱 IDEACIÓN / PROCESO
Inicialmente, elegí Wriggle de Cosmo Sheldrake como canción. Esto es lo que me imaginé como primer concepto:
```
I want something whimsical and bizarre, that feels kind of like looking at microorganisms that move like pieces on a clock. I want each beat to give them a boost, so that their movement itself feels snappy, but the patterns they create feel organic. I want them to have different shapes. Some stars with many points (maybe 10+), some triangles, some circles... something that will vary their trails. At some points of the song I do want it to change to look like a flock of birds flying together in a fluid motion, before going back to the snappy weird little creatures. I also want to implement all the algorithms. For the steering, I want them to move with the beat of the song AWAY from each other; For the flocking, I want them to follow the mouse; for the flow fields, I want very wavey and fluid patterns. For physarum, very organic and moss-like shapes.

For now, I want to use CTRL to move though stages/algorithms. Here is what I had in mind:

- Comienza con steering.
00:00 - 2 agentes moviéndose a distintos ritmos; uno con los agudos de la canción, el otro con el beat. Formas distintas. Tamaños medianos, para ser visibles en la pantalla.
00:06 - 1 agente más aparece al presionar CTRL.
00:12 - 5 agentes más aparecen al presionar CTRL.
00:23 - 20 agentes más aparecen al presionar CTRL.
00:34 - Cambian a flow fields al presionar CTRL. 100 agentes más aparecen
00:46 - 200 agentes más aparecen al presionar CTRL.
00:59 - Disminuye a 150 agentes al presionar CTRL.
01:00 - Disminuye a 50 agentes al presionar CTRL.
01:01 - Disminuye a 20 agentes al presionar CTRL.
01:02 - Disminuye a 3 agentes al presionar CTRL.
1:03 - Cambia a flock con esos 3 agentes.&#x20;
1:15 - Al presionar CTRL, gradualmente empiezan a entrar más a la escena por los lados, uniéndose al flock y siguiendo el mouse. Cada CTRL agrega más agentes.
1:26 - Al presionar CTRL, muchísimos más agentes aparecen. Cambia a interactive physarum y comienzan a crear patrones como raíces creciendo hacia arriba.
1:38 - Al presionar CTRL, el physarum cambia y los agentes comienzan a extenderse en patrones en todas las direcciones desde el centro de la pantalla, como explorando.
1:49 - Al presionar CTRL, vuelve a steering con solo 3 agentes en la mitad de la pantalla.
1:55 - Al presionar CTRL, vuelve a 20 agentes.
2:00 - Al presionar CTRL, cambia a flocking de nuevo, siguiendo el mouse.
2:11 - Cada CTRL agrega nuevos agentes que entran por los lados de la pantalla.
2:23 - Al presionar CTRL, vuelve a physarum con esos agentes. Patrones orgánicos.
2:46 - Al presionar CTRL, regresa a flocking con esos agentes.
2:58 - Al presionar CTRL, vuelve a flow fields con esos agentes.
3:09 - Al presionar CTRL, vuelve a steering con 20 agentes.
3:21 - Al presionar CTRL, vuelve a steering con 100 agentes.
3:33 - Al presionar CTRL, vuelve a physarum con cada vez más agentes.
3:52 - Al presionar CTRL, vuelve a flocking con 30 agentes.
3:56 - Al presionar CTRL, vuelve a physarum con más agentes.
4:19 - Al presionar CTRL, regresa a steering con 3 agentes.
```
  
Con una descripción mucho más extensa de mi visión, conseguík que ChatGPT me escribiera un prompt para Gemini y Claude.
Sin embargo, me pegué un choque muy rápido cuando noté que los resultados que obtenía con la generación de la IA eran:
1) Súper flops. Muy aburridos, peyes, nada único.  
2) Diferentes a lo que imaginaba en mi cabeza. No lograban captar la esencia de los movimientos ni shots, a pesar de que el prompt lo describía SUPREMAMENTE claro.
Me iba a resignar a aceptar el resultado... pero decidí mejor darle una oportunidad a otra canción del mismo artista. Esta vez, escogí `Pelicans We`; es una adaptación musical de un poema llamado "The Pelican Chorus" por Edward Lear, el poeta del "sinsentido".
<img width="644" height="825" alt="image" src="https://github.com/user-attachments/assets/0c1bdc53-998b-4eaf-94f5-8b7395860f60" />  

  
El cantante tiene una identidad visual muy marcada. Colores vibrantes: naranjas, amarillos, rojos, negro; ilustraciones de collage, papel, surrealismo...
<img width="1126" height="1200" alt="image" src="https://github.com/user-attachments/assets/a28e95f4-d835-4e5b-bda1-d170d32766ce" /><img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/d2e6bbd2-7edf-415b-94ff-89dce8769e09" /><img width="391" height="511" alt="image" src="https://github.com/user-attachments/assets/09d293e5-c60d-48a8-817b-16c2fb88128c" /><img width="447" height="447" alt="image" src="https://github.com/user-attachments/assets/66150956-54f4-4dd0-9f79-4cc241e4b5eb" /><img width="447" height="447" alt="image" src="https://github.com/user-attachments/assets/4464bbc2-6911-40dc-aab6-c5f2ee3d50e5" />
    
Cuando escuchaba la canción, me imaginaba a los pelícanos como siluetas volando sobre el río Nilo en el atardecer (como lo mencionan en la canción). Me recordaba a una estética como la de Kiriku y el teatro de sombras, por sus colores saturados, contraste altísimo y textura como de papel mojado en té o café:  
<img width="780" height="1170" alt="image" src="https://github.com/user-attachments/assets/b97e2d6d-7e50-40bd-b042-b6a05be300b5" /> <img width="1024" height="576" alt="image" src="https://github.com/user-attachments/assets/61cfb7e6-ed30-463e-bc81-252114b782d7" /><img width="474" height="266" alt="image" src="https://github.com/user-attachments/assets/0a20888b-d79e-42b4-ab0f-d441760a3e25" /><img width="640" height="480" alt="image" src="https://github.com/user-attachments/assets/2592f315-708e-4577-b17d-2eed02d0f003" /><img width="1024" height="659" alt="image" src="https://github.com/user-attachments/assets/b75c6822-bf65-4595-ad08-a87a770c630d" />
  
Eso es lo que intenté capturar. La energía de los mitos y leyendas indígenas, los collage de papel, el teatro de sombras... todo eso que hace que las canciones de Cosmo Sheldrake se sientan como historias olvidadas de otro mundo. 
  
Teniendo esto claro, volví a ChatGPT para que me ayudara a plantear un nuevo prompt para esta idea:
<a name="score"></a>
  
```
Let's change it up. I want to try going in a completely different direction.
I now want to use  Cosmo Sheldrake - Pelicans We instead; with a bpm of 77 BPM.
I want the visual aesthetic to be like the images I sent you: deep and vibrant reds, orange, yellows...
Shapes that look like paper cut-outs, collages...
I want the agents on the background to use physarum and feel like a lake vibrantly reflecting a vibrant orange sunset, getting the light distorted in flowing patterns. For the agents in the foreground, i want them to feel like flying pelicans dancing in patterns.
It should feel ominous, powerful, a bit uneasy (like the song).
I want the camera to be constantly rotating counter-clockwise slowly, on all stages, to add to the feeling of looking at a moving mandala. 

Here is what I imagine. I will switch between each stage with CTRL and a number:
0:00 - 0:23:
Flow fields with long lines (following example of https://www.tylerxhobbs.com/words/flow-fields), using a black background and coloured lines. They should start outside the screen and slowly draw themselves along the flow fields towards the center, covering the whole screen in flowing lines. Let me control them with my mouse.

 0:24 - 00:49
The lines transform into 3d birds, switching to flocking algorithm. The background changes to a rich orange, making the birds look like black silhouettes as they fly. When I hit CTRL, the background turns black (the same colour as the model of the birds) and only ONE bird changes to orange colour, so that we see only that one flying around. When I press CTRL again, it goes back to the initial colours where the background is orange and the birds are black. The purpose of this is to emphasize a specific beat.

00:49 - 1:14
The background explodes into a bright red, and the birds turn into agents for the physarum. The phyrasum extends outwards in a moss-like explosion with white and yellow colour, the camera keeps moving back to see the moss expanding.

1:14 - 1:40
Back to flow fields. The agents change back to bird shapes silhouettes and follow the flow fields around in wavy patterns around the center, but still occupying the whole screen; kinda like they're birds dancing above a lake. The background is another moving physarum, creating organic fire or water like patterns (once again, for the sun reflecting on water). The camera zooms in on them, seeing a sort of mandala that never ends as the camera goes through it. Background is now orange.

1:40 - 2:04
They explode once again into many layers of different physarum: some white, some yellow, some orange. The background turns an orangy red. The physarum slowly expands, evolves, gets disturbed. If i click on the screen and draw, allow the physarum to grow over that line. This is the climax. It should feel grand and mysterious.

2:04 - 2:29
The physarum melts down the screen, the background turning black.
The camera follows it down as it keeps growing, like roots going down. When I hit CTRL, agents should appear from the outside of the screen and start flowing in flow field patterns over the physarum.

2:29 - 2:54
Background goes bright yellow and the agents become birds again, flying in flock. As they do, a bright red physarum slowly spreads from the center. When I press CTRL, all birds leave the screen, leaving only the physarum which grows stronger, like a mold overtaking the whole screen into bright red. When I press CTRL again, long yellow lines emerge from the outside of the screen and draw themselves along moving flow fields, layered with an orange physarum. Lastly, once I press CTRL again, Everything goes black and only one orange bird stays still on the middle of the screen.

The visuals should still be audio reactive in some subtle way. Keep the debug that tells me the time of the song and the next CTRL press.
Try to replicate the patterns on the images I showed you.
Add bloom, vignette, noise... to make it look like a polished music video.

Using the Z/X keys, allow me to control the cohesion of the flock of birds. Using the mouse, allow me to draw on the physarum.

These are the algo references:
https://www.tylerxhobbs.com/words/flow-fields
https://natureofcode.com/autonomous-agents/
https://github.com/mrdoob/three.js/blob/master/examples/webgpu_compute_birds.html

Also, tell it not to separate the code in too many different files.
The audio will be named "song.mp3" in the assets folder on the root.

Use:

Three.js
WebGL
GLSL shaders
GPU-based simulation where practical
GPU instancing

The target development machine has an RTX 4060. Do NOT split the project into dozens of tiny files. I want a relatively compact project structure. The visual should still be subtly audio reactive. However, do NOT turn the project into a conventional frequency visualizer.

```
Ya teniendo esto, el resultado que me arrojó Claude fue CASI PERFECTO!! Logró captar 100% lo que tenía en mente. :D
Me dediqué a experimentar con los parámetros, ajustar comportamientos y velocidades, probar pequeñas variaciones y hacer ajustes chiquitos para comprender el comportamiento del programa.  

____

<a name="explicacion"></a>
# 🌿Explicación del programa

Tengo 2 tipos distintos de agentes, pero la intención es hacer que entre transiciones se sienta que el uno se transforma en el otro:


| Población |	Cantidad |	Qué representa |
|-----------|-----------|-----------------|
| Agentes de pintura |	589.824	| Los ríos, el sol reflejándose en el agua, las vibras generales del terreno en el atardecer.
| Aves | 784 | Los pelícanos de papel |

Cada población vive en una textura RGBA float: .xy = posición, .zw = velocidad. Cada frame se lee la textura vieja, se calcula la nueva, y se hace swap. Además hay un trail que acumula lo que los agentes depositan y decae lentamente.

## Agentes de pintura:
Son el mismo material en todo momento. Lo que cambia entre stages es cuánto peso le dan al flow field vs. al Physarum. 
- `Si solo flow field:` lineas largas y coherentes.
- `Si solo Physarum`: redes ramificadas, patrones tipo moho/raíz/río.
- `Miti/miti`: pintura arrastrada por una corriente.
  
Cada agente tiene una especie {0,1,2,3} que sale de un hash de su posición en la grilla. La especie determina:
- a qué canal del trail pertenece (capa de pintura: rojo, naranja, amarillo, cremita)
- qué pesos (flow) y (Physarum) tiene en el stage actual

### Cada una percibe:
**Percepción del flow field:**
- Solo el vector de su campo en su propia posición.
- No ve a otros agentes, no ve el trail, no ve las aves (excepto cuando se inicializa desde ellas).
  
**Percepción del Physarum:**
- Solo el valor del trail en 3 sensores situados a distancia.
En cada sensor lee el vector de 4 canales del trail  y calcula un escalar sense() donde su propia especie atrae, las otras repelen.

Todo lo que esté más allá de los sensores es invisible para ellos.
- No hay percepción global. No sabe dónde está el centro de la pantalla, ni cuántos agentes hay, ni qué stage es.
- No conoce el mouse directamente, a menos que yo dibuje en el trail o deforme el campo.
  
Calcula las fuerzas del flow field y la rotación del physarum.

## Aves
Agentes de flocking puro. La geometría visible es un quad instanciado por ave, y el shader de fragmento dibuja una silueta de pelícano recortada en papel: triángulos planos, bordes irregulares (ruido), alas que aletean, cuello y pico (medio chiviado, pero se entiende que es un pajarito).

### Cada una percibe:
- Cada ave hace un loop sobre las 784 aves y para cada una encuentra la distancia entre ellos; si es vecina, se deja afectar por su velocidad y dirección.
- Solo perciben 4 unidades; todo lo que esté más lejitos, le es invisible.
- Si el mouse está a menos de 12 unidades, lo puede percibir.
  
Calcula las fuerzas de separación, de alineación, de cohesión, del flow field...
  
Con los seed, puedo controlar que aparezcan fuera de la pantalla o encima de los agentes de pintura. También les puedo aplicar otra fuerza para hacer que se salgan de la pantalla. 

___

Tengo también un flow field compartido entre los dos agentes, que es donde mis clics del mouse los afecta con una fuerza como de vortex. 
El steering lo uso entre las transiciones de fases para mover a los pájaros y sacarlos/meterlos en la pantalla.

**Verificaciones que hice durante el desarrollo:**
- Cambiar `spd` escala la velocidad de todas las capas proporcionalmente
- Cambiar `dec` alarga o acorta la persistencia del trail (lo medí a ojo en los stages de Physarum)
- Cambiar swirl entre 0 y 1 transforma el flow field de corriente libre a mandala centrado (donde evitaban el medio del Canvas)
- Cambiar wF/wP por especie permite que las cuatro capas de pintura coexistan con comportamientos distintos.
  
____

# 🌻AUTOEVALUACIÓN

| Criterio | Puntaje | Evidencia |
|---|---|---|
| 1. Cumplimiento del encargo | 25 / 25 | https://estorrente.github.io/SIM-U6-Agentes/ |
| 2. Comprensión y verificación | 25 / 25 | Lo expliqué claramente en la bitácora [aquí](#explicacion)
| 3. Diseño e intención | 25 / 25 | En ningún momento dejé a la IA inventar lo que quería que sucediera. [Mi idea de cada momento de la canción](#score) era supremamente claro, y exigí que el código se apegara a él. Había una intención muy clara de representar el estilo visual del cantante y conectarlo con la energía y narrativa de la canción, aportando también algunas partes de recuerdos de mi infancia (como Kiriku y el teatro de sombras) que relaciono con el tono narrativo de We Pelicans. 
| 4. Interpretación humana | 25 / 25 | Todo está pensado para que yo conduzca el instrumento. CTRL avanza el score visual que YOOOO planeé completo, el mouse interviene el entorno (en el clímax dibujo un atrayente en el trail para que el physarum crezca por encima, y también puedo revolver el flow field con un vórtex), y con Z/X puedo apretar o dispersar el flock en vivo. Ninguna de esas cosas se da por temporizador ni por audio; si yo no toco el programa, ahí se queda en el primer physarum; nunca decide estructura. La sincronización con la música depende 100% de mi oído, yo decido cuándo cae el momento y aprieto CTRL. Y lo de usar una sola tecla para avanzar el score, en vez de una tecla por comportamiento, fue a propósito. En el proyecto de las fuerzas tenía como 10 botones para los cambios, y con los nervios terminé usando apenas como 4 :c. Con CTRL eso no me pasa.  
| **Total** | **100 / 100** |
