# ejercicio3
trabajo de pow ejercicio 3
<!--
Instrucciones:
+ Crear un editor wysiwyg (what you see is what you get) simple
+ Cambiar el texto dentro del div "text" de acuerdo con la selección que se haga del formulario
OJO
solo se puede cambiar el tamaño del texto seleccionado
problemas con el tamaño de la letra tengo que recargar o escribir una nueva palabra palabra para poder cambiar el tamaño del texto
me gustaria saber donde esta el problema gracias
-->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title> Exercise #4: Formatting text</title>
    <style>
        div#form{
          margin: 0 auto;
          width: 450px;
          height: 300px;
        }
        div#cuadro{
          border-bottom: none;
          padding: 10px;
          background-color: rgb(153,102,51);
          color; white;
          border-radius: 8px 8px 0px 0px;
        }
        div#text{
          border: 2px solid rgb(153,102,51);
          height:100%;
          width: 446px;
        }
        iframe#edit{
          height: 100%;
          width: 100%;
        }

    </style>
    <script>
        window.addEventListener("load",function(){
        var editor = edit.document;
        editor.designMode = "on";

        font_italic.addEventListener("click", function(){
            editor.execCommand("Italic", false, null);
        },false);

        font_bold.addEventListener("click", function(){
            editor.execCommand("Bold", false, null);
        },false);

        font_underline.addEventListener("click", function(){
            editor.execCommand("Underline", false, null);
        },false);

        font_family.addEventListener("change", function(event){
            editor.execCommand("FontName", false, event.target.value);
        },false);

        font_size.addEventListener("change", function(event){
            editor.execCommand("FontSize", false, event.target.value);
        },false);

      },false);
    </script>
</head>
<body>
  <div id="form">
          <div id="cuadro">
            <select name="font_family" id="font_family">
                <option value="Arial" selected>Arial</option>
                <option value="Verdana">Verdana</option>
                <option value="Helvetica">Helvetica</option>
                <option value="Times New Roman">Times New Roman</option>
                <option value="Courier New">Courier New</option>
            </select>
            <select name="font_size" id="font_size">
                  <option value="8pt">8pt</option>
                  <option value="10pt">10pt</option>
                  <option value="12pt" selected>12pt</option>
                  <option value="14pt">14pt</option>
                  <option value="16pt">16pt</option>
                  <option value="16pt">18pt</option>
            </select>
            <label>Italic <input type="checkbox" name="font_italic" id="font_italic"></label>
            <label>Bold <input type="checkbox" name="font_bold" id="font_bold"></label>
            <label>Underline <input type="checkbox" name="font_underline" id="font_underline"></label>

          </div>
            <div id="text">
                <iframe id="edit" name="edit" frameborder="0"> </iframe>
            </div>
  </div>
  <script>
      var fonts = document.querySelectorAll("select#font_family > option");
      for (var i = 0; i < fonts.length; i++) {
        fonts[i].style.fontFamily = fonts[i].value;
      }
  </script>
</body>
</html>
