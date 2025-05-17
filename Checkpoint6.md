# Checkpoint 6 

## ¿Para qué usamos Clases en Python?

Se usa para definir una estructura o plantilla que sirve como base para crear objetos. Las clases permiten organizar código de manera eficiente, encapsular datos y comportamiento, y facilitar la reutilización de código a través de la herencia y el polimorfismo. 

Las clases proveen una forma de empaquetar datos y funcionalidad juntos. Al crear una nueva clase, se crea un nuevo tipo de ```objeto```, permitiendo crear nuevas instancias de ese tipo. Cada ```instancia``` de clase puede tener atributos adjuntos para mantener su estado. Las instancias de clase también pueden tener métodos (definidos por su clase) para modificar su estado.

Comparado con otros lenguajes de programación, el mecanismo de clases de ```Python``` agrega clases con un mínimo de nuevas sintaxis y semánticas. Es una mezcla de los mecanismos de clases encontrados en ```C++``` y ```Modula-3```. Las clases de Python proveen todas las características normales de la Programación Orientada a Objetos: el mecanismo de la herencia de clases permite múltiples clases base, una clase derivada puede sobre escribir cualquier método de su(s) clase(s) base, y un método puede llamar al método de la clase base con el mismo nombre. Los objetos pueden tener una cantidad arbitraria de datos de cualquier tipo. Igual que con los módulos, las clases participan de la naturaleza dinámica de Python: se crean en tiempo de ejecución, y pueden modificarse luego de la creación.

En terminología de ```C++```, normalmente los miembros de las clases (incluyendo los miembros de datos), son públicos (excepto ver abajo Variables privadas), y todas las funciones miembro son virtuales. Como en ```Modula-3```, no hay atajos para hacer referencia a los miembros del objeto desde sus métodos: la función método se declara con un primer argumento explícito que representa al objeto, el cual se provee implícitamente por la llamada. Como en Smalltalk, las clases mismas son objetos. Esto provee una semántica para importar y renombrar. A diferencia de C++ y Modula-3, los tipos de datos integrados pueden usarse como clases base para que el usuario los extienda. También, como en C++ pero a diferencia de Modula-3, la mayoría de los operadores integrados con sintaxis especial (operadores aritméticos, de sub-índice, etc.) pueden volver a ser definidos por instancias de la clase.

(Sin haber una terminología universalmente aceptada sobre clases, haré uso ocasional de términos de Smalltalk y C++. Usaría términos de Modula-3, ya que su semántica orientada a objetos es más cercana a Python que C++, pero no espero que muchos lectores hayan escuchado hablar de él.)

 **Sintaxis de definición de clases**
La forma más sencilla de definición de una clase se ve así:
```python 
class ClassName:
    <statement-1>
    .
    .
    .
    <statement-N> 
  ```
**Plantilla para objetos:** 
Una clase define los atributos (variables que almacenan información) y los métodos (funciones que realizan acciones) que tendrá un objeto. 

**Organización y estructura:**
Las clases ayudan a organizar el código en módulos lógicos, lo que facilita la comprensión y la modificación del programa. 
**Encapsulación:**
Las clases permiten ocultar la implementación interna de un objeto, exponiendo solo una interfaz para interactuar con él. 

**Reutilización de código:**
Con la herencia, una clase puede heredar atributos y métodos de otra clase, evitando la duplicación de código y promoviendo la reutilización. 

**Polimorfismo:**
Las clases permiten a diferentes objetos responder de manera diferente a la misma solicitud (método), lo que facilita la flexibilidad del código. 

**Programación Orientada a Objetos (POO):**
Las clases son el concepto fundamental de la POO en Python, permitiendo modelar objetos del mundo real y sus interacciones en código. 

```python 
class NombreDeLaClase:
    """
    Documentación de la clase (docstring).
    Describe el propósito y la funcionalidad de la clase.
    """

    # Atributos de clase (compartidos por todas las instancias)
    atributo_de_clase = valor

    # Método especial de inicialización (constructor)
    def __init__(self, argumento1, argumento2, ...):
        """
        Documentación del método __init__.
        Inicializa los atributos de la instancia cuando se crea un objeto.
        """
        # Atributos de instancia (propios de cada objeto)
        self.atributo_de_instancia1 = argumento1
        self.atributo_de_instancia2 = argumento2
        # ...

    # Otros métodos de instancia
    def metodo1(self, otro_argumento):
        """
        Documentación del método metodo1.
        Define una acción que puede realizar la instancia.
        """
        # Código del método
        return resultado

    def metodo2(self):
        """
        Documentación del método metodo2.
        Otro método de instancia.
        """
        # Más código
        pass

    # Métodos de clase (se llaman en la clase, no en la instancia)
    @classmethod
    def metodo_de_clase(cls, argumento):
        """
        Documentación del método de clase.
        Puede acceder y modificar atributos de clase.
        'cls' es la convención para el primer parámetro, que representa la clase.
        """
        # Código del método de clase
        return algo

    # Métodos estáticos (no acceden ni modifican la clase ni la instancia)
    @staticmethod
    def metodo_estatico(argumento1, argumento2):
        """
        Documentación del método estático.
        Funciona como una función normal dentro del espacio de nombres de la clase.
        """
        # Código del método estático
        return otro_resultado
```
### Componentes principales:

- ```class NombreDeLaClase::``` Esta es la declaración de la clase.

  - ```class``` es la palabra clave que indica que estamos definiendo una clase.
   - ```NombreDeLaClase``` es el nombre que le das a tu clase. Por convención, se usa la notación PascalCase (cada palabra comienza con una letra mayúscula).
  - Los dos puntos (```:```) indican el inicio del bloque de código de la clase.
- ```"""Documentación de la clase..."""```: Esto es el docstring de la clase. Es una cadena de texto multilínea que se utiliza para documentar la clase. Es una buena práctica incluirlo para explicar el propósito de la clase.

- ```atributo_de_clase = valor```: Estos son atributos que pertenecen a la clase en sí misma y son compartidos por todas las instancias (objetos) que se creen a partir de esta clase.

- ```def __init__(self, argumento1, argumento2, ...)```:: Este es un método especial llamado constructor. Se ejecuta automáticamente cuando se crea una nueva instancia de la clase.

    - ```self``` es el primer parámetro y siempre se refiere a la instancia del objeto que se está creando.
  - ```argumento1```, ```argumento2```, etc., son los parámetros que puedes pasar al crear una instancia de la clase.
  - Dentro de ```__init__```, se suelen inicializar los atributos de instancia utilizando ```self.nombre_del_atributo = valor```. Estos atributos son específicos de cada objeto.
- ```def metodo1(self, otro_argumento):```, ```def metodo2(self):```: Estos son métodos de instancia. Son funciones definidas dentro de la clase y operan sobre la instancia del objeto (```self```). El primer parámetro de un método de instancia siempre es ```self```.

- ```@classmethod def metodo_de_clase(cls, argumento):```: Este es un método de clase. Se define utilizando el decorador ```@classmethod```.

  - El primer parámetro es ```cls```, que se refiere a la clase en sí misma (no a una instancia específica).
  - Los métodos de clase pueden acceder y modificar los atributos de clase.
- ```@staticmethod def metodo_estatico(argumento1, argumento2):```: Este es un método estático. Se define utilizando el decorador ```@staticmethod```.

  - No tienen acceso automático a la instancia (```self```) ni a la clase (```cls```).
  - Funcionan como funciones regulares, pero están dentro del espacio de nombres de la clase. Se utilizan para agrupar lógica relacionada con la clase.
``` python
  class Coche:
    """Representa un coche."""

    ruedas = 4  # Atributo de clase

    def __init__(self, marca, modelo, color):
        """Inicializa un nuevo coche."""
        self.marca = marca
        self.modelo = modelo
        self.color = color
        self.velocidad = 0

    def acelerar(self, incremento):
        """Aumenta la velocidad del coche."""
        self.velocidad += incremento

    def frenar(self):
        """Detiene el coche."""
        self.velocidad = 0

# Crear instancias de la clase Coche
mi_coche = Coche("Seat", "León", "Rojo")
otro_coche = Coche("Ford", "Focus", "Azul")

# Acceder a los atributos de instancia
print(mi_coche.marca)      # Salida: Seat
print(otro_coche.color)     # Salida: Azul

# Acceder al atributo de clase
print(Coche.ruedas)        # Salida: 4
print(mi_coche.ruedas)     # Salida: 4

# Llamar a los métodos de instancia
mi_coche.acelerar(20)
print(mi_coche.velocidad)  # Salida: 20
mi_coche.frenar()
print(mi_coche.velocidad)  # Salida: 0
```
## ¿Qué método se ejecuta automáticamente cuando se crea una instancia de una clase?
El método que se ejecuta automáticamente cuando se crea una instancia de una clase en Python es el método ```__init__```.

Este método especial se conoce como el constructor. Su principal propósito es inicializar los atributos de la instancia del objeto que se está creando. Cuando llamas a la clase para crear un nuevo objeto (por ejemplo, ```mi_objeto = MiClase(argumentos)```), Python automáticamente invoca el método ```__init__``` de esa clase, pasando la nueva instancia (```self```) y cualquier argumento que hayas proporcionado durante la creación del objeto.

Dentro del método ```__init__```, es donde típicamente defines y asignas los valores iniciales a los atributos específicos de cada objeto de esa clase.

**Ejemplo:**
``` python 
class Persona:
    """Representa a una persona con nombre y edad."""

    def __init__(self, nombre, edad):
        """
        Inicializa una nueva persona.

        Args:
            nombre (str): El nombre de la persona.
            edad (int): La edad de la persona.
        """
        print(f"¡Se está creando una nueva persona llamada {nombre}!")
        self.nombre = nombre
        self.edad = edad

    def saludar(self):
        """Saluda a la persona."""
        print(f"Hola, mi nombre es {self.nombre} y tengo {self.edad} años.")

# Crear instancias de la clase Persona
persona1 = Persona("Alice", 30)
persona2 = Persona("Bob", 25)

# Acceder a los atributos de las instancias
print(f"Nombre de persona1: {persona1.nombre}")
print(f"Edad de persona2: {persona2.edad}")

# Llamar al método saludar de las instancias
persona1.saludar()
persona2.saludar()
```
**¿Qué sucede cuando se ejecuta este código?**
1. ```persona1 = Persona("Alice", 30)```:

    - Cuando Python encuentra esta línea, sabe que debe crear una nueva instancia de la clase ```Persona```.
    - Automáticamente llama al método ```__init__``` de la clase Persona.
    - Le pasa tres argumentos al método``` __init__```:
      - ```self```: La nueva instancia del objeto Persona que se está creando (aunque no lo pases explícitamente, Python lo hace por ti).
      - ```nombre```: El valor ```"Alice"``` que proporcionaste.
      - ```edad```: El valor ```30``` que proporcionaste.
   - Dentro de ```__init__```:
       - Se imprime el mensaje: ```"¡Se está creando una nueva persona llamada Alice!"```.
      - Se asigna el valor ```"Alice"``` al atributo de instancia ```self.nombre```.
     - Se asigna el valor ```30``` al atributo de instancia ```self.edad```.
   - Finalmente, la nueva instancia del objeto ```Persona``` se asigna a la variable ```persona1```.
2. ```persona2 = Persona("Bob", 25)```:

   - De manera similar, cuando se ejecuta esta línea, se crea otra instancia de ```Persona```.
   - Se llama automáticamente a ```__init__``` con ```self```, ```"Bob"``` y ```25```.
   - Se imprime: ```"¡Se está creando una nueva persona llamada Bob!"```.
   - Se asignan los valores a ```self.nombre``` y ```self.edad``` para esta instancia.
   - La nueva instancia se asigna a la variable ```persona2```.
## ¿Cuáles son los tres verbos de API?

En el contexto de las APIs RESTful (que son las más comunes), los tres verbos principales, aunque no los únicos, que se utilizan para realizar operaciones y que se corresponden a las acciones CRUD (Crear, Leer, Actualizar, Borrar) más básicas son:

1. ```POST:``` Se utiliza principalmente para crear un nuevo recurso en el servidor. Los datos del nuevo recurso se envían en el cuerpo de la solicitud.

2. ```GET:``` Se utiliza para leer o recuperar uno o varios recursos del servidor. Las solicitudes ```GET``` suelen ser idempotentes, lo que significa que realizar la misma solicitud varias veces debería tener el mismo resultado.

3. ```PUT:``` Se utiliza para actualizar un recurso existente en el servidor. Los datos actualizados del recurso se envían en el cuerpo de la solicitud. A menudo se utiliza para reemplazar completamente el recurso identificado por la URI. También puede utilizarse para crear un recurso si no existe en la URI especificada (aunque ```POST ```es más convencional para la creación).

Aunque estos son los tres más fundamentales y a menudo mencionados como los "tres verbos de API" en una introducción simplificada, es importante saber que existen otros verbos HTTP (métodos) importantes que se utilizan en las APIs RESTful, como:

- ```DELETE:``` Se utiliza para borrar un recurso identificado por la URI.
- ```PATCH:``` Similar a ```PUT```, pero se utiliza para aplicar actualizaciones parciales a un recurso. Es decir, solo se envían los datos que se desean modificar, sin necesidad de enviar la representación completa del recurso.
```OPTIONS:``` Se utiliza para obtener información sobre las opciones de comunicación disponibles para un recurso dado. Por ejemplo, puede indicar qué métodos HTTP son soportados por una URI específica.
```HEAD:``` Similar a ```GET```, pero no devuelve el cuerpo de la respuesta. Se utiliza para obtener los metadatos (cabeceras HTTP) sobre un recurso sin descargar su contenido.

Por lo tanto, si bien ```POST```, ```GET``` y ```PUT``` cubren las operaciones de creación, lectura y actualización, en un contexto más completo de APIs RESTful, es crucial considerar también ```DELETE``` y ```PATCH``` para una implementación robusta del paradigma CRUD. La mención de solo tres suele ser una simplificación para introducir los conceptos básicos.

## ¿Es MongoDB una base de datos SQL o NoSQL?

  **MongoDB es una base de datos NoSQL.**

La distinción clave entre las bases de datos SQL (también conocidas como relacionales) y NoSQL (no relacionales) radica en cómo almacenan y estructuran los datos:

- **Bases de datos SQL:** Almacenan los datos en tablas con filas y columnas, siguiendo un esquema predefinido. Utilizan el lenguaje SQL (Structured Query Language) para la gestión y manipulación de los datos. Ejemplos comunes incluyen MySQL, PostgreSQL y SQL Server.

- **Bases de datos NoSQL:** Ofrecen esquemas más flexibles y diversos modelos de datos diferentes a las tablas relacionales. MongoDB, en particular, es una base de datos orientada a documentos. Almacena los datos en documentos con formato similar a JSON (llamados BSON en MongoDB), que pueden tener estructuras variables y diferentes campos. Otros tipos de bases de datos NoSQL incluyen bases de datos de clave-valor (como Redis), bases de datos de grafos (como Neo4j) y bases de datos de columnas (como Cassandra).

**Características de MongoDB como base de datos NoSQL:**

- *Orientada a documentos:* Los datos se almacenan en documentos flexibles y auto-descriptivos.
Esquema dinámico: No requiere un esquema fijo, lo que permite una mayor flexibilidad en la estructura de los datos.
- *Escalabilidad horizontal:* Diseñada para escalar distribuyendo datos en múltiples servidores (sharding).
- *Alto rendimiento:* Optimizado para el desarrollo ágil y la escalabilidad.
- *Lenguaje de consulta:* Utiliza el lenguaje de consulta de MongoDB (MQL), que es similar a SQL pero adaptado al modelo de documentos.

**¿Qué es NoSQL?**
```NoSQL```, que significa Not only SQL, es un enfoque de sistema de gestión de bases de datos que se emplea para ingerir, almacenar y recuperar datos no estructurados y semiestructurados dentro de una base de datos. Esto significa que los datos que no se pueden analizar o contar a través de bases de datos relacionales tradicionales (por ejemplo, SQL) pueden permanecer en su formato nativo y ser ingeridos en una base de datos NoSQL. La razón por la que se llama NoSQL es para enfatizar que estas bases de datos pueden manejar modelos de datos no tabulares y no relacionales, así como admitir lenguajes de consulta similares a SQL.

**¿Qué son los datos no estructurados?**
Los datos no estructurados son datos que no tienen un modelo de datos predefinido ni una organización coherente. Además, los datos no estructurados, como las publicaciones en las redes sociales, pueden actualizar y cambiar rápidamente, mientras que los datos estructurados, como las transacciones bancarias, tienen una tasa de cambio mucho menor. Algunos ejemplos de datos no estructurados son las imágenes, los archivos de audio, los videos y los mapas.

**¿Qué es una base de datos NoSQL?**
Las bases de datos NoSQL son bases de datos que emplean un esquema flexible que admite datos no estructurados y datos semiestructurados, al tiempo que emplean un método de almacenamiento de datos no tabular.

El uso de un esquema flexible permite a las bases de datos NoSQL ingerir datos no estructurados en su formato nativo (por ejemplo, .txt, .JPG, MP3), lo cual no es posible con bases de datos SQL debido al requisito de que todos los datos se alineen a un formato predefinido. Además, cuando las bases de datos NoSQL almacenan datos, se emplean modelos de datos flexibles para que los archivos de datos no estructurados puedan tener diferentes estructuras de datos y aún así almacenar dentro de la misma 
collection.

**Tipos de bases de datos NoSQL**

Existen diferentes tipos de bases de datos NoSQL, entre las que se incluyen:

- **Bases de datos de documentos:** Las bases de datos de documentos, a veces denominadas bases de datos orientadas a objetos, almacenan datos en documentos similares a objetos JSON (JavaScript Object Notation), aunque no son almacenes JSON. Utilizan los controladores devueltos de objetos nativos al lenguaje de programación utilizado por el desarrollador sin necesidad de un mapeador relacional de objetos (ORM). Cada documento en sí se trata como un registro y puede contener valores que incluyen números, matrices, objetos, cadenas o incluso caracteres booleanos. Además, se pueden incluir pares clave-valor, documentos anidados u otros datos estructurados. Un proveedor popular de estas bases de datos NoSQL es MongoDB.

- **Bases de datos de clave-valor:** Las bases de datos de clave-valor recopilan, recuperan y almacenan datos como agrupaciones de pares clave-valor. Esto significa que cada registro de datos está representado por una clave única y un valor asociado. La clave se emplea para recuperar el valor correspondiente de la base de datos. Por ejemplo, en una base de datos clave-valor de diseño de interiores, una clave podría ser " color " y el valor podría ser " púrpura. " Los proveedores más populares de estos sistemas de bases de datos NoSQL son AWS y ScyllaDB.
- **Almacenes de familias de columnas:** Las bases de datos de familias de columnas organizan los datos en columnas en lugar de filas, lo que resulta útil cuando se trabaja con conjuntos de datos amplios que son escasos en profundidad. De hecho, las tiendas familiares de columnas a veces se denominan "tiendas de columna ancha". En los almacenes de familias de columnas, cada fila tiene un conjunto diferente de columnas, y las columnas se agrupan en "familias". Estos modelos de datos son útiles cuando se trabaja con conjuntos de datos a gran escala que se benefician del escalado horizontal para optimizar el rendimiento. Los proveedores populares de estas bases de datos NoSQL incluyen Apache, Cassandra y HBase.
- **Bases de datos de grafos:** Las bases de datos de grafos almacenan datos en nodos y bordes. Los nodos suelen almacenar información sobre personas, lugares y cosas, mientras que las aristas almacenan información sobre las relaciones entre los nodos. Las bases de datos de grafos son excelentes herramientas para consultar estructuras de grafos (por ejemplo, redes sociales, jerarquías). Los proveedores populares de estas bases de datos NoSQL incluyen Neo4j, AWS y Kibana.

**Diferencias clave entre bases de datos SQL y NoSQL**

Si bien las bases de datos SQL y NoSQL ofrecen una funcionalidad valiosa, es importante comprender las diferencias clave entre ellas.

**Modelo de almacenamiento de base de datos**

La diferencia entre los sistemas de bases de datos SQL y NoSQL en relación con el almacenamiento de datos es muy marcada. Específicamente, las bases de datos SQL almacenan datos en tablas que contienen filas y columnas, mientras que los sistemas NoSQL almacenan datos utilizando varios métodos según el tipo de datos no estructurados que se ingieren (por ejemplo, documentos JSON, emparejamiento de valor clave, agrupación familiar, nodos/bordes de gráficos).

**Tipo de datos**

Mientras que las bases de datos NoSQL, a veces denominadas bases de datos no relacionales, son capaces de ingerir, almacenar y recuperar datos no estructurados, las bases de datos SQL (por ejemplo, bases de datos relacionales tradicionales) no lo son. Las bases de datos SQL solo pueden ingerir, almacenar y recuperar datos estructurados. Esto se debe a la diferencia entre los esquemas SQL y NoSQL utilizados.

**Esquemas**
Las bases de datos SQL se basan en un esquema de datos estricto y predefinido con el que deben alinear los datos que se van a ingerir. Sin embargo, las bases de datos NoSQL emplean esquemas flexibles que les permiten ingerir datos en sus diversos formatos nativos.

**Escalabilidad**
Es importante que los administradores de bases de datos planifiquen el crecimiento y la expansión de sus sistemas de bases de datos; este es otro punto claro de diferenciación entre las bases de datos SQL y NoSQL.

<img src="https://github.com/KatherineAGM/Checkpoint-6-/blob/main/images/basesdatos.png" img width="800px">

## ¿Qué es una API?

Una ```API``` (**Interfaz de Programación de Aplicaciones**) es un conjunto de reglas y protocolos que permiten que diferentes aplicaciones de software se comuniquen e intercambien información entre sí. Imagínala como un intermediario digital que facilita la interacción entre dos sistemas sin que necesiten conocer los detalles internos de cómo funciona el otro.

**¿Cómo funcionan las API?**

Es útil pensar en la comunicación de la API en términos de una solicitud y respuesta entre un cliente y un servidor. La aplicación que envía la solicitud es el cliente y el servidor proporciona la respuesta. La API es el puente que establece la conexión entre ellos.

Una forma sencilla de entender cómo funcionan las API es examinar un ejemplo común: el procesamiento de pagos de terceros. Cuando un usuario compra un producto en un sitio de comercio electrónico, es posible que se le pida que "pague con PayPal" u otro tipo de sistema externo. Esta función depende de las API para realizar la conexión.

- Cuando el comprador hace clic en el botón de pago, se envía una llamada a la API para recuperar la información. Esta es la petición. Esta solicitud se procesa desde una aplicación al servidor web a través del identificador uniforme de recursos (URI) de la API e incluye un verbo de solicitud, una cabecera y, a veces, un cuerpo de solicitud.
 

- Tras recibir una solicitud válida desde la página web del producto, la API llama al programa externo o al servidor web, en este caso, al sistema de pago externo.
 

- El servidor envía una respuesta a la API con la información solicitada.
 

- La API transfiere los datos a la aplicación solicitante inicial, en este caso, el sitio web del producto.

Si bien la transferencia de datos diferida según el servicio web utilizado, las solicitudes y respuestas se realizan a través de una API. No hay visibilidad en la interfaz de usuario, lo que significa que las API intercambian datos dentro del ordenador o la aplicación, y aparecen ante el usuario como una conexión sin fisuras.

**Tipos de API**
Las API se pueden clasificar por casos de uso: API de datos, API de sistemas operativos, API remotas y API web.

 **API web**
Las API web permiten la transferencia de datos y funcionalidades a través de Internet mediante el protocolo HTTP.

Hoy en día, la mayoría de las API son API web. Las API web son un tipo de API remota (lo que significa que la API utiliza protocolos para manipular recursos externos) que exponen los datos y la funcionalidad de una aplicación a través de Internet.

**Los cuatro tipos principales de API web son:**

API abiertas
Las API abiertas son interfaces de programación de aplicaciones de código abierto que se puede acceder con el protocolo HTTP. También conocidas como API públicas, han definido endpoints de API y formatos de solicitud y respuesta.

**API de socios**
Las API de socios conectan a Business Partners estratégicos. Normalmente, los programadores acceden a estas API en modo de autoservicio a través de un portal público para programadores de API . Aún así, deben completar un proceso de incorporación y obtener credenciales de inicio de sesión para acceder a las API de socios.

**API internas**
Las API internas o privadas permanecen ocultas para los usuarios externos. Estas API privadas no están disponibles para usuarios fuera de la empresa. En cambio, las organizaciones los utilizan para mejorar la productividad y la comunicación entre diferentes equipos de desarrollo internos.

**API compuestas**
Las API compuestas combinan múltiples API de datos o servicios. Permiten a los programadores acceder a varios endpoints en una sola llamada. Las API compuestas son útiles en la arquitectura de microservicios, donde la realización de una única tarea puede requerir información de varias fuentes.

#### **Otros tipos de API**
Entre los tipos menos comunes de API se incluyen los siguientes:

- **API de datos (o bases de datos)**, utilizadas para conectar aplicaciones y sistemas de gestión de bases de datos

- **API del sistema operativo (o locales)**, utilizadas para definir cómo utilizan las apps los servicios y recursos del sistema operativo.

- **API remotas**, utilizadas para definir cómo interactúan las aplicaciones en diferentes dispositivos

#### Ventajas de la API
Las API simplifican el diseño y el desarrollo de nuevas aplicaciones y servicios, así como la integración y gestión de las existentes. También ofrecen beneficios significativos a los desarrolladores y a las organizaciones en general.

- **Colaboración mejorada**
La empresa promedio utiliza casi 1200 aplicaciones en la nube, muchas de las cuales están desconectadas. Las API permiten la integración, para que estas plataformas y aplicaciones puedan comunicarse entre sí sin problemas. Mediante esta integración, las empresas pueden automatizar los flujos de trabajo y mejorar la colaboración en el lugar de trabajo. Sin las API, muchas empresas carecerían de conectividad, lo que provocaría silos de información que comprometerían la productividad y el rendimiento.

- **Innovación acelerada**
Las API ofrecen flexibilidad, lo que permite a las empresas establecer conexiones con nuevos business partners y ofrecer nuevos servicios a su mercado existente. Esta flexibilidad también permite a las empresas acceder a nuevos mercados que pueden aumentar los rendimientos e impulsar la transformación digital.

    Por ejemplo, la empresa Stripe comenzó como una API con solo siete líneas de código. Desde entonces, la compañía ha trabajado con muchas de las empresas más grandes del mundo. Stripe se ha diversificado para ofrecer préstamos y tarjetas corporativas, y recientemente ha recibido una valoración de 65 000 millones de USD.

- **Monetización de datos**
Muchas empresas optan por ofrecer API gratuitas, al menos al principio, para poder crear una audiencia de desarrolladores en torno a su marca y forjar relaciones con posibles socios. Si la API da acceso a recursos digitales valiosos, una empresa lo monetiza vendiendo el acceso. Esta práctica se conoce como la economía API.

    Cuando AccuWeather puso en marcha su portal de autoservicio para desarrolladores con el fin de vender una amplia gama de paquetes de API, tardó solo diez meses en atraer a 24 000 desarrolladores y vender 11 000 claves de API. Este movimiento ayudó a construir una comunidad próspera en el proceso.

- **Seguridad del sistema**
Las API separan la aplicación solicitante de la infraestructura del servicio que responde y ofrecen capas de seguridad entre las dos a medida que se comunican. Por ejemplo, las llamadas a la API suelen requerir credenciales de autenticación. Los encabezados HTTP, cookies o cadenas de consulta pueden proporcionar seguridad adicional durante el intercambio de datos. Una pasarela API puede controlar el acceso para minimizar aún más las amenazas a la seguridad.

- **Seguridad y privacidad del usuario**
Las API brindan protección adicional dentro de una red. También pueden proporcionar otra capa de protección para los usuarios personales. Cuando un sitio web solicita la ubicación de un usuario (una API de ubicación proporciona esta información), el usuario puede decidir si permite o rechaza esta solicitud.

Muchos navegadores web y sistemas operativos móviles y de escritorio tienen estructuras de permisos integradas. Cuando una aplicación debe acceder a los archivos a través de una API, los sistemas operativos como iOS, macOS, Windows y Linux utilizan permisos para ese acceso.

#### **Ejemplos comunes de APIs:**

- La API de Twitter que permite a otras aplicaciones acceder a tweets y publicar contenido.
- La API de Google Maps que permite integrar mapas y funcionalidades de ubicación en otras aplicaciones.
- Las APIs de pago como PayPal o Stripe que permiten procesar transacciones en línea.
- Las APIs de servicios meteorológicos que proporcionan datos del clima a diferentes aplicaciones.

## ¿Qué es Postman? 

**Postman** es una plataforma gratuita si trabajas solo o de pago si quieres trabajar de manera colaborativa con tu equipo. Esta plataforma posibilita y facilita la creación y el uso de APIs. Se puede usar, por ejemplo, para obtener información sobre las respuestas HTTP, en diferentes métodos, que realicemos a APIs de diferentes temáticas.

A su vez, postsman posee un **repositorio colaborativo** donde podrás integrar todos los artefactos, herramientas y programas para el uso de las APIs o las llamadas hacia las API’s.

Por otro lado, esta plataforma tiene una serie de herramientas que te ayudan a acelerar el círculo de vida de cualquier API desde cualquiera de sus funcionalidades o componentes.

es una popular plataforma de colaboración para el desarrollo de APIs (Interfaces de Programación de Aplicaciones). Principalmente, se utiliza como un cliente HTTP gráfico que simplifica la tarea de probar, desarrollar y documentar APIs.

Asi se ve la **interfaz de usurio de poastman:** 

<img src="https://github.com/KatherineAGM/Checkpoint-6-/blob/main/images/postman.png" img width="800px">

**Cómo utilizar Postman**
En primer lugar, para utilizar la versión gratuita de Postman, tendrás que crear una cuenta dentro de la plataforma. Puedes crearla desde tu Gmail, SSO o el email que desees. La cuenta gratuita te permite invitar a máximo dos personas para que puedan trabajar en el mismo programa.

Aunque es posible trabajar con postment desde el navegador, te recomendamos descargarla en tu ordenador. Puedes instalarlo de manera muy sencilla desde su página oficial; brinda los permisos según tu sistema operativo y disfruta de la aplicación.

Una vez instalada, puedes empezar a prácticar con el envío de tu primera petición.

Para hacerlo, solo tendrás que crear un nuevo archivo, pegar el link de la API u otra URL para la request a la que vamos a llamar y **elegir el verbo con el que deseamos realizar la llamada**(GET, POST, PUT, PATCH o DELETE, entre otros). Después, debes pulsar el botón send y, así, ya tienes la respuesta a tu petición.

#### **Algunas de las funcionalidades de Postman:**

- **Enviar Solicitudes HTTP**: Permite construir y enviar diferentes tipos de solicitudes HTTP (GET, POST, PUT, DELETE, etc.) a endpoints de APIs. Puedes configurar los encabezados, el cuerpo de la solicitud (en formatos como JSON, XML, form-data, etc.), los parámetros de consulta y la autenticación.
- **Inspeccionar Respuestas**: Muestra las respuestas del servidor de manera organizada, incluyendo el código de estado HTTP, los encabezados, el cuerpo de la respuesta (formateado para facilitar la lectura) y el tiempo de respuesta.
- **Crear y Organizar Colecciones**: Permite agrupar solicitudes relacionadas en colecciones, lo que facilita la organización y la ejecución secuencial de pruebas. Puedes compartir estas colecciones con otros desarrolladores.
- **Definir Entornos**: Permite crear diferentes entornos (por ejemplo, desarrollo, pruebas, producción) y almacenar variables específicas para cada uno (como URLs base o claves de API). Esto facilita el cambio entre diferentes configuraciones sin modificar las solicitudes.
- **Escribir Pruebas**: Ofrece la posibilidad de escribir scripts de prueba en JavaScript para validar las respuestas de la API. Puedes verificar códigos de estado, valores específicos en el cuerpo de la respuesta, encabezados, etc. Estas pruebas se pueden ejecutar automáticamente como parte de una colección.
- **Generar Documentación**: Puede generar documentación de API a partir de las colecciones y los ejemplos de solicitudes y respuestas, lo que facilita que otros desarrolladores entiendan cómo usar tu API.
- **Colaboración**: Permite trabajar en equipo en colecciones, entornos y documentación, facilitando la colaboración en proyectos de desarrollo de APIs.
- **Mock Servers**: Ofrece la capacidad de crear servidores simulados (mocks) que emulan el comportamiento de una API real. Esto es útil para probar tu aplicación cliente antes de que la API real esté completamente desarrollada.
- **Automatización**: Se integra con herramientas de integración continua/entrega continua (CI/CD) para automatizar la ejecución de pruebas de API.

#### Ventajas de Postman respecto a otras herramientas
El uso de Postman ofrece múltiples ventajas que lo destacan frente a otras herramientas de desarrollo y prueba de APIs:

1. **Interfaz gráfica intuitiva:** Postman cuenta con una interfaz de usuario que es a la vez sencilla y poderosa, lo que facilita su uso incluso para desarrolladores novatos. Además, es personalizable, lo que permite adaptarla a las necesidades específicas de cada proyecto.
2. **Compatibilidad con diversas tecnologías:** Postman es compatible con una amplia gama de tecnologías y protocolos web, incluyendo HTTP, HTTPS, REST, SOAP y GraphQL. Esto permite a los desarrolladores trabajar con diferentes tipos de APIs sin complicaciones.
3. **Funcionalidades completas:** Postman ofrece una amplia gama de funcionalidades que cubren todas las fases del ciclo de vida de desarrollo de APIs, desde el diseño y prueba hasta la documentación y la colaboración. Esto lo convierte en una solución integral para desarrolladores.
4. **Colaboración mejorada:** Postman fomenta la colaboración entre los miembros del equipo de desarrollo al permitir el intercambio de colecciones de solicitudes y la documentación de APIs. Esto es especialmente útil en proyectos donde varios desarrolladores trabajan en diferentes partes de la misma API.
5. **Comunidad activa:** Postman cuenta con una comunidad de usuarios en constante crecimiento que aporta recursos valiosos, como tutoriales, foros y grupos de discusión. Esto facilita la resolución de problemas y el aprendizaje continuo.
6. **Integración con otras herramientas:** Postman se integra perfectamente con otras herramientas populares en el desarrollo de software, como sistemas de control de versiones (por ejemplo, GitHub), servicios de generación de documentación (como Swagger) y herramientas de automatización de pruebas (como Jenkins).
7. **Scripts personalizados:** Los usuarios de Postman pueden agregar scripts personalizados utilizando JavaScript para automatizar tareas repetitivas, configurar pruebas avanzadas o agregar validaciones específicas a las respuestas de la API. Esto añade un nivel de flexibilidad que otras herramientas pueden no ofrecer.


## ¿Qué es el polimorfismo?
Es un concepto fundamental y muy elegante en la programación orientada a objetos (POO). Literalmente significa "muchas formas". En el contexto de la programación, se refiere a la capacidad de que objetos de diferentes clases respondan al mismo método (o interfaz) de manera diferente.

El ```polimorfismo``` es uno de los pilares básicos en la programación orientada a objetos, por lo que para entenderlo es importante tener las bases de la POO y la herencia bien asentadas.

El término ```polimorfismo``` tiene origen en las palabras poly (muchos) y morfo (formas), y aplicado a la programación hace referencia a que los objetos pueden tomar diferentes formas. ¿Pero qué significa esto?

Pues bien, significa que objetos de diferentes clases pueden ser accedidos utilizando el mismo interfaz, mostrando un comportamiento distinto (tomando diferentes formas) según cómo sean accedidos.

En lenguajes de programación como **Python**, que tiene tipado dinámico, el polimorfismo va muy relacionado con el duck typing.

Sin embargo, para entender bien este concepto, es conveniente explicarlo desde el punto de vista de un lenguaje de programación con tipado estático como Java. 

visto desde el punto de vista de Python es complicado de explicar sin hablar del duck typing, por lo que te recomendamos la lectura.

Al ser un lenguaje con tipado dinámico y permitir duck typing, en Python no es necesario que los objetos compartan un interfaz, simplemente basta con que tengan los métodos que se quieren llamar.

Supongamos que tenemos un clase ```Animal``` con un método ```hablar()```

```Python 
class Animal:
    def hablar(self):
        pass
```
Por otro lado tenemos otras dos clases, ```Perro```,```Gato``` que heredan de la anterior. Además, implementan el método ```hablar()``` de una forma distinta.
```python 
class Perro(Animal):
    def hablar(self):
        print("Guau!")

class Gato(Animal):
    def hablar(self):
        print("Miau!")
```
A continuación creamos un objeto de cada clase y llamamos al método ```hablar()```. Podemos observar que cada animal se comporta de manera distinta al usar ```hablar()```.

```python
for animal in Perro(), Gato():
    animal.hablar()

# Guau!
# Miau!
```
En el caso anterior, la variable ```animal``` ha ido “tomando las formas” de ```Perro```y ```Gato```. Sin embargo, nótese que al tener tipado dinámico este ejemplo hubiera funcionado igual sin que existiera herencia entre ```Perro``` y ```Gato```.

**Pongamos otro ejemplo** por si acaso no ha quedado claro con lo visto hasta el momento, volviendo de nuevo a la clase Vehiculo. Además nos centramos en la utilidad del polimorfismo y sus posibilidades para reducir el mantenimiento de los programas informáticos, que es lo que realmente me gustaría que se entienda.

Tenemos la clase ```Parking```. Dentro de ésta tenemos un método ```estacionar()```. Puede que en un parking tenga que estacionar coches, motos o autobuses. Sin polimorfismo tendría que crear un método que permitiese estacionar objetos de la clase "Coche", otro método que acepte objetos de la clase "Moto" para estacionarlos, etc. Pero todos estaremos de acuerdo que estacionar un coche, una moto o un bus es bastante similar: "entrar en el parking, recoger el ticket de entrara, buscar una plaza, situar el vehículo dentro de esa plaza...".

Lo ideal sería que nuestro método me permita permita recibir todo tipo de vehículos para estacionarlos, primero por reutilización del código, ya que es muy parecido estacionar uno u otro vehículo, pero además porque así si mañana el mercado trae otro tipo de vehículos, como una van, todoterreno hibrido, o una nave espacial, mi software sea capaz de aceptarlos sin tener que modificar la clase ```Parking```.

Gracias al ```polimorfismo```, cuando declaro la función ```estacionar()``` puedo decir que recibe como parámetro un objeto de la clase ```"Vehiculo"``` y el compilador me aceptará no solamente vehículos genéricos, sino todos aquellos objetos que hayamos creado que hereden de la clase Vehículo, osea, coches, motos, buses, etc. Esa relajación del sistema de tipos para aceptar una gama de objetos diferente es lo que llamamos polimorfismo.

<img src="https://github.com/KatherineAGM/Checkpoint-6-/blob/main/images/poliformismo.gif" img width="600px">

## ¿Qué es un método dunder?

Es un término coloquial y bastante común en la comunidad de Python para referirse a los **métodos especiales** que tienen nombres que comienzan y terminan con **doble guion bajo** (double underscore). Por eso el nombre "dunder" (de "double underscore").

Estos métodos también se conocen como **métodos mágicos** o **métodos especiales**. Tienen una importancia crucial en Python porque implementan funcionalidades fundamentales del lenguaje y permiten que tus objetos se comporten de manera consistente con los tipos built-in de Python.

<img src="https://github.com/KatherineAGM/Checkpoint-6-/blob/main/images/Dunder%20.png" img width="700px">

#### Características principales de los métodos dunder:

- **Nombres especiales:** Siempre empiezan y terminan con __ (doble guion bajo).
- **Implementan comportamiento especial**: Están asociados a operaciones o funcionalidades específicas del lenguaje. No los llamas directamente de forma habitual. En su lugar, Python los invoca automáticamente cuando ocurre cierta acción.
- **Sobrescritura**: Puedes definir (o sobrescribir) estos métodos en tus propias clases para personalizar el comportamiento de tus objetos en diversas situaciones.
#### Ejemplos comunes de métodos dunder y su propósito:

- ```__init__(self, ...)```: El constructor de la clase. Se llama automáticamente cuando se crea una nueva instancia de la clase. Inicializa los atributos del objeto.
```python 
  class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
persona1 = Persona("Alice", 30)
print(persona1.nombre)  # Salida: Alice
print(persona1.edad)    # Salida: 30
```

- ```__str__(self)```: Define cómo se debe representar un objeto como una cadena de texto "informal" o legible para humanos (por ejemplo, cuando usas la función ```print()``` o ```str()```).
```python
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
    
    def __str__(self):
        return f"Persona: {self.nombre}, {self.edad} años"
    
    def __repr__(self):
        return f"Persona('{self.nombre}', {self.edad})"

persona1 = Persona("Alice", 30)
print(str(persona1))  # Salida: Persona: Alice, 30 años
print(repr(persona1)) # Salida: Persona('Alice', 30)
```

- ```__repr__(self)```: Define la representación "oficial" de un objeto como una cadena. Idealmente, esta cadena debería ser una expresión Python válida que podría usarse para recrear el objeto (útil para debugging y desarrollo).
- ```__len__(self)```: Implementa la funcionalidad de la función built-in ```len()```. Define la "longitud" de un objeto (si tiene sentido para esa clase).
```python
class Grupo:
    def __init__(self, miembros):
        self.miembros = miembros
    
    def __len__(self):
        return len(self.miembros)

grupo = Grupo(["Alice", "Bob", "Charlie"])
print(len(grupo))  # Salida: 3
```

- ```__getitem__(self, key)```: Permite acceder a elementos de un objeto utilizando la sintaxis de indexación (por ejemplo, ```mi_objeto[clave]```).
- ```__setitem__(self, key, value)```: Permite asignar valores a elementos de un objeto utilizando la sintaxis de indexación (por ejemplo, ```mi_objeto[clave] = valor```).
- ```__delitem__(self, key)```: Permite eliminar elementos de un objeto utilizando la sintaxis del ```mi_objeto[clave]```.
```python
class MiLista:
    def __init__(self):
        self.data = []
    
    def __getitem__(self, index):
        return self.data[index]
    
    def __setitem__(self, index, value):
        self.data[index] = value
    
    def __delitem__(self, index):
        del self.data[index]

mi_lista = MiLista()
mi_lista.data = [1, 2, 3, 4, 5]
print(mi_lista[2])   # Salida: 3
mi_lista[2] = 30
print(mi_lista[2])   # Salida: 30
del mi_lista[2]
print(mi_lista.data) # Salida: [1, 2, 4, 5]
```


- **Métodos de comparación:**
    - ```__eq__(self, other)```: Implementa la igualdad (```==```).
    - ```__ne__(self, other)```: Implementa la desigualdad (```!=```).
    - ```__lt__(self, other)```: Implementa "menor que" (```<```).
    - ```__le__(self, other)```: Implementa "menor o igual que" (```<=```).
    - ```__gt__(self, other)```: Implementa "mayor que" (```>```).
    - ```__ge__(self, other)```: Implementa "mayor o igual que" (```>=```).
- **Métodos aritméticos:**
    - ```__add__(self, other)```: Implementa la adición (+).
    - ```__sub__(self, other)```: Implementa la sustracción (-).
    - ```__mul__(self, other)```: Implementa la multiplicación (*).
    - ```__truediv__(self, other)```: Implementa la división (/).
    Y muchos otros (```__floordiv__```, ```__mod__```,```__pow__```, etc.).
```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def __add__(self, otro):
        return Vector(self.x + otro.x, self.y + otro.y)
    
    def __repr__(self):
        return f"Vector({self.x}, {self.y})"

v1 = Vector(2, 3)
v2 = Vector(4, 5)
v3 = v1 + v2
print(v3)  # Salida: Vector(6, 8)
```

- **Métodos relacionados con el contexto (```with ```statement):**
    - ```__enter__(self)```: Se llama al entrar en un bloque with.
    - ```__exit__(self, exc_type, exc_val, exc_tb)```: Se llama al salir de un bloque with.
  
**Importancia:**

Los métodos dunder son esenciales porque permiten que tus clases se integren de manera fluida con el lenguaje Python. Al implementar estos métodos, puedes definir cómo tus objetos se comportan en operaciones comunes como la impresión, la comparación, la indexación, las operaciones aritméticas y el manejo de contextos. Esto hace que tu código sea más intuitivo y consistente con la forma en que se utilizan los tipos built-in de Python.

## ¿Qué es un decorador de python?

Los decoradores son funciones que **modifican el comportamiento de otras funciones**, ayudan a acortar nuestro código y hacen que sea más Pythonic. Si alguna vez has visto ```@```, estás ante un decorador o decorator, bien sea uno que Python ofrece por defecto o uno que puede haber sido creado ex profeso.

Veamos un ejemplo muy sencillo. Tenemos una función ```suma()``` que vamos a decorar usando ```mi_decorador()```. Para ello, antes de la declaración de la función suma, hacemos uso de ```@mi_decorador```.
```python
def mi_decorador(funcion):
    def nueva_funcion(a, b):
        print("Se va a llamar")
        c = funcion(a, b)
        print("Se ha llamado")
        return c
    return nueva_funcion

@mi_decorador
def suma(a, b):
    print("Entra en funcion suma")
    return a + b

suma(5,8)

# Se va a llamar
# Entra en funcion suma
# Se ha llamado
```
Lo que realiza ```mi_decorador()``` es definir una nueva función que encapsula o envuelve la función que se pasa como entrada. Concretamente lo que hace es hace uso de dos ```print()```, uno antes y otro después de la llamada la función.

Por lo tanto, cualquier función que use ```@mi_decorador``` tendrá dos print, uno y al principio y otro al final, dando igual lo que realmente haga la función.

Veamos otro ejemplo usando el decorador sobre otra función.
```python
@mi_decorador
def resta(a ,b):
    print("Entra en funcion resta")
    return a - b

resta(5, 3)

# Se va a llamar
# Entra en funcion resta
# Se ha llamado
```
#### **Definiendo decoradores**
Antes de nada hay que entender que todo en Python es un objeto, incluso una función. De hecho se puede asignar una función a una variable. Nótese la diferencia entre:

- ```di_hola()``` llama a la función.
- ```di_hola``` hace referencia a la función, no la llama.
```python
def di_hola():
    print("Hola")
    
f1 = di_hola() # Llama a la función
f2 = di_hola   # Asigna a f2 la función

print(f1)      # None, di_hola no devuelve nada
print(f2)      # <function di_hola at 0x1077bf158>

#f1()          # Error! No es válido
f2()           # Llama a f2, que es di_hola()

del f2         # Borra el objeto que es la función 
#f2()          # Error! Ya no existe

di_hola()      # Ok. Sigue existiendo
```
Entendido esto, demos un paso más. En Python se pueden definir funciones dentro de otras funciones. La función ```operaciones``` define ```suma()``` y ```resta()```, y dependiendo del parámetro de entrada ```op```, se devolverá una u otra.
```python
def operaciones(op):
    def suma(a, b):
        return a + b
    def resta(a, b):
        return a - b
    
    if op == "suma":
        return suma
    elif op == "resta":
        return resta
    
funcion_suma = operaciones("suma")
print(funcion_suma(5, 7)) # 12

funcion_suma = operaciones("resta")
print(funcion_suma(5, 7)) # -2
```
Si llamamos a la función devuelta con dos operandos, se realizará una operación distinta en función de si se uso suma o resta.

Ahora ya podemos dar la última vuelta de tuerca y **escribir nuestro propio decorador** sin hacer uso de ```@```. Por un lado tenemos el ```decorador```, que recibe como entrada una función y devuelve otra función decorada. Por el otro la función ```suma()``` que queremos decorar.
```python
def decorador(func):
    def envoltorio_func(a, b):
        print("Decorador antes de llamar a la función")
        c = func(a, b)
        print("Decorador después de llamar a la función")
        return c
    return envoltorio_func

def suma(a, b):
    print("Dentro de suma")
    return a + b

# Nueva funcion decorada
funcion_decorada = decorador(suma)

funcion_decorada(5, 8)
```
Entonces, haciendo uso de ```decorador``` y pasando como entrada ```suma```, recibimos una nueva función decorada con una funcionalidad nueva, lista para ser usada. Sería el equivalente al uso de ```@```.

#### **Decoradores con parámetros**
Tal vez quieras que tu decorador tenga algún parámetro de entrada para modificar su comportamiento. Se puede hacer envolviendo una vez más la función como se muestra a continuación.
```python
def mi_decorador(arg):
    def decorador_real(funcion):
        def nueva_funcion(a, b):
            print(arg)
            c = funcion(a, b)
            print(arg)
            return c
        return nueva_funcion
    return decorador_real

@mi_decorador("Imprimer esto antes y después")
def suma(a, b):
    print("Entra en funcion suma")
    return a + b

suma(5,8)
# Imprimer esto antes y después
# Entra en funcion suma
# Imprimer esto antes y después
```

Es importante recalcar que los ejemplos mostrados hasta ahora son didácticos, y no tienen mucha utilidad práctica. Veamos un ejemplo más práctico.

#### Ejemplo: logger
Una de las utilidades más usadas de los decoradores son los **logger**. Su uso nos permite escribir en un fichero los resultados de ciertas operaciones, que funciones han sido llamadas, o cualquier información que en un futuro resulte útil para ver que ha pasado.

En el siguiente ejemplo tenemos un uso más completo del decorador ```log()``` que escribe en un fichero los resultados de las funciones que han sido llamadas.
```python
def log(fichero_log):
    def decorador_log(func):
        def decorador_funcion(*args, **kwargs):
            with open(fichero_log, 'a') as opened_file:
                output = func(*args, **kwargs)
                opened_file.write(f"{output}\n")
        return decorador_funcion
    return decorador_log

@log('ficherosalida.log')
def suma(a, b):
    return a + b

@log('ficherosalida.log')
def resta(a, b):
    return a - b

@log('ficherosalida.log')
def multiplicadivide(a, b, c):
    return a*b/c

suma(10, 30)
resta(7, 23)
multiplicadivide(5, 10, 2)
```

Nótese que el decorador puede ser usado sobre funciones que tienen diferente número de parámetros de entrada, y su funcionalidad será siempre la misma. Escribir en el fichero pasado como parámetro los resultados de las operaciones.

#### Ejemplo: Uso autorizado
Otro caso de uso muy importante y ampliamente usado en Flask, que es un framework de desarrollo web, es el uso de decoradores para asegurarse de que una función es llamada cuando el usuario se ha autenticado.

Realizando alguna simplificación, podríamos tener un decorador que requiriera que una variable ```autenticado``` fuera ```True```. La función se ejecutará solo si dicha variable global es verdadera, y se dará un error de lo contrario.
```python
autenticado = True

def requiere_autenticación(f):
    def funcion_decorada(*args, **kwargs):
        if not autenticado:
            print("Error. El usuario no se ha autenticado")
        else:
            return f(*args, **kwargs)
    return funcion_decorada

@requiere_autenticación
def di_hola():
    print("Hola")
    
di_hola()
```
Prueba a cambiar la variable de ```True``` a ```False```.
