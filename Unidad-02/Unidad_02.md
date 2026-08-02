# 🌱 ACTIVIDAD 04

## 🌿 **1) Ideación**
Al ver los conjuntos de partículas creadas en los ejemplos, y con base en mi trabajo anterior, quedó en mí un asombro por lo fácil que es simular el comportamiento básico de un ser vivo por medio de reglas, asignando deseos y temores. Me gusta ese concepto de que somos una colección de predisposiciones.    
  
Desde el primer momento que se mencionó el concepto de tensión, lo primero que vino a mi mente es el empuje y jale de la marea en el mar. Nosotros, al igual que ella, parecemos seguir el mismo ciclo: algo nos empuja a buscar, investigar y perseguir... y luego una palabra, interacción, presencia o error nos hace echar para atrás. Es un proceso por el que paso con demasiada frecuencia; un día estoy pensando en grande, imaginando proyectos ambiciosos, sintiendo la alegría de crear... y luego Juanferfranco vuelve a hablar de la IA y me achicopalo un poquito. Empiezo a dudar de la viabilidad, del concepto, del tiempo, de mi valor como artista, del valor del arte como tal, del público, de mi propósito, de mi utilidad... y bueno, la idea queda atrás (hasta que una semana después vuelve a empezar).
  
Creo que quiero representar esa experiencia de alguna manera. El deseo de serlo todo, hacerlo todo, apuntar a las estrellas... y luego el miedo que aterriza y echa atrás.

## 🌿**2) Definición**
  
**`Intención:` ¿Qué transformación, sensación, tensión o idea debe experimentar quien observa?**
> Debe sentir que la criatura formada por las partículas está luchando internamente entre su anhelo de perseguir algo y su miedo de salir de su zona de confort.  
  
**`Entidades:` ¿Qué elementos existen? Partículas, especies, campos, fronteras, memorias o señales. / `Relaciones:` ¿Cómo se afectan? Atracción, repulsión, persecución, cooperación, competencia o indiferencia.**
> 1) **Especies:** Criatura formada por múltiples partículas pequeñas, representando los miles de deseos, miedos y pensamientos que conforman a un ser vivo. Se desplaza como grupo en dirección de partículas de anhelo que aparecen en el canvas para absorberlas. Por cada 3 anhelos, aparecerá dentro de ella un pulso de vida. Si pasan más de 20 segundos sin absorber un anhelo, aparecerá dentro de ella un miedo o un impulso de muerte.
> 2) **Partículas:** habrán 5 tipos de partículas:
>    - `Miedos:` partículas de color azul que se mueven de forma errática, vibrando fuertemente. Repelen a los anhelos, son repelidas por los pulsos de vida, y son atraídas por los pulsos de muerte. Crean conexiones entre otros miedos más cercanos, extendiendo líneas entre sí. Cada conexión hace crecer un poco más a la partícula. Representa la manera en la que los miedos y preocupaciones, de ser dejados a continuar sin intervención, crecen exponencialmente y se alimentan los unos de los otros. Las conexiones sólo pueden ser cortadas al ser atravesadas por una partícula pulso de vida.  
>    - `Anhelos:` partículas de color amarillo con movimientos suaves, floaty, curiosas. Son repelidas por los miedos, atraen a los miedos, y no repelen a ninguna partícula. Atraen a los pulsos de vida. Si un anhelo se ve rodeado por conexiones de partículas de miedo, muere.    
>    - `Pulsos de vida:` partículas de color naranja que pulsan, haciéndose más grandes y pequeñas. Son repelidas por los pulsos de muerte y atraídas por los anhelos. Forman estructuras alrededor de los anhelos para protegerlos de las conexiones de los miedos.  
>    - `Pulsos de muerte:` Los pulsos de muerte son partículas completamente estáticas de color gris. Su color pulsa lentamente.    
>    - `Alma:` Una partícula grande y central de tipo único, color blanco e iluminada. Mientras haya un decente equilibrio entre los tipos de partículas o una mayor cantidad de anhelos y pulsos de vida, se mantendrá pura. Si predominan los miedos y pulsos de muerte, el alma se apagará hasta que la criatura no pueda desplazarse más y sus partículas mueran. Su vida disminuirá a medida que otras criaturas a su alrededor mueran.  
> 3) Fronteras: las partículas de cada criatura serán contenidas por una membrana fluida que puede empujarlas. Al acercarse a una partícula de anhelo, se extenderá un tipo de brazo o tentáculo que la tome y absorba.
  
**MATRIZ (vertical partícula ejerciendo fuerza, horizontal partícula afectada:**  
<img width="585" height="99" alt="image" src="https://github.com/user-attachments/assets/d4db6d80-fb8f-4a12-b2ec-6b7f2d5bf568" />
  
  
**`Entradas:` ¿Qué alimenta el sistema? Semilla, tiempo, audio, interacción, datos o decisiones del participante.**
> Las criaturas se unirán para formar patrones de olas y corrientes en el canvas, recorriendo el espacio y alimentándose. Las olas representan esa lucha interna de cada uno de los seres. De ser dejadas solas, dependerá de la interacción interna de sus partículas y la probabilidad de spawn de los anhelos. El participante podrá utilizar su mouse para generar un movimiento de onda o marea en las olas de las criaturas, empujándolas en dirección de sus anhelos, como lo hacen muchas de las personas a nuestro alrededor a diario (maestros, padres, amigos, modelos a seguir...)  

**`Reglas:` ¿Cómo cambia el estado de un frame al siguiente?**
> Las olas se verían afectadas por las almas de las criaturas, permitiendo el movimiento de marea mientras suficientes de ellas permanezcan vivas. A medida que pasa el tiempo, más y más citraturias morirán, reduciendo la resistencia de las demás. Lo que quedará finalmente es una imagen estática de los cadáveres, representando a todos aquellos que se permitieron ser consumidos por sus temores y apagaron su voluntad.  

**`Invariantes:` ¿Qué debe permanecer para conservar la identidad del sistema?**
> Aunque el número de criaturas pueda ser controlado, siempre deben haber suficientes de ellas como para que el patrón de la ola sea visible. Cada criatura debe spawnear por lo menos 3 de cada tipo de partícula, garantizando la interacción de estas desde el inicio. Además, las partículas internas no deben salirse de sus membranas. También, las dinámicas de atracción y repulsión entre partículas.      

**`Variabilidad:` ¿Qué puede ser diferente en cada ejecución sin destruir esa identidad?**
> La cantidad exacta de las partículas iniciales, la cantidad exacta de las criaturas, el color y tamaño de las partículas (mientras se mantengan dentro de distintos tonos de su color), el rate de spawn de los anhelos, la velocidad de movimiento de las partículas y de las criaturas, los tamaños y las formas de las partículas...  

**`Curaduría y reflexión:` ¿Qué resultado es significativo y cuál es solo un accidente interesante?**  
Los patrones de olas y corrientes, junto a la muerte eventual de las criaturas, son significativas. Por otro lado, los patrones formados dentro de ellas es un accidente interesante.  
___

# 🌱 ACTIVIDAD 5

🌿 **Formula la tensión:**  
Quiero explorar la tensión entre `los anhelos` y `los miedos`.  
  
🌿 **Describe brevemente cómo esperas que se manifieste en el comportamiento del sistema.**
    
Espero que esta tensión se manifieste como un comportamiento oscilante. La criatura nunca debería avanzar de manera continua hacia sus objetivos ni permanecer inmóvil indefinidamente. Cada vez que aparezca un anhelo, la criatura reorganizará sus partículas internas para perseguirlo; sin embargo, el crecimiento de los miedos y de sus conexiones generará una fuerza opuesta que ralentizará, desviará o incluso impedirá ese movimiento.
  
La contradicción está incorporada en las reglas del sistema. Los anhelos producen organización, expansión y desplazamiento hacia el exterior, mientras que los miedos generan redes que aumentan su propia influencia y restringen progresivamente el movimiento de la criatura. Ninguno de los dos estados es permanente: el sistema oscila constantemente entre ambos dependiendo de las interacciones internas y de los eventos que ocurran durante la simulación.
  
🌿 **Diseño del sistema**
  
1) `Tipos de partículas:` seleccioné cinco tipos de partículas (alma, anhelos, miedos, pulsos de vida y pulsos de muerte) porque quiero hacer perceptible que un estado emocional complejo surge de múltiples comportamientos simples y no de un único elemento. Espero que produzca una organización interna donde cada población contribuya con un rol diferente al comportamiento colectivo de la criatura.
  
2) `Cantidad de partículas de cada tipo:`
Por criatura:
- 1 Alma
- 10–15 Miedos
- 8-12 Anhelos
- 3 Pulsos de Vida iniciales
- 1 Pulso de Muerte inicial (o ninguno hasta que pase suficiente tiempo)

Seleccioné una mayor cantidad de miedos y anhelos porque quiero hacer perceptible que el conflicto principal ocurre entre estas dos fuerzas. Espero que produzca una lucha constante en lugar de depender únicamente de eventos excepcionales como los pulsos.

🌿 `Matriz de atracción, repulsión e indiferencia`  
<img width="585" height="99" alt="image" src="https://github.com/user-attachments/assets/d4db6d80-fb8f-4a12-b2ec-6b7f2d5bf568" />  
  
**Justificación:**
Seleccioné relaciones asimétricas entre algunas partículas porque quiero hacer perceptible que las influencias emocionales no siempre son recíprocas. Espero que produzca dinámicas impredecibles donde una población pueda modificar profundamente a otra sin recibir el mismo efecto de regreso.  
   
🌿 `Intensidad y alcance de cada relación`  
1) **Miedos**  
- repulsión media/fuerte a anhelos  
- alcance medio  
  
2) **Anhelos**  
- atracción suave entre sí  
- alcance largo  
  
3) **Vida**  
- atracción fuerte hacia anhelos  
- alcance corto  
  
4) **Muerte**
- atracción fuerte sobre miedos  
- alcance medio  

**Justificación:**  
Seleccioné distintas intensidades y alcances porque quiero hacer perceptible que algunas emociones actúan lentamente mientras otras tienen efectos inmediatos. Espero que produzca cambios graduales interrumpidos por momentos de reorganización rápida.  
  
🌿 `Distancias de interacción`   
Cada partícula puede variar entre:  
- **corto:** 20 px  
- **medio:** 50 px  
- **largo:** 90 px  

**Justificación:**  
Seleccioné diferentes radios de interacción porque quiero hacer perceptible que no todas las influencias afectan desde la misma distancia. Espero que las criaturas desarrollen estructuras internas cambiantes y no únicamente grupitos compactos.  

🌿 `Fricción y velocidad máxima`

| | Miedos | Anhelos | Vida | Muerte | Alma |
|--|--------|---------|------|--------|------|
|Velocidad | alta | media-baja | media | cero | movimiento únicamente con la criatura |
| fricción  | alta | baja | baja | cero | cero |
   
**Justificación:**  
Seleccioné velocidades y fricciones distintas porque quiero hacer perceptible que cada tipo de partícula expresa una actitud diferente frente al movimiento. Espero que los miedos transmitan ansiedad, mientras que los anhelos sugieran exploración y calma.  
  
🌿 `Distribución inicial`  
Alma al centro, anhelos distribuidos alrededor del centro, miedos mezclados con ligera concentración a los bordes de la membrana, vida cerca del alma, muerte ausente o muy cercana al centro.  
  
**Justificación:**  
Seleccioné una distribución inicial organizada porque quiero hacer perceptible que todas las criaturas parten de un estado relativamente estable. Espero que las diferencias entre ejecuciones aparezcan como consecuencia de las reglas y no de configuraciones completamente aleatorias.  

🌿 `Parámetros constantes y variables`  
  
| Constantes | Variables |
|------------|------------|
| reglas de atracción, radios, velocidad máxima, fricción | cantidad inicial de partículas, tiempo entre aparición de anhelos, posición inicial, dirección inicial, tamaño, colores dentro de un rango |
  
**Justificación:**  
Seleccioné estos parámetros constantes y variables porque quiero hacer perceptible una identidad reconocible entre simulaciones sin eliminar la posibilidad de resultados distintos y mantener las asociaciones emotivas ligadas al significado de cada color. Espero que cada ejecución conserve el mismo comportamiento general, aunque produzca historias diferentes.  

___

🌿 `Todo completito:`  Quiero explorar la tensión entre `los anhelos` y `los miedos`.  
Quiero representar la tensión entre los anhelos y los miedos como un conflicto dinámico, donde una criatura oscila constantemente entre avanzar hacia sus metas y retroceder por la influencia de sus propias dudas. Mi intención es que esta contradicción no se explique mediante símbolos, sino que sea visible en el comportamiento emergente del sistema.  

| **Característica**           | **Miedos**                                                                 | **Anhelos**                                                       | **Pulsos de Vida**                                                  | **Pulsos de Muerte**                                             | **Alma**                                                                                                                                       |
| ---------------------------- | -------------------------------------------------------------------------- | ----------------------------------------------------------------- | ------------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| **Significado**              | Dudas, ansiedad y pensamientos que frenan el avance.                       | Metas, curiosidad y deseo de crecer.                              | Esperanza y resiliencia que fortalecen los anhelos e impulsan a movimiento.                 | Desesperanza y estancamiento.                                    | La esencia de la criatura; representa su voluntad de seguir existiendo.                                                                        |
| **Cantidad inicial**         | 10–15                                                                      | 8–12                                                              | 3                                                                   | 0–1                                                              | 1                                                                                                                                              |
| **Color**                    | Azul                                                                       | Amarillo                                                          | Naranja                                                             | Gris                                                             | Blanco brillante                                                                                                                               |
| **Tamaño**                   | Pequeño (crece al conectarse)                                              | Pequeño                                                           | Mediano (pulsa)                                                     | Mediano                                                          | Grande                                                                                                                                         |
| **Movimiento**               | Errático, vibrante                                                         | Suave, flotante y curioso                                         | Estable, protector                                                  | Inmóvil                                                          | Se mueve únicamente con la criatura                                                                                                            |
| **Velocidad**                | Alta                                                                       | Media-baja                                                        | Media                                                               | Cero                                                             | Movimiento únicamente con la criatura                                                                                                          |
| **Fricción**                 | Alta                                                                       | Baja                                                              | Baja                                                                | Cero                                                             | Cero                                                                                                                                           |
| **Aceleración**              | Alta y cambiante                                                           | Suave y gradual                                                   | Media                                                               | Nula                                                             | Determinada por el movimiento colectivo                                                                                                        |
| **Alcance de interacción**   | Medio                                                                      | Largo                                                             | Corto                                                               | Medio                                                            | Afecta toda la criatura                                                                                                                        |
| **Comportamiento principal** | Se conectan entre sí formando redes que crecen y restringen el movimiento. | Buscan ser absorbidos por la criatura y favorecen su crecimiento. | Rodean y protegen a los anhelos; pueden romper conexiones de miedo. | Atraen a los miedos y debilitan el sistema.                      | Evalúa el equilibrio interno y determina la supervivencia de la criatura.                                                                      |
| **Qué atrae**                | Pulsos de muerte                                                           | Pulsos de vida                                                    | Anhelos                                                             | Miedos                                                           | —                                                                                                                                              |
| **Qué repele**               | Anhelos                                                                    | Miedos                                                            | Pulsos de muerte                                                    | Pulsos de vida                                                   | —                                                                                                                                              |
| **Efecto emergente**         | Forman redes cada vez más grandes que dificultan alcanzar nuevos anhelos.  | Generan movimiento y reorganización constante de la criatura.     | Mantienen vivo el sistema y evitan que los miedos dominen.          | Favorecen el crecimiento de los miedos y aceleran la decadencia. | Si predominan la vida y los anhelos permanece brillante; si predominan el miedo y la muerte, se apaga hasta provocar la muerte de la criatura. |
