# Práctica obligatoria - Las elecciones

La práctica obligatoria de Programación II consiste en la definición, diseño e implementación de una aplicación para la gestión de los procesos electorales en un determinado pais. La aplicación deberá ser lo suficientemente flexible como para poder gestionar, por ejemplo, las elecciones en España, USA o Francia, con sistemas electorales distintos. Para ello será imprescindible el uso de patrones de diseño que se podrán implementar una vez aprobado su diseño por parte del profesorado de la asignatura.

La información inicial se encuentra contenida en un archivo que representa la estructura electoral de un estado. Tomaremos dos ejemplos: Pennsylvania, en USA, y Castilla y León, en España.

## Funcionamiento de la práctica

Inicialmente se crea e inicializa un objeto Elections al cual se le pasa el pais del cual son las elecciones, un fichero que contiene los censos municipios y provincias y un fichero de partidos, ambos CSV, se inicia el metodo leerCSV que extrae los datos de los ficheros y los guarda en forma del objeto pertinente, para esto se utilizan Handlers para controlar los datos de entrada (Name, ShortName, LongName), una vez tienes todo en un array con los objetos se le pasa al Builder indicado para cada tipo de elecciones, en este se crea un arbol logico utilizando el patron Composite, despues se pasará este arbol a otro Builder junto son el patron Strategy pertinente para realizar el conteo de los votos, este concecta con la interfaz grafica a través de ElectionController y lo representara visualmente por pantalla, finalmente se podran editar los resultados, asi como aplicar Decorator a los mismos (colores, porcentajes...) y crear Observers en los distintos nodos para visualizar distintos puntos de la simulacion de las elecciones

Diagrama de flujo: (./esquemas/diagrama-de-flujo.png)

## Patrones estructurales

### Patrón *composite*

1. Aplicación

Se utiliza el patrón para representar los ciudadanos de un país organizados a su vez en regiones, provincias y ciudades, según el siguiente diagrama UML:

![Composite UML diagram](./esquemas/UML-Composite.png)

### Patrón *decorator*

Se utiliza para decorar los resultados mostrados por pantalla en la interfaz gráfica
![Composite UML diagram](./esquemas/UML-Decorator.png)


## Patrones de comportamiento

### Patrón *iterator*

Se utiliza el patrón para recorrer el agregado del compuesto del *composite*, que a su vez se ha adaptado de la clase `java.util.Vector<>`

![Iterator UML diagram](./esquemas/UML-Iterator.png)

### Patrón *strategy*

Se utiliza para las diferentes estrategias de conteo para los distintos paises en añadiendose al patron Builder
![Iterator UML diagram](./esquemas/UML-Strategy.png)

## Patrones creacionales

Se utiliza para la creación de árboles de datos para tratarlos de forma más cómoda y mostrarlos en la interfaz. Se combina con el Composite para la creacion de nodos compuestos y los diferentes elementos que conforman las elecciones.
![Iterator UML diagram](./esquemas/UML-Builder.png)

### Patrón *observer*

Se utiliza para poder fijar el estado de los nodos en el momento deseado y mantenerlos en pantalla para poder ver como evolucionan las elecciones en distintos momentos.
![Iterator UML diagram](./esquemas/UML-Observer.png)



