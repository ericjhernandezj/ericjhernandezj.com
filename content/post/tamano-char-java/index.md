+++
title = 'Tamaño de char. ¿Por qué es diferente en Java?'
date = '2024-10-24'
author = 'Eric J. Hernandez J.'
description = '¿Por qué el tamaño del char es diferente en Java? En este post, descubrirás las razones y cómo afecta a tus programas.'
categories = ['Programación']
tags = ['ASCII', 'Unicode', 'Java', 'C/C++']
series = ['Aprendiendo Java']
aliases = ['tamano-de-char-en-java']
draft = false
+++

El **tipo de dato _char_** es fundamental en muchos lenguajes de programación, pero **su tamaño varía dependiendo de su implementación**.

En este pequeño post veremos **el porqué de su tamaño en Java** y por qué es más grande que en otros lenguajes como C o C++.

## ASCII y Unicode

Otros lenguajes como **C y C++ solo usan caracteres ASCII**, los cuales se pueden representar con **7 bits**, por lo que solo se necesitan 8 bits, o sea, **1 byte para representar todos los caracteres ASCII**, los cuales son 128, que van desde letras (A-Z, a-z) y números (0-9) hasta caracteres especiales y la tecla Enter. El **ASCII no admite caracteres acentuados ni de otros idiomas** que no sea el inglés.

Pero **en Java, se usa el Unicode**, un estándar **más reciente a comparación del ASCII**, el cual usa 16 bits (**2 bytes**) para representar sus caracteres (0-65535). Entre estos caracteres podemos encontrar los del ASCII más caracteres acentuados, caracteres de casi todos los idiomas del mundo, símbolos matemáticos, emojis, entre muchos otros.

De esta forma **Java nos ofrece una gama más amplia de caracteres** para usar en nuestros programas.

## En Pocas Palabras...

**C y C++** usan el estándar **ASCII**. **Java** usa el estándar **Unicode**.
