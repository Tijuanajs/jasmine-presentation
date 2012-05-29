jasmine-presentation
====================

Jasmine demo presentation

# Que es el BDD
El BDD se ofrece como respuesta a las limitantes del TDD, es una manera nueva de describir comportamiento mas que a las pruebas que acompañan el software.

# Algunas caracteristicas del BDD
. Los enunciados inician por should
. Describe comportamiento y no pruebas
. Determinar el siguiente comportamiento mas importante
. Los requerimientos son pruebas tambien

# Domain Driven Design:

> Como un [x]
> Quiero [y]
> para que [z]

# Jasmine
http://pivotal.github.com/jasmine

Jasmine es un marco de trabajo de BDD para probar codigo Javascript

* No depende de ningun otro marco de trabajo
* No requiere un DOM
* Nos permite realizar pruebas de manera limpia y obvia

Alternativas: JSpec, JSSpec, Screw.Unit

# Las Suites describen tus pruebas
Una suite de pruebas comienza por la funcion `describe` con dos parametros, una cadena ( string ) y una funcion.

La cadena es el nombre de la suite, y la funcion es el codigo que la implementa.

# Specs
Las especificaciones o "Specs" se definen con la funcion `it`, muy parecida a describe utiliza una cadena y la funcion del spec ( o prueba ).
Un spec puede tener una o mas expectativas que prueban el estado del codigo dentro de la prueba.

Una expectativa en Jasmine es una aseveracion de que algo es verdadero o falso. Un spec con todas sus expectativas verdaderas significan que el spec es satisfactorio. Un spec con una o mas expectativas que evaluen a falso, es un spec que fallo.

# Ejemplo ( de la pagina ):

```
describe("A suite", function() {
  it("contains spec with an expectation", function() {
    expect(true).toBe(true);
  }
}
```

# `describe` é `it`

Jasmine nos dice que `describe` y `it` son solo funciones, pueden contener codigo necesario para implementar la prueba. Las reglas de "scope" de Javascript aplican aqui, asi que si se declara algo dentro de un `describe` este estara disponible a los bloques `it` dentro de la suite.

# Expectations
Se construyen con la funcion `expect` que toma un valor llamado `actual`. y se encadena con una funcion `matcher` con el valor esperado.

# Matchers
Cada matcher toma una comparacion booleana que le reporta a Jasmine si la expectativa fue falsa o verdadera. se puede evaluar a `false` si se utiliza `not` antes de llamar al matcher.

# Algunos Matchers

Todos comienzan con el codigo `expect(foo).`

* `toEqual(bar);`  compara objetos o primitivos de `foo` y `bar` y es satisfactorio si son equivalentes.
* `toBe(bat)` pasa si `foo` y `bar` son el mismo objeto.
* `toBeDefined()` pasa si `foo` no es `undefined`

por mostrar algunos. la lista completa la podemos observar en [ Jasmine Matchers ]( https://github.com/pivotal/jasmine/wiki/Matchers ) asi como un ejemplo de construir uno personalizado.

# Agrupar Specs, Setup y Teardown y Anidar suites
* Podemos agrupar specs dentro de suites, el nombre de la suite se combinara junto con el del spec. El nombre resultante sera el nombre completo del spec.
* Se puede ejecutar codigo antes y despues de cada spec dentro de una suite utilizando las funciones `beforeEach` y `AfterEach`
* Otra caracteristica importante es que podemos anidar funciones `describe` dentro de otras

# Espias

Los espias son los "dobles" de las pruebas nos permiten espiar, falsificar y realizar "mocks". Un espia reemplaza a la funcion que esta espiando.



# Referencias y material de ejemplo de:

* [http://dannorth.net/introducing-bdd](http://dannorth.net/introducing-bdd)
* [http://pivotal.github.com/jasmine/]( http://pivotal.github.com/jasmine/ )
* Espias - Jasmine wiki [ Spies ](https://github.com/pivotal/jasmine/wiki/Spies)
