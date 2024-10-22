+++
title = 'Tipos de Variables y Tipos de Datos de Java'
date = '2024-10-22'
author = 'Eric J. Hernandez J.'
description = 'Qué son las variables, tipos de variables y tipos de datos de Java'
categories = ['Programación']
tags = ['Java', 'Sintaxis', 'Variables', 'Tipos de Variables', 'Variables Locales', 'Variables de Instancia', 'Variables de Clase', 'Tipos de Datos', 'Tipo de Dato Primitivo', 'boolean', 'byte', 'char', 'short', 'int', 'long', 'float', 'double', 'Tipo de Dato No Primitivo', 'String', 'Class', 'Object', 'Interface', 'Array']
series = ['Aprendiendo Java']
aliases = ['tipos-de-variables-y-tipos-de-datos-de-java', 'tipos-variables-datos-java']
draft = false
+++

Repaso sobre las **variables**, **tipos de variables** y **tipos de datos** que hay en **Java**, entre otras cosas respecto a como podemos almacenar información en la memoria.

## Variables

Las variables son **contenedores** que guardan información durante la ejecución del programa Java. Una variable tiene asignado un **tipo de dato**, el cual se encarga de asignar el **tipo y cantidad de información** que puede contener. Es la **unidad básica de almacenamiento** de nuestro programa.

Aquí algunas características:

- El valor almacenado **puede cambiar durante la ejecución** del programa.
- Estas variables son un nombre que se le da a un **lugar en memoria**.
- Las operaciones hechas a una variable **afectan su lugar en la memoria**.
- Todas las variables **deben ser declaradas antes de su uso**.

### Declaración

La declaración de una variable consta de dos componentes:

- **Tipo de dato**: Asigna el tipo y cantidad de información que puede almacenar.
- **Identificador**: Es el nombre de la variable.

```
int myVar;
```

Aunque ya le dimos nombre a una **sección en memoria**, esta no contiene nada. O eso es lo que se podría pensar, porque realmente ya está ocupando **4 bytes en memoria**.

Hay dos formas de darle un valor a esta variable: **Inicializando** la variable o asignándole un **valor por entrada**.

### Inicialización

A diferencia de la forma anterior, en la inicialización se le asigna el valor a la variable **en el mismo momento**. Para esto se requieren tres componentes:

- **Tipo de dato**: Tipo y cantidad de información que puede almacenar.
- **Identificador**: Nombre de la variable.
- **Valor**: Valor inicial que almacenará.

```
int myVar = 22;
```

En este caso ya apartamos **4 bytes en memoria**, en los cuales estamos **almacenando el número 22**.

## Tipos de Variables

### Variable Locales

Se le llama variable local a una variable que es **definida en un bloque, método o constructor**.

- Estas variables **son creadas cuando se declaran** y **se destruyen al salir del bloque** o cuando la llamada regresa de la función.
- El **alcance** de estas variables solo **existe en el bloque donde son declaradas**. Solo se pueden acceder a esas variables desde dentro de su propio bloque.
- La **inicialización** de estas variables es **obligatoria antes de usarlas**.

### Variables de Instancia (no-estáticas)

Estas variables son no-estáticas y son **declaradas en una clase fuera de cualquier método, constructor o bloque**.

- Son **declaradas en una clase**.
- Se **crean y se destruyen junto con el objeto** creado de esa clase.
- Se les puede asignar un **especificador de acceso**. Aunque si no lo haces manualmente, lo hará Java, asignándole el `default`.
- No es necesaria su **inicialización**. Según su tipo de dato se le asigna un **valor por defecto**. Para un `String` es `null`, para un `int` es `0`.
- Solo pueden acceder a estas variables **si se crea un objeto**.
- Se inicializan usando **constructores mientras se crea un objeto**.

### Variables de Clase (estáticas)

- Son declaradas de forma similar a las variables de instancia, pero en este caso **se usa la palabra reservada _static_** en una clase **fuera de cualquier método, constructor o bloque**.
- Solo se puede tener **una copia de una variable estática por clase**, sin importar cuantos objetos sean creados.
- **Se crean al inicio de la ejecución** del programa y **se destruyen cuando la ejecución termina**, esto de forma automática.
- No es necesaria su **inicialización**. Según su tipo de dato **se le asigna un valor por defecto**.
- No pueden ser declaradas localmente **dentro un método de una instancia**.

### Notas Sobre Tipos de Variables

Las **variables estáticas** son **buenas para el manejo de memoria**, esto porque a diferencia de las **variables no-estáticas**, que **crean una copia de la variable para cada objeto**, las estáticas solo son una, o sea que **solo tenemos una copia de esa variable por clase**, sin importar cuantos objetos creemos de esa clase.

Si le hacemos **algún cambio a una variable no-estática en algún objeto**, los demás objetos de esa misma clase **no serán afectados**. Pero si hacemos **un cambio a una variable estática**, los objetos derivados de esa clase **serán afectados**.

Se accede a las variable de instancia por medio de **referencias de objetos**. Y se accede a una variable de clase usando el **nombre de la clase**.

Las variables no-estáticas **se crean y se destruyen junto a su objeto**, mientras que las estáticas **se crean y se destruyen junto a la ejecución** del programa.

## Tipos de Datos

### Tipos de Datos Primitivos

Almacenan **valores individuales**, y no tienen mucha gracia por si solos. A continuación los 8 tipos de datos primitivos que tenemos en Java.

- `boolean`: Puede ser **_verdadero_ o _falso_**. Su valor por defecto es `false`. Su tamaño es de **8 bits**.
- `byte`: Permite representar tanto **números negativos como positivos**. Su valor por defecto es `0`. Su tamaño es de **8 bits**. Su rango es de **-128 a 127**.
- `char`: Guarda **caracteres Unicode**. Su valor por defecto es `\u0000`. Su tamaño es de **16 bits**. Su rango es de **0 a 255**.
- `short`: Permite representar tanto **números negativos como positivos**. Su valor por defecto es `0`. Su tamaño es de **16 bits**. Su rango es de **-32,768 a 32,767**.
- `int`: Permite representar tanto **números negativos como positivos**. Su valor por defecto es `0`. Su tamaño es de **32 bits**. Su rango es de **-2,147,483,648 a 2,147,483,647**.
- `long`: Permite representar tanto **números negativos como positivos**. Su valor por defecto es `0`. Su tamaño es de **64 bits**. Su rango es de **-9,223,372,036,854,775,808 a 9,223,372,036,854,775,807**.
- `float`: Permite representar **número punto flotante**. Su valor por defecto es `0.0`. Su tamaño es de **32 bits**. Su rango es de **hasta 7 dígitos decimales**.
- `double`: Permite representar **número punto flotante**. Su valor por defecto es `0.0`. Su tamaño es de **64 bits**. Su rango es de **hasta 16 dígitos decimales**.

#### Notas Sobre Tipos de Datos Primitivos

Los tipos de datos **`byte`, `short` y `float` son útiles para el ahorro de memoria** debido a su tamaño. 

Desde **Java SE 8 en adelante** se puede usar el tipo de dato **`int` para representar un entero de 32 bits sin signo**, o sea con un rango de \[0,2<sup>32</sup> -1]. Usar la clase _Integer_ para usar el tipo de dato `int` como un entero sin signo.

Desde **Java SE 8 en adelante** se puede usar el tipo de dato **`long` para representar un _long_ sin signo de 64 bits**, el cual tiene un valor mínimo de 0 y un máximo de 2<sup>64</sup> -1. La clase _Long_ tiene métodos para hacer operaciones aritméticas para el _long_ sin signo.

**`double` y `float`** fueron diseñados para cálculos científicos donde **los errores de aproximación son aceptables**. Pero si se requiere **mayor precisión**, se recomienda **usar la clase _BigDecimal_**.

### Tipos de Datos No Primitivos (De Referencia)

En Java, una variable de este tipo de dato **almacena una referencia a la ubicación en memoria** donde se encuentran los valores de las variables. Esto significa que , en lugar de contener directamente el valor, **la variable guarda la dirección en memoria que apunta a los datos**.

Imagina que tienes un objeto que representa un libro. Al crear una variable para este libro, en realidad estás guardando una dirección donde se encuentran todos los detalles del libro, como el título y el autor.

#### String

Se definen como un **arreglo de caracteres**. La diferencia entre un arreglo de caracteres y un _string_, es que los _strings_ están **diseñados para contener una secuencia de caracteres en una sola variable**, mientras que un arreglo de caracteres es una colección de entidades de tipo `char` separadas.

#### Class

En un **modelo definido por el usuario** con el que se pueden **crear objetos**. Representa el **conjunto de propiedades y métodos** que son comunes a todos los objetos de un tipo.

La declaración de una clase puede contener modificadores, nombre de la clase, superclase, interfaces, cuerpo.

#### Object

Es una **unidad básica de la Programación Orientada a Objetos**, usada para representar entidades de la vida real. Un programa en Java crea muchos objetos, los cuales interactuan invocando métodos.

Un objeto consiste de un Estado, Comportamiento y Identidad.

#### Interface

Parecido a una clase, una interfaz **puede tener métodos y variables**, pero **los métodos de una interfaz son abstractos** por defecto.

- Una interfaz especifica **qué debe hacer una clase, no el cómo debe hacerlo**.
- Se relaciona con **capacidades**. Especifica un conjunto de métodos que la clase debe implementar.
- Si una clase **implementa una interfaz y no proporciona cuerpos de métodos** para todas las funciones especificadas en la interfaz, la clase debe ser declarada como **abstracta**.

#### Array

Un **arreglo o matriz**, es un **grupo de variables del mismo tipo** a las que se hace referencia por un nombre en común.

- Como **los arreglos son objetos**, estos contienen miembros útiles como _length_, para saber la longitud.
- Las variables en un arreglo son **ordenadas y cada una tiene un índice**.
- El **tamaño de un arreglo** debe ser **especificado por un valor tipo `int`** y no por un `long` o `short`.
- La **superclase** directa del _array_ es **_Object_**.

#### Notas Sobre Tipos de Datos No Primitivos

Todos los arreglos son asignados de forma **dinámica**.

Una vez que se crea un _String_, este **no puede ser cambiado**, esto para asegurar **seguridad en entornos de multiples hilos**.

La longitud de un arreglo es **fija** una vez que se declara.

## Fin

Recuerda analizar bien el tipo de dato que vas a usar para almacenar la información, de esta forma optimizas la memoria y evitas errores.
