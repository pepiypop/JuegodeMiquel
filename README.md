# JuegodeMiquel
<!DOCTYPE html>
 <html lang="es">
<head>
     <meta charset="UTF-8">
     <title>Aventuras en la Naturaleza</title>
     </head>
      <body>
         <h1>¡Bienvenido a Aventuras en la Naturaleza!</h1>
          <div id="pregunta"></div>
           <div id="respuestas"></div>
            <div id="resultado"></div>
             <button id="siguiente"
              style="display:none;">Siguiente</button>
               <script>
                const preguntas = [
                     { pregunta: "Estás en el Bosque. Te encuentras con una ardilla.", preguntaTexto: "¿Qué comen las ardillas?", respuestas: ["Carne", "Frutas y nueces", "Insectos"], correcta: 1 },
                      { pregunta: "Estás en el Desierto. Te encuentras con un camello.", preguntaTexto: "¿Cuánto tiempo puede sobrevivir un camello sin agua?", respuestas: ["1 semana", "2 semanas", "1 mes"], correcta: 1 },
                       { pregunta: "Estás en el Océano. Te encuentras con un delfín.", preguntaTexto: "¿Cómo respiran los delfines?", respuestas: ["Por las branquias", "Por los pulmones", "Por la piel"], correcta: 1 },
                        { pregunta: "Estás en la Jungla. Te encuentras con un jaguar.", preguntaTexto: "¿Cuál es el hábitat principal del jaguar?", respuestas: ["Desierto", "Jungla", "Montaña"], correcta: 1 },
                         { pregunta: "Estás en el Ártico. Te encuentras con un oso polar.", preguntaTexto: "¿Qué comen los osos polares?", respuestas: ["Focas", "Pingüinos", "Hojas"], correcta: 0 },
                          { pregunta: "Estás en la Sabana. Te encuentras con un elefante.", preguntaTexto: "¿Cuál es la principal fuente de alimento del elefante?", respuestas: ["Carne", "Hierba", "Peces"], correcta: 1 },
                           { pregunta: "Estás en la Montaña. Te encuentras con una cabra montés.", preguntaTexto: "¿Qué característica ayuda a las cabras montesas a escalar?", respuestas: ["Sus pezuñas", "Sus garras", "Sus alas"], correcta: 0 },
                            { pregunta: "Estás en el Pantano. Te encuentras con un cocodrilo.", preguntaTexto: "¿Cómo cazan los cocodrilos?", respuestas: ["Corren rápido", "Se esconden y emboscan", "Cazan en manada"], correcta: 1 },
                             { pregunta: "Estás en la Tundra. Te encuentras con un reno.", preguntaTexto: "¿De qué se alimentan los renos en invierno?", respuestas: ["Lichens", "Insectos", "Frutas"], correcta: 0 },
                              { pregunta: "Estás en un Lago. Te encuentras con un pez dorado.", preguntaTexto: "¿Qué tipo de animal es el pez dorado?", respuestas: ["Mamífero", "Reptil", "Pez"], correcta: 2 }
                               ];
                                let indice = 0;
                                 let puntos = 0;
                                  function
                                   mostrarPregunta() {
                                     document.getElementById("resultado").innerHTML = "";
                                      document.getElementById("siguiente").style.display = "none";
                                       document.getElementById("pregunta").innerText = preguntas[indice].preguntaTexto;
                                        const respuestasDiv = document.getElementById("respuestas"); respuestasDiv.innerHTML = "";
                                         preguntas[indice].respuestas.forEach((respuesta, i) => {
                                             const button = document.createElement("button");
                                              button.innerText = respuesta;
                                               button.onclick = () => verificarRespuesta(i);
                                                respuestasDiv.appendChild(button);
                                                 });
                                                  }
                                                   function
                                                    verificarRespuesta(opcion) {
                                                         if (opcion === preguntas[indice].correcta) { puntos += 10;
                                                          document.getElementById("resultado").innerText = "¡Correcto!"; } else {
                                                             document.getElementById("resultado").innerText = "Incorrecto."; }
                                                              document.getElementById("siguiente").style.display = "block"; }
                                                               document.getElementById("siguiente").onclick = () => {
                                                                 indice++;
                                                                  if (indice < preguntas.length) {
                                                                     mostrarPregunta(); 
                                                                     } else {
                                                                         document.getElementById("pregunta").innerText = "Juego terminado. Puntos obtenidos: " + puntos;
                                                                          document.getElementById("respuestas").innerHTML = "";
                                                                           document.getElementById("siguiente").style.display = "none";
                                                                            } };
                                                                             mostrarPregunta(); </script> </body> </html>
