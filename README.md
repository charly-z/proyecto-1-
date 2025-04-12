<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>Examen con Explicación</title>
  <style>
    body { font-family: Arial; background: #eef3fb; padding: 20px; max-width: 800px; margin: auto; }
    .pregunta { margin-bottom: 30px; padding: 20px; background: white; border-radius: 10px; box-shadow: 0 0 10px #ccc; }
    .boton { background-color: #3498db; color: white; border: none; padding: 10px 15px; margin: 5px; border-radius: 5px; cursor: pointer; }
    .explicacion { margin-top: 10px; font-style: italic; color: #555; }
    .resultado { font-weight: bold; margin-top: 10px; }
  </style>
</head>
<body>
  <h1>Examen de Inglés - Nivel 1</h1>
  <div class="pregunta">
    <p><strong>1. ¿Cuál es la forma correcta del verbo en esta oración?</strong><br>
    “She ___ to school every day.”</p>
    <button class="boton" onclick="responder(this, 'go')">go</button>
    <button class="boton" onclick="responder(this, 'goes')">goes</button>
    <button class="boton" onclick="responder(this, 'gone')">gone</button>
    <div class="resultado" id="resultado1"></div>
    <div class="explicacion" id="explicacion1"></div>
  </div>

  <script>
    function responder(boton, seleccionada) {
      const correcta = "goes";
      const resultado = document.getElementById("resultado1");
      const explicacion = document.getElementById("explicacion1");

      if (resultado.textContent !== "") return;

      if (seleccionada === correcta) {
        resultado.textContent = "¡Correcto!";
        resultado.style.color = "green";
      } else {
        resultado.textContent = "Incorrecto. La respuesta correcta es: " + correcta;
        resultado.style.color = "red";
      }

      explicacion.textContent = "Explicación: En tercera persona del singular (he, she, it), al verbo en presente simple se le agrega 's' o 'es'. Por eso es 'goes'.";
      
      const botones = boton.parentElement.querySelectorAll("button");
      botones.forEach(b => b.disabled = true);
    }
  </script>
</body>
</html>
