---
layout: page
title: Media o projekcie
permalink: /cyfrowa/
---

### Muzykologia cyfrowa

Trwają ostatnie przygotowania do rozpoczęcia prac nad sporządzaniem na niespotykaną dotąd skalę cyfrowych edycji wszystkich dzieł Fryderyka Chopina.
O niezwykłości działań prowadzonych w ramach projektu *Dziedzictwo Chopinowskie w otwartym dostępie* świadczą dwa aspekty.
Po pierwsze, każdy utwór doczeka się kilku wersji cyfrowych, będących dokładnym odwzorowaniem konkretnego pierwodruku ze zbiorów Biblioteki - Fonoteki - Fototeki NIFC i Muzeum Fryderyka Chopina.
Po drugie, edycje będą sporządzone w formacie Humdrum - w pełni cyfrowym języku zapisu muzycznego.
Dzięki temu możliwe będzie nie tylko automatyczne porównanie różnic między wydaniami tej samej kompozycji, lecz także przeprowadzenie komputerowej analizy muzycznej i muzykologicznej.
Dodatkowo dzięki rozwijanemu także dzięki BFF NIFC oprogramowaniu *Verovio* edycje w formie graficznej będzie można wyświetlać online na komputerach i urządzeniach mobilnych.

![Schemat tworzenia i wyświetlania edycji](https://nifc.github.io/images/2018-03_JI_001.png?raw=true)

---
<html>
<head>
<title>SimpleViewer</title>
<script src="http://verovio-script.humdrum.org/scripts/verovio-toolkit.js">
</script>
</head>
<body>

Here is a short musical example:

<script id="input" type="text/humdrum"> 
**kern	**kern
*clefF4	*clefG2
*k[f#]	*k[f#]
*M4/4	*M4/4
=-	=-
8GL	8ddL
8AJ	8ccJ
16BLL	2.b;
16A	.
16G	.
16F#JJ	.
2G;	.
==	==
*-	*-
</script>

<div id="output"></div>

<script>
   var vrvToolkit = new verovio.toolkit();
   var Input = document.querySelector("#input");
   var Output = document.querySelector("#output");
   document.addEventListener("DOMContentLoaded", displayNotation);

   function displayNotation() {
      if (!vrvToolkit) {
         return;
      }
      var data = Input.textContent;
      var options = {
         inputFormat: "humdrum",
         adjustPageHeight: 1,
         pageHeight: 1000,
         pageWidth:  1000,
         scale:  40,
         font: "Leipzig"
      };

      var svg = vrvToolkit.renderData(data, options);
      Output.innerHTML = svg;
   }
</script>

</body>
</html>

