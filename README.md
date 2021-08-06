# Sass
Sass *(Syntactically Awesome StyleSheets)* es una extencio de CSS que añade caracteristicas muy potentes y elegantes a este lenguahe de estilos.

Sass es basado en Ruby a diferencia de Less y Stylus que se basan en Javascript.

Sass nos permite usar variables , reglas anidadas , mixins y funciones.  
La razón de que en SASS usemos la extensión ‘.scss’ es porque esta nos permite usar una sintaxis muy parecida a css.  
La otra opción es usar SASS con la extensión ‘.sass’ la única diferencia es que con esta extensión podremos omitir las llaves ‘{}’ y los punto y coma ‘;’ después de cada valor, esta sintaxis interpretará los atributos y valores por medio de la identación.

## Variables
En las variables almacenamos datos que se puede reutilizar en todas nuestras hojas de estilos. Así evitamos tener que escribir lo mismo una y otra vez cuando se realiza algún cambio, ya que sólo vamos a modificar el valor de la variable y se aplicará a todos los lugares donde sea usada.

Comúnmente almacenamos en variables las guías de estilo de nuestro sitio, como pueden ser los colores y fuentes.

Declar:
`$Font-1: "Loto", sans-serif;`

Invocar:
`$family-font: $Font-1;`
## Imports y Extends
**Import** nos permite escribir código modular separando en diferentes archivos para después importarlos todos en uno solo y tener una base código mucho más ordenada.
Usamos **_modulo.scss** para que no se compile.
```
@import "ruta.scss"
```
**Extends** sirve para insertar los estilos de un selector en otro.

```
.boton {
	padding: 20px;
	text-transform: uppercase;
	text-align: center;
	font-size: 1.4rem;
	font-weight: 700;
}
.boton-texto {
	@extend .boton;
}
```
## Mixins
Su finalidad es ofrecer una funcionalidad que pueda ser **reutilizada** en otras clases pero que no está pensada para usarse de forma autónoma. Nos permite crear bloques reusables de código que cambian su resultado dependiendo del parámetro que enviemos.

Con los mixin logramos escribir menos código, produciendo un código más claro, más expresivo y sobre todo más fácil de mantener.

Declarar: 
```
@mixin  caja {
	border-radius: 20px;
	box-shadow: 0px 20px 33px 0px rgba($color-primario,0.50);
color: $color-primario;
background-color: $color-claro;

}
```
Invocar:
```
.estadistica--perfil {
	display: flex;
	width: 50%;
	height: 90px;
	margin: 0  auto;
	padding-top: 15px;
	justify-content: space-around;
	@include  caja;
```
## Funciones
La diferencia entre mixins y funciones es que las funciones por general hacen cálculos y regresan un resultado que es usado como valor de alguna propiedad.

Declarar:
```
@function  get-opacity($color, $nivel) {
	@return  rgba($color, $nivel);
}
```
Invocar:
```
background-color: get-opacity($color-primario, .20);
```
## Loops
Un **loop** es un fragmento de código que va a ejecutar de forma repetitiva hasta que cumpla una condición.

Declarar:
```
@each  $header, $size  in (h1: 30px, h2: 25px ,h3: 20px) {
	#{$header} {
		font-size: $size;
		margin: 0;
	}
}
```
## Condicionales
Un condicional nos permite evaluar cierta condición y bifurcar entre dos caminos dependiendo de si se cumple o no.

Declaracion:
```
@mixin  titulos($fuente) {
	@if  $fuente==$Fuente1 {
		font-family: $Fuente1;
	} @else {
		font-family: $Fuente2;
		text-transform: uppercase;
	}
}
```
# Referencias

[Platzi-games-Sass](https://github.com/daywalkerhn/platzi-games-sass-publico)

[Documentacion de Sass](https://sass-lang.com/documentation/at-rules/control/each)
