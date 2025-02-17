# Guía completa para aprender Java y escribir complementos de RuneLite



---


¡Bienvenido a la Guía completa para aprender Java y escribir complementos de RuneLite! Esta guía está diseñada para brindarte una base sólida en programación Java y ayudarte a comenzar a desarrollar complementos para el cliente RuneLite. Ya seas principiante o tengas algo de experiencia en programación, esta guía te guiará por los aspectos esenciales y te brindará ejemplos y recursos para mejorar tu aprendizaje.
<br></br>

<a href="https://discord.gg/ehvSsj24cn">
  <img src="https://cdn.discordapp.com/icons/1096562449009872939/5aaf8eb1a5562cbc8eabee2967887a89.webp?size=100" alt="Discord Logo" width="12%" height="12%">
</a>

[Únete al servidor de Discord de Myre](https://discord.gg/ehvSsj24cn)

## Tabla de contenido

- [Sección 1: Fundamentos de Java](#section-1-java-fundamentals)
  - [1.1 Entendiendo Java](#11-understanding-java)
  - [1.2 Configuración del entorno de desarrollo](#12-setting-up-the-development-environment)
  - [1.3 Fundamentos de la sintaxis de Java](#13-basics-of-java-syntax)
  - [1.4 Programación Orientada a Objetos (POO)](#14-object-oriented-programming-oop)
  - [1.5 Manejo de excepciones](#15-exception-handling)
  - [1.6 Subprocesos múltiples](#16-multi-threading)

- [Sección 2: Desarrollo del complemento RuneLite](#section-2-RuneLite-plugin-development)
  - [2.1 Introducción a RuneLite](#21-introduction-to-RuneLite)
  - [2.2 Configuración del entorno de desarrollo](#22-setting-up-the-development-environment)
  - [2.3 Creando tu primer plugins RuneLite](#23-creating-your-first-RuneLite-plugin)
  - [2.4 Interacción con el cliente del juego RuneScape](#24-interacting-with-the-runescape-game-client)
  - [2.5 Funciones avanzadas del complemento](#25-advanced-plugin-features)

- [Sección 3: Información sobre plugins externos](#section-3-external-plugin-informative)
  - [3.1 Advertencia sobre complementos externos](#31-external-plugin-warning)
  - [3.2 API del plugin EthanVann](#32-ethanvann-plugin-api)
  - [3.3 Cargador de complementos Kotori](#33-kotori-plugin-loader)
  - [3.4 Reflexión sobre el paquete de juego](#34-game-pack-reflection)
  - [3.5 Actualizaciones de revisión](#35-revision-updates)
- [Créditos](#credits)
- [HACER](#todo)
- [Recursos adicionales](#additional-resources)
- [Información de contacto](#contact-info)

---

## Sección 1: Fundamentos de Java

### 1.1 Entendiendo Java

Java es un lenguaje de programación muy utilizado, conocido por su simplicidad, portabilidad y versatilidad. En esta sección, aprenderá los conceptos básicos de Java, incluidas sus características, su historia y sus ventajas como lenguaje.

#### Características de Java

Java es un lenguaje de programación de uso general que se utiliza para desarrollar una amplia gama de aplicaciones, incluidas aplicaciones de escritorio, móviles y web. Es un lenguaje orientado a objetos y basado en clases que está diseñado para ser simple, portátil y seguro. Estas son algunas de las características clave de Java:

- **Sencillo**: Java está diseñado para ser simple y fácil de aprender. Tiene una sintaxis concisa y un pequeño conjunto de palabras clave, lo que facilita la lectura y escritura de código en Java.
- **Portátil**: Java está diseñado para ser portable entre distintas plataformas. Se compila en código de bytes, que se puede ejecutar en cualquier plataforma que tenga una máquina virtual Java (JVM).
- **Seguro**: Java está diseñado para ser seguro. Tiene funciones de seguridad integradas, como administración automática de memoria y seguridad de tipos.
- **Orientado a objetos**: Java es un lenguaje orientado a objetos. Respalda los cuatro pilares de la programación orientada a objetos: encapsulación, abstracción, herencia y polimorfismo.
- **Multiproceso**: Java está diseñado para ser multiproceso. Admite subprocesos múltiples, lo que permite que varios subprocesos se ejecuten simultáneamente.

#### Historia de Java

Java fue desarrollado originalmente por James Gosling en Sun Microsystems en 1991. Fue diseñado para ser un lenguaje de programación simple, portátil y seguro para sistemas integrados. La primera versión de Java se lanzó en 1995. Desde entonces, Java se ha convertido en uno de los lenguajes de programación más populares del mundo.

---

### 1.2 Configuración del entorno de desarrollo

Para comenzar a programar en Java, debe configurar su entorno de desarrollo. En esta sección, lo guiaremos a través del proceso de instalación del JDK (Java Development Kit) y la configuración de su IDE (Integrated Development Environment) para una experiencia de desarrollo fluida.

#### Instalación de JDK 11 desde Adoptium

Para instalar JDK 11 desde Adoptium, siga estos pasos:

1. Visita el [Sitio web de Adoptium](https://adoptium.net/) y navegar a la página de descargas.
2. Seleccione la distribución JDK 11 adecuada para su sistema operativo.
3. Descargue el paquete de instalación y ejecútelo.
4. Siga las instrucciones del asistente de instalación para completar la instalación del JDK.

#### Configuración de Intellij IDEA Community Edition

Intellij IDEA es un IDE popular para el desarrollo de Java. En esta guía, utilizaremos Intellij IDEA Community Edition. Para configurar Intellij IDEA para el desarrollo de Java, siga estos pasos:

1. Descargar e instalar [Edición comunitaria de Intellij IDEA](https://www.jetbrains.com/idea/download/).
2. Inicie Intellij IDEA una vez completada la instalación.

#### Configuración de un nuevo proyecto en Intellij IDEA

Una vez que haya instalado Intellij IDEA, podrá configurar un nuevo proyecto Java. A continuación, le indicamos cómo hacerlo:

1. Abra Intellij IDEA y haga clic en "Create New Project" o ir a "File" > "New" > "Project".
2. Seleccione "Java" en el panel izquierdo y asegúrese de que JDK 11 esté seleccionado como SDK del proyecto.
3. Seleccione la plantilla de proyecto deseada y haga clic en "Next".
4. Ingrese el nombre del proyecto y seleccione la ubicación del proyecto en su computadora.
5. Haga clic en "Finish" para crear el proyecto.

#### Comprender build.gradle tanto en Kotlin (KTS) como en Groovy

En los proyectos Java, los archivos build.gradle se utilizan habitualmente para la configuración del proyecto y la gestión de dependencias. Hay dos opciones de sintaxis para escribir archivos build.gradle: Kotlin (KTS) y Groovy.

##### Sintaxis de Kotlin (KTS)

El DSL de Kotlin (KTS) proporciona una sintaxis más concisa y segura para los tipos de archivos build.gradle. Se recomienda para proyectos nuevos. A continuación, se muestra un ejemplo de un archivo build.gradle.kts:

```kotlin
// build.gradle.kts (Kotlin DSL)
plugins {
  kotlin("jvm") version "1.5.20"
}

group = "com.example"
version = "1.0-SNAPSHOT"

repositories {
  mavenCentral()
}

dependencies {
  implementation(kotlin("stdlib-jdk8"))
  testImplementation(kotlin("test"))
}
```

##### Sintaxis Groovy

La sintaxis Groovy es la sintaxis tradicional para los archivos build.gradle y todavía se utiliza ampliamente. A continuación, se muestra un ejemplo equivalente de un archivo build.gradle escrito en Groovy:

```groovy
// build.gradle (Groovy DSL)
plugins {
  id 'java'
}

group 'com.example'
version '1.0-SNAPSHOT'

repositories {
  mavenCentral()
}

dependencies {
  implementation 'org.jetbrains.kotlin:kotlin-stdlib-jdk8'
  testImplementation 'org.jetbrains.kotlin:kotlin-test'
}
```

Elija la sintaxis con la que se sienta más cómodo o que se alinee con la estructura del proyecto existente.

---

### 1.3 Fundamentos de la sintaxis de Java

En esta sección, aprenderá los componentes básicos de los programas Java. Trataremos temas como variables, tipos de datos, operadores, sentencias condicionales y construcciones de bucles. Al comprender estos conceptos, podrá escribir programas Java básicos y manipular datos de manera eficaz.

#### Variables

En Java, las variables se utilizan para almacenar datos a los que se puede acceder y manipular a lo largo del programa. Tienen un tipo de datos específico y un nombre. A continuación, se muestra un ejemplo de declaración e inicialización de una variable:

```java
int age = 25;
```

Tipos de datos
Java tiene tipos de datos integrados para representar distintos tipos de valores. Algunos tipos de datos comunes son:

`int`: para valores enteros
`double`: para valores de punto flotante
`boolean`: para valores booleanos (true o false)
`String`: para representar datos textuales
`float`: para valores de punto flotante (menos precisos que el doble)
`char`: para caracteres individuales
`long`: para valores enteros (rango mayor que int)
`byte`: para valores enteros (rango más pequeño que int)
`short`: para valores enteros (rango más pequeño que int)

A continuación se muestra un ejemplo de uso de diferentes tipos de datos:

```java
int age = 25;
double height = 1.75;
boolean isStudent = true;
String name = "Juan Pérez";
```

#### Operadores
Java ofrece varios operadores para realizar operaciones con variables y valores. Algunos operadores comunes son:

Operadores aritméticos: + (suma), - (resta), * (multiplicación), / (división), % (módulo)
Operadores de comparación: == (igualdad), != (desigualdad), < (menor que), > (mayor que), <= (menor o igual que), >= (mayor o igual que)
Operadores lógicos: && (logical AND), || (logical OR), ! (logical NOT)
Operadores de asignación: =, +=, -=, *=, /=, %= (asignación compuesta)

```java
int a = 5;
int b = 10;
int sum = a + b; // sum = 15

boolean isTrue = (a > b) && (a != 0); // isTrue = false

int counter = 0;
counter += 1; // counter = 1        
```

#### Declaraciones condicionales
Las sentencias condicionales permiten que el programa tome decisiones y ejecute distintos bloques de código en función de determinadas condiciones. La sentencia if es una sentencia condicional de uso común. A continuación, se muestra un ejemplo:

```java
int age = 18;

        if (age >= 18) {
        System.out.println("Eres un adulto.");
        } else {
        System.out.println("Eres menor de edad.");
        }
```

#### Construcciones de bucle
Las construcciones de bucle permiten repetir un bloque de código varias veces. El bucle for se utiliza habitualmente cuando se conoce de antemano la cantidad de iteraciones. A continuación, se muestra un ejemplo:

```java
for (int i = 0; i < 5; i++) {
        System.out.println("Iteration " + i);
        }
```


---

### 1.4 Programación Orientada a Objetos (POO)

Java es un lenguaje de programación orientado a objetos (OOP), lo que significa que enfatiza el uso de clases y objetos para estructurar programas. En esta sección, explorará los conceptos clave de OOP, incluidas las clases, los objetos, la herencia, el polimorfismo y la encapsulación. Aprenderá a crear y usar clases, definir métodos y aplicar modificadores de acceso para controlar la visibilidad de los miembros de la clase.

#### Clases y objetos

En Java, una clase es un modelo o plantilla que define las propiedades (atributos) y los comportamientos (métodos) de los objetos. Un objeto es una instancia de una clase. A continuación, se muestra un ejemplo de una clase simple y su uso:

```java
public class Person {
  // Atributos
  private String name;
  private int age;

  // Constructor
  public Person(String name, int age) {
    this.name = name;
    this.age = age;
  }

  // Método
  public void sayHello() {
    System.out.println("Hola, mi nombre es " + name + " Y yo soy " + age + " años.");
  }
}

  // Uso
  Person person = new Person("Juan Pérez", 25);
person.sayHello();
```

#### Métodos y parámetros

Los métodos son los comportamientos de una clase. Se utilizan para realizar acciones o cálculos específicos. Un método puede tener parámetros, que son entradas para el método. A continuación, se muestra un ejemplo:

```java
public class Calculator {
  public int add(int a, int b) {
    return a + b;
  }

  public double divide(double numerator, double denominator) {
    if (denominator != 0) {
      return numerator / denominator;
    } else {
      throw new IllegalArgumentException("No se puede dividir por cero.");
    }
  }
}

  // Uso
  Calculator calculator = new Calculator();
  int sum = calculator.add(5, 3);
  double result = calculator.divide(10.0, 2.0);

```

#### Modificadores de acceso

Los modificadores de acceso controlan la visibilidad y accesibilidad de los miembros de la clase (variables, métodos, constructores) desde otras partes del programa. Java ofrece cuatro modificadores de acceso:

- `public`: accesible desde cualquier lugar
- `private`: accesible solo dentro de la misma clase
- `protected`: accesible dentro de la misma clase y subclases
- default (no explicit modifier): accesible dentro del mismo paquete

#### Herencia

La herencia es un mecanismo de programación orientada a objetos que permite que una clase herede las propiedades y los métodos de otra clase. La clase de la que se hereda se denomina superclase o clase padre, y la clase que hereda se denomina subclase o clase hija. A continuación, se muestra un ejemplo:

```java
public class Vehicle {
  protected String brand;

  public Vehicle(String brand) {
    this.brand = brand;
  }

  public void start() {
    System.out.println("Starting the " + brand + " vehicle.");
  }
}

public class Car extends Vehicle {
  private int numberOfDoors;

  public Car(String brand, int numberOfDoors) {
    super(brand);
    this.numberOfDoors = numberOfDoors;
  }

  public void drive() {
    System.out.println("Driving the " + brand + " car with " + numberOfDoors + " doors.");
  }
}

  // Uso
  Car car = new Car("Toyota", 4);
car.start();
        car.drive();

```

#### Polimorfismo

El polimorfismo es la capacidad de los objetos de diferentes clases de ser tratados como objetos de una superclase común. Permite escribir código que pueda funcionar con objetos de diferentes tipos, siempre que estén relacionados a través de la herencia. A continuación, se muestra un ejemplo:

```java
public class Shape {
  public void draw() {
    System.out.println("Dibujar una forma.");
  }
}

public class Circle extends Shape {
  @Override
  public void draw() {
    System.out.println("Dibujar un círculo.");
  }
}

public class Square extends Shape {
  @Override
  public void draw() {
    System.out.println("Dibujar un cuadrado.");
  }
}

  // Uso
  Shape shape1 = new Circle();
  Shape shape2 = new Square();
shape1.draw(); // Salida: Dibujar un círculo.
        shape2.draw(); // Salida: Dibujar un cuadrado.

```

#### Encapsulación

La encapsulación es el principio de agrupar datos (atributos) y métodos (comportamientos) dentro de una clase y controlar el acceso a ellos. Ayuda a mantener la integridad y la seguridad de los datos. A continuación, se muestra un ejemplo:

```java
public class BankAccount {
  private double balance;

  public BankAccount(double initialBalance) {
    this.balance = initialBalance;
  }

  public double getBalance() {
    return balance;
  }

  public void deposit(double amount) {
    balance += amount;
  }

  public void withdraw(double amount) {
    if (amount <= balance) {
      balance -= amount;
    } else {
      System.out.println("Insufficient funds.");
    }
  }
}

  // USo
  BankAccount account = new BankAccount(1000.0);
  double currentBalance = account.getBalance(); // 1000.0
account.deposit(500.0);
        account.withdraw(200.0);
        double updatedBalance = account.getBalance(); // 1300.0

```

---

### 1.5 Manejo de excepciones

Los errores y las excepciones son comunes en el desarrollo de software. Java proporciona un mecanismo de manejo de excepciones sólido para lidiar con situaciones inesperadas. En esta sección, aprenderá a manejar excepciones y errores en tiempo de ejecución mediante bloques try-catch, y también descubrirá cómo crear excepciones personalizadas para manejar situaciones específicas.

#### Bloques Try-Catch

En Java, se pueden gestionar excepciones mediante bloques try-catch. El código que puede generar una excepción se coloca en el bloque try y el bloque catch captura y gestiona la excepción si se produce. A continuación, se muestra un ejemplo:

```java
try {
        int result = divide(10, 0);
        System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
        System.out.println("An error occurred: " + e.getMessage());
        }
```

#### Manejo de múltiples excepciones

Puede gestionar varias excepciones mediante el uso de varios bloques catch. Cada bloque catch puede gestionar un tipo específico de excepción. A continuación, se muestra un ejemplo:

```java
try {
        // Code that may throw exceptions
        } catch (IOException e) {
        // Handle IOException
        } catch (SQLException e) {
        // Handle SQLException
        }
```

#### Finalmente bloquear

El bloque finally se utiliza para ejecutar código que siempre debe ejecutarse, independientemente de si se produce una excepción o no. Se utiliza habitualmente para liberar recursos o realizar operaciones de limpieza. A continuación, se muestra un ejemplo:

```java
try {
        // Code that may throw exceptions
        } catch (Exception e) {
        // Handle exceptions
        } finally {
        // Code to be executed regardless of exceptions
        }
```

#### Excepciones personalizadas

Java le permite crear sus propias excepciones personalizadas ampliando la clase `Exception` o una de sus subclases. Las excepciones personalizadas se pueden utilizar para gestionar situaciones específicas en su código. A continuación, se muestra un ejemplo:

```java
public class CustomException extends Exception {
  public CustomException(String message) {
    super(message);
  }
}

// Usage
try {
        // Code that may throw CustomException
        throw new CustomException("Custom exception occurred");
        } catch (CustomException e) {
        System.out.println("An error occurred: " + e.getMessage());
        }
```

#### Propagación de excepciones

Cuando se lanza una excepción, se puede capturar y manejar mediante un método que se encuentra más arriba en la pila de llamadas o se puede propagar al método que realiza la llamada. De manera predeterminada, las excepciones controladas se deben declarar en la firma del método utilizando la palabra clave `throws` si no se capturan ni manejan. A continuación, se muestra un ejemplo:

```java
public void method1() throws IOException {
        method2();
        }

public void method2() throws IOException {
        method3();
        }

public void method3() throws IOException {
        throw new IOException("Exception occurred");
        }

// Usage
        try {
        method1();
        } catch (IOException e) {
        System.out.println("An error occurred: " + e.getMessage());
        }
```

---

### 1.6 Subprocesos múltiples

El subprocesamiento múltiple es una técnica de programación que permite que un solo proceso realice varias tareas simultáneamente. Se utiliza para mejorar el rendimiento de las aplicaciones que realizan tareas de larga duración, como solicitudes de red, E/S de archivos y cálculos. En esta sección, aprenderá a crear y administrar subprocesos en Java.

#### Creando hilos

En Java, puedes crear subprocesos extendiendo la clase `Thread` o implementando la interfaz `Runnable`.

##### Extendiendo la clase `Thread`:

Extender la clase `Thread` le permite definir una nueva clase que es una subclase de `Thread` y anular su método `run()` para definir la tarea que ejecutará el hilo. A continuación, se muestra un ejemplo:

```java
public class MyThread extends Thread {
  @Override
  public void run() {
    System.out.println("MyThread en ejecución");
  }
}
```

##### Implementando la interfaz `Runnable`:

Para implementar la interfaz `Runnable` es necesario implementar el método `run()` definido en la interfaz. Este enfoque es útil cuando se desea separar la lógica de la tarea de la clase de subproceso. A continuación, se muestra un ejemplo:

```java
public class MyRunnable implements Runnable {
  @Override
  public void run() {
    System.out.println("MyRunnable corriendo");
  }
}
```

#### Comenzando hilos

Para iniciar un hilo, debes crear una instancia de la clase de hilo y llamar al método `start()` en ella. Esto ejecutará el método `run()` en el nuevo hilo. A continuación, se muestra un ejemplo:

```java
Thread thread1 = new MyThread();
        thread1.start(); // Salida: MyThread en ejecución

        Thread thread2 = new Thread(new MyRunnable());
        thread2.start(); // Salida: MyRunnable en ejecución
```

#### Estados del hilo

Un hilo puede estar en uno de los siguientes estados:

- `NEW`: El hilo ha sido creado pero aún no ha comenzado.
- `RUNNABLE`: El hilo se está ejecutando o está listo para ejecutarse.
- `BLOCKED`: El hilo está bloqueado esperando un bloqueo del monitor.
- `WAITING`: El hilo está esperando indefinidamente que otro hilo realice una acción particular.
- `TIMED_WAITING`: El hilo está esperando que otro hilo realice una acción particular durante un período de tiempo específico.
- `TERMINATED`: El hilo ha salido y ya no se está ejecutando.

Comprender los diferentes estados de los subprocesos es importante para administrarlos y sincronizarlos de manera eficaz en sus programas Java.

#### Sincronización de subprocesos

Cuando varios subprocesos acceden a recursos compartidos simultáneamente, es fundamental sincronizar su acceso para evitar condiciones de competencia y garantizar la coherencia de los datos. Java proporciona la palabra clave `synchronized` y los objetos `Lock` para lograr la sincronización de subprocesos.

La palabra clave `synchronized` se puede aplicar a métodos o bloques de código para garantizar que solo un subproceso pueda ejecutarlos a la vez. A continuación, se muestra un ejemplo:

```java
public class Counter {
  private int count;

  public synchronized void increment() {
    count++;
  }
}
```

En este ejemplo, el método `increment()` está sincronizado, lo que significa que solo un subproceso puede ejecutarlo en un momento determinado. Esto evita que varios subprocesos interfieran entre sí y provoquen resultados inconsistentes.

Como alternativa, puede utilizar objetos `Lock` del paquete `java.util.concurrent.locks` para lograr un control más preciso sobre la sincronización. A continuación, se muestra un ejemplo:

```java
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

public class Counter {
  private int count;
  private Lock lock = new ReentrantLock();

  public void increment() {
    lock.lock();
    try {
      count++;
    } finally {
      lock.unlock();
    }
  }
}
```

En este ejemplo, se utiliza la clase `ReentrantLock` para crear un bloqueo, y los métodos `lock()` y `unlock()` se utilizan para adquirir y liberar el bloqueo, respectivamente. El bloque `try-finally` garantiza que el bloqueo siempre se libere, incluso si se produce una excepción.

La sincronización adecuada de los subprocesos es esencial para evitar la corrupción de datos y garantizar la corrección de los programas Java simultáneos.

#### Seguridad de subprocesos

La seguridad de subprocesos se refiere a la capacidad de un programa o de un fragmento específico de código para funcionar correctamente y producir los resultados esperados cuando varios subprocesos acceden a él simultáneamente. Escribir código seguro para subprocesos es crucial en aplicaciones multiproceso para evitar la corrupción de datos y el comportamiento inesperado.

Para lograr la seguridad de subprocesos, puede utilizar varias técnicas de sincronización, como la palabra clave `synchronized`, bloqueos, clases atómicas y estructuras de datos concurrentes proporcionadas por el paquete `java.util.concurrent` de Java. Estas técnicas ayudan a garantizar que varios subprocesos accedan y modifiquen de forma segura los datos compartidos.

Al diseñar aplicaciones multiproceso, es importante identificar los recursos compartidos y las secciones críticas del código que se deben sincronizar para mantener la seguridad de los subprocesos. La aplicación de mecanismos de sincronización adecuados le ayudará a evitar condiciones de carrera, bloqueos y otros problemas relacionados con la concurrencia.

#### Comunicación entre subprocesos

En aplicaciones multiproceso, los subprocesos a menudo necesitan comunicarse y coordinarse entre sí. Java proporciona varios mecanismos para la comunicación entre subprocesos, entre ellos:

- **Esperar y notificar**: Los métodos `wait()` y `notify()` de la clase `Object` permiten que los subprocesos esperen una condición específica y notifiquen a otros subprocesos cuando se cumple esa condición.
- **Colas de bloqueo**: El paquete `java.util.concurrent` proporciona implementaciones de colas de bloqueo como `LinkedBlockingQueue` y `ArrayBlockingQueue`, que permiten que los subprocesos intercambien datos de forma segura.
- **Señalización de subprocesos**: se pueden implementar mecanismos de señalización personalizados utilizando objetos compartidos, indicadores y primitivos de sincronización como bloqueos y semáforos.

Comprender y utilizar estos mecanismos de forma adecuada es crucial para crear aplicaciones multiproceso robustas y eficientes en Java.

#### Manejo de excepciones en subprocesos

El manejo de excepciones en programas multiproceso requiere una consideración cuidadosa. Cuando se lanza una excepción en un subproceso, puede terminar la ejecución del subproceso y afectar potencialmente la estabilidad de toda la aplicación. Para manejar excepciones en subprocesos de manera efectiva, puede utilizar los siguientes enfoques:

- **Capturar y manejar excepciones localmente**: coloque el código que puede lanzar excepciones dentro de un bloque `try-catch` dentro del método `run()` del subproceso para capturar y manejar excepciones localmente. Esto garantiza que las excepciones se capturen y procesen dentro del subproceso, lo que evita que finalice abruptamente.
- **Registro**: utilice marcos de registro como `java.util.logging`, Log4j o SLF4J para registrar excepciones e información relacionada. Esto ayuda a depurar y solucionar problemas en aplicaciones multiproceso.
- **Manejador de excepciones no detectadas de subprocesos**: establezca un manejador de excepciones no detectadas para subprocesos llamando al método `setUncaughtExceptionHandler()`. Esto le permite definir un manejador de excepciones global que se invocará siempre que se produzca una excepción no detectada en un subproceso. El manejador puede registrar la excepción o tomar las medidas adecuadas para manejarla correctamente.

Al implementar estrategias adecuadas de manejo de excepciones, puede asegurarse de que las excepciones en subprocesos se detecten, registren y manejen adecuadamente, mejorando la solidez general de sus aplicaciones Java.

#### Resumen

En esta sección, aprendió sobre subprocesos múltiples en Java. Descubrió cómo crear subprocesos ampliando la clase `Thread` o implementando la interfaz `Runnable`. También aprendiste sobre el inicio de subprocesos, estados de subprocesos, sincronización de subprocesos, seguridad de subprocesos, comunicación de subprocesos y manejo de excepciones en subprocesos. Aplicar estos conceptos correctamente te ayudará a escribir aplicaciones Java multiproceso eficientes, confiables y escalables.

---

# Sección 2: Desarrollo de complementos de RuneLite

## 2.1 Introducción a RuneLite

RuneLite es un cliente de juego de código abierto para Old School RuneScape. Proporciona una alternativa personalizable y rica en funciones al cliente de juego oficial. RuneLite ofrece varios complementos que mejoran la experiencia de juego agregando nuevas funciones, mejorando los elementos visuales y brindando herramientas útiles para los jugadores.

#### ¿Qué es RuneLite?

RuneLite se basa en los principios del desarrollo impulsado por la comunidad y la colaboración de código abierto. Su objetivo es proporcionar un cliente de juego altamente personalizable y liviano para Old School RuneScape. El cliente de RuneLite está diseñado para ser fácil de usar, intuitivo y accesible para jugadores de todos los niveles de habilidad.

#### Arquitectura y cómo funciona

RuneLite utiliza una arquitectura modular que permite a los desarrolladores crear complementos para ampliar y mejorar la funcionalidad del cliente. El cliente está escrito en Java y aprovecha

- [Sitio web oficial de RuneLite](https://RuneLite.net/)
- [Repositorio de GitHub de RuneLite](https://github.com/RuneLite/RuneLite)
- [Repositorio de complementos de ejemplo de RuneLite](https://github.com/RuneLite/example-plugin)

El repositorio de complementos de ejemplo de RuneLite ofrece un punto de partida útil para desarrollar sus propios complementos. Ofrece ejemplos de código y una guía para ayudarlo a comprender el proceso de desarrollo de complementos.

La comunidad activa de RuneLite y la extensa documentación brindan más soporte y recursos para el desarrollo de complementos. ¡Siéntase libre de explorar, experimentar y crear sus propios complementos de RuneLite para mejorar su experiencia con RuneScape de la vieja escuela!

---

## 2.2 Configuración del entorno de desarrollo

Para desarrollar complementos de RuneLite, debe configurar su entorno de desarrollo en consecuencia. En esta sección, aprenderá a descargar e instalar RuneLite y a configurar su IDE para comenzar a crear sus propios complementos. Cubriremos las bibliotecas, dependencias y herramientas necesarias.

#### Descarga e instalación de RuneLite

Para comenzar con el desarrollo de complementos de RuneLite, siga estos pasos para descargar e instalar RuneLite:

1. Visita el .[Sitio web de RuneLite](https://RuneLite.net/) y navegar a la página de descargas.
2. Descargue el instalador de RuneLite adecuado para su sistema operativo.
3. Ejecute el instalador y siga las instrucciones de instalación.

#### Configuración del IDE

Una vez que haya instalado RuneLite, puede configurar su entorno de desarrollo integrado (IDE) para comenzar a crear complementos de RuneLite. El IDE recomendado para el desarrollo de complementos de RuneLite es IntelliJ IDEA. A continuación, se muestra cómo configurarlo:

1. Descargue e instale [Edición comunitaria de IntelliJ IDEA](https://www.jetbrains.com/idea/download/).
2. Inicie IntelliJ IDEA una vez finalizada la instalación.

#### Obtener el proyecto RuneLite desde el control de versiones

Para comenzar a desarrollar complementos de RuneLite, deberá obtener el proyecto RuneLite desde el control de versiones. Siga estos pasos para obtener el proyecto:

1. Abra IntelliJ IDEA y seleccione "Obtener desde el control de versiones" en la pantalla de bienvenida.
2. Elija la opción Git e ingrese la URL del repositorio de RuneLite: `https://github.com/RuneLite/RuneLite.git`.
3. Especifique el directorio deseado en el que clonar el proyecto.
4. Haga clic en "Clonar" para iniciar el proceso de clonación.

#### Configuración de argumentos de programa y de máquina virtual

Para habilitar funciones y opciones específicas durante el desarrollo del complemento de RuneLite, es posible que deba configurar argumentos de programa y de máquina virtual en IntelliJ IDEA. A continuación, se muestran algunos argumentos de uso común:

- `-ea` (Habilitar aserciones): habilita las aserciones en el cliente de RuneLite para fines de depuración.
- `--developer-mode` (Modo de desarrollador): habilita el modo de desarrollador, que proporciona herramientas y funciones de depuración adicionales.

Para configurar estos argumentos en IntelliJ IDEA, vaya a "Ejecutar" > "Editar configuraciones", seleccione la configuración "Cliente" y especifique los argumentos deseados en los campos "Opciones de VM" y "Argumentos del programa".

#### Cómo omitir el lanzador de Jagex para el desarrollo

Durante el desarrollo del complemento de RuneLite, es posible que desee omitir el lanzador de Jagex para iniciar directamente el cliente de RuneLite. La Wiki de RuneLite proporciona instrucciones detalladas sobre cómo omitir el lanzador de Jagex para fines de desarrollo. Consulta la guía [Uso de cuentas de Jagex](https://github.com/RuneLite/RuneLite/wiki/Using-Jagex-Accounts) para obtener más información.

Ten en cuenta que el desarrollo de complementos de RuneLite requiere conocimientos de programación en Java y familiaridad con el sistema de complementos de RuneLite. Se recomienda tener conocimientos básicos de Java e IntelliJ IDEA antes de sumergirse en el desarrollo de complementos.

---

## 2.3 Creación de tu primer complemento de RuneLite

En esta sección, aprenderás a crear un complemento básico de RuneLite paso a paso. Al final, tendrás una base sólida para crear complementos más complejos para RuneLite.

Para crear un complemento de RuneLite, sigue estos pasos:

#### Paso 1: Configuración de la clase de complemento

Primero, crea una nueva clase Java para tu complemento. Puedes ponerla en un paquete como `com.plugins`. La clase debe extender la clase `Plugin` proporcionada por RuneLite.

```java
package com.plugins;

import net.RuneLite.client.plugins.Plugin;

public class ExamplePlugin extends Plugin {
  // Plugin code goes here
}
```

#### Paso 2: Agregar dependencias (opcional)

Si su complemento requiere complementos adicionales o bibliotecas externas, puede especificarlos como dependencias mediante anotaciones. Por ejemplo, si su complemento necesita `OtherPlugin` para funcionar, puede agregar la anotación `@PluginDependency(OtherPlugin.class)`.

```java
@PluginDependency(OtherPlugin.class)
public class ExamplePlugin extends Plugin {
  // Plugin code goes here
}
```

#### Paso 3: Inyección de dependencias

Para acceder a los servicios y configuraciones de RuneLite, puede utilizar la inyección de dependencias. Esto le permite acceder cómodamente a objetos y configuraciones importantes. Por ejemplo, puede inyectar los objetos `Client`, `KeyManager` y `ExampleConfig` en su complemento utilizando la anotación `@Inject`.

```java
import javax.inject.Inject;
import net.RuneLite.client.Client;
import net.RuneLite.client.input.KeyManager;
import net.RuneLite.client.plugins.Plugin;
import net.RuneLite.client.config.ConfigManager;

public class ExamplePlugin extends Plugin {
  @Inject
  private Client client;

  @Inject
  private KeyManager keyManager;

  @Inject
  private ExampleConfig config;

  // Plugin code goes here
}
```

#### Paso 4: Configuración del complemento

Si su complemento requiere ajustes de configuración, puede crear un método anotado con `@Provides` para recuperar la configuración desde `ConfigManager`. Esto le permite acceder a la configuración del complemento fácilmente.

```java
import javax.inject.Inject;
import net.RuneLite.client.config.ConfigManager;
import net.RuneLite.client.plugins.Plugin;
import com.google.inject.Provides;

public class ExamplePlugin extends Plugin {
  @Inject
  private ExampleConfig config;

  @Provides
  public ExampleConfig getConfig(ConfigManager configManager) {
    return configManager.getConfig(ExampleConfig.class);
  }

  // Plugin code goes here
}
```

#### Paso 5: Implementación de métodos de ciclo de vida

Reemplace los métodos `startUp()` y `shutDown()` proporcionados por la clase `Plugin`. En el método `startUp()`, puede realizar tareas de inicialización para su complemento, como enviar un mensaje de bienvenida al chat del cliente o registrar oyentes de eventos. En el método `shutDown()`, puede realizar tareas de limpieza o finalizar operaciones, como enviar un mensaje de despedida o anular el registro de oyentes de eventos.

```java
import net.RuneLite.api.ChatMessageType;
import net.RuneLite.api.events.ChatMessage;
import net.RuneLite.client.plugins.Plugin;

public class ExamplePlugin extends Plugin {
  // ...

  @Override
  public void startUp() {
    sendClientMessage("Hello " + client.getLocalPlayer().getName() + "!");
    keyManager.registerKeyListener(startButton);
  }

  @Override
  public void shutDown() {
    sendClientMessage("Goodbye " + client.getLocalPlayer().getName() + "!");
    keyManager.unregisterKeyListener(startButton);
  }

  // ...
}
```

#### Paso 6: Interacción con el cliente de RuneLite

Para interactuar con el cliente de RuneLite, puede agregar elementos de la interfaz de usuario y registrar detectores de eventos. Por ejemplo, puede definir un `HotkeyListener` para escuchar eventos de teclas de acceso rápido específicos. Cuando se presiona la tecla de acceso rápido, se ejecutará el método asociado. Puede usar el método `sendClientMessage()` para enviar mensajes al chat del cliente.

```java
import net.RuneLite.client.input.KeyManager;
import net.RuneLite.client.util.HotkeyListener;
import net.RuneLite.client.plugins.Plugin;

public class ExamplePlugin extends Plugin {
  @Inject
  private KeyManager keyManager;

  private final HotkeyListener startButton = new HotkeyListener(() -> config.ExampleHotKey()) {
    @Override
    public void hotkeyPressed() {
      sendClientMessage("¡Botón de inicio presionado!");
    }
  };

  // ...

  @Override
  public void startUp() {
    // ...
    keyManager.registerKeyListener(startButton);
  }

  @Override
  public void shutDown() {
    // ...
    keyManager.unregisterKeyListener(startButton);
  }

  public void sendClientMessage(String message) {
    client.addChatMessage(ChatMessageType.GAMEMESSAGE, "", message, null);
  }

  // ...
}
```

#### Paso 7: Manejo de eventos

Puedes escuchar eventos específicos, como mensajes de chat, anotando un método con `@Subscribe`. Dentro del método de escucha de eventos, puedes verificar el tipo de evento y realizar acciones en consecuencia. Por ejemplo, si un mensaje de chat de tipo `GAMEMESSAGE` contiene la palabra "test", puedes enviar un mensaje de respuesta al chat del cliente.

```java
import net.RuneLite.api.ChatMessageType;
import net.RuneLite.api.events.ChatMessage;
import net.RuneLite.client.plugins.Plugin;
import net.RuneLite.client.eventbus.Subscribe;

public class ExamplePlugin extends Plugin {
  // ...

  @Subscribe
  public void onChatMessage(ChatMessage event) {
    if (event.getType() == ChatMessageType.GAMEMESSAGE) {
      String message = event.getMessage();
      if (message.contains("test")) {
        sendClientMessage("Test successful!");
      }
    }
  }

  // ...
}
```

Si sigue estos pasos, podrá crear su primer complemento de RuneLite. Es importante estructurar correctamente el complemento, manejar las dependencias e interactuar con el cliente de RuneLite de manera eficaz. Con práctica y más exploración, podrá desarrollar complementos más avanzados y con más funciones para RuneLite.

## 2.4 Interacción con el cliente de juego de RuneScape

Los complementos de RuneLite brindan amplias capacidades para interactuar con el cliente de juego de RuneScape, lo que le permite acceder a los datos del juego, escuchar eventos y modificar el comportamiento del juego. En esta sección, exploraremos algunas de las potentes funciones disponibles para los desarrolladores de complementos.

#### Acceso a los datos del cliente de juego

Los complementos pueden acceder a una amplia gama de datos del juego proporcionados por la API de RuneLite. Esto incluye información sobre el jugador, los objetos del juego, los NPC, el mundo del juego y más. Al acceder a estos datos, puede crear complementos dinámicos e interactivos.

Por ejemplo, puedes recuperar el nombre del jugador local usando el método `getClient()` provisto por la clase `Plugin`:

```java
String playerName = client.getLocalPlayer().getName();
```

De manera similar, puedes acceder a otras entidades y propiedades del juego usando los métodos y clases apropiados provistos por la API de RuneLite.

#### Escuchar eventos del juego

Los complementos pueden escuchar varios eventos del juego para recibir notificaciones de cambios o acciones específicas en el juego. Al suscribirte a estos eventos, puedes responder en consecuencia y realizar acciones basadas en el estado del juego.

Para escuchar eventos del juego, necesitas anotar un método con la anotación `@Subscribe` y especificar la clase de evento que quieres escuchar. Aquí hay un ejemplo de cómo escuchar el evento `GameStateChanged`:

```java
import net.RuneLite.api.events.GameStateChanged;
import net.RuneLite.client.plugins.Plugin;
import net.RuneLite.client.eventbus.Subscribe;

public class ExamplePlugin extends Plugin {
  // ...

  @Subscribe
  public void onGameStateChanged(GameStateChanged event) {
    // Handle the game state change event
  }

  // ...
}
```

Al implementar detectores de eventos, puede responder a cambios en el estado del juego, acciones del jugador y otros eventos importantes.

#### Modificación del comportamiento del juego con ganchos

RuneLite expone varios ganchos que le permiten modificar el comportamiento del cliente del juego. Al usar ganchos, puede ampliar la funcionalidad del cliente del juego o personalizar su comportamiento para adaptarlo a sus necesidades.

Por ejemplo, puede modificar el comportamiento de renderización del juego accediendo al objeto `client` y configurando propiedades o invocando métodos proporcionados por la API de RuneLite. A continuación, se muestra un ejemplo de modificación de la renderización del juego:

```java
client.setDrawDistance(100);
```

Al utilizar ganchos, puede mejorar la funcionalidad del cliente del juego, crear visualizaciones personalizadas o implementar nuevas funciones.

#### Visualización de superposiciones

Los complementos pueden mostrar superposiciones en el cliente del juego para proporcionar información adicional o señales visuales. Las superposiciones se utilizan normalmente para resaltar elementos específicos del juego, mostrar temporizadores o presentar información adicional relevante para el jugador.

Para crear una superposición, puede ampliar la clase `Overlay` proporcionada por la API de RuneLite e implementar los métodos necesarios. A continuación, se muestra un ejemplo:

```java
import net.RuneLite.api.overlay.Overlay;
import net.RuneLite.api.overlay.OverlayLayer;
import net.RuneLite.api.overlay.OverlayPosition;
import net.RuneLite.api.overlay.OverlayUtil;
import java.awt.Graphics2D;

public class ExampleOverlay extends Overlay {
  @Override
  public void render(Graphics2D graphics) {
    // Render the overlay
  }
}
```

Luego puedes registrar tu superposición usando `OverlayManager` en el método `startUp()` del complemento:

```java
@Override
public void startUp() {
        overlayManager.add(overlay);
        }
```

Al utilizar superposiciones, puede proporcionar información visual útil a los jugadores dentro del cliente del juego.

#### Respuesta a la entrada del usuario

Los complementos pueden responder a los eventos de entrada del usuario, como clics del mouse o pulsaciones de teclas, para proporcionar una funcionalidad interactiva. Al escuchar los eventos de entrada del usuario, puede realizar acciones basadas en las interacciones del jugador.

Para escuchar los eventos de entrada del usuario, puede implementar las interfaces `MouseListener` o `KeyListener` proporcionadas por la API de RuneLite. A continuación, se muestra un ejemplo de implementación de un detector de clics del mouse:

```java
import net.RuneLite.client.input.MouseListener;
import net.RuneLite.client.plugins.Plugin;

public class ExamplePlugin extends Plugin implements MouseListener {
  // ...

  @Override
  public MouseEvent mouseClicked(MouseEvent event) {
    // Manejar el evento de clic del mouse
  }

  // ...
}
```

You can then register your plugin as a mouse listener using the `MouseManager` in the plugin's `startUp()` method:

```java
@Override
public void startUp() {
        mouseManager.registerMouseListener(this);
        }
```

Al responder a los eventos de entrada del usuario, puedes crear complementos interactivos que permitan a los jugadores interactuar con las funciones de tu complemento.

---

## 2.5 Funciones avanzadas de los complementos

Una vez que comprendas bien los conceptos básicos, puedes explorar funciones y técnicas más avanzadas para llevar el desarrollo de tu complemento de RuneLite al siguiente nivel. En esta sección, profundizaremos en conceptos más avanzados y brindaremos orientación sobre cómo utilizarlos de manera efectiva.

#### Creación de superposiciones personalizadas

Las superposiciones personalizadas te permiten agregar elementos visuales al cliente del juego, lo que brinda información adicional o mejora la interfaz de usuario. RuneLite ofrece un conjunto completo de API para crear superposiciones con varios estilos y comportamientos.

Para crear una superposición personalizada, puedes extender la clase `Overlay` proporcionada por la API de RuneLite e implementar la lógica de renderizado necesaria. Aquí tienes un ejemplo:

```java
import net.RuneLite.api.overlay.Overlay;
import net.RuneLite.api.overlay.OverlayLayer;
import net.RuneLite.api.overlay.OverlayPosition;
import java.awt.Color;
import java.awt.Dimension;
import java.awt.Graphics2D;

public class CustomOverlay extends Overlay {
  private static final Color OVERLAY_COLOR = new Color(255, 0, 0, 100);

  @Override
  public Dimension render(Graphics2D graphics) {
    // Realice aquí una lógica de representación personalizada
    graphics.setColor(OVERLAY_COLOR);
    graphics.fillRect(50, 50, 100, 100);

    return null; // Devuelve nulo para indicar que la superposición debe representarse de forma continua
  }
}
```

Puede configurar la capa y la posición de la superposición mediante anotaciones como `@OverlayLayer` y `@OverlayPosition`. Al registrar su superposición personalizada con `OverlayManager`, se representará sobre el cliente del juego.

#### Manejo de la entrada del mouse y del teclado

Los complementos avanzados a menudo requieren interacción con eventos del mouse y del teclado para brindar una funcionalidad dinámica y responsiva. RuneLite ofrece sólidas capacidades de manejo de entrada que le permiten escuchar y responder a los eventos de entrada del usuario.

Para manejar eventos del mouse, puede implementar la interfaz `MouseListener` proporcionada por la API de RuneLite. A continuación, se incluye un ejemplo:

```java
import net.RuneLite.client.input.MouseAdapter;
import net.RuneLite.client.plugins.Plugin;

public class ExamplePlugin extends Plugin {
  private final MouseAdapter mouseAdapter = new MouseAdapter() {
    @Override
    public MouseEvent mousePressed(MouseEvent event) {
      // Manejar evento de pulsación del ratón
      return event;
    }

    @Override
    public MouseEvent mouseReleased(MouseEvent event) {
      // Manejar el evento de liberación del mouse
      return event;
    }

    // Anule otros métodos de eventos del mouse según sea necesario
  };

  @Override
  public void startUp() {
    mouseManager.registerMouseListener(mouseAdapter);
  }

  @Override
  public void shutDown() {
    mouseManager.unregisterMouseListener(mouseAdapter);
  }
}
```

De manera similar, puedes manejar eventos del teclado implementando la interfaz `KeyListener` y registrándola con `KeyManager`. Esto te permite responder a las pulsaciones y liberaciones de teclas:

```java
import net.RuneLite.client.input.KeyListener;
import net.RuneLite.client.plugins.Plugin;

public class ExamplePlugin extends Plugin {
  private final KeyListener keyListener = new KeyListener() {
    @Override
    public void keyTyped(KeyEvent event) {
      // Manejar evento de escritura de tecla
    }

    @Override
    public void keyPressed(KeyEvent event) {
      // Manejar evento de pulsación de tecla
    }

    @Override
    public void keyReleased(KeyEvent event) {
      // Manejar evento de liberación de clave
    }
  };

  @Override
  public void startUp() {
    keyManager.registerKeyListener(keyListener);
  }

  @Override
  public void shutDown() {
    keyManager.unregisterKeyListener(keyListener);
  }
}
```

Al aprovechar el manejo de la entrada del mouse y el teclado, puede crear complementos que respondan a las acciones del usuario en tiempo real.

#### Uso de API y bibliotecas externas

Los complementos de RuneLite pueden utilizar API y bibliotecas externas para expandir sus capacidades e integrarse con sistemas externos. Esto le permite aprovechar las herramientas y los servicios existentes para mejorar sus complementos.

Para usar una API o biblioteca externa, debe incluir las dependencias necesarias en la configuración de compilación de su complemento. Esto se puede hacer usando herramientas de compilación como Maven o Gradle. Una vez que se agregan las dependencias, puede importar y utilizar la API o la biblioteca en el código de su complemento.

Por ejemplo, si desea utilizar la biblioteca Apache HttpClient para realizar solicitudes HTTP, puede incluir la siguiente dependencia de Maven:

```xml
<dependencies>
  <dependency>
    <groupId>org.apache.httpcomponents</groupId>
    <artifactId>httpclient</artifactId>
    <version>4.5.13</version>
  </dependency>
</dependencies>
```

Luego, puedes importar y usar HttpClient en el código de tu complemento:

```java
import org.apache.http.client.HttpClient;
import org.apache.http.impl.client.HttpClientBuilder;

public class ExamplePlugin extends Plugin {
  private final HttpClient httpClient = HttpClientBuilder.create().build();

  // Use the httpClient to make HTTP requests
}
```

Al utilizar bibliotecas y API externas, puede ampliar las capacidades de sus complementos e integrarlos con sistemas externos sin problemas.

#### Gestión de configuraciones y ajustes de complementos

Los complementos suelen requerir ajustes de configuración que los usuarios pueden personalizar. RuneLite ofrece un marco de configuración integrado que le permite administrar y almacenar fácilmente las configuraciones de los complementos.

Para crear una configuración para su complemento, puede definir una clase de configuración y anotarla con las anotaciones `@ConfigGroup` y `@ConfigItem`. A continuación, se incluye un ejemplo:

```java
import net.RuneLite.client.config.Config;
import net.RuneLite.client.config.ConfigGroup;
import net.RuneLite.client.config.ConfigItem;

@ConfigGroup("example")
public interface ExampleConfig extends Config {
  @ConfigItem(
          keyName = "optionEnabled",
          name = "Habilitar opción",
          description = "Habilitar una opción específica",
          position = 0
  )
  default boolean optionEnabled() {
    return false;
  }
}
```

Al utilizar `ConfigManager`, puede acceder y modificar la configuración del complemento dentro del código del complemento:

```java
import javax.inject.Inject;
import net.RuneLite.client.config.ConfigManager;
import net.RuneLite.client.plugins.Plugin;

public class ExamplePlugin extends Plugin {
  @Inject
  private ExampleConfig config;

  @Inject
  private ConfigManager configManager;

  @Override
  public void startUp() {
    boolean optionEnabled = config.optionEnabled();
    // Utilice la configuración
  }

  public void setOptionEnabled(boolean enabled) {
    configManager.setConfiguration("example", "optionEnabled", enabled);
  }
}
```

Al aprovechar el marco de configuración integrado, puede proporcionar una experiencia personalizable para los usuarios de su complemento.

#### Optimización del rendimiento del complemento

A medida que sus complementos se vuelven más complejos, es esencial optimizar su rendimiento para garantizar una jugabilidad fluida y un uso eficiente de los recursos. A continuación, se ofrecen algunos consejos para optimizar sus complementos:

- Minimizar el uso de operaciones que consumen mucha CPU en los escuchas de eventos.
- Evitar sondeos frecuentes o actualizaciones de datos innecesarias.
- Desechar los recursos de forma adecuada para evitar fugas de memoria.
- Optimizar la representación y limitar la cantidad de superposiciones dibujadas simultáneamente.
- Utilizar el almacenamiento en caché y algoritmos eficientes cuando corresponda.
- Utilizar operaciones asincrónicas y de subprocesamiento múltiple para descargar tareas pesadas.
- Crear perfiles de sus complementos para identificar posibles cuellos de botella y áreas de mejora.

Al seguir estas técnicas de optimización, puede crear complementos de alto rendimiento que proporcionen una experiencia fluida y receptiva para los usuarios.

---

# Sección 3: Información sobre complementos externos

## 3.1 Advertencia sobre complementos externos

Aquí exploraremos el uso de la API de RuneLite para algunas cosas no tan buenas. Esto puede incluir la carga de complementos que no están destinados a usarse a través del Centro de complementos de RuneLite o complementos que se eliminaron a pedido de Gagex.

#### Solo con fines educativos

Esta sección es solo con fines educativos. No aprobamos el uso de estos complementos de ninguna manera. Simplemente estamos mostrando las capacidades de la API de RuneLite y cómo se puede usar para crear complementos que no están destinados a usarse a través del Centro de complementos. Úselo bajo su propio riesgo.

---

## 3.2 API de complementos de EthanVann

EthanVann ha realizado contribuciones significativas al repositorio de complementos que estamos creando, mostrando sus habilidades como desarrollador de complementos de RuneLite. En este capítulo, exploraremos las contribuciones de EthanVann, centrándonos en su API y el impacto que ha tenido en la comunidad de desarrollo de complementos.

## Uso de EthanVannAPI en SuperGlassMakerPlugin

### Dependencias de paquetes
SuperGlassMakerPlugin importa los siguientes paquetes:

```java
import com.plugins.Collections.*;
import com.plugins.EthanApiPlugin;
import com.google.inject.Inject;
import com.google.inject.Provides;
import lombok.SneakyThrows;
```

### Definiciones de clases
La clase `SuperGlassMakerPlugin` extiende la clase `Plugin` y está decorada con varias anotaciones que definen ciertas propiedades del complemento.

```java
@PluginDescriptor(
        name = "Super fabricante de vidrio",
        description = "",
        enabledByDefault = false,
        tags = {"ethan"}
)
@Slf4j
@PluginDependency(PacketUtilsPlugin.class)
@PluginDependency(EthanApiPlugin.class)
public class SuperGlassMakerPlugin extends Plugin {
```

- `@PluginDescriptor`: proporciona información básica sobre el complemento, como su nombre, una breve descripción, su estado habilitado predeterminado y las etiquetas relacionadas.

- `@Slf4j`: esta anotación de Lombok permite que la clase utilice una instancia de un registrador.

- `@PluginDependency`: este complemento requiere `PacketUtilsPlugin` y `EthanApiPlugin` para funcionar de manera efectiva, de ahí la dependencia.

### Variables a nivel de clase
Los siguientes campos se declaran a nivel de clase:

```java
public int timeout = 0;

@Inject
Client client;

@Inject
EthanApiPlugin api;

@Inject
SuperGlassMakerPluginConfig config;
        
int timesFailed = 0;
```

### Métodos del complemento
- `startUp()`: este método se llama automáticamente cuando el usuario habilita el complemento. Actualmente, establece el tiempo de espera en 0.

- `shutDown()`: este método se llama automáticamente cuando el complemento está deshabilitado. Actualmente, no tiene ninguna implementación específica.

- `getConfig(ConfigManager configManager)`: este método devuelve los ajustes de configuración para este complemento.

- `onGameTick(GameTick event)`: este método se llama automáticamente en cada tick del juego. Contiene la funcionalidad principal del complemento, interactuando con los NPC, el banco y los elementos de vidrio en el juego.

- `handleSecondary()`: esta función es responsable de manejar tareas secundarias en el juego. Sin más contexto, se desconoce la implementación específica.

### Interacciones del juego
El método `onGameTick(GameTick event)` maneja varias interacciones del juego, como la selección de elementos, las interacciones con los NPC y las transacciones bancarias. El uso de WidgetPackets y MousePackets sugiere operaciones relacionadas con la interfaz de usuario y los movimientos del mouse.

Tenga en cuenta que este complemento parece estar diseñado para un juego específico, ya que hace referencia a elementos específicos del juego como `Secondary.GIANT_SEAWEED` y `SuperGlassMakerPluginConfig`. Para usar este complemento con un juego diferente, es posible que deba reemplazar estos elementos con equivalentes específicos del juego.

### Registro
En todo el complemento, hay varias declaraciones de registro que se utilizan para rastrear operaciones y ayudar en la depuración en caso de errores o excepciones.

### Suscripción al evento de tick del juego
El complemento se suscribe al evento de tick del juego. Cada tick del juego activa la ejecución del método `onGameTick`.

```java
@Subscribe
public void onGameTick(GameTick event) throws NoSuchFieldException, ClassNotFoundException, InvocationTargetException, NoSuchMethodException, IllegalAccessException {
    // Code here...
}
```

### Interacción con el banco o el banquero
Si no hay ningún widget de banco activo, el complemento busca un PNJ banquero o un objeto de ficha de banco (ambos con una acción denominada "Banco") más cercano al jugador. Interactúa con el primero que encuentra para abrir la interfaz del banco.

```java
Optional<NPC> banker = NPCs.search().withAction("Bank").nearestToPlayer();
Optional<TileObject> bank = TileObjects.search().withAction("Bank").nearestToPlayer();
```

### Verificación de objetos
El complemento verifica si hay objetos específicos en el banco necesarios para la creación de supervidrio: Balde de arena, Vidrio fundido, Runa astral y un objeto secundario. También verifica si hay el widget de hechizo necesario. Si no se encuentra alguno de estos, se envía un mensaje correspondiente al chat del juego.

```java
Optional<Widget> sand = Bank.search().withId(ItemID.BUCKET_OF_SAND).first();
Optional<Widget> glass = BankInventory.search().withId(ItemID.MOLTEN_GLASS).first();
Optional<Widget> astral = BankInventory.search().withId(ItemID.ASTRAL_RUNE).first();
Optional<Widget> secondary = Bank.search().withId(config.secondary().getId()).first();
Widget make_glass = client.getWidget(14286966);
```

### Manejo de errores
Si falla alguna verificación de elemento, se incrementa el contador de errores. Si el contador de errores supera 2, el complemento se detiene.

```java
timesFailed++;

if (timesFailed > 2) {
    EthanApiPlugin.stopPlugin(this);
}
```

### Retiro de artículos
Si se encuentran todos los artículos necesarios, el complemento comienza a retirarlos del banco en cantidades precisas.

```java
BankInteraction.withdrawX(sand.get(), config.secondary().getSandAmount());
```

### Manejo de elementos secundarios
Un método adicional, `handleSecondary()`, se encarga de manejar diferentes tipos de elementos secundarios. Si algo sale mal en esta función, devuelve falso, lo que indica a la rutina principal que detenga el complemento.

```java
Optional<Widget> secondary = Bank.search().withId(config.secondary().getId()).first();
if (secondary.isEmpty()) {
    client.addChatMessage(ChatMessageType.GAMEMESSAGE, "", "no secondary second try", null);
    return false;
}

if (config.secondary() == Secondary.GIANT_SEAWEED) {
    MousePackets.queueClickPacket();
    WidgetPackets.queueWidgetAction(secondary.get(), "Withdraw-1");
    MousePackets.queueClickPacket();
    WidgetPackets.queueWidgetAction(secondary.get(), "Withdraw-1");
    MousePackets.queueClickPacket();
    WidgetPackets.queueWidgetAction(secondary.get(), "Withdraw-1");
    return true;
}

BankInteraction.withdrawX(secondary.get(), config.secondary().getSandAmount());
return true;
```

### Lanzamiento del hechizo
Finalmente, si todos los pasos son exitosos, el complemento lanza el hechizo Super Glass Making a través de un paquete de clics y queueWidgetAction.

```java
MousePackets.queueClickPacket();
WidgetPackets.queueWidgetAction(make_glass, "Cast");
```
<sup> Hay una forma más fácil de hacer esto: crear una clase de Manejo Mágico, podemos cubrir la carta - Cago </sup>

### Tiempo de espera
Después de realizar una operación, se establece un tiempo de espera de 3 tics para evitar que el método se vuelva a activar de inmediato.

```java
timeout = 3;
```

Este tiempo de espera se utiliza posteriormente en algún lugar al comienzo de onGameTick de la siguiente manera:

```java
if (timeout > 0){
  timeout--;
  return;
}
```
<sup> 

En proceso

Para ver el código completo, consulte el siguiente enlace: [SuperGlassMakerPlugin](https://github.com/Ethan-Vann/EthanVannPlugins/tree/master/src/main/java/com/example/superglass) 

</sup>

---

## 3.3 Cargador de complementos Kotori

<sup> 

En curso

</sup>


---

## 3.4 Reflexión sobre el paquete de juego

><i>" Los archivos mixin en RuneLite sirven como conexiones al cliente del juego, lo que permite a los desarrolladores acceder a métodos y datos específicos. Estos archivos se mantienen privados y ofuscados, lo que significa que su funcionamiento interno está oculto. Cuando se inicializa RuneLite, estos archivos mixin se cargan para inyectar o recuperar información del juego de forma lógica.
<br><br>Para entender los mixins, consideremos un par de ejemplos. Imaginemos que queremos obtener datos sobre el widget de hechizo seleccionado actualmente en el juego. En este caso, usamos un gancho para acceder directamente a la información necesaria desde el cliente del juego. Por otro lado, si necesitamos determinar el ID de animación de un personaje, es posible que necesitemos información adicional de diferentes campos. Aquí es donde entra en juego un mixin, que nos ayuda a acceder a esos campos específicos para calcular el ID de animación correctamente.
<br><br>Encontrar los nombres de los métodos ofuscados en el cliente parcheado de RuneLite implica un proceso simple. Por ejemplo, si buscamos el nombre ofuscado del método "getAnimationID", podemos obtener una instancia de la clase relevante, como un Actor. Al llamar a un método en esa instancia y registrar el resultado, podemos identificar el nombre ofuscado que buscamos.
<br><br>Normalmente, los nombres de métodos ofuscados tienen un parámetro adicional en comparación con sus versiones originales no ofuscadas. Este parámetro adicional suele ser un valor descartable, como un entero. Al observar la cantidad de parámetros y verificar si hay alguno adicional, podemos identificar el método ofuscado.
<br><br>Los archivos Mixin y los ganchos permiten a los desarrolladores mejorar la funcionalidad del cliente RuneLite. Permiten el acceso a información específica del juego y admiten operaciones más complejas. En los casos en los que RuneLite no proporciona ganchos integrados para ciertos métodos del paquete de juegos, los desarrolladores pueden utilizar mixins y ganchos para interactuar con ellos y lograr sus objetivos deseados. Esta flexibilidad permite a los desarrolladores personalizar y mejorar el cliente RuneLite para que se ajuste a sus necesidades.
>"</i>
>
> -- <cite>[SkylerMiner](#SkylerMiner) 7/18/2023</cite>

<sup>
En curso
</sup>

---

## 3.5 Actualizaciones de revisión
Esta sección cubrirá las diferencias básicas entre los dos tipos de actualizaciones de revisión que se ven más comúnmente en el mercado de desarrollo de complementos de Runelite. Esto ayuda a comprender qué está sucediendo y posiblemente podría ayudarlo a comenzar a poder ayudar a actualizar las revisiones en el futuro.

### ¿Qué es una actualización de revisión?
Una actualización de revisión significa una "actualización de revisión". Cuando esto sucede, Runelite ha enviado una actualización de mixin que cambia su ofuscación. O Jagex ha actualizado el paquete de juego base que cambia casi todos los nombres de métodos ofuscados a los que intentamos acceder.

### Actualizaciones de sub-revisión
Las actualizaciones de sub-revisión son lo que sucede cuando Runelite envía una actualización. Esto es cuando actualizan sus mixins. Este es un término que es una capa "intermedia" del proceso de inyección que permite a Runelite inyectar un bytcode específico en el paquete de juego original. Esto les permite agregar ganchos al paquete de juego, así como métodos y campos de captura reales que los convierten en una llamada de método más útil. Esto significa que cualquiera de sus métodos específicos que necesite reflejar tendrá que cambiar. Por ejemplo, si puede ver que Runelite se actualizó recientemente, puede estar seguro de tener algunos problemas con el desarrollo de complementos si su repositorio depende de algún método API de Runelite reflejado. Dichos métodos incluyen cosas como getAnimation() en la clase de actor y getPath() de Npcs/Players. Estos dependen de los mixins base de RuneLite, por lo que tendrá que obtener los nombres ofuscados más nuevos cuando ocurra este tipo de actualización.

En los repositorios basados ​​en API de Ethan, uno de los métodos reflejados es fundamental para la creación de paquetes, lo que generalmente hace que cualquiera de estos repositorios se rompa, mientras que otros repositorios que solo usan invocaciones pueden no verse afectados en un día de actualización de sub-revisión.

### Actualización de la revisión de Gamepack
Las actualizaciones de Gamepack son donde Java vuelve a ofuscar todo su código de cliente cuando lanza una nueva versión. Por lo general, ocurren en cualquier momento entre 1 mes y 3 meses entre cada revisión importante. Cuando esto sucede, tenemos que desofuscar el paquete de juegos y mapearlo con un mapeo previo del último paquete de juegos. Esto nos arroja archivos mapeados que son más legibles para humanos y nos permite obtener fácilmente los métodos/campos que queremos, pero esta salida se usa directamente en la actualización de cualquier repositorio OPRS como Storm, Squire y Devious. Mientras que otros repositorios usan una combinación de esta salida y otras entradas para mapear el nombre de clase/campos/métodos que necesitan.

El nivel de dificultad aquí es realmente comprender qué está sucediendo para empezar y las personas que no entienden cómo se refleja el paquete de juegos para cambiar los métodos del cliente pueden tener dificultades para intentar esto. Además, la dificultad depende del tipo de cliente para el que sea la actualización de rev.

Si la actualización es para un cliente estrictamente basado en invocación sin actualizaciones de reflexión adicionales, se puede realizar en alrededor de 10 a 30 minutos. Los clientes basados ​​en OpenOSRS tienen una cantidad decente de archivos de clase que solo necesitan convertirse en Java adecuado y garantizar que los mixins que tienen sigan funcionando correctamente. Los clientes de paquetes generalmente tienen que asegurarse de que todas las partes del paquete + nombres de campos de paquete + nodos de búfer + funciones de escritura de paquete funcionen correctamente.

<sub>
in progress
</sub>


---

# TODO:

- [ ] Ampliar la Sección 3
- [ ] Más ejemplos
- [ ] Recursos

---

# Créditos
#### [EthanVann](https://github.com/Ethan-Vann)

#### [Kotori](https://github.com/OreoCupcakes)

#### [SkylerMiner](https://github.com/SkylerPIlot)
#### [Bilbo](https://www.youtube.com/watch?v=Z65DM37RhyY)
#### [Cago](https://github.com/CagoThaPlug)

---

## Recursos adicionales

Para obtener recursos adicionales, referencias y soporte continuo de la comunidad, consulte lo siguiente:

### Repositorios de interés

- EthanVann Forks
    - [PiggyPlugins](https://github.com/0Hutch/PiggyPlugins)
    - [ImpactPlugins](https://github.com/moneyprinterbrrr/ImpactPlugins)
    - [Oluiscabral](https://github.com/oluiscabral/runescape-plugins)
    - [RuneBotEVP](https://github.com/KALE1111/RuneBotEVP)
    - [KatAnalPlug](https://github.com/PaJauKat/KatAnalPlug)

<br>

<sup> ¿Quieres añadir a la lista? ¡Envíame un mensaje privado o envíame un mensaje directo en Discord! </sup>

---

## Información de contacto

- Discord: .zalc (ID de usuario: 242837834120036353)
- Discord: cagomyre (ID de usuario: 1072925304982614138)
- Discord: bilbomyre (ID de usuario: 693075521051033602)

Solo tengo estos dos Discord. Nunca te enviaré un mensaje privado desde otro. <br> Si recibes un mensaje privado de alguien que dice ser yo, no soy yo.

Lo mismo ocurre con el Discord de Bilbo.

---

¿Quieres dar las gracias?
<br>
<br>
[![coinbase](https://img.shields.io/badge/Donate-Coinbase-blue.svg)](https://commerce.coinbase.com/checkout/57579fb4-002e-4a2a-a4a3-a1cf523c2dfd)

---

[![CagoThaPlug - LEECH](https://img.shields.io/static/v1?label=CagoThaPlug&message=LEECH&color=grey&logo=github)](https://github.com/CagoThaPlug/LEECH "Go to GitHub repo")
![](https://komarev.com/ghpvc/?username=CagoThaPlug&label=PROFILEVIEWS)
![License](https://img.shields.io/badge/License-BSD--3--Clause_license-grey)

<br>
    
![stars - LEECH](https://img.shields.io/github/stars/CagoThaPlug/LEECH?style=social)
![forks - LEECH](https://img.shields.io/github/forks/CagoThaPlug/LEECH?style=social)


<sup>[Back to Top](#table-of-contents)</sup>

---
