# isahflix<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <title>Sequência com música “Olha” e imagens</title>
  <style>
    body {
      display: flex;
      flex-direction: column;
      align-items: center;
      background-color: #111;
      color: white;
      font-family: sans-serif;
      margin: 0;
      padding: 0;
    }
    #image-container {
      width: 600px;
      height: 400px;
      margin-top: 20px;
      position: relative;
      overflow: hidden;
    }
    #image-container img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      position: absolute;
      opacity: 0;
      transition: opacity 1s;
    }
    #image-container img.active {
      opacity: 1;
    }
    #video-frame {
      margin-top: 30px;
    }
  </style>
</head>
<body>

  <h1>Maria Bethânia – Olha</h1>

  <!-- Container de imagens -->
  <div id="image-container">
    <img src="imagem1.jpg" alt="Imagem 1" class="active">
    <img src="imagem2.jpg" alt="Imagem 2">
    <img src="imagem3.jpg" alt="Imagem 3">
    <!-- adicione mais imagens conforme quiser -->
  </div>

  <!-- Player de áudio da música (se tiver arquivo mp3 local ou hospedado) -->
  <audio id="audio" controls>
    <source src="olha-maria-bethania.mp3" type="audio/mp3">
    Seu navegador não suporta o elemento de áudio.
  </audio>

  <!-- Vídeo do YouTube embutido -->
  <div id="video-frame">
    <iframe width="560" height="315"
      src="https://www.youtube.com/embed/K5V8Bqnafrg?rel=0"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
      allowfullscreen>
    </iframe>
  </div>

  <script>
    // JavaScript para trocar as imagens em sequência
    const imagens = document.querySelectorAll('#image-container img');
    let idx = 0;

    function mostrarProximaImagem() {
      imagens[idx].classList.remove('active');
      idx = (idx + 1) % imagens.length;
      imagens[idx].classList.add('active');
    }

    // Muda de imagem a cada 5 segundos
    setInterval(mos
