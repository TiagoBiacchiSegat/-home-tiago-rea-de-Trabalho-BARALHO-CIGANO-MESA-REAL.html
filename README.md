# -home-tiago-rea-de-Trabalho-BARALHO-CIGANO-MESA-REAL.html
// Projeto inicial Mesa real  Baralho Cigano

<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Baralho Cigano Interativo</title>
  <style>
    body {
      background: linear-gradient(to right, #111, #333);
      color: #fff;
      font-family: 'Georgia', serif;
      text-align: center;
      padding: 20px;
    }

    h1 {
      color: #ffcc00;
      margin-bottom: 10px;
    }

    select, button {
      padding: 10px;
      margin: 10px;
      font-size: 1em;
      border-radius: 5px;
      border: none;
    }

    .carta {
      display: inline-block;
      border: 2px solid #fff;
      border-radius: 10px;
      padding: 10px;
      margin: 10px;
      width: 180px;
      background: #222;
    }

    .carta h2 {
      color: #ffcc00;
      margin-bottom: 5px;
    }

    .mesa {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
    }
  </style>
</head>
<body>
  <h1>✨ Baralho Cigano Interativo ✨</h1>

  <select id="metodo">
    <option value="3">Método 3 Cartas</option>
    <option value="9">Método 9 Cartas</option>
    <option value="36">Mesa Real (36 Cartas)</option>
  </select>
  <button onclick="sortearCartas()">Sortear</button>

  <div class="mesa" id="mesa"></div>

  <script>
    const cartas = [
      { nome: "Cavaleiro", significado: "Notícias, ação, movimento." },
      { nome: "Trevo", significado: "Sorte repentina, oportunidades." },
      { nome: "Navio", significado: "Viagens, mudanças, comércio." },
      { nome: "Casa", significado: "Segurança, lar, estabilidade." },
      { nome: "Árvore", significado: "Crescimento, saúde, raízes." },
      { nome: "Nuvens", significado: "Confusão, dúvidas, enganos." },
      { nome: "Cobra", significado: "Traição, sedução, sabedoria." },
      { nome: "Caixão", significado: "Fim de ciclo, transformação." },
      { nome: "Buquê", significado: "Felicidade, beleza, convite." },
      { nome: "Foice", significado: "Cortes, decisões, colheita." },
      { nome: "Chicote", significado: "Conflito, repetição, força." },
      { nome: "Pássaros", significado: "Conversas, ansiedade, dupla." },
      { nome: "Criança", significado: "Novidades, inocência, recomeço." },
      { nome: "Raposa", significado: "Esperteza, alerta, estratégia." },
      { nome: "Urso", significado: "Poder, ciúmes, autoridade." },
      { nome: "Estrela", significado: "Guia, espiritualidade, fama." },
      { nome: "Cegonha", significado: "Mudanças positivas, novidades." },
      { nome: "Cão", significado: "Amizade, lealdade, ajuda." },
      { nome: "Torre", significado: "Isolamento, autoridade, estrutura." },
      { nome: "Jardim", significado: "Sociedade, encontros, eventos." },
      { nome: "Montanha", significado: "Obstáculo, desafio, superação." },
      { nome: "Caminhos", significado: "Escolhas, bifurcações, decisão." },
      { nome: "Ratos", significado: "Perdas, desgastes, roubo." },
      { nome: "Coração", significado: "Amor, emoções, paixões." },
      { nome: "Aliança", significado: "Compromisso, contrato, parceria." },
      { nome: "Livro", significado: "Segredo, estudo, aprendizado." },
      { nome: "Carta", significado: "Mensagem, notícia, revelação." },
      { nome: "Homem", significado: "O consulente ou figura masculina." },
      { nome: "Mulher", significado: "A consulente ou figura feminina." },
      { nome: "Lírios", significado: "Paz, maturidade, harmonia." },
      { nome: "Sol", significado: "Sucesso, clareza, energia." },
      { nome: "Lua", significado: "Intuição, emoções, reconhecimento." },
      { nome: "Chave", significado: "Soluções, acesso, resposta." },
      { nome: "Peixes", significado: "Dinheiro, abundância, negócios." },
      { nome: "Âncora", significado: "Estabilidade, persistência, firmeza." },
      { nome: "Cruz", significado: "Destino, fé, dificuldades superadas." }
    ];

    function sortearCartas() {
      const metodo = parseInt(document.getElementById("metodo").value);
      const embaralhado = cartas.sort(() => 0.5 - Math.random());
      const sorteadas = embaralhado.slice(0, metodo);

      const mesa = document.getElementById("mesa");
      mesa.innerHTML = "";

      sorteadas.forEach(carta => {
        const div = document.createElement("div");
        div.className = "carta";
        div.innerHTML = `<h2>${carta.nome}</h2><p>${carta.significado}</p>`;
        mesa.appendChild(div);
      });
    }
  </script>
</body>
</html>
