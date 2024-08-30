# SECCION 6: CSS DISEÑANDO SITIOS WEB CON FLEXBOX

# 71. Introduccion a flexbox y propiedades para elementos padre

Flexbox es un conjunto de propiedades que nos permiten distribuir nuestros elementos de una forma flexible para mejores layouts / plantillas o diseños mas facilmente

Para utilizar flexbox necesitamos un contenedor padre que tenga elementos hijos. Ya que a estos son los que se haran flexiblex.

Flexbox se divide en 2 grupos de propiedades:
	- Propiedades para los elementos padre
	- Propiedades para los elementos hijo

=================================
Propiedades del contenedor padre:
=================================

- display:flex;
	Nos permite habilitar que los elementos hijos sean flexibles

- flex-direction:;
	row | row-reverse | column | column-reverse

- flex-wrap: si las cajas no caben en la fila, se moverán a la siguiente línea, manteniendo el diseño ordenado
	no-wrap | wrap | wrap-reverse

- flex-flow: <flex-direction> || flex-wrap;
	Es un atajo de flex-direction y flex-wrap.


- justify-content:;
	flex-start | flex-end | center | space-between | space-around


- align-items:;
	flex-start | flex-end | center | stretch | baseline


- align-content:;
	IMPORTANTE: Esta propiedad solo funciona cuando hay mas de una linea de elementos.

	flex-start | flex-end | center | stretch | space-between | space-around

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flexbox</title>
    <link rel="stylesheet" href="flexbox.css">
</head>
<body>
    <div class="contenedor">
        <div class="caja">1</div>
        <div class="caja">2</div>
        <div class="caja">3</div>
    </div>
</body>
</html>
```

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    background: #f2f2f2;
    font-family: Arial, Helvetica, sans-serif;
}

.contenedor {
    width: 80%;
    height: 700px;
    max-width: 700px;
    background-color: #212d40;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    /* flex-flow: row wrap; */
    justify-content: space-between;

    /* Cuando tenemos solo una linea de elementos */
    align-items: center; 

    /* Cuando tenemos mas de una linea de elementos */
    /* align-content: center; */
}

.caja {
    width: 100px;
    height: 100px;
    background: #f79256;
    text-align: center;
    margin: 20px;
    padding: 20px;
    font-size: 40px;
    color: #fff;
}
```

# 72. Propiedades para los elementos hijo

=================================
Propiedades de los elementos hijo
=================================

- order:;

- flex-grow:;
	Acepta un numero que servira de proporcion para hacer crecer el elemento en relacion a los otros.

	Si todos los elementos tienen flex-grow 1 el espacio restante se distribuira entre los elementos.

- flex-shrink:;
	Define la habilidad de un elemento para hacerse mas pequeño.

	Por defecto todos se pueden hacer mas pequeños pero si le ponemos flex-shrink 0 el elemento no podra ser mas pequeño que su ancho especificado.

- flex-basis:;
	Nos permite especificar el valor inicial que tendra un elemento.


- flex:1 1 auto;
	Es un atajo para flex-grow, flex-shrink y flex-basis

- align-self:;
	auto | flex-start | flex-end | center | baseline | stretch;


# 73. [PRACTICA] Diseñando una pagina con flexbox 1 - Estructura HTML

# 74. [PRACTICA] Diseñando una pagina con flexbox 2 - Estilos CSS del Header

# 75. [PRACTICA] Diseñando una pagina con flexbox 3 - Estilos CSS del Main y Aside

# 76. [PRACTICA] Diseñando una pagina con flexbox 4 - Estilos del Footer

# 77. [PRACTICA] Diseñando una pagina con flexbox 5 - Responsive Design

**MI PROPUESTA**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flexbox</title>
    <link rel="stylesheet" href="estilos.css">
</head>
<body>
    <div class="principal">
        <header>
            <div class="logo">

            </div>
            <div class="menu">
                <ul>
                    <li><a href="">Inicio</a></li>
                    <li><a href="">Blog</a></li>
                    <li><a href="">Contacto</a></li>
                </ul>
            </div>
        </header>
        <main>
            <section>
                <div class="img-principal">

                </div>
                <div class="content-article">
                    <h1>Titulo del articulo</h1>
                    <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Odio numquam voluptate unde, ab pariatur recusandae labore corrupti itaque maiores repudiandae velit, quos, facere ipsam harum consequuntur illum illo temporibus laboriosam!</p>
                    <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Possimus alias adipisci ducimus, rerum at mollitia cumque non accusantium exercitationem modi repudiandae nobis dignissimos omnis molestiae dolor labore ullam, animi autem?</p>
                </div>
            </section>
            <aside>
                <div class="content-aside">
                    <p>AD</p>
                </div>
                <div class="content-aside">
                    <p>AD</p>
                </div>
            </aside>
        </main>
        <footer>
            <div class="autor">
                <p>Creado por Walter Suel Arroyo</p>
            </div>
            <div class="redes-sociales">
                <a href="#">Facebook</a>
                <a href="#">Twitter</a>
            </div>
        </footer>
    </div>
</body>
</html>
```

```css
* {
    margin: 0px;
    padding: 0px;
}

body {
    background-image: url("img/fondo.jpg");
    background-repeat: no-repeat;
    width: 100%;
    display: flex;
    justify-content: center;
}

.principal {
    padding: 20px;
    width: 50%;
}

header {
    width: 100%;
    height: 100px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}

.logo {
    width: 50%;
    background-image: url("img/logo.png");
    background-repeat: no-repeat;
}

.menu {
    width: 50%;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    margin-right: 30px;
    font-size: 20px;
}

li {
    list-style: none;
    width: 80px;
    height: 50px;
    margin: 5px;
    display: inline-block;

}

a {
    color: white;
    text-decoration: none;
    float: left;
}

a:hover {
    text-decoration: underline;
}

main {
    display: flex;
    width: 100%;
    flex-direction: row;
}

section {
    display: flex;
    flex-direction: column;
    width: 65%;
    align-content: center;
    padding: 20px;
    background-color: white;
}

.img-principal {
    width: 100%;
    height: 200px;
    background-image: url("img/thumb.jpg");
    background-repeat: no-repeat;
}

aside {
    width: 35%;
    background-color: rgba(147, 48, 241, 0.7);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 20px;
}

.content-aside {
    width: 100%;
    height: 150px;
    background-color: rgba(88, 25, 135, 0.5);
    color: white;
    font-size: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
}

footer {
    width: 100%;
    height: 100px;
    background-color: rgb(136, 77, 194);
}

.content-article {
    margin-top: 20px;
}

h1 {
    margin-bottom: 20px;
}

p {
    margin: 10px;
    line-height: 30px;
}

footer {
    margin-top: 20px;
    color: white;
    font-size: 20px;
    display: flex;
    align-items: center;
    background-color: rgba(253, 244, 244, 0.2);
    justify-content: space-between;
}

.autor {
    width: 60%;
}

.redes-sociales {
    width: 40%;
    display: flex;
    justify-content: flex-end;
    margin-right: 20px;
}

.redes-sociales a {
    margin: 20px;
}
```

*SOLUCION DEL PROFESOR*

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flexbox</title>
    <link rel="stylesheet" href="estilos.css">
</head>

<body>
    <div class="contenedor">
        <header>
            <div class="logo">
                <img src="img/logo.png" alt="">
            </div>
            <nav class="menu">
                <a href="#">Inicio</a>
                <a href="#">Blog</a>
                <a href="#">Contacto</a>
            </nav>
        </header>
        <section class="main">
            <article>
                <div class="thumb">
                    <img src="img/thumb.jpg" alt="">
                </div>
                <h2>Titulo del articulo</h2>
                <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Magnam quibusdam eligendi sunt dolore unde,
                    accusamus sequi deleniti natus ut iste enim voluptatibus amet perferendis tempora rem nemo expedita
                    voluptatem aspernatur?adipisicing elit. Magnam quibusdam eligendi sunt dolore unde, accusamus sequi
                    deleniti natus ut iste enim voluptatibus amet perferendis tempora rem nemo expedita voluptatem
                    aspernatur?</p>
                <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Magnam quibusdam eligendi sunt dolore unde,
                    accusamus sequi deleniti natus ut iste enim voluptatibus amet perferendis tempora rem nemo expedita
                    voluptatem aspernatur?adipisicing elit. Magnam quibusdam eligendi sunt dolore unde, accusamus sequi
                    deleniti natus ut iste enim voluptatibus amet perferendis tempora rem nemo expedita voluptatem
                    aspernatur?</p>
            </article>
        </section>
        <aside>
            <div class="ad">
                <p>AD</p>
            </div>
            <div class="ad">
                <p>AD</p>
            </div>
        </aside>
        <footer>
            <div class="autor">
                <p>Creado por Walter Suel</p>
            </div>
            <div class="redes-sociales">
                <a href="#">Fcebook</a>
                <a href="#">Twitter</a>
            </div>
        </footer>
    </div>

</body>

</html>
```

```css
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300..800;1,300..800&display=swap');

* {
    margin: 0px;
    padding: 0px;
    box-sizing: border-box;
    font-family: "Open Sans", sans-serif;
}

body {
    background: #000 url('img/fondo.jpg');
    background-size: cover;
    background-attachment: fixed;
}

.contenedor {
    margin: auto;
    width: 90%;
    max-width: 1000px;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}

header {
    width: 100%;
    padding: 50px 0px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
}

header .menu a {
    color: #fff;
    text-decoration: none;
    margin-right: 40px;
    font-size: 18px;
    
}

header .menu a:hover {
    text-decoration: underline;
}

.main {
    background: #fff;
    padding: 20px;
    width: 70%;
}

.main article .thumb {
    margin-bottom: 20px;
}

.main article .thumb img {
    width: 100%;
    vertical-align: top;
}

.main article h2 {
    margin-bottom: 20px;
    font-weight: normal;
    font-size: 32px;
}

.main article p {
    margin-bottom: 20px;
    font-size: 14px;
    line-height: 27px;
}

aside {
    width: 30%;
    background: #537dca;
    padding: 20px;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: space-between;
}

aside .ad {
    font-size: 30px;
    text-align: center;
    color: #fff;
    background: #4264a2;
    padding: 50px 0px;
}

footer {
    margin: 20px 0px;
    width: 100%;
    background: rgba(255, 255, 255, .2);
    padding: 20px;
    color: #fff;
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: space-between;
}

footer .redes-sociales a{
    color: #fff;
    text-decoration: underline;
    margin-left: 20px;
}

footer .redes-sociales a:hover {
    text-decoration: none;
}

@media screen and (max-width: 800px) {
    .main {
        width: 100%;
    }
    aside {
        width: 100%;
        flex-direction: row;
    }
    aside .ad {
        width: 40%;
    }
}

@media screen and (max-width: 600px){
    header {
        flex-direction: column;
        padding-bottom: 20px;
    }

    header .menu {
        width: 100%;
        background: rgba(255, 255, 255, .2);
        text-align: center;
        padding: 20px;
    }

    header .menu a {
        margin: 0px 20px;
    }

    header .logo {
        margin-bottom: 20px;
    }

    footer {
        flex-direction: column;
        text-align: center;
    }

    footer .autor {
        order: 2;
    }

    footer .redes-sociales {
        order: 1;
        margin-bottom: 20px;
    }
}

@media screen and (max-width: 400px){
    aside {
        display: none;
    }
}
```
# 78. CSS Grid

Hola, espero que te encuentres genial y estés aprendiendo mucho en el curso.

Mucha gente me ha estado preguntando acerca de CSS Grid, es por eso que agrego este articulo para explicar un poco que es y donde puedes aprenderlo.



"Espera un momento Carlos, ¿Que es CSS Grid?"
Respuesta:

Bueno pues CSS Grid es un nuevo sistema que tenemos con CSS y con el que podemos crear estructuras de paginas web (o a lo que se le conoce como Layouts) de una forma mucho mas fácil, correcta y que ademas nos va a permitir hacer sitios adaptables a dispositivos mas fácilmente.



"¿Eso significa que Flexbox ya no sirve?"
Respuesta:

No, Flexbox es increíblemente poderoso, genial y es una de las cosas que mas se utilizan para diseñar sitios web hoy en día.

Yo mismo no podría vivir sin Flexbox, es una de las cosas que mas me gusta de CSS!

Muchas veces cuando la gente escucha acerca de CSS Grid por primera vez creen que es el remplazo de Flexbox o que tienen que escoger entre Flexbox o CSS Grid para diseñar un sitio web. Y esto es completamente falso.

CSS Grid y Flexbox aunque son sistemas similares la realidad es que se usan para cosas diferentes ya que ambos fueron creados con un propósito diferente. Y la mayoría del tiempo se utilizan ambos.



"¿Vas a enseñar CSS Grid en el curso?".
Respuesta:

De momento no tengo planes de crear una sección de CSS Grid directamente en el curso, y la razón de esto es porque ya tengo un curso completamente gratuito de CSS Grid en mi canal de YouTube.



Así que de momento hago este articulo para invitarte a que veas el curso de CSS Grid si es que tu lo deseas.

Link del curso: https://www.youtube.com/watch?v=HpH12iNlLmg



"¿Necesito aprender CSS Grid obligatoriamente?".
Respuesta:

No, en el curso vamos a continuar trabajando con Flexbox, así que no es necesario que aprendas CSS Grid de momento.

Aunque si tu objetivo es aprender mas de diseño web entonces si que te recomendaría altamente que tomaras ese curso porque te va a enseñar muchas cosas nuevas.