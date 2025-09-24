# Salario_Mensual
codigo con html, java script y bootstrap 
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Calculadora de Sueldo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f0f4f8;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .container {
      background-color: #ffffff;
      padding: 30px 40px;
      border-radius: 15px;
      box-shadow: 0px 5px 15px rgba(0,0,0,0.2);
      width: 350px;
    }
    h1 {
      text-align: center;
      color: #333;
    }
    label {
      display: block;
      margin-top: 15px;
      color: #555;
    }
    input[type="text"] {
      width: 100%;
      padding: 8px 10px;
      margin-top: 5px;
      border-radius: 8px;
      border: 1px solid #ccc;
      box-sizing: border-box;
    }
    button {
      width: 100%;
      padding: 10px;
      margin-top: 20px;
      border: none;
      border-radius: 10px;
      background-color: #4CAF50;
      color: white;
      font-size: 16px;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover {
      background-color: #45a049;
    }
    #resultado {
      margin-top: 20px;
      background-color: #eef6f7;
      padding: 15px;
      border-radius: 10px;
      color: #333;
    }
    ul {
      padding-left: 20px;
    }
    li {
      margin-bottom: 8px;
    }
  </style>
</head>
<body>
 <div class="container">
  <h1>Calculadora de Sueldo</h1>

  <label for="Nombre">Nombre:</label>
  <input type="text" id="Nombre" placeholder="Nombre del empleado">

  <label for="Sueldo_Mensual">Sueldo Mensual:</label>
  <input type="text" id="Sueldo_Mensual" placeholder="Sueldo Mensual">

  <label for="Meses_Trabajados">Meses Trabajados:</label>
  <input type="text" id="Meses_Trabajados" placeholder="Meses Trabajados">

  <button onclick="calcularSueldo()">Calcular Sueldo</button>
  <div id="resultado"></div>
 </div>
 <script>
  function calcularSueldo() {
      let nombre = document.getElementById("Nombre").value;
      let sueldo = Number(document.getElementById("Sueldo_Mensual").value);
      let meses = Number(document.getElementById("Meses_Trabajados").value);
      if(nombre === "" || isNaN(sueldo) || isNaN(meses)){
        alert("Por favor, complete todos los campos correctamente.");
        return;
      }
      let años = Math.floor(meses / 12); // corregido
      let mesesSobrantes = meses % 12;
      let bonoAnual = anios * 2000;
      if (bonoAnual > 10000) bonoAnual = 10000;
      let bonoMensual = mesesSobrantes * 100;
      let aguinaldo = bonoAnual + bonoMensual;
      let totalPagar = sueldo + aguinaldo;
      document.getElementById("resultado").innerHTML = `
        <ul>
          <li><strong>Empleado:</strong> ${nombre}</li>
          <li><strong>Sueldo Mensual:</strong> $${sueldo.toLocaleString()}</li>
          <li><strong>Aguinaldo:</strong> $${aguinaldo.toLocaleString()}</li>
          <li><strong>Total a Pagar:</strong> $${totalPagar.toLocaleString()}</li>
        </ul>
      `;
  }
 </script>
</body>
</html>
