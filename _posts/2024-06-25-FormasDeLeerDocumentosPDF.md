---
title: Buenas formas de leer documentos en pdf
date: '2024-06-25 17:44:27'
comments: true
categories: [Consejos tecnologicos]
tags: [ConsejosTecnologia]
---



Suelo utilizar estos metodos cuando deseo leer algun pdf y tengo la vista un poco agotada, les recomiendo probar esto a todos los lectores y a compartir el tutorial en caso os haya sido de ayuda.

# Metodo 1 : Instalando una extension de firefox
Esta ha sido la mejor extension que he encontrado hasta el momento, tiene distintos tonos y es facil de usar, tan solo abre la instalacion y arrastra el archivo que deseas leer. Ademas de eso, creo que al abrir un pdf en la web, este le aplicara el filtro.
Enlace de la extension:  
https://addons.mozilla.org/en-US/firefox/addon/doqment/ 

# Metodo 2 : insertando javascript en herramientas de desarrollador
Esta opcion suele ser de ayuda cuando uno no puede instalar extensiones en el entorno donde se encuentra por distintas razones, por ejemplo reglas o quizas no cuentas con internet para instalar una extension.
```javascript
document.getElementById('viewerContainer').style.filter = 'invert(0.95)';
```
