<body>
  <div class="container-lg px-3 my-5 markdown-body">
    <h1><a href="https://daniel5677fhd.github.io/sitee-book/">sitee-book</a></h1>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MEU SITE - Comentários</title>
    <link href="css/style.css" rel="stylesheet">

    <style>
      @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600&display=swap');
      /* ... (seu CSS completo permanece o mesmo) ... */
    </style>

    <h1>SITE DOS MEUS PRODUTOS</h1>
    <p class="subtitle">Clique nos botões abaixo para interagir com os produtos e deixar seu comentário!</p>
    <a class="btn" href="https://dashboard.kiwify.com/products" target="_blank">Ver Produtos</a>
    <a class="btn" href="https://app.cakto.com.br/dashboard/products?tab=products" target="_blank">Ver Produtos</a>
    <button class="btn" id="btnComentar">Comentar</button>

    <div id="comentario-form" style="display:none;">
      <h2 id="deixe-seu-comentário">Deixe seu comentário:</h2>
      <textarea id="txtComentario" placeholder="Digite seu comentário aqui..."></textarea><br>
      <button id="enviar">Enviar Comentário</button>
      <button id="cancelar">Cancelar</button>
    </div>

    <button class="btn" id="btnVerComentarios" style="display: inline-block;">Ver Comentários</button>

    <div id="comentarios" style="display:none;">
      <h2 id="comentários">Comentários:</h2>
      <div id="listaComentarios"></div>
      <button id="fecharComentarios">Fechar Comentários</button>
    </div>

    <!-- Botões sociais -->
    <a id="instagram-link" href="https://www.instagram.com/danioficial704?igsh=MWdod2IxNjV3b2owOA==" target="_blank" title="Instagram Danioficial704" aria-label="Instagram">
      <svg viewBox="0 0 24 24" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
        <circle cx="12" cy="12" r="3.5"></circle>
        <line x1="17.5" y1="6.5" x2="17.5" y2="6.5"></line>
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

    <script src="https://cdnjs.cloudflare.com/ajax/libs/anchor-js/4.1.0/anchor.min.js" integrity="sha256-lZaRhKri35AyJSypXXs4o6OPFTbTmUoltBbDCbdzegg=" crossorigin="anonymous"></script>
    <script>anchors.add();</script>
  </div>
</body>
