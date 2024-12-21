# mi-tienda-sicaf
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Menú Hamburguesa - Estilo Epic Games</title>
  <style>
  

    body {
    
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      background-color: #f5f5f5;
    }

    .header {
      text-align: center;
      background-color: #333;
      color: white;
      padding: 30px 0;
      font-size: 36px;
      position: sticky;
      top: 0;
      z-index: 1000;
    }

    .menu-container {
      margin: 40px;
      text-align: center;
    }

    .menu-item {
      display: inline-block;
      margin: 20px;
      cursor: pointer;
      text-align: center;
    }

    .menu-item img {
      width: 250px;
      height: auto;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
    }

    .menu-item p {
      margin-top: 15px;
      font-size: 24px;
      font-weight: bold;
      color: #333;
    }

    /* Pantalla completa */
    .fullscreen {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.9);
    z-index: 1001; /* Asegura que la pantalla completa esté por encima del contenido normal */
    color: white;
    text-align: center;
    font-size: 24px;
  }


    .fullscreen.active {
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .fullscreen .title {
      font-size: 48px;
      margin-bottom: 20px;
    }

    .fullscreen a {
      color: white;
      text-decoration: none;
      font-size: 20px;
      margin: 10px;
      display: inline-block;
      background: rgba(255, 255, 255, 0.2);
      padding: 10px 20px;
      border-radius: 10px;
      transition: background 0.3s;
    }

    .fullscreen a:hover {
      background: rgba(255, 255, 255, 0.5);
    }

    .close-btn {
    position: absolute;
    top: 20px;
    right: 30px;
   cursor: pointer;
    font-size: 30px;
    color: rgb(69, 8, 221);
    z-index: 2000; /* Asegura que la 'X' esté por encima de otros elementos */
  }
    

    /* Pantallas individuales */
    .screen {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: white;
      z-index: 1002;
    }

    .screen img {
      position: absolute;
      top: 20px;
      left: 20px;
      width: 200px;
      height: auto;
    }

    .screen h1 {
      margin-top: 200px;
      text-align: center;
      font-size: 48px;
      color: #333;
    }
  </style>
</head>
<body>
  <!-- Encabezado -->
  <div class="header">SICAF</div>

  <!-- Menú principal -->
  <div class="menu-container">
    <div class="menu-item" onclick="openFullscreen('tommy')">
      <img src="tommy.png" alt="Tommy Hilfiger">
      <p>Tommy Hilfiger</p>
    </div>
    <div class="menu-item" onclick="openFullscreen('adidas')">
      <img src="adidas.png" alt="Adidas">
      <p>Adidas</p>
    </div>
    <div class="menu-item" onclick="openFullscreen('lacoste')">
      <img src="lacost.png" alt="Lacoste">
      <p>Lacoste</p>
    </div>
    <div class="menu-item" onclick="openFullscreen('calvin')">
      <img src="calvin.png" alt="Calvin Klein">
      <p>Calvin Klein</p>
    </div>
  </div>

  <!-- Pantallas completas -->
  <div class="fullscreen" id="fullscreen-tommy">
    <div class="close-btn" onclick="closeFullscreen()">×</div>
    <div class="title">Tommy Hilfiger</div>
    <a onclick="openScreen('tommy', 'calentadores')">Calentadores</a>
    <a onclick="openScreen('tommy', 'zapatos')">Zapatos</a>
    <a onclick="openScreen('tommy', 'camisetas')">Camisetas</a>
    <a onclick="openScreen('tommy', 'pantalones')">Pantalones</a>
    <a onclick="openScreen('tommy', 'chaquetas')">Chaquetas</a>
  </div>

  <div class="fullscreen" id="fullscreen-adidas">
    <div class="close-btn" onclick="closeFullscreen()">×</div>
    <div class="title">Adidas</div>
    <a onclick="openScreen('adidas', 'calentadores')">Calentadores</a>
    <a onclick="openScreen('adidas', 'zapatos')">Zapatos</a>
    <a onclick="openScreen('adidas', 'camisetas')">Camisetas</a>
    <a onclick="openScreen('adidas', 'pantalones')">Pantalones</a>
    <a onclick="openScreen('adidas', 'chaquetas')">Chaquetas</a>
  </div>

  <div class="fullscreen" id="fullscreen-lacoste">
    <div class="close-btn" onclick="closeFullscreen()">×</div>
    <div class="title">Lacoste</div>
    <a onclick="openScreen('lacoste', 'calentadores')">Calentadores</a>
    <a onclick="openScreen('lacoste', 'zapatos')">Zapatos</a>
    <a onclick="openScreen('lacoste', 'camisetas')">Camisetas</a>
    <a onclick="openScreen('lacoste', 'pantalones')">Pantalones</a>
    <a onclick="openScreen('lacoste', 'chaquetas')">Chaquetas</a>
  </div>

  <div class="fullscreen" id="fullscreen-calvin">
    <div class="close-btn" onclick="closeFullscreen()">×</div>
    <div class="title">Calvin Klein</div>
    <a onclick="openScreen('calvin', 'calentadores')">Calentadores</a>
    <a onclick="openScreen('calvin', 'zapatos')">Zapatos</a>
    <a onclick="openScreen('calvin', 'camisetas')">Camisetas</a>
    <a onclick="openScreen('calvin', 'pantalones')">Pantalones</a>
    <a onclick="openScreen('calvin', 'chaquetas')">Chaquetas</a>
  </div>

  <!-- Pantallas individuales -->
  <!-- Tommy -->
  <div class="screen" id="screen-tommy-calentadores">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="tommy-calentadores.png" alt="Calentadores Tommy Hilfiger">
    <h1>Calentadores Tommy Hilfiger</h1>
  </div>

  <div class="screen" id="screen-tommy-zapatos">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="tommy-zapatos.png" alt="Zapatos Tommy Hilfiger">
    <h1>Zapatos Tommy Hilfiger</h1>
  </div>

  <div class="screen" id="screen-tommy-camisetas">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="tommy-camisetas.png" alt="Camisetas Tommy Hilfiger">
    <h1>Camisetas Tommy Hilfiger</h1>
  </div>

  <div class="screen" id="screen-tommy-pantalones">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="tommy-pantalones.png" alt="Pantalones Tommy Hilfiger">
    <h1>Pantalones Tommy Hilfiger</h1>
  </div>

  <div class="screen" id="screen-tommy-chaquetas">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="tommy-chaquetas.png" alt="Chaquetas Tommy Hilfiger">
    <h1>Chaquetas Tommy Hilfiger</h1>
  </div>

  <!-- Adidas -->
  <div class="screen" id="screen-adidas-calentadores">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="adidas-calentadores.png" alt="Calentadores Adidas">
    <h1>Calentadores Adidas</h1>
  </div>

  <div class="screen" id="screen-adidas-zapatos">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="adidas-zapatos.png" alt="Zapatos Adidas">
    <h1>Zapatos Adidas</h1>
  </div>

  <div class="screen" id="screen-adidas-camisetas">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="adidas-camisetas.png" alt="Camisetas Adidas">
    <h1>Camisetas Adidas</h1>
  </div>

  <div class="screen" id="screen-adidas-pantalones">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="adidas-pantalones.png" alt="Pantalones Adidas">
    <h1>Pantalones Adidas</h1>
  </div>

  <div class="screen" id="screen-adidas-chaquetas">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="adidas-chaquetas.png" alt="Chaquetas Adidas">
    <h1>Chaquetas Adidas</h1>
  </div>

  <!-- Lacoste -->
  <div class="screen" id="screen-lacoste-calentadores">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="lacoste-calentadores.png" alt="Calentadores Lacoste">
    <h1>Calentadores Lacoste</h1>
  </div>

  <div class="screen" id="screen-lacoste-zapatos">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="lacoste-zapatos.png" alt="Zapatos Lacoste">
    <h1>Zapatos Lacoste</h1>
  </div>

  <div class="screen" id="screen-lacoste-camisetas">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="lacoste-camisetas.png" alt="Camisetas Lacoste">
    <h1>Camisetas Lacoste</h1>
  </div>

  <div class="screen" id="screen-lacoste-pantalones">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="lacoste-pantalones.png" alt="Pantalones Lacoste">
    <h1>Pantalones Lacoste</h1>
  </div>

  <div class="screen" id="screen-lacoste-chaquetas">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="lacoste-chaquetas.png" alt="Chaquetas Lacoste">
    <h1>Chaquetas Lacoste</h1>
  </div>

  <!-- Calvin Klein -->
  <div class="screen" id="screen-calvin-calentadores">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="calvin-calentadores.png" alt="Calentadores Calvin Klein">
    <h1>Calentadores Calvin Klein</h1>
  </div>

  <div class="screen" id="screen-calvin-zapatos">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="calvin-zapatos.png" alt="Zapatos Calvin Klein">
    <h1>Zapatos Calvin Klein</h1>
  </div>

  <div class="screen" id="screen-calvin-camisetas">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="calvin-camisetas.png" alt="Camisetas Calvin Klein">
    <h1>Camisetas Calvin Klein</h1>
  </div>

  <div class="screen" id="screen-calvin-pantalones">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="calvin-pantalones.png" alt="Pantalones Calvin Klein">
    <h1>Pantalones Calvin Klein</h1>
  </div>

  <div class="screen" id="screen-calvin-chaquetas">
    <div class="close-btn" onclick="closeScreen()">×</div>
    <img src="calvin-chaquetas.png" alt="Chaquetas Calvin Klein">
    <h1>Chaquetas Calvin Klein</h1>
  </div>

  <script>
    // Función para abrir pantalla completa para cada marca
    function openFullscreen(brand) {
      document.getElementById('fullscreen-' + brand).classList.add('active');
    }

    // Función para cerrar pantalla completa
    function closeFullscreen() {
      const fullscreenElements = document.querySelectorAll('.fullscreen');
      fullscreenElements.forEach(element => {
        element.classList.remove('active');
      });
    }

    // Función para abrir pantallas de productos específicos
    function openScreen(brand, product) {
      document.getElementById('screen-' + brand + '-' + product).style.display = 'block';
    }

    // Función para cerrar pantallas de productos
    function closeScreen() {
      const screenElements = document.querySelectorAll('.screen');
      screenElements.forEach(element => {
        element.style.display = 'none';
      });
    }
  </script>
</body>
</html>
