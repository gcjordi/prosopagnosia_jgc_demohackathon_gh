# Propósito:

Proyecto de Jordi Garcia Castillón - Inclusión y accesibilidad (Hackathon for Good AWS - Intel): Visión por computador para personas con prosopagnosia y para otras enfermedades y/o discapacidades.

# Solución propuesta e impacto social:

Este sistema simplemente está pensado para ser un aplicativo base para “proveer” a cualquier otro sistema o elemento (tal y como se mencionaba en los puntos anteriores) de la funcionalidad para el que ha sido preparado, y todo ello por lo siguiente:

Aunque la aplicación de este sistema también puede servir para el supuesto de otras enfermedades (como, por ejemplo, el Alzheimer donde una persona no recuerda a una persona si la ve y el sistema si se le incorporase voz podría reconocer la imagen y decirle quien es) u otras enfermedades o discapacidades, primariamente este aplicativo se ha planteado para las personas que sufren la enfermedad denominada prosopagnosia.

La prosopagnosia es una enfermedad poco común que puede ser tanto congénita (se estima que afectando a un 2’5% de la población) como adquirida (a causa de accidentes vasculares cerebrales, tumores, Parkinson, etc.), por la cual la persona se torna incapaz de reconocer facialmente a la persona que tiene delante (o incluso a ella misma en un espejo).

Esta dificultad por reconocer a otra persona, además de suponer una clara merma en la calidad de vida para la persona afectada, imponerle fuertes limitaciones y suponerle un alto impacto negativo a nivel psicológico, puede llegar a poner en peligro su propia integridad física. Por ejemplo, una persona con prosopagnosia que se encuentra en su domicilio y no puede reconocer si cuando abre la puerta esa persona es conocida o no o si, incluso, puede llegar a ser alguien que quiere dañarle de algún modo (alguien de quien se haya apartado sentimentalmente por abusos, violencia u otros muchos casos o supuestos).

La solución aquí presentada mediante un sistema de reconocimiento fácil le permite a la persona afectada establecer categorías de personas para que cuando le llaman a la puerta o habla con alguien en la calle (por poner sólo dos ejemplos) pueda conocer de forma automatizada si la persona sujeto que se encuentra enfrente es un familiar, es un conocido o si es una persona de peligro y debe apartarse o solicitar ayuda y asistencia. En resumen, le sirve de alerta y de ponerle en sobre aviso de quien puede ser y de prepararle para actuar en consecuencia.

Evidentemente, este sistema tan sólo se ha desarrollado en una primera fase incipiente y se le podrían incorporar capas adicionales que permitiesen a la persona conocer aún con más detalle a aquella persona que por su enfermedad por sí mismo es incapaz de conocer.

Las capas adicionales anteriormente mencionadas podrían incluir, por ejemplo, que el sistema reconociese directamente de que persona se trata (su padre, madre, nombre del amigo, etc.), o que estableciese una probabilidad de que fuese parte de su entorno más cercano (por ejemplo, por detección de patrones en rasgos entre personas que exista relación de parentesco y consanguineidad entre ellas, entre otras).

Para todo ello se ha trabajado en una base primaria de imágenes que se han etiquetado para cada uno de los grupos deseados y se les ha aplicado técnica de data augmentation (con Roboflow) tanto para incrementar la base como para hacer más “resistente” al algoritmo ante posibles cambios, distorsiones, variantes que puedan existir en la cámara o en el sujeto a reconocer. En el repositorio se encuentra toda la información al respecto (algunos de los archivos json han sido modificados para la eliminación de potenciales datos identificativos del recurso).

# Introducción técnica y disclaimer:

Este proyecto se ha desarrollado únicamente con fines de demostración prototipo para el Hackathon for Good (https://www.hackathoniberia.com/), organizado por AWS e Intel en marzo del 2022.

La fuente de datos abierta primaria se encuentra en el conocido dataset de imágenes LFW de la Universidad de Massachusetts (http://vis-www.cs.umass.edu/lfw/).

El estado actual de desarrollo no habilita al mismo en estos momentos para sus usos médicos, orientación o función sanitaria alguna.

Tanto los resultados obtenidos como la funcionalidad misma de este desarrollo tan sólo puede interpretarse por ahora como una mera demostración básica, pues se encuentra en un estado funcional pero evidentemente ni la cantidad de imágenes con las que se ha preparado el sistema ni muchas otras variables o consideraciones hacen que la fiabilidad en producción de este desarrollo esté ahora ni mucho menos establecida.

# Secciones requeridas:

**1.	¿Cuál es el desafío elegido y el valor de la solución en su resolución?**

La categoría presentada a concurso es la de “Inclusión y accesibilidad”. 

El valor que se considera que la solución aporta es que consigue dar una respuesta que puede llegar a ser de vital importancia y aportar, en cualquier caso, una mejora en la calidad de vida de las personas que sufren una enfermedad que les impide reconocer a las personas.

**2.	¿Qué servicios funcionan con AWS e Intel y por qué fueron elegidos?**

Esencialmente se ha trabajado con AWS Rekognition (https://aws.amazon.com/es/rekognition/) y se ha escogido esta modalidad por ser un servicio gestionado y completamente administrado por AWS que permite preparar un modelo rápidamente, generando en muy poco tiempo un aplicativo completamente funcional y operativo que posteriormente podrá ser fácilmente reproducible, escalable y accesible de muchas maneras.

El uso de **AWS Rekognition** para el reconocimiento de imágenes permite habilitar el modelo (por ejemplo a través de su API) a multitud de sistemas que se puedan pensar, desde WebApps hasta cámaras y sistemas que pueda utilizar la persona enferma para su uso.

Obviamente, todos o casi todos los sistemas, pueden correr sobre procesadores Intel, pero el gran valor de Intel en esta solución no resulta sólo en esta capacidad, sino en la posibilidad de llevar el modelo a soluciones específicas de Intel como placas SBC que corren sobre Intel en general e **Intel Coffe Lake** (https://www.intel.es/content/www/es/es/products/platforms/details/coffee-lake-s.html) en particular, y aún más en soluciones propias a las que se les puede implementar la solución en sus modalidades Edge con los miniordenadores **Intel NUC** (https://www.intel.es/content/www/es/es/products/details/nuc/mini-pcs.html) y cualquier Webcam (pudiendo ser esta cualquiera de Intel si se desea).

# Notas finales: 

Los miembros del jurado pueden solicitarme el acceso al recurso en Rekognition, a la API en el momento que lo deseen para poder comprobar el funcionamiento del sistema si lo desean, tal y como consta establecido en las normas del concurso.

Link al video del proyecto: https://youtu.be/oVg64B8UGvo
