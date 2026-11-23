# Bitácora portafolio Karoline Muñoz

# Links

Figma: 
GitHub Pages: 

# Referencias

https://www.briannecoglon.com/work-projects/work me gusta que usa un elemento que reemplaza el mouse.

https://a-chen.webflow.io/ me gusta mucho que exista un personaje que representa al artista, también cómo usa los colores y las tipografías, pero yo solo me quedaré con el personaje para mis referencias.

https://andwalsh.com/ la forma en la que se muestran los proyectos expandidos en la pantalla.

https://www.kindstudio.co.uk/ me gusta mucho la interacción que se hace al mostrar sus proyectos cuando uno selecciona la imagen.

Me gustaría crear una página web en la que se reflejen mayoritariamente mis proyectos universitarios y presentarme a través de un personaje que tenga atributos míos. Me guío por la referencia de A Chen, que en su página web se representa con un personaje interactivo. Mi idea es que mi personaje se vea en grande en la página de inicio y que, a medida que la navegación vaya bajando, se aleje de la pantalla hasta que se vea completo en la última sección del home.

Me gustaría presentar mis proyectos con interacciones o con un video en el que se vean varias páginas a la vez, ya que la mayoría son proyectos editoriales, y si no se puede, igual con una interacción como la de Andwalsh. También me gusta mucho Kind Studio, que al poner el mouse encima de una imagen de sus proyectos se despliega información del proyecto, lo encuentro chori. Hablando del mouse, me gustaría que fuera un glifo o algún elemento más entretenido, usando la referencia de Brianne Coglon. Me gustaría que mi portafolio fuera más personal, pero iré viendo en el proceso qué más le puedo agregar para que sea más propio.

# Avance 1 

Presenté mi idea, mis referencias y mi diseño en Figma con el home, la página de proyectos y mi UI kit.

Mis correcciones fueron arreglar mi página de proyectos y que la visualización fuera mucho más rápida, lo demás estaba ok.

Así que comencé a corregir mi home directamente en Figma y también creé el mobile que me faltaba. Hice algunos cambios para el mobile, por ejemplo que la página principal sea en blanco y solo con mi nombre, y luego con un botón se va a todos los proyectos. Agregué algunos de mis proyectos personales, mi idea es que la gran mayoría se vean en GIF, pero lo evaluaré jeje.

# Avance 2

Presenté el home corregido en Figma

Comentarios que recibí: Comenzar el HTML ya que el figma ya estaba bien.

Después comencé a preparar mi HTML. Tenía dudas sobre cómo agregar los botones, pero creo que tenía que descargar los SVG para que me aparecieran bien. Me ayudé con IA para la estructura del HTML (lo explico más abajo), pero no me quedé con ese código, lo usé de guía. Eliminé los botones que me daba, cambié los nombres de las imágenes por los míos y saqué los estilos que me había puesto dentro del HTML, porque tenían que ir en el CSS.

Al abrir mi HTML en Chrome vi que tenía muchos errores, parte del código me aparecía escrito en la página y había etiquetas mal cerradas, así que con ayuda de internet y del material complementario del Drive comencé a corregir.

Después arreglé los tamaños, por ejemplo la imagen de las muñecas me quedó en 64rem y era demasiado grande, la fui ajustando hasta que me convenció dejarla en 43rem.

También corregí las tipografías. Había agregado la JetBrains Mono pero no todos los pesos, así que agregué la Medium y le puse font-weight a los textos, porque todos estaban en regular. Por ejemplo:

```css
.presentacion p {
  margin-bottom: 1.8rem;
}
```

quedó así:

```css
.presentacion p {
  margin-bottom: 1.8rem;
  font-weight: 500;
}
```

En ese momento me faltaba agregar los íconos a algunos elementos y la interacción al apretar un proyecto.

Revisando la rúbrica me di cuenta de que tenía una sola página HTML y piden mínimo dos. En Figma ya tenía diseñadas las páginas de cada proyecto, así que las pasé a código (proyecto-01.html hasta proyecto-08.html). Ahora cada proyecto del home lleva a su página y desde ahí se vuelve con el ícono de la casa o con el botón SOBRE MÍ.

Exporté de Figma las imágenes de cada proyecto y escribí las descripciones de Jack in the box, Bicho raro y Reservoir Dogs, que en Figma tenían copiado el texto de otro proyecto. En Latin Mafia puse un video.

Exporté los íconos de mi UI kit como SVG (home, estrella, descargar, instagram y mail) y los agregué. El de descargar cambia a su variante hover y la estrella se pone roja al marcarla.

Arreglé el mobile para que quedara como mi Figma, con el logo al centro y la flecha para bajar, solo el botón SOBRE MÍ y el contacto centrado. También comparé el sitio con mi Figma y corregí tamaños de texto y de imágenes.

Al final agregué un cursor con la estrella de mi UI kit (era una de mis ideas desde el principio por Brianne Coglon) y que los proyectos del home se vean borrosos al pasar el mouse. Probé un modo blanco y negro con el botón que tenía en Figma, pero no me gustó cómo quedó, así que lo saqué del código y de mi diseño.

# Uso de IA

Usé Claude. Mi prompt fue:

```
Adjunto png de mi diseño en Figma (escritorio de 1440 px). Ayúdame solo con el HTML.
Comenta cada regla en español explicando qué hace, en lenguaje simple.
```

Me entregó un index.html con el CSS dentro de una etiqueta style y cada regla comentada en español. Las imágenes tenían rutas de ejemplo (img/proyecto-01.png, img/muneca-portada.png, etc.) y me dijo que las exportara desde Figma con esos nombres o que cambiara las rutas.

<details>
<summary>Código que me entregó</summary>

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <!-- Define la codificación para que se vean bien las tildes y la ñ -->
  <meta charset="UTF-8">
  <!-- Hace que la página se adapte al ancho del celular -->
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Karoline Muñoz · Portafolio</title>

  <!-- Descarga el archivo de la tipografía Space Mono (solo la carga; usarla se hace en el CSS) -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">

  <!-- Conecta tu archivo de estilos (aquí irá todo el diseño) -->
  <link rel="stylesheet" href="styles.css">
</head>

<body>

  <!-- Barra superior: logo y menú -->
  <header class="cabecera">
    <a class="logo" href="#" aria-label="Inicio">2</a>

    <nav class="menu" aria-label="Principal">
      <!-- Botón con el icono de interruptor -->
      <button class="boton-icono" type="button" aria-label="Cambiar modo">
        <svg width="22" height="14" viewBox="0 0 22 14" fill="none" stroke="currentColor" stroke-width="1.2" aria-hidden="true">
          <rect x="1" y="1" width="20" height="12" rx="6"/>
          <circle cx="7" cy="7" r="2.5"/>
        </svg>
      </button>
      <a href="#proyectos">Proyectos</a>
      <a href="#sobre-mi">Sobre mí</a>
    </nav>
  </header>

  <main>
    <!-- Portada: muñeca 3D -->
    <section class="portada">
      <img src="img/muneca-portada.png" alt="Ilustración 3D de Karoline con el pelo largo rubio y un vestido negro">
    </section>

    <!-- Lista de proyectos: cada <figure> es un recuadro con una imagen -->
    <section class="proyectos" id="proyectos" aria-label="Proyectos">
      <figure class="proyecto">
        <img src="img/proyecto-01.png" alt="Libro abierto con ilustraciones en azul y una silla alta dibujada">
      </figure>
      <figure class="proyecto">
        <img src="img/proyecto-02.png" alt="Portada de revista lila con una letra T grande en amarillo">
      </figure>
      <figure class="proyecto">
        <img src="img/proyecto-03.png" alt="Revista abierta con fotografías en tonos azules y rosados">
      </figure>
      <figure class="proyecto">
        <img src="img/proyecto-04.png" alt="Afiche en blanco y negro con el texto “Como te digo que Latin Mafia”">
      </figure>
      <figure class="proyecto">
        <img src="img/proyecto-05.png" alt="Páginas de revista con detalles en verde limón y tipografía grande">
      </figure>
      <figure class="proyecto">
        <img src="img/proyecto-06.png" alt="Portada “Jack in the Box” con papeles rasgados y letras rosadas">
      </figure>
      <figure class="proyecto">
        <img src="img/proyecto-07.png" alt="Tres piezas con imágenes borrosas en tonos azules">
      </figure>
      <figure class="proyecto">
        <img src="img/proyecto-08.png" alt="Afiche de Reservoir Dogs con un perro ilustrado en azul">
      </figure>
    </section>

    <!-- Sobre mí: texto, muñeca de cuerpo completo y contacto -->
    <section class="sobre-mi" id="sobre-mi">
      <div class="presentacion">
        <h2>Karoline Muñoz</h2>
        <p>Estudiante de tercer año en la Universidad Diego Portales en la carrera de Diseño en mención Gráfico. Actualmente soy parte del Laboratorio OTF de la universidad.</p>
        <p>Conocimiento en</p>
        <ul>
          <li>InDesign</li>
          <li>Letterpress</li>
          <li>Illustrator</li>
          <li>Photoshop</li>
          <li>Impresión en risografía</li>
          <li>Uso de plotter de corte</li>
        </ul>
      </div>

      <img src="img/muneca-cuerpo.png" alt="Muñeca 3D de Karoline de cuerpo completo con botas negras">

      <div class="contacto">
        <a href="https://instagram.com/258almendra" target="_blank" rel="noopener">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" aria-hidden="true">
            <rect x="3" y="3" width="18" height="18" rx="5"/>
            <circle cx="12" cy="12" r="4"/>
            <circle cx="17.2" cy="6.8" r="0.8" fill="currentColor"/>
          </svg>
          258ALMENDRA
        </a>
        <a href="mailto:karoline.munoz@mail.udp.cl">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" aria-hidden="true">
            <rect x="3" y="5" width="18" height="14" rx="2"/>
            <path d="M3.5 6.5 12 13l8.5-6.5"/>
          </svg>
          karoline.munoz@mail.udp.cl
        </a>
      </div>
    </section>
  </main>

</body>
</html>
```

</details>

No me quedé con este código porque me puso los botones de una forma que no era la que yo quería, así que lo usé de guía. Borré los botones, cambié las rutas por mis imágenes, saqué los estilos que iban en el CSS y usé mi tipografía (JetBrains Mono) en vez de Space Mono. Al borrar cosas me quedaron errores que después corregí yo.

También le pregunté:

```
¿Cómo puedo agregar las animaciones que creé en los botones a mis archivos para que funcionen?
```

Me explicó que Figma no guarda la animación dentro del SVG, entonces hay que exportar cada estado del botón como un SVG distinto (por ejemplo boton.svg y boton-hover.svg), poner los dos en el HTML y cambiar de uno a otro con CSS. Si la animación tiene varios movimientos hay que hacerla con @keyframes o exportarla como Lottie o GIF. Esto lo usé después para el ícono de descargar, que tiene sus dos estados exportados de mi UI kit.


Para la entrega final, Le mandé la rúbrica, mi index.html, mi styles.css y el link de mi Figma, y le escribí:

```
Ayúdame con mi proyecto de HTML y CSS.
```

Me revisó todo con la rúbrica y me di cuenta de que me faltaba la segunda página. Primero me propuso separar "Sobre mí" en otra página, pero eso no era lo que yo tenía en Figma, así que le mandé el link para que viera que mi segunda página era la de cada proyecto. Con eso me armó las 8 páginas de proyecto y la parte del CSS para la galería, los títulos y los íconos.

No me gustó que me cambiara mi HTML y los íconos que hizo no eran los míos y se veían gigantes, entonces le dije:

```
No cambies mi HTML que ya había hecho anteriormente, solo agrégale lo restante para hacer las otras páginas web.
Los íconos que me hiciste están enormes. Si puedes ingresar a mi UI kit, ahí están mis componentes.
```

Exporté mis propios SVG del UI kit y se los mandé para que usara esos. Los puso con tamaño fijo para que no se estiraran:

```html
<img src="iconos/home.svg" alt="" width="48" height="48">
```

Mi componente de descargar venía con sus dos estados en un solo archivo, así que lo separó en descargar.svg y descargar-hover.svg, y en el CSS cambian al pasar el mouse:

```css
.icono .hover {
  display: none;
}

a.icono:hover .normal {
  display: none;
}

a.icono:hover .hover {
  display: block;
}
```

Después puse las imágenes reales de mis proyectos y escribí yo las descripciones que faltaban.

Para el correo que se me cortaba en dos líneas le pregunté:

```
¿Qué parte del código puedo editar para evitar que pase esto?
```

Me dijo cuáles eran las líneas del CSS que lo hacían y las cambié yo:

```css
/* antes */
.contacto {
  overflow-wrap: anywhere;
}

/* después */
.contacto {
  min-width: max-content;
}

.contacto a {
  white-space: nowrap;
}
```

Y en la media query de mobile cambié `word-break: break-all;` por `min-width: 0;`.

Lo mismo con las letras que se ponían rojas al pasar el mouse:

```
¿Cómo puedo sacar que al pasar el mouse por alguna letra se ponga roja?
```

Me dijo que era esta regla y la borré completa:

```css
a:hover,
a:focus-visible {
  color: var(--color-acento);
}
```

Le pedí "¿Puedes entrar a mi Figma y revisar el mobile?" y me mostró las diferencias entre mi Figma y mi código. Me dio a elegir entre cambiar el código o cambiar el Figma, y elegí cambiar el código porque me gusta más mi diseño. Ahí me ajustó el CSS mobile y agregó la flecha para bajar. También agregó el botón de blanco y negro que tenía en mi Figma, pero no me gustó, así que le pedí sacarlo y lo borré también de mi diseño.

Después le pedí:

```
No cambies nada de mi código, solo ve los errores que tengo en cuanto a la fidelidad de mi Figma y mi código y dime cómo lo puedo cambiar y dónde muy específicamente.
```

Me dio una lista con los números de línea y los cambios los hice yo en mi código.

Los enlaces de descarga estaban rotos porque apuntaban a imágenes que no existían:

```html
<!-- antes -->
<a class="icono" href="img/p01-1.jpg" download>

<!-- después -->
<a class="icono" href="proyecto-01.gif" download>
```

El video de Latin Mafia no tenía cierre:

```html
<!-- antes -->
<video class="completa" src="video.mp4" alt="Bitácora: Latin Mafia, imagen 6">

<!-- después -->
<video class="completa" src="video.mp4" autoplay muted loop playsinline></video>
```

Todo se veía más chico que en mi Figma porque mi Figma es de 1728 px y el CSS dejaba de crecer en 1440:

```css
/* antes */
font-size: clamp(0.6rem, 1.111vw, 1rem);

/* después */
font-size: clamp(0.6rem, 1.111vw, 1.2rem);
```

En mobile los textos y la imagen de inicio eran más chicos que en mi Figma mobile:

```css
/* antes */
--tam-logo: 2.25rem;
--tam-titulo: 1.25rem;
--tam-nav: 1.25rem;
--tam-cuerpo: 1rem;

/* después */
--tam-logo: 3rem;
--tam-titulo: 2.25rem;
--tam-nav: 2rem;
--tam-cuerpo: 1.25rem;
```

```css
/* antes */
.portada img {
  height: auto;
  max-height: 28rem;
}

/* después */
.portada {
  overflow: hidden;
}

.portada img {
  width: 126%;
  max-width: none;
}
```

También cambié el botón SOBRE MÍ de mobile de `font-weight: 700` a `font-weight: 500`, porque en Figma está en Medium.


También le pregunté:

```
¿Cómo puedo eliminar esta franja si en mi Figma está pegada?
```

Me explicó que era un título oculto que la misma IA había agregado antes y que dejaba un espacio por el gap, así que borré esta línea de mi index.html:

```html
<h1 class="oculto">Proyectos</h1>
```

Por último le pregunté:

```
¿Cómo puedo agregarle al mouse un elemento para que se vea mejor?
```

Me explicó que se hace con un SVG y la propiedad cursor. Elegí la estrella de mi UI kit, hice una copia rellena en rojo (cursor.svg) y lo agregué en mi CSS:

```css
body {
  cursor: url("iconos/cursor.svg") 16 16, auto;
}

a,
label {
  cursor: url("iconos/cursor.svg") 16 16, pointer;
}
```

Y para que los proyectos del home se vieran borrosos al pasar el mouse:

```
Me gustaría que en el home, al pasar el mouse por los proyectos, se vieran más borrosos.
```

Cambié el efecto de opacidad que tenía por desenfoque:

```css
/* antes */
.proyecto img {
  transition: opacity 0.2s;
}

.proyecto:hover img {
  opacity: 0.85;
}

/* después */
.proyecto img {
  transition: filter 0.3s;
}

.proyecto:hover img,
.proyecto:focus-visible img {
  filter: blur(0.25rem);
}
```

Sin IA hice todo el diseño en Figma (UI kit, componentes, pantallas desktop y mobile y prototipo), elegí las referencias, preparé las imágenes y los textos de mis proyectos y corregí los errores del HTML del Avance 2.

# Problemas y soluciones

Al abrir mi HTML en Chrome me aparecía parte del código escrito en la página. Tenía un `</html>` cerrado al principio, el logo sin cerrar, el nav sin abrir y el header sin cierre. Lo corregí así:

```html
<!-- antes -->
<html lang="es">
</html>
<head>

<!-- después -->
<html lang="es">
<head>
```

```html
<!-- antes -->
<header class="cabecera">
  <a class="logo"
   <button> class="boton-icono">
   </button>
   <a href="#proyectos">Proyectos</a>
    <a href="#sobre-mi">Sobre mí</a>
  </nav>

<!-- después -->
<header class="cabecera">
  <a class="logo" href="#">258ALMENDRA</a>
  <nav>
    <a href="#proyectos">Proyectos</a>
    <a href="#sobre-mi">Sobre mí</a>
  </nav>
</header>
```

También me faltaban el meta viewport y el title, así que los agregué.

Se me veía un recuadro negro detrás de las imágenes y GIF de los proyectos. Era porque .proyecto tenía min-height, padding y un background-color. Eliminé el margin-top de .proyectos y en .proyecto dejé solo display flex y width:

```css
.proyectos {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 7.5rem;
  width: 86%;
}

.proyecto {
  display: flex;
  width: 100%;
}
```

La muñeca estaba en 64rem y era demasiado grande, la fui bajando hasta dejarla en 43rem.

Los íconos de las páginas de proyecto se veían gigantes. Los cambié por mis SVG del UI kit con width y height en el HTML.

El correo se me cortaba en dos líneas porque tenía overflow-wrap: anywhere y word-break: break-all, que cortan la palabra en cualquier letra. Los cambié por white-space: nowrap.

Entre la portada y el primer proyecto me quedaba una franja, y en mi Figma están pegados. Era un h1 oculto que contaba como elemento dentro de .proyectos y el gap de 7.5rem dejaba el espacio. Lo borré.

El botón de descargar apuntaba a imágenes que no existían, así que cambié cada href por una imagen que sí está en mi carpeta.

El video de Latin Mafia no se veía porque la etiqueta no estaba cerrada y no tenía cómo reproducirse. Quedó así:

```html
<video class="completa" src="video.mp4" autoplay muted loop playsinline></video>
```

En pantallas grandes todo se veía más chico que en mi Figma, porque mi Figma es de 1728 px y el CSS dejaba de crecer en 1440. Cambié el máximo del clamp de 1rem a 1.2rem.

# Aprendizajes

Fue un gran trabajo, que me hace sentirme muy orgullosa porque nunca pensé en lograr una página web sola. Aprendí que si una etiqueta no está bien cerrada el navegador muestra el código como texto o desordena la página, así que ahora reviso que todo tenga su cierre. También entendí mejor que el HTML es la estructura y el CSS es el diseño, por eso saqué los estilos que la IA me había puesto en el HTML. Aprendí a ordenar todo con flexbox. Con rem y clamp todo el sitio se escala junto y se mantienen las proporciones de mi Figma, y con una sola media query para mobile puedo cambiar tamaños y ocultar cosas como el botón de proyectos.Támbien aprendí que Figma no exporta las animaciones, cada estado de un componente se exporta como un SVG distinto y se cambia con hover en el CSS. Aunque da flojera el resultado es genial!! Aprendí a revisar las rutas, porque si el nombre de un archivo está mal escrito la imagen no carga (y se puede perder mucho tiempo buscando el error) Comparar mi Figma con el sitio me hizo entender que la fidelidad no es solo que se parezca, también son los tamaños, los espacios y las proporciones. Con la IA aprendí que me ayuda a encontrar errores y a avanzar más rápido, pero también se equivoca (los íconos no eran los míos y el título oculto me creó la franja). Por eso tengo que revisar lo que me entrega y decidir yo qué uso y qué no.

Muchas gracias profes por los aprendizajes!!