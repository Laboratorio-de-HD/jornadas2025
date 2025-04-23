<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>{{ page.title }}</title>

  <!-- CSS principal del sitio -->
  <link rel="stylesheet" href="{{ '/assets/css/post.css' | relative_url }}">

  <!-- Fuentes y librerías de íconos -->
  <link href="https://fonts.googleapis.com/css2?family=Ubuntu:wght@400;700&family=Ubuntu+Condensed&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
  <link href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.1/font/bootstrap-icons.css" rel="stylesheet">

</head>

<body class="post-page">

  <!-- Encabezado con ícono animado -->
  <header class="post-header">
    <h1 class="home-title">
      <i class="fas fa-code" title="Humanidades digitales y tecnología"></i> {{ site.title }}
    </h1>
   <nav class="home-nav">
  <a href="{{ '/home/' | relative_url }}" title="Inicio">
    <i class="fas fa-house"></i>
  </a>
</nav>
  </header>

  <!-- Contenido principal -->
  <main class="post-content">
    {{ content }}
  </main>

  <!-- Pie de página -->
 <footer class="home-footer">
  <footer class="home-footer">
  <div class="footer-content">
    <div class="footer-logo-box">
      <img class="footer-logo"
           src="{{ '/assets/img/logoehe.png' | relative_url }}"
           alt="Logo ehe">
    </div>

    <div class="footer-text">
      <p>
        © 2025 Jornadas de Humanidades Digitales,<br>
        Escuela de Humanidades y Educación, Tec de Monterrey
      </p>

      <nav class="footer-links">
        <a href="https://tec.mx/es/aviso-legal/">Aviso legal</a> |
        <a href="https://tec.mx/es/politicas-de-privacidad-del-tecnologico-de-monterrey/">Políticas de privacidad</a> |
        <a href="https://tec.mx/es/avisos-de-privacidad/">Aviso de privacidad</a>
      </nav>
    </div>

    <!-- Caja vacía para compensar el logo -->
    <div class="footer-logo-box"></div>
  </div>
</footer>