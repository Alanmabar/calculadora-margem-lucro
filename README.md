# calculadora-margem-lucro

<!DOCTYPE html>
<html>
<head>
  <title>Calculadora de Margem de Lucro</title>
  <style>
    /* Estilos CSS para a calculadora */
    body {
      font-family: Arial, sans-serif;
      background-image: url('https://scontent.fcgh6-1.fna.fbcdn.net/v/t39.30808-6/411885195_10232266367386951_343195903545497581_n.jpg?_nc_cat=101&ccb=1-7&_nc_sid=3635dc&_nc_eui2=AeEg7ln0-gzms-k4lwXMdVbVQ0A9IHS7aRZDQD0gdLtpFp8oN9L2bsllX6KyRrHKz1A&_nc_ohc=qqmwbkb5860AX8p1C0J&_nc_ht=scontent.fcgh6-1.fna&oh=00_AfA0A_fNBs7D0YGYPwlEZb71oR9BOeM5LRKpt14Kla11Cg&oe=658BF5A8');
      background-size: cover;
      background-position: center;
      margin: 0;
    }

    .container {
      max-width: 600px;
      margin: 0 auto;
      padding: 20px;
      background-color: rgba(255, 255, 255, 0.8);
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      border-radius: 5px;
    }

    h1 {
      text-align: center;
      color: #333;
    }

    .input-group {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 20px;
    }

    .input-group label {
      flex: 1;
      text-align: right;
      margin-right: 10px;
      color: #666;
    }

    .input-group input {
      flex: 2;
      padding: 5px;
      border-radius: 3px;
      border: 1px solid #ccc;
    }

    .btn-calcular {
      display: block;
      width: 100%;
      padding: 10px;
      text-align: center;
      font-weight: bold;
      color: #fff;
      background-color: #3498db;
      border: none;
      border-radius: 3px;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    .btn-calcular:hover {
      background-color: #2980b9;
    }

    .resultado {
      text-align: center;
      font-size: 18px;
      font-weight: bold;
      margin-top: 20px;
    }

    .social-icons {
      display: flex;
      justify-content: center;
      align-items: center;
      margin-top: 20px;
    }

    .social-icons a {
      display: inline-block;
      margin: 0 5px;
      color: #666;
      text-decoration: none;
    }

    .social-icons img {
      width: 20px;
      height: 20px;
      vertical-align: middle;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Calculadora de Margem de Lucro</h1>
    <div class="input-group">
      <label for="custo-produto">Custo do Produto:</label>
      <input type="number" id="custo-produto">
    </div>
    <div class="input-group">
      <label for="frete">Frete:</label>
      <input type="number" id="frete">
    </div>
    <div class="input-group">
      <label for="custo-trafego">Custo de Tráfego:</label>
      <input type="number" id="custo-trafego">
    </div>
    <div class="input-group">
      <label for="multiplicador">Multiplicador:</label>
      <input type="number" id="multiplicador" step="0.01" min="0" value="1.9">
    </div>
    <button class="btn-calcular" onclick="calcularMargemLucro()">Calcular Margem de Lucro</button>
    <div class="resultado" id="resultado"></div>
    <div class="social-icons">
      <a href="https://grazioza.com.br" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/1356/1356332.png" alt="Site"></a>
      <a href="https://www.instagram.com/alanm.barros" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/1936/1936319.png" alt="Instagram"></a>
    </div>
  </div>

  <script>
    // Função para calcular a margem de lucro e exibir o resultado
    function calcularMargemLucro() {
      var custoProduto = parseFloat(document.getElementById("custo-produto").value);
      var frete = parseFloat(document.getElementById("frete").value);
      var custoTrafego = parseFloat(document.getElementById("custo-trafego").value);
      var multiplicador = parseFloat(document.getElementById("multiplicador").value);

      var custoTotal = custoProduto + frete + custoTrafego;
      var valorVenda = custoTotal * multiplicador;
      var taxas = valorVenda * 0.065;
      var margemLucro = valorVenda - taxas - custoTotal;

      document.getElementById("resultado").innerHTML = "A margem de lucro é de R$ " + margemLucro.toFixed(2);
    }
  </script>
</body>
</html>
