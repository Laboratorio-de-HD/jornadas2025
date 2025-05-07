<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{ page.title }}</title>

  <!-- CSS principal -->
  <link rel="stylesheet" href="{{ '/assets/css/home.css' | relative_url }}">

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Ubuntu:wght@400;700&family=Ubuntu+Condensed&display=swap" rel="stylesheet">

  <!-- Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

  <!-- Estilos específicos del encabezado -->
  <style>
    .home-title {
      text-align: center;
      font-family: 'Ubuntu', sans-serif;
      font-size: 2.5rem;
      color: #4e3b8c;
      text-transform: uppercase;
      font-weight: 700;
      letter-spacing: 1px;
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 12px;
      margin-top: 2em;
      margin-bottom: 1.5em;
      border-bottom: 2px solid #6c5eb5;
      padding-bottom: 0.4em;
    }

    .home-title i {
      font-size: 1.4em;
      color: #6c5eb5;
      animation: bounceIn 1s ease-out;
      transition: transform 0.3s ease;
    }

    .home-title i:hover {
      animation: bounceHover 0.6s ease;
    }

    @keyframes bounceIn {
      0% {
        transform: scale(0.8) translateY(-20px);
        opacity: 0;
      }
      60% {
        transform: scale(1.1) translateY(8px);
        opacity: 1;
      }
      80% {
        transform: scale(0.95) translateY(-4px);
      }
      100% {
        transform: scale(1) translateY(0);
      }
    }

    @keyframes bounceHover {
      0% {
        transform: translateY(0);
      }
      30% {
        transform: translateY(-6px);
      }
      60% {
        transform: translateY(3px);
      }
      100% {
        transform: translateY(0);
      }
    }
  </style>
</head>

<body class="home-page">

  <!-- Navegación -->
  <nav class="home-nav">
  <a href="{{ '/home/' | relative_url }}" title="Inicio">
    <i class="fas fa-house"></i>
  </a>
</nav>

  <!-- Encabezado principal -->
  <header class="home-header">
    <h1 class="home-title">
      <i class="fas fa-code" title="Humanidades digitales y tecnología"></i> {{ site.title }}
    </h1>
  </header>

  <!-- Lista de posts -->
 <section class="post-list-grid">
  <h2>Últimos Posts</h2>
  <ul class="grid-posts">
    {% for post in site.posts %}
      <li class="post-card">
        <a href="{{ post.url | relative_url }}">
          <div class="post-meta">
            <i class="fas fa-file-alt"></i>
            <span class="post-title">{{ post.title }}</span>
            <span class="post-date">{{ post.date | date: "%d %b %Y" }}</span>
          </div>
        </a>
      </li>
    {% endfor %}
  </ul>
</section>



  <!-- Contenido dinámico de home.md -->
  <main class="home-content">
    {{ content }}
  </main>

 <footer class="home-footer">
  <div class="footer-content">
    <img src="{{ '/assets/img/logoehe.png' | relative_url }}" alt="Logoehe">
    <p>© 2025 Jornadas de Humanidades Digitales,<br>Escuela de Humanidades y Educación, Tec de Monterrey</p>
  </div>

  <nav class="footer-links">
    <a href="https://tec.mx/es/aviso-legal/">Aviso legal</a> |
    <a href="https://tec.mx/es/politicas-de-privacidad-del-tecnologico-de-monterrey/">Políticas de privacidad</a> |
    <a href="https://tec.mx/es/avisos-de-privacidad/">Aviso de privacidad</a>
    <p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><span property="dct:title">Jornadas Humanidades Digitales</span> by <span property="cc:attributionName">Natalia Rocha</span> is licensed under <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY-NC-SA 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1" alt=""></a></p>
  </nav>
</footer>

</body>
</html>

