+++
title = 'Sintaxis Básica de Java'
date = '2024-10-20'
author = 'Eric J. Hernandez J.'
description = 'Sintaxis básica del lenguaje de programación Java'
categories = ['Programación']
tags = ['Java', 'Sintaxis']
series = ['Aprendiendo Java']
aliases = ['sintaxis-basica-de-java', 'sintaxis-java', 'java-sintaxis']
draft = false
+++

Repaso de la sintaxis básica de este lenguaje de programación. Esto incluye cosas como reglas para nombrar componentes, modificadores de acceso, tipos de variables, etc., entre otras cosas básicas.

## Lo Básico

- Java es **case sensitive**, lo que significa que distingue entre mayúsculas y minúsculas.
- Los nombres de las **clases** siempre **inician con mayúscula**.
- Los nombres de los **métodos** deben **iniciar con minúscula**.
- El nombre del archivo debe tener el **mismo nombre que la clase** que contiene, y debe terminar con la extensión **.java**. En caso de que no se tenga una clase pública en el archivo, éste se puede llamar de otra forma. Tampoco es obligatorio tener una clase pública en el archivo.
- El programa siempre **inicia desde el método `main()`**, el cual es necesario para iniciar todo programa Java.

## Identificadores

Todos los componentes necesitan un nombre, a este nombre se le conoce como **identificador**. Todas las clases, métodos, variables, etc. deben tener un identificador.

- Todos los identificadores pueden iniciar con una letra (A-Z, a-z), símbolo de dólar ($) o guión bajo (\_).
- Después del primer carácter se puede continuar el identificador con cualquier combinación.
- Está prohibido usar **Keywords** como identificadores ya que están apartadas por Java.

Ejemplos de como nombrar identificadores:

✅ age, $salary, \_value, \_\_1\_value

❎ 123abc, -salary

## Modificadores

Es posible modificar clases, métodos, etc. usando **modificadores**.

### Modificadores de Acceso

- `default`: Cuando no se especifica el modificador de acceso para la clase, método o miembro, se dice que tiene el **modificador por defecto**, o sea el `defualt`. Esto significa que las cosas con este modificador **solo son accesibles en el mismo paquete**.
- `private`: Todo lo que sea declarado como `private` es **sólo accesible en la clase en la que son declarados**.
    * Cualquier otra clase del mismo paquete no puede acceder a estos miembros.
	* Clases de top-level o interfaces no pueden ser `private`.
- `protected`: Todo lo que sea declarado como `protected` **sólo es accesible desde el mismo paquete** o subclase en diferentes paquetes.
- `public`: Tiene el alcance más grande. Todo lo declarado como `public`puede ser **accesible desde cualquier parte del programa**.

|                                  | default | private | protected | public |
| -------------------------------- | ------- | ------- | --------- | ------ |
| Misma clase                      | ✅       | ✅       | ✅         | ✅      |
| Misma subclase de paquete        | ✅       | ❎       | ✅         | ✅      |
| Misma no-subclase de paquete     | ✅       | ❎       | ✅         | ✅      |
| Diferente subclase de paquete    | ❎       | ❎       | ✅         | ✅      |
| Diferente no-subclase de paquete | ❎       | ❎       | ❎         | ✅      |

### Modificadores Sin Acceso

- `final`: En una **clase** indica que esta **no puede ser extendida**, o que un **método** **no puede ser sobrescrito**.
- `static`: La entidad a la que se le asigna está **disponible fuera de cualquier instancia de la clase**. Esto significa que los métodos estáticos o los atributos son **parte de la clase y no un objeto**.
- `abstract`: Se usa para declarar una **clase como parcialmente implementada**. O sea, que **un objeto no puede ser creado directamente** de esa clase abstracta. `abstract` no puede ser usado con `static`, `final` o `private` porque previenen anulación y necesitamos anular métodos en el caso de una clase abstracta.
- `synchronized`: Previene que un bloque de código sea **corrido por múltiples hilos a la vez**.
- `volatile`: Solo es aplicable a una variable. Sirve para que los cambios hechos a variables sean **reflejados a través de todos los hilos que están accediendo a la misma variable**.
- `transient`: Se le puede aplicar a variables de una clase para indicar que **una variable no debería ser serializada** cuando la clase contenedora es serializada.
- `native`: Se le puede aplicar a un método para indicar que **ese método se implementó en otro lenguaje de programación** como _C_, _C++_ o _ensamblador_.

## Otras cosas

Las variables pueden tener ciertos alcances como.

- **Locales**
- **Variables de clase** (static)
- **Variables de instancia** (non-static)

Los **arrays/arreglos** sirven almacenar **múltiples variables del mismo tipo**.

Los `enum` restringen una variable para tener **uno de unos pocos valores predefinidos**.

## Fin

Seguiré subiendo y actualizando mi contenido conforme voy aprendiendo sobre Java, Spring, Linux, sistemas operativos, entre otros temas relacionados. 🤓
