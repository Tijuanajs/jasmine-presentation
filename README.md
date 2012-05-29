Jasmine-presentation
====================

# Que es el BDD
El BDD se ofrece como respuesta a las limitantes del TDD, es una manera nueva de describir comportamiento mas que a las pruebas que acompañan el software.

# Algunas características del BDD
. Los enunciados inician por should
. Describe comportamiento y no pruebas
. Determinar el siguiente comportamiento mas importante
. Los requerimientos son pruebas también

# Domain Driven Design:

> Como un [x]
> Quiero [y]
> para que [z]

# Jasmine
http://pivotal.github.com/jasmine

Jasmine es un marco de trabajo de BDD para probar código Javascript

* No depende de ningún otro marco de trabajo
* No requiere un DOM
* Nos permite realizar pruebas de manera limpia y obvia

Alternativas: JSpec, JSSpec, Screw.Unit

# Las Suites describen tus pruebas
Una suite de pruebas comienza por la función `describe` con dos parámetros, una cadena ( string ) y una función.

La cadena es el nombre de la suite, y la función es el código que la implementa.

# Specs
Las especificaciones o "Specs" se definen con la función `it`, muy parecida a describe utiliza una cadena y la función del spec ( o prueba ).
Un spec puede tener una o mas expectativas que prueban el estado del código dentro de la prueba.

Una expectativa en Jasmine es una aseveración de que algo es verdadero o falso. Un spec con todas sus expectativas verdaderas significan que el spec es satisfactorio. Un spec con una o mas expectativas que evalúen a falso, es un spec que fallo.

# Ejemplo ( de la pagina ):

```
describe("A suite", function() {
  it("contains spec with an expectation", function() {
    expect(true).toBe(true);
  }
}
```

# `describe` e `it`

Jasmine nos dice que `describe` y `it` son solo funciones, pueden contener código necesario para implementar la prueba. Las reglas de "scope" de Javascript aplican aquí, así que si se declara algo dentro de un `describe` este estará disponible a los bloques `it` dentro de la suite.

# Expectations
Se construyen con la función `expect` que toma un valor llamado `actual`. y se encadena con una función `matcher` con el valor esperado.

# Matchers
Cada matcher toma una comparación booleana que le reporta a Jasmine si la expectativa fue falsa o verdadera. se puede evaluar a `false` si se utiliza `not` antes de llamar al matcher.

# Algunos Matchers

Todos comienzan con el código `expect(foo).`

* `toEqual(bar);`  compara objetos o primitivos de `foo` y `bar` y es satisfactorio si son equivalentes.
* `toBe(bar)` pasa si `foo` y `bar` son el mismo objeto.
* `toBeDefined()` pasa si `foo` no es `undefined`

por mostrar algunos. la lista completa la podemos observar en [ Jasmine Matchers ]( https://github.com/pivotal/jasmine/wiki/Matchers ) así como un ejemplo de construir uno personalizado.

# Agrupar Specs, Setup y Teardown y Anidar suites
* Podemos agrupar specs dentro de suites, el nombre de la suite se combinara junto con el del spec. El nombre resultante sera el nombre completo del spec.
* Se puede ejecutar código antes y después de cada spec dentro de una suite utilizando las funciones `beforeEach` y `AfterEach`
* Otra característica importante es que podemos anidar funciones `describe` dentro de otras

# Espías

Los espías son los "dobles" de las pruebas nos permiten espiar, falsificar y realizar "mocks". Un espía reemplaza a la función que esta espiando.

## matchers:
* `toHaveBeenCalled` verdadero si el espía ha sido llamado.
* `toHaveBeenCalledWith` verdadero si la lista de argumentos corresponde a la lista de argumentos para cualquiera de las llamadas grabadas al espía.

# Soporte Asíncrono
* Los specs se escriben con llamadas a `runs`, que usualmente terminan con una llamada asíncrona.
* El bloque `waitsFor` toma una función que se ejecuta repetidamente hasta que regrese verdadero o expire el limite de tiempo. Si expira el spec falla.
* Finalmente otro `runs` define el comportamiento final de la prueba, usualmente expectativas basadas en lo que regrese la llamada asíncrona.

# Ejecución y el Reporteador
Se debe incluir Jasmine a un ambiente Javascript para que pueda ejecutarse.
El objeto HTMLReporter proporciona resultados de cada suite y de cada spec.

# Jasmine esta disponible:
* De manera autónoma
* Como gem de Ruby
* Para Node.js
* Java
* Django
* .NET

# Referencias y material de ejemplo de:
* Google group [http://groups.google.com/group/jasmine-js](http://groups.google.com/group/jasmine-js)
* Twitter [http://twitter.com/JasmineBDD](http://twitter.com/JasmineBDD)

* [http://dannorth.net/introducing-bdd](http://dannorth.net/introducing-bdd)
* [http://pivotal.github.com/jasmine/]( http://pivotal.github.com/jasmine/ )
* Espías - Jasmine wiki [ Spies ](https://github.com/pivotal/jasmine/wiki/Spies)

Aviso de excención:
*Tijuana.js no esta asociado con Jasmine o Pivotal de ninguna manera*

*Jasmine es software Open Source bajo la licencia MIT*

*Jasmine es una marca de Pivotal Labs.*

*Logos y marcas son propiedad de sus respectivos propietarios.*
