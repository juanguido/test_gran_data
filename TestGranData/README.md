# Deploy Spark using Docker

<img width="1440" alt="Spark" src="https://user-images.githubusercontent.com/118063572/215892742-d17570d7-3375-4166-8c52-87875b82d0ef.png">

Una vez que tengas abierto el notebook podrás cargar la data tal y como está el código para que puede ser usado.

1) El monto total es igual a 391367.
2) En el mismo container se agrega la carpeta con el dataset que se escribió del punto 2.
3) Se agrega la imagen PNG del histograma del punto 3.

Ejercicio 2 - Preguntas generales
1. La empresa cuenta con un cluster on premise de Hadoop en el cual se ejecuta, tanto el
data pipeline principal de los datos, como los análisis exploratorios de los equipos de
Data Science y Data Engineering. Teniendo en cuenta que cada proceso compite por un
número específico de recursos del cluster:
● ¿Cómo priorizaría los procesos productivos sobre los de análisis exploratorios?
- Si están dentro de un data warehouse, se puede gestionar los recursos para así priorizar a los procesos y que tengan los recursos minimos para poder trabajar.

● Debido a que los procesos productivos del pipeline poseen un uso intensivo
tanto de CPU como de memoria, ¿qué estrategia utilizaría para administrar su
ejecución durante el día? ¿Qué herramientas de scheduling conoce para tal fin?
 - Ejecutar por la mañana todos los pipelines productivos que requieren mucho recursos para así puedan realizar dicho proceso sin que se vaya a saturar, usando ADF se puede automatizar por medio de triggers y así calederizarlo.

2. Existe una tabla del Data Lake con alta transaccionalidad, que es actualizada
diariamente con un gran volumen de datos. Consultas que cruzan información con esta
tabla ven afectada su performance en tiempos de respuesta.
● Según su criterio, ¿cuáles serían las posibles causas de este problema?
- Revisar duplicidad, tratar de ver si está normalizada ya que puede traer duplicidad. Particionado, si se puede optimizar el proceso mediante el particionamiento de la información.

● Dada la respuesta anterior, ¿qué sugeriría para solucionarlo?
- Revisar el proceso o código para optimizar el proceso mediante buenas prácticas, como normalizado de la tabla, o utilizar métodos eficientes, desde funciones hasta el paralelismo del proceso.

3. Imagine un clúster Hadoop de 3 nodos, con 50 GB de memoria y 12 cores por
nodo. Necesita ejecutar un proceso de Spark que utilizará la mitad de los
recursos del clúster, dejando la otra mitad disponible para otros jobs que se
lanzarán posteriormente.
● ¿Qué configuraciones en la sesión de Spark implementaría para
garantizar que la mitad del clúster esté disponible para los jobs
restantes?

- Dentro del notebook, podemos configurar los recursos que vamos a utilizar en ese notebook o en el proceso, estos pueden ser:
    --num-executors
    --executor-cores
    --executor-memory
Y hay más configuraciones que se le pueden hacer al cluster dentro del notebook para satisfacer nuestras necesidades según lo que se requiera.