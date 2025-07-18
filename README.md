
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>MEU SITE - Comentários</title>
  <link href="css/style.css" rel="stylesheet" />
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600&display=swap');

    * {
      box-sizing: border-box;
    }

    body {
      font-family: 'Montserrat', sans-serif;
      background-color: #121212;
      color: #e0e0e0;
      margin: 0;
      padding: 40px 20px;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      position: relative;
    }

    h1 {
      font-weight: 600;
      font-size: 3rem;
      margin-bottom: 15px;
      color: #fff;
      text-shadow: 0 0 12px #6a0dad;
    }

    p.subtitle {
      font-size: 1.1rem;
      margin-bottom: 40px;
      color: #bbb;
      text-align: center;
      max-width: 600px;
    }

    .btn,
    button {
      background-color: #6a0dad;
      color: #fff;
      border: none;
      border-radius: 30px;
      padding: 15px 40px;
      font-size: 1.15rem;
      font-weight: 600;
      cursor: pointer;
      margin: 0 10px 20px 10px;
      box-shadow: 0 6px 15px rgba(106, 13, 173, 0.7);
      transition: all 0.3s ease;
      text-decoration: none;
      display: inline-block;
    }

    .btn:hover,
    button:hover {
      background-color: #9300d3;
      box-shadow: 0 8px 20px rgba(147, 0, 211, 0.9);
      transform: translateY(-3px);
    }

    #comentario-form,
    #comentarios,
    #btnVerComentarios {
      width: 100%;
      max-width: 650px;
      background: #1e1e1e;
      border-radius: 20px;
      padding: 30px 35px;
      box-shadow: 0 0 30px rgba(106, 13, 173, 0.6);
      color: #ddd;
      margin-top: 30px;
    }

    #comentario-form h2,
    #comentarios h2 {
      margin-top: 0;
      margin-bottom: 20px;
      font-weight: 700;
      text-align: center;
      color: #d6b7ff;
      text-shadow: 0 0 8px rgba(106, 13, 173, 0.8);
    }

    textarea {
      width: 100%;
      min-height: 120px;
      padding: 18px 22px;
      border-radius: 15px;
      border: none;
      resize: vertical;
      font-size: 1rem;
      font-family: 'Montserrat', sans-serif;
      background-color: #2a2a2a;
      color: #eee;
      box-shadow: inset 0 0 10px rgba(106, 13, 173, 0.6);
      transition: background-color 0.3s, color 0.3s;
    }

    textarea::placeholder {
      color: #aa80ff;
    }

    textarea:focus {
      background-color: #3c007d;
      outline: none;
      color: #fff;
    }

    #enviar,
    #cancelar {
      margin-top: 20px;
      width: 48%;
      display: inline-block;
      font-weight: 700;
      box-shadow: 0 4px 12px rgba(106, 13, 173, 0.8);
    }

    #cancelar {
      background-color: #a80044;
      color: white;
      transition: background-color 0.3s ease;
    }

    #cancelar:hover {
      background-color: #cc0055;
    }

    .comentario {
      background: #292929;
      padding: 18px 25px;
      border-radius: 15px;
      margin-bottom: 15px;
      box-shadow: 0 4px 15px rgba(106, 13, 173, 0.5);
      font-size: 1rem;
      line-height: 1.5;
      color: #ddd;
      word-wrap: break-word;
      border-left: 6px solid #6a0dad;
    }

    .comentario small {
      display: block;
      font-size: 0.75rem;
      margin-bottom: 10px;
      color: #bb99ff;
      font-style: italic;
    }

    #fecharComentarios {
      background-color: #a80044;
      color: #fff;
      border: none;
      border-radius: 30px;
      padding: 12px 40px;
      font-size: 1rem;
      font-weight: 700;
      cursor: pointer;
      margin: 30px auto 0 auto;
      display: block;
      box-shadow: 0 5px 15px rgba(168, 0, 68, 0.8);
      transition: background-color 0.3s ease;
    }

    #fecharComentarios:hover {
      background-color: #cc0055;
    }

    /* Botões sociais fixos */
    #instagram-link,
    #tiktok-link,
    #facebook-link,
    #youtube-link {
      position: fixed;
      bottom: 25px;
      border-radius: 50%;
      width: 60px;
      height: 60px;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      z-index: 1000;
      transition: background-color 0.3s ease, transform 0.3s ease;
    }

    #instagram-link {
      right: 25px;
      background: #6a0dad;
      box-shadow: 0 0 15px rgba(106, 13, 173, 0.7);
    }

    #instagram-link:hover {
      background-color: #9300d3;
      transform: scale(1.1);
    }

    #youtube-link {
      right: 85px;
      background: #6a0dad;
      box-shadow: 0 0 15px rgba(106, 13, 173, 0.7);
    }

    #youtube-link:hover {
      background-color: #9300d3;
      transform: scale(1.1);
    }

    #youtube-link svg {
      stroke: #fff;
      width: 30px;
      height: 30px;
      display: block;
      fill: none;
    }

    #tiktok-link {
      right: 145px;
      background: #000;
      box-shadow: 0 0 15px rgba(255, 255, 255, 0.3);
    }

    #tiktok-link:hover {
      background-color: #ff0050;
      transform: scale(1.1);
    }

    #facebook-link {
      right: 205px;
      background: #1877f2;
      box-shadow: 0 0 15px rgba(24, 119, 242, 0.7);
    }

    #facebook-link:hover {
      background-color: #0d65d9;
      transform: scale(1.1);
    }

    #instagram-link svg,
    #tiktok-link svg,
    #facebook-link svg {
      display: block;
      width: 30px;
      height: 30px;
      stroke: #fff;
      fill: none;
    }

    @media (max-width: 700px) {
      body {
        padding: 30px 15px;
      }
      h1 {
        font-size: 2.2rem;
      }
      .btn,
      button {
        padding: 12px 30px;
        font-size: 1rem;
        margin: 8px 6px 16px 6px;
      }
      #comentario-form,
      #comentarios,
      #btnVerComentarios {
        padding: 25px;
      }
      #enviar,
      #cancelar {
        width: 100%;
        margin-bottom: 12px;
      }
    }
  </style>
</head>
<body>
  <h1>SITE DOS MEUS PRODUTOS</h1>
  <p class="subtitle">
    Clique nos botões abaixo para interagir com os produtos e deixar seu comentário!
  </p>

  <a class="btn" href="https://dashboard.kiwify.com/products" target="_blank">Ver Produtos</a>
  <a class="btn" href="https://app.cakto.com.br/dashboard/products?tab=products" target="_blank">Ver Produtos</a>
  <button class="btn" id="btnComentar">Comentar</button>

  <div id="comentario-form" style="display: none;">
    <h2 id="deixe-seu-comentario">Deixe seu comentário:</h2>
    <textarea id="txtComentario" placeholder="Digite seu comentário aqui..."></textarea><br/>
    <button id="enviar">Enviar Comentário</button>
    <button id="cancelar">Cancelar</button>
  </div>

  <button class="btn" id="btnVerComentarios" style="display: none;">Ver Comentários</button>

  <div id="comentarios" style="display: none;">
    <h2 id="comentarios-titulo">Comentários:</h2>
    <div id="listaComentarios"></div>
    <button id="fecharComentarios">Fechar Comentários</button>
  </div>

  <!-- Botões Sociais -->
  <a id="instagram-link" href="https://www.instagram.com/motivacao_com_daniel/?hl=en" target="_blank" title="Instagram Danioficial704" aria-label="Instagram">
    <svg viewBox="0 0 24 24" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
      <circle cx="12" cy="12" r="3.5"></circle>
      <line x1="17.5" y1="6.5" x2="17.5" y2="6.5"></line>
    </svg>
  </a>

  <a id="youtube-link" href="https://youtube.com/@telaetextos?si=BpiNrRU3b6SS6kEc" target="_blank" title="YouTube Tela e Textos" aria-label="YouTube">
    <svg viewBox="0 0 24 24" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" fill="none">
      <path d="M10 15l5.19-3L10 9v6z"></path>
      <rect x="2" y="5" width="20" height="14" rx="4" ry="4"></rect>
    </svg>
  </a>

  <a id="tiktok-link" href="https://www.tiktok.com/@jovem.investidor516?_t=ZM-8xb6XYcHwog&amp;_r=1" target="_blank" title="TikTok Jovem Investidor" aria-label="TikTok">
    <svg viewBox="0 0 24 24" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <path d="M9 18c-1 0-1.9-.5-2.5-1.3"></path>
      <path d="M9 9V5h3a4 4 0 0 0 4 4h1"></path>
      <path d="M9 18v-6h4"></path>
      <circle cx="12" cy="19" r="3"></circle>
    </svg>
  </a>

  <a id="facebook-link" href="https://www.facebook.com/profile.php?id=61577731419361&mibextid=ZbWKwL" target="_blank" title="Compartilhar no Facebook" aria-label="Facebook">
    <svg viewBox="0 0 24 24" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <path d="M18 2h-3a4 4 0 0 0-4 4v3H8v4h3v9h4v-9h3l1-4h-4V6a1 1 0 0 1 1-1h3z"></path>
    </svg>
  </a>

  <script>
    const btnComentar = document.getElementById('btnComentar');
    const comentarioForm = document.getElementById('comentario-form');
    const btnVerComentarios = document.getElementById('btnVerComentarios');
    const comentariosDiv = document.getElementById('comentarios');
    const listaComentarios = document.getElementById('listaComentarios');
    const txtComentario = document.getElementById('txtComentario');
    const btnEnviar = document.getElementById('enviar');
    const btnCancelar = document.getElementById('cancelar');
    const btnFecharComentarios = document.getElementById('fecharComentarios');

    btnComentar.addEventListener('click', () => {
      comentarioForm.style.display = 'block';
      btnComentar.style.display = 'none';
      btnVerComentarios.style.display = 'none';
      comentariosDiv.style.display = 'none';
      txtComentario.focus();
    });

    btnCancelar.addEventListener('click', () => {
      comentarioForm.style.display = 'none';
      btnComentar.style.display = 'inline-block';
      // mostrar botão ver comentários só se houver comentários
      const comentarios = JSON.parse(localStorage.getItem('comentarios') || '[]');
      btnVerComentarios.style.display = comentarios.length > 0 ? 'inline-block' : 'none';
    });

    function salvarComentario(texto) {
      let comentarios = JSON.parse(localStorage.getItem('comentarios')) || [];
      comentarios.push({ texto: texto, data: new Date().toLocaleString() });
      localStorage.setItem('comentarios', JSON.stringify(comentarios));
    }

    function mostrarComentarios() {
      let comentarios = JSON.parse(localStorage.getItem('comentarios')) || [];
      listaComentarios.innerHTML = '';
      if (comentarios.length === 0) {
        listaComentarios.innerHTML = '<p>Nenhum comentário ainda.</p>';
      } else {
        comentarios.forEach((c) => {
          const div = document.createElement('div');
          div.className = 'comentario';
          div.innerHTML = `<small>${c.data}</small>${c.texto}`;
          listaComentarios.appendChild(div);
        });
      }
      comentariosDiv.style.display = 'block';
      btnVerComentarios.style.display = 'none';
      comentarioForm.style.display = 'none';
      btnComentar.style.display = 'inline-block';
    }

    btnEnviar.addEventListener('click', () => {
      const texto = txtComentario.value.trim();
      if (texto === '') {
        alert('Por favor, digite um comentário.');
        return;
      }
      salvarComentario(texto);
      txtComentario.value = '';
      alert('Comentário enviado!');
      btnVerComentarios.style.display = 'inline-block';
      comentarioForm.style.display = 'none';
    });

    btnVerComentarios.addEventListener('click', mostrarComentarios);

    btnFecharComentarios.addEventListener('click', () => {
      comentariosDiv.style.display = 'none';
      btnVerComentarios.style.display = 'inline-block';
      btnComentar.style.display = 'inline-block';
    });

    window.onload = () => {
      let comentarios = JSON.parse(localStorage.getItem('comentarios')) || [];
      if (comentarios.length > 0) {
        btnVerComentarios.style.display = 'inline-block';
      } else {
        btnVerComentarios.style.display = 'none';
      }
    };
  </script>
</body>
</html>
