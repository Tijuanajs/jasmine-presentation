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

# Ejemplo ( de la pagina ):

```
describe("A suite", function() {
  it("contains spec with an expectation", function() {
    expect(true).toBe(true);
  }
}
```
