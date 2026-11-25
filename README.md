[index.html](https://github.com/user-attachments/files/35388577/index.html)
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!-- AQUÍ SE MODIFICA EL TÍTULO DE LA PESTAÑA DEL NAVEGADOR -->
  <title>Tocho's Food | Menú Digital - Comida Criolla de Chone</title>
  
  <style>
    /* ==========================================================================
       1. AQUÍ SE CAMBIAN LOS COLORES Y TIPOGRAFÍA DE LA MARCA
       Modifica los códigos hexadecimales si deseas ajustar el tono de blanco/negro
       ========================================================================== */
    :root {
      --color-primario: #111111;       /* Negro profundo para textos principales y botones */
      --color-secundario: #2b2b2b;     /* Gris muy oscuro para contrastes */
      --color-fondo: #ffffff;          /* Blanco puro de fondo */
      --color-fondo-suave: #f6f6f6;    /* Gris muy claro para secciones alternas */
      --color-texto: #1a1a1a;          /* Color de lectura principal */
      --color-texto-suave: #595959;    /* Gris medio para descripciones e ingredientes */
      --color-borde: #e2e2e2;          /* Líneas divisorias sutiles */
      --fuente-principal: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    }

    /* ==========================================================================
       2. ESTILOS GENERALES Y DESPLAZAMIENTO SUAVE
       ========================================================================== */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth; /* Hace que el botón "Ver menú" y los enlaces bajen suavemente */
    }

    body {
      font-family: var(--fuente-principal);
      background-color: var(--color-fondo);
      color: var(--color-texto);
      line-height: 1.6;
      -webkit-font-smoothing: antialiased;
    }

    .contenedor {
      width: 90%;
      max-width: 1120px;
      margin: 0 auto;
    }

    /* ==========================================================================
       3. ENCABEZADO Y NAVEGACIÓN
       ========================================================================== */
    header {
      background-color: var(--color-fondo);
      border-bottom: 1px solid var(--color-borde);
      position: sticky;
      top: 0;
      z-index: 1000;
      padding: 1rem 0;
    }

    .nav-contenido {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .marca {
      display: flex;
      align-items: center;
      gap: 0.85rem;
      text-decoration: none;
      color: var(--color-primario);
    }

    .marca img {
      height: 48px;
      width: auto;
      object-fit: contain;
    }

    /* Emblema de respaldo por si aún no subes logo.png */
    .logo-respaldo {
      display: none;
      width: 46px;
      height: 46px;
      background-color: var(--color-primario);
      color: var(--color-fondo);
      font-weight: 800;
      font-size: 1.1rem;
      align-items: center;
      justify-content: center;
      border-radius: 6px;
      letter-spacing: 1px;
    }

    .marca-texto {
      font-size: 1.35rem;
      font-weight: 800;
      letter-spacing: -0.5px;
      text-transform: uppercase;
    }

    nav ul {
      list-style: none;
      display: flex;
      gap: 1.75rem;
    }

    nav a {
      text-decoration: none;
      color: var(--color-texto);
      font-weight: 600;
      font-size: 0.95rem;
      transition: opacity 0.2s ease;
    }

    nav a:hover {
      opacity: 0.6;
    }

    /* ==========================================================================
       4. SECCIÓN DE BIENVENIDA (HERO)
       ========================================================================== */
    .hero {
      padding: 5.5rem 0 4.5rem;
      text-align: center;
      background-color: var(--color-fondo);
      border-bottom: 1px solid var(--color-borde);
    }

    .etiqueta-ubicacion {
      display: inline-block;
      font-size: 0.8rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 2px;
      color: var(--color-texto-suave);
      border: 1px solid var(--color-borde);
      padding: 0.35rem 0.9rem;
      border-radius: 50px;
      margin-bottom: 1.5rem;
    }

    .hero h1 {
      font-size: clamp(2.2rem, 5vw, 3.6rem);
      font-weight: 900;
      line-height: 1.12;
      letter-spacing: -1px;
      max-width: 820px;
      margin: 0 auto 1.25rem;
      color: var(--color-primario);
    }

    .hero p {
      font-size: 1.125rem;
      color: var(--color-texto-suave);
      max-width: 640px;
      margin: 0 auto 2.25rem;
    }

    .btn-principal {
      display: inline-block;
      background-color: var(--color-primario);
      color: var(--color-fondo);
      padding: 1rem 2.4rem;
      font-size: 1rem;
      font-weight: 700;
      text-decoration: none;
      border-radius: 6px;
      letter-spacing: 0.5px;
      transition: transform 0.2s ease, background-color 0.2s ease;
    }

    .btn-principal:hover {
      background-color: var(--color-secundario);
      transform: translateY(-2px);
    }

    /* ==========================================================================
       5. SECCIÓN ESPECIALIDADES DE LA CASA
       ========================================================================== */
    .especialidades {
      padding: 4.5rem 0;
      background-color: var(--color-primario);
      color: var(--color-fondo);
    }

    .encabezado-seccion {
      text-align: center;
      margin-bottom: 3rem;
    }

    .encabezado-seccion h2 {
      font-size: 2rem;
      font-weight: 800;
      letter-spacing: -0.5px;
      margin-bottom: 0.5rem;
    }

    .encabezado-seccion p {
      color: #b8b8b8;
      max-width: 600px;
      margin: 0 auto;
    }

    .grid-especialidades {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 2rem;
    }

    .tarjeta-especial {
      background-color: #1c1c1c;
      border: 1px solid #333333;
      border-radius: 10px;
      padding: 2rem;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .badge-estrella {
      display: inline-block;
      background-color: var(--color-fondo);
      color: var(--color-primario);
      font-size: 0.75rem;
      font-weight: 800;
      text-transform: uppercase;
      letter-spacing: 1px;
      padding: 0.3rem 0.75rem;
      border-radius: 4px;
      margin-bottom: 1.25rem;
      align-self: flex-start;
    }

    .tarjeta-especial h3 {
      font-size: 1.45rem;
      margin-bottom: 0.75rem;
      color: var(--color-fondo);
    }

    .tarjeta-especial p {
      color: #cccccc;
      font-size: 0.98rem;
      margin-bottom: 1.25rem;
    }

    .motivo-especial {
      font-size: 0.88rem;
      color: #999999;
      border-top: 1px solid #333333;
      padding-top: 1rem;
      margin-bottom: 1.25rem;
      font-style: italic;
    }

    .precio-especial {
      font-size: 1.5rem;
      font-weight: 800;
      color: var(--color-fondo);
    }

    /* ==========================================================================
       6. SECCIÓN DEL MENÚ DIGITAL POR CATEGORÍAS
       ========================================================================== */
    .seccion-menu {
      padding: 5rem 0;
      background-color: var(--color-fondo);
    }

    .seccion-menu .encabezado-seccion p {
      color: var(--color-texto-suave);
    }

    /* Botones de filtro rápido */
    .filtros-menu {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 0.75rem;
      margin-bottom: 3.5rem;
    }

    .btn-filtro {
      background-color: transparent;
      color: var(--color-texto);
      border: 1px solid var(--color-borde);
      padding: 0.6rem 1.3rem;
      border-radius: 50px;
      font-size: 0.9rem;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.2s ease;
    }

    .btn-filtro:hover,
    .btn-filtro.activo {
      background-color: var(--color-primario);
      color: var(--color-fondo);
      border-color: var(--color-primario);
    }

    .bloque-categoria {
      margin-bottom: 4rem;
    }

    .titulo-categoria {
      font-size: 1.5rem;
      font-weight: 800;
      text-transform: uppercase;
      letter-spacing: 0.5px;
      padding-bottom: 0.75rem;
      border-bottom: 2px solid var(--color-primario);
      margin-bottom: 2rem;
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }

    .grid-productos {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(310px, 1fr));
      gap: 1.75rem;
    }

    .tarjeta-producto {
      background-color: var(--color-fondo);
      border: 1px solid var(--color-borde);
      border-radius: 10px;
      padding: 1.75rem;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      transition: transform 0.2s ease, box-shadow 0.2s ease, border-color 0.2s ease;
    }

    .tarjeta-producto:hover {
      transform: translateY(-4px);
      border-color: var(--color-primario);
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.06);
    }

    .producto-cabecera {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      gap: 1rem;
      margin-bottom: 0.85rem;
    }

    .producto-nombre {
      font-size: 1.18rem;
      font-weight: 700;
      color: var(--color-primario);
      line-height: 1.3;
    }

    .producto-precio {
      font-size: 1.15rem;
      font-weight: 800;
      background-color: var(--color-fondo-suave);
      color: var(--color-primario);
      padding: 0.25rem 0.65rem;
      border-radius: 6px;
      border: 1px solid var(--color-borde);
      white-space: nowrap;
    }

    .producto-descripcion {
      font-size: 0.95rem;
      color: var(--color-texto);
      margin-bottom: 1.1rem;
    }

    .producto-ingredientes {
      font-size: 0.84rem;
      color: var(--color-texto-suave);
      border-top: 1px dashed var(--color-borde);
      padding-top: 0.85rem;
    }

    .producto-ingredientes strong {
      color: var(--color-primario);
    }

    .nota-precios {
      text-align: center;
      font-size: 0.85rem;
      color: var(--color-texto-suave);
      margin-top: 2rem;
    }

    /* ==========================================================================
       7. LLAMADA A LA ACCIÓN (CTA) E INFORMACIÓN DEL RESTAURANTE
       ========================================================================== */
    .seccion-cta {
      background-color: var(--color-fondo-suave);
      border-top: 1px solid var(--color-borde);
      border-bottom: 1px solid var(--color-borde);
      padding: 4.5rem 0;
      text-align: center;
    }

    .seccion-cta h2 {
      font-size: clamp(1.5rem, 3.5vw, 2.2rem);
      font-weight: 800;
      max-width: 720px;
      margin: 0 auto 1.5rem;
      color: var(--color-primario);
    }

    .info-restaurante {
      padding: 4.5rem 0;
      background-color: var(--color-fondo);
    }

    .grid-info {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 2rem;
    }

    .caja-info {
      padding: 1.5rem;
      border-left: 3px solid var(--color-primario);
      background-color: var(--color-fondo-suave);
    }

    .caja-info h3 {
      font-size: 1.05rem;
      font-weight: 800;
      text-transform: uppercase;
      margin-bottom: 0.5rem;
      letter-spacing: 0.5px;
    }

    .caja-info p {
      font-size: 0.95rem;
      color: var(--color-texto-suave);
    }

    /* ==========================================================================
       8. PIE DE PÁGINA (FOOTER)
       ========================================================================== */
    footer {
      background-color: var(--color-primario);
      color: var(--color-fondo);
      text-align: center;
      padding: 2.5rem 0;
    }

    footer .nombre-footer {
      font-size: 1.25rem;
      font-weight: 800;
      letter-spacing: 1px;
      text-transform: uppercase;
      margin-bottom: 0.4rem;
    }

    footer p {
      font-size: 0.88rem;
      color: #a3a3a3;
    }

    /* ==========================================================================
       9. ADAPTACIÓN A TELÉFONOS CELULARES (RESPONSIVE)
       ========================================================================== */
    @media (max-width: 680px) {
      .nav-contenido {
        justify-content: center;
      }

      nav ul {
        gap: 1.1rem;
        font-size: 0.88rem;
      }

      .hero {
        padding: 3.5rem 0 3rem;
      }

      .grid-productos,
      .grid-especialidades {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>

  <!-- ========================================================================
       ENCABEZADO: LOGOTIPO, NOMBRE DEL RESTAURANTE Y ENLACES DE NAVEGACIÓN
       ======================================================================== -->
  <header>
    <div class="contenedor nav-contenido">
      <a href="#inicio" class="marca">
        <!-- AQUÍ SE REEMPLAZA EL LOGOTIPO: Asegúrate de que tu archivo se llame exactamente logo.png -->
        <img src="logo.png" alt="Logotipo de Tocho's Food" onerror="this.style.display='none'; document.getElementById('logo-alternativo').style.display='flex';">
        <div id="logo-alternativo" class="logo-respaldo">TF</div>
        
        <!-- AQUÍ SE MODIFICA EL NOMBRE DEL RESTAURANTE -->
        <span class="marca-texto">Tocho's Food</span>
      </a>

      <nav>
        <ul>
          <li><a href="#inicio">Inicio</a></li>
          <li><a href="#especialidades">Especialidades</a></li>
          <li><a href="#menu">Menú</a></li>
          <li><a href="#nosotros">Nosotros</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <!-- ========================================================================
       SECCIÓN DE BIENVENIDA CON FRASE COMERCIAL Y BOTÓN PRINCIPAL
       ======================================================================== -->
  <section id="inicio" class="hero">
    <div class="contenedor">
      <span class="etiqueta-ubicacion">Portoviejo, Ecuador &bull; Tradición Chonera</span>
      <h1>El auténtico sabor de Chone, reinventado para tu mesa.</h1>
      <p>
        En Tocho’s Food rescatamos las recetas tradicionales de Chone con un toque original y una sazón inconfundible. Platos criollos preparados al momento con ingredientes frescos y precios accesibles para toda la familia.
      </p>
      <a href="#menu" class="btn-principal">Ver menú</a>
    </div>
  </section>

  <!-- ========================================================================
       SECCIÓN DESTACADA: ESPECIALIDADES DE LA CASA
       ======================================================================== -->
  <section id="especialidades" class="especialidades">
    <div class="contenedor">
      <div class="encabezado-seccion">
        <h2>Especialidades de la Casa</h2>
        <p>Nuestras dos recetas insignia, elegidas por representar la verdadera esencia culinaria de Chone.</p>
      </div>

      <div class="grid-especialidades">
        <!-- ESPECIALIDAD 1 -->
        <article class="tarjeta-especial">
          <div>
            <span class="badge-estrella">&#9733; Plato Insignia</span>
            <h3>Tonga Chonera Tradicional</h3>
            <p>
              Arroz amarillo y estofado de gallina bañados en salsa de maní artesanal, envueltos y horneados en hoja de plátano.
            </p>
            <div class="motivo-especial">
              <strong>¿Por qué pedirla?</strong> Su cocción en hoja de plátano conserva un aroma ahumado único y ofrece una presentación tradicional inigualable.
            </div>
          </div>
          <!-- AQUÍ SE MODIFICA EL PRECIO -->
          <div class="precio-especial">$5.00</div>
        </article>

        <!-- ESPECIALIDAD 2 -->
        <article class="tarjeta-especial">
          <div>
            <span class="badge-estrella">&#9733; Receta Original</span>
            <h3>Greñoso de Cerdo al Estilo Tocho’s</h3>
            <p>
              Maíz molido cremoso cocinado en caldo sustancioso con trozos de cerdo dorado, maní y un toque de hierbita fresca.
            </p>
            <div class="motivo-especial">
              <strong>¿Por qué pedirlo?</strong> Una receta clásica de campo difícil de encontrar en la ciudad, preparada con nuestra sazón secreta de la casa.
            </div>
          </div>
          <!-- AQUÍ SE MODIFICA EL PRECIO -->
          <div class="precio-especial">$4.25</div>
        </article>
      </div>
    </div>
  </section>

  <!-- ========================================================================
       SECCIÓN DEL MENÚ ORGANIZADO POR CATEGORÍAS
       ======================================================================== -->
  <section id="menu" class="seccion-menu">
    <div class="contenedor">
      <div class="encabezado-seccion">
        <h2>Nuestro Menú Digital</h2>
        <p>Explora nuestras categorías y elige tu combinación favorita preparada al instante.</p>
      </div>

      <!-- BOTONES DE FILTRO POR CATEGORÍA -->
      <div class="filtros-menu">
        <button class="btn-filtro activo" onclick="filtrarMenu('todos', this)">Todo el menú</button>
        <button class="btn-filtro" onclick="filtrarMenu('fuertes', this)">Platos Fuertes</button>
        <button class="btn-filtro" onclick="filtrarMenu('antojos', this)">Antojos y Entradas</button>
        <button class="btn-filtro" onclick="filtrarMenu('bebidas', this)">Bebidas Tradicionales</button>
      </div>

      <!-- ====================================================================
           CATEGORÍA 1: PLATOS FUERTES CRIOLLOS
           ==================================================================== -->
      <div class="bloque-categoria" data-categoria="fuertes">
        <h3 class="titulo-categoria">&#9670; Platos Fuertes Criollos</h3>
        <div class="grid-productos">
          
          <!-- PRODUCTO 1 -->
          <article class="tarjeta-producto">
            <div>
              <div class="producto-cabecera">
                <h4 class="producto-nombre">Seco de Gallina Criolla de la Casa</h4>
                <!-- AQUÍ SE MODIFICA EL PRECIO -->
                <span class="producto-precio">$4.50</span>
              </div>
              <p class="producto-descripcion">
                Gallina de campo cocida a fuego lento en chicha de maíz y hierbas aromáticas, servida con arroz y maduro.
              </p>
            </div>
            <p class="producto-ingredientes">
              <strong>Ingredientes:</strong> Gallina criolla, chicha de maíz, pimiento, cebolla colorada, cilantro, arroz blanco y plátano maduro frito.
            </p>
          </article>

          <!-- PRODUCTO 2 -->
          <article class="tarjeta-producto">
            <div>
              <div class="producto-cabecera">
                <h4 class="producto-nombre">Tonga Chonera Tradicional</h4>
                <!-- AQUÍ SE MODIFICA EL PRECIO -->
                <span class="producto-precio">$5.00</span>
              </div>
              <p class="producto-descripcion">
                Arroz amarillo y estofado de gallina bañados en salsa de maní artesanal, envueltos y horneados en hoja de plátano.
              </p>
            </div>
            <p class="producto-ingredientes">
              <strong>Ingredientes:</strong> Arroz con achiote, presa de gallina, pasta de maní tostado, plátano maduro y hoja de plátano.
            </p>
          </article>

          <!-- PRODUCTO 3 -->
          <article class="tarjeta-producto">
            <div>
              <div class="producto-cabecera">
                <h4 class="producto-nombre">Greñoso de Cerdo al Estilo Tocho’s</h4>
                <!-- AQUÍ SE MODIFICA EL PRECIO -->
                <span class="producto-precio">$4.25</span>
              </div>
              <p class="producto-descripcion">
                Maíz molido cremoso cocinado en caldo sustancioso con trozos de cerdo dorado, maní y un toque de hierbita fresca.
              </p>
            </div>
            <p class="producto-ingredientes">
              <strong>Ingredientes:</strong> Maíz seco molido, carne de cerdo, maní, refrito manabita, ajo y cilantro.
            </p>
          </article>

          <!-- PRODUCTO 4 -->
          <article class="tarjeta-producto">
            <div>
              <div class="producto-cabecera">
                <h4 class="producto-nombre">Bollo de Pescado Albacora</h4>
                <!-- AQUÍ SE MODIFICA EL PRECIO -->
                <span class="producto-precio">$3.75</span>
              </div>
              <p class="producto-descripcion">
                Masa suave de plátano verde y maní rellena de lomo de albacora en refrito criollo, cocida al vapor.
              </p>
            </div>
            <p class="producto-ingredientes">
              <strong>Ingredientes:</strong> Plátano verde rallado, albacora fresca, maní molido, pimiento, cebolla y hoja de plátano.
            </p>
          </article>

          <!-- AQUÍ SE AGREGAN NUEVOS PRODUCTOS EN PLATOS FUERTES:
               Copia desde <article class="tarjeta-producto"> hasta </article> y pégalo aquí arriba -->

        </div>
      </div>

      <!-- ====================================================================
           CATEGORÍA 2: ANTOJOS Y ENTRADAS
           ==================================================================== -->
      <div class="bloque-categoria" data-categoria="antojos">
        <h3 class="titulo-categoria">&#9670; Antojos y Entradas</h3>
        <div class="grid-productos">
          
          <!-- PRODUCTO 5 -->
          <article class="tarjeta-producto">
            <div>
              <div class="producto-cabecera">
                <h4 class="producto-nombre">Corviche de Pescado Crujiente</h4>
                <!-- AQUÍ SE MODIFICA EL PRECIO -->
                <span class="producto-precio">$1.75</span>
              </div>
              <p class="producto-descripcion">
                Masa dorada de plátano verde con maní, rellena de pescado sazonado y acompañada de curtido fresco de cebolla.
              </p>
            </div>
            <p class="producto-ingredientes">
              <strong>Ingredientes:</strong> Plátano verde, pasta de maní, pescado albacora, cilantro, cebolla colorada y limón.
            </p>
          </article>

          <!-- PRODUCTO 6 -->
          <article class="tarjeta-producto">
            <div>
              <div class="producto-cabecera">
                <h4 class="producto-nombre">Empanadas de Verde con Queso Chonero (2 u.)</h4>
                <!-- AQUÍ SE MODIFICA EL PRECIO -->
                <span class="producto-precio">$2.25</span>
              </div>
              <p class="producto-descripcion">
                Empanadas crocantes de masa de plátano verde artesanal, rellenas de abundante queso fresco de Chone derretido.
              </p>
            </div>
            <p class="producto-ingredientes">
              <strong>Ingredientes:</strong> Plátano verde, queso fresco chonero, mantequilla blanca y sal.
            </p>
          </article>

          <!-- PRODUCTO 7 -->
          <article class="tarjeta-producto">
            <div>
              <div class="producto-cabecera">
                <h4 class="producto-nombre">Muchines de Yuca con Miel de Panela (3 u.)</h4>
                <!-- AQUÍ SE MODIFICA EL PRECIO -->
                <span class="producto-precio">$2.00</span>
              </div>
              <p class="producto-descripcion">
                Bocaditos dorados de yuca rallada rellenos de queso criollo, servidos con reducción tibia de panela artesanal.
              </p>
            </div>
            <p class="producto-ingredientes">
              <strong>Ingredientes:</strong> Yuca fresca, queso chonero, huevo, panela orgánica y anís estrellado.
            </p>
          </article>

          <!-- AQUÍ SE AGREGAN NUEVOS PRODUCTOS EN ANTOJOS Y ENTRADAS -->

        </div>
      </div>

      <!-- ====================================================================
           CATEGORÍA 3: BEBIDAS TRADICIONALES
           ==================================================================== -->
      <div class="bloque-categoria" data-categoria="bebidas">
        <h3 class="titulo-categoria">&#9670; Bebidas Tradicionales</h3>
        <div class="grid-productos">
          
          <!-- PRODUCTO 8 -->
          <article class="tarjeta-producto">
            <div>
              <div class="producto-cabecera">
                <h4 class="producto-nombre">Chicha de Maíz Helada</h4>
                <!-- AQUÍ SE MODIFICA EL PRECIO -->
                <span class="producto-precio">$1.25</span>
              </div>
              <p class="producto-descripcion">
                Bebida refrescante elaborada con maíz amarillo fermentado suavemente, especias dulces y servida bien fría.
              </p>
            </div>
            <p class="producto-ingredientes">
              <strong>Ingredientes:</strong> Maíz amarillo, panela, canela, clavo de olor y agua purificada.
            </p>
          </article>

          <!-- PRODUCTO 9 -->
          <article class="tarjeta-producto">
            <div>
              <div class="producto-cabecera">
                <h4 class="producto-nombre">Jugo Natural de Maracuyá y Hierbabuena</h4>
                <!-- AQUÍ SE MODIFICA EL PRECIO -->
                <span class="producto-precio">$1.50</span>
              </div>
              <p class="producto-descripcion">
                Pulpa fresca de maracuyá licuada al instante con hojas de hierbabuena del huerto y un toque justo de dulce.
              </p>
            </div>
            <p class="producto-ingredientes">
              <strong>Ingredientes:</strong> Maracuyá fresco, hojas de hierbabuena, agua purificada y azúcar.
            </p>
          </article>

          <!-- AQUÍ SE AGREGAN NUEVOS PRODUCTOS EN BEBIDAS -->

        </div>
      </div>

      <p class="nota-precios">
        * Todos los precios están expresados en dólares estadounidenses (USD) y son valores referenciales sujetos a actualización.
      </p>
    </div>
  </section>

  <!-- ========================================================================
       SECCIÓN DE LLAMADA A LA ACCIÓN (CTA)
       ======================================================================== -->
  <section class="seccion-cta">
    <div class="contenedor">
      <h2>¿Se te hizo agua la boca? Pide tu plato favorito ahora y disfruta el verdadero sabor de Chone sin salir de casa.</h2>
      <a href="#nosotros" class="btn-principal">Visítanos en Portoviejo</a>
    </div>
  </section>

  <!-- ========================================================================
       SECCIÓN FINAL: INFORMACIÓN DEL RESTAURANTE
       ======================================================================== -->
  <section id="nosotros" class="info-restaurante">
    <div class="contenedor">
      <div class="grid-info">
        <div class="caja-info">
          <h3>Nuestra Propuesta</h3>
          <p>Comida criolla auténtica de Chone con recetas originales, sazón única y precios accesibles para todos.</p>
        </div>
        <div class="caja-info">
          <h3>Ubicación</h3>
          <p>Portoviejo, Manabí, Ecuador.<br>Atención en local y pedidos para llevar.</p>
        </div>
        <div class="caja-info">
          <h3>Horario de Atención</h3>
          <p>Lunes a Domingo<br>08:00 AM – 04:00 PM</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ========================================================================
       PIE DE PÁGINA (FOOTER)
       ======================================================================== -->
  <footer>
    <div class="contenedor">
      <!-- AQUÍ SE MODIFICA EL NOMBRE DEL RESTAURANTE EN EL PIE DE PÁGINA -->
      <div class="nombre-footer">Tocho's Food</div>
      <p>Gastronomía Criolla de Chone &bull; Portoviejo, Ecuador</p>
    </div>
  </footer>

  <!-- ========================================================================
       JAVASCRIPT SENCILLO PARA FILTRAR CATEGORÍAS DEL MENÚ
       ======================================================================== -->
  <script>
    function filtrarMenu(categoriaSeleccionada, botonPulsado) {
      // 1. Actualizar el estilo activo de los botones
      const botones = document.querySelectorAll('.btn-filtro');
      botones.forEach(boton => boton.classList.remove('activo'));
      botonPulsado.classList.add('activo');

      // 2. Mostrar u ocultar las categorías según el botón seleccionado
      const bloques = document.querySelectorAll('.bloque-categoria');
      bloques.forEach(bloque => {
        if (categoriaSeleccionada === 'todos' || bloque.dataset.categoria === categoriaSeleccionada) {
          bloque.style.display = 'block';
        } else {
          bloque.style.display = 'none';
        }
      });
    }
  </script>

</body>
</html>
