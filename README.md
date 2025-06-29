<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
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

    .btn, button {
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

    .btn:hover, button:hover {
      background-color: #9300d3;
      box-shadow: 0 8px 20px rgba(147, 0, 211, 0.9);
      transform: translateY(-3px);
    }

    #comentario-form, #comentarios, #btnVerComentarios {
      width: 100%;
      max-width: 650px;
      background: #1e1e1e;
      border-radius: 20px;
      padding: 30px 35px;
      box-shadow: 0 0 30px rgba(106, 13, 173, 0.6);
      color: #ddd;
      margin-top: 30px;
    }

    #comentario-form h2, #comentarios h2 {
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

    #enviar, #cancelar {
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

    #instagram-link, #tiktok-link {
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

    #tiktok-link {
      right: 95px;
      background: #000;
      box-shadow: 0 0 15px rgba(255, 255, 255, 0.3);
    }

    #tiktok-link:hover {
      background-color: #ff0050;
      transform: scale(1.1);
    }

    #instagram-link svg, #tiktok-link svg {
      width: 30px;
      height: 30px;
      fill: #fff;
    }

    @media (max-width: 700px) {
      body {
        padding: 30px 15px;
      }
      h1 {
        font-size: 2.2rem;
      }
      .btn, button {
        padding: 12px 30px;
        font-size: 1rem;
        margin: 8px 6px 16px 6px;
      }
      #comentario-form, #comentarios, #btnVerComentarios {
        padding: 25px;
      }
      #enviar, #cancelar {
        width: 100%;
        margin-bottom: 12px;
      }
    }
  </style>
</head>
<body>
  <h1>SITE DOS MEUS PRODUTOS</h1>
  <p class="subtitle">Clique nos botões abaixo para interagir com os produtos e deixar seu comentário!</p>
  <a class="btn" href="https://dashboard.kiwify.com/products" target="_blank">Ver Produtos</a>
  <a class="btn" href="https://app.cakto.com.br/dashboard/products?tab=products" target="_blank">Ver Produtos</a>
  <button class="btn" id="btnComentar">Comentar</button>

  <div id="comentario-form" style="display:none;">
    <h2>Deixe seu comentário:</h2>
    <textarea id="txtComentario" placeholder="Digite seu comentário aqui..."></textarea><br>
    <button id="enviar">Enviar Comentário</button>
    <button id="cancelar">Cancelar</button>
  </div>

  <button class="btn" id="btnVerComentarios" style="display:none;">Ver Comentários</button>

  <div id="comentarios" style="display:none;">
    <h2>Comentários:</h2>
    <div id="listaComentarios"></div>
    <button id="fecharComentarios">Fechar Comentários</button>
  </div>

  <!-- Botão Instagram -->
  <a id="instagram-link" href="https://www.instagram.com/danioficial704?igsh=MWdod2IxNjV3b2owOA==" target="_blank" title="Instagram Danioficial704">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M224.1 141c-63.6 0-114.9..."/></svg>
  </a>

  <!-- Botão TikTok -->
  <a id="tiktok-link" href="https://www.tiktok.com/@jovem.investidor516?_t=ZM-8xb6XYcHwog&_r=1" target="_blank" title="TikTok Jovem Investidor">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M448,209.9v125.1c0,97.2..."/></svg>
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
      btnVerComentarios.style.display = JSON.parse(localStorage.getItem('comentarios') || '[]').length > 0 ? 'inline-block' : 'none';
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
        comentarios.forEach(c => {
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
      }
    }
  </script>
</body>
</html>
