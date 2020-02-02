# Smpider
Standalone Js Crawler. (Human Version)

Como Ejecutar:

1. Copia todo el código javascript.
2. Visita cualquier página web.
3. Introduce el código en la barra de direcciones y pulsa ir.
IMPORTANTE: Es posible que el navegador Google Chrome elimine la palabra javascript: al pegar el código en la barra de direcciones. Debes ir al principio del código y añadírselo. O usa otro navegador.

Como Usar:

La opción número 1 para los mensajes emergentes para dejarte visualizar la página web.

La opción número 2 te pide un selector (se usa igual que los estilos de css) si por ejemplo quieres extraer los links de la página web, introduces la letra a.
 La opción número 2 te pide un atributo. Por ejemplo href.
 La opción número 2 guarda los resultados en memoria local. Si no es la primera vez que utilizas esta opción te permite añadir resultados para que puedas visualizar todo lo que extraigas de la página simultaneamente o descargarlo.
Ejemplos de selectores y atributos útiles:
a href
img src
a outerHTML
img outerHTML
title innerHTML
.btn-class outerHTML
#miDiv innerHTML
html outerHTML
...


La opción número 3 te permite descargar todo lo que seleccionases con la opción numero 2. Te pide el nombre del archivo, ej: MiDocumento
También te pide la extensión, ej: txt

La opción número 4 carga la página web original para que puedas seguir sacando contenido. Recomendado usar la opción número 1 tras esta opción para dejar cargar la web 2 o 3 segundos.

La opción número 0 cierra el programa. Recomendado usarla en vez de forzar el cierre, ya que libera memoria.

ESTÁ EN DESARROLLO. CAMBIOS SERÁN INTRODUCIDOS.

Codigo:
https://raw.githubusercontent.com/StringManolo/Smpider/master/codigo.js


Codigo:

javascript:var links,tam,res,guardarLocal,defecto,chino,espanhol,ingles,actual,menu=99,tags="",mantenerResultados=1,primeraVuelta=1,liberar=!1,idioma=99;for(localStorage.setItem("web",document.querySelectorAll("html")[0].outerHTML),localStorage.setItem("tags","a"),localStorage.setItem("esp1","a"),localStorage.setItem("esp2","a"),localStorage.setItem("esp3","a"),localStorage.setItem("esp4","a"),localStorage.setItem("esp5","a"),localStorage.setItem("esp6","a"),localStorage.setItem("esp7","a"),localStorage.setItem("esp8","a"),localStorage.setItem("esp9","a"),localStorage.setItem("esp10","a"),localStorage.setItem("esp11","a"),localStorage.setItem("esp12","a"),localStorage.setItem("esp13","a"),localStorage.esp1="SMpider\n* 1. Visualizar Pagina Actual\n* 2. Seleccion Personalizada\n* 3. Descargar\n* 4. Cargar Página Original\n* 0. Salir",localStorage.esp2="Introduce solo el número correspondiente a la opción",localStorage.esp3="Segundos de Visualización?",localStorage.esp4="Quieres añadir los nuevos resultados a resultados anteriores?",localStorage.esp5="Introduce un selector",localStorage.esp6="Introduce un atributo",localStorage.esp7="Resumen:\n*numero de resultados: ",localStorage.esp8="\n\n*algunos resultados: ",localStorage.esp9="Mostrar Todo?",localStorage.esp10="Ups...\n\nParece que te cargaste algo. Error:\n",localStorage.esp11="Nombre Del Archivo\n\nEjemplo:\nlinksdegoogle",localStorage.esp12="Nombre De La Extension\n\nEjemplo:\ntxt",localStorage.esp13="La página puede tardar en cargar un poco. Usa Visualizar para dejarla cargar",localStorage.setItem("ing1","a"),localStorage.setItem("ing2","a"),localStorage.setItem("ing3","a"),localStorage.setItem("ing4","a"),localStorage.setItem("ing5","a"),localStorage.setItem("ing6","a"),localStorage.setItem("ing7","a"),localStorage.setItem("ing8","a"),localStorage.setItem("ing9","a"),localStorage.setItem("ing10","a"),localStorage.setItem("ing11","a"),localStorage.setItem("ing12","a"),localStorage.setItem("ing13","a"),localStorage.ing1="SMpider\n* 1. View Current Page\n* 2. Custom Selecction\n* 3. Download\n* 4. Load Original Content\n* 0. Quit!",localStorage.ing2="Enter only the number corresponding to the option",localStorage.ing3="Display Seconds?",localStorage.ing4="Do you want to add the new results to previous results?",localStorage.ing5="Enter a selector",localStorage.ing6="Enter an attribute",localStorage.ing7="Summary:\n*number of results:  ",localStorage.ing8="\n\n*some results: ",localStorage.ing9="Show everything?",localStorage.ing10="Oops...\n\nSeems like you fucked up!. Error:\n",localStorage.ing11="Filename\n\nExample:\ngooglelinks",localStorage.ing12="Extension Name\n\nExample:\ntxt",localStorage.ing13="The page may take a bit to load. Use \"View Current Page\" to let it load",localStorage.setItem("chi1","a"),localStorage.setItem("chi2","a"),localStorage.setItem("chi3","a"),localStorage.setItem("chi4","a"),localStorage.setItem("chi5","a"),localStorage.setItem("chi6","a"),localStorage.setItem("chi7","a"),localStorage.setItem("chi8","a"),localStorage.setItem("chi9","a"),localStorage.setItem("chi10","a"),localStorage.setItem("chi11","a"),localStorage.setItem("chi12","a"),localStorage.setItem("chi13","a"),localStorage.chi1="字符串马诺洛网络蜘蛛\n * 1.查看當前頁面\n * 2.自定義選擇\n * 3.下載\n * 4.加載原始內容\n *0。退出！",localStorage.chi2="僅輸入與選項相對應的數字",localStorage.chi3="顯示秒？",localStorage.chi4="是否要將新結果添加到以前的結果中？",localStorage.chi5="輸入選擇器",localStorage.chi6="輸入屬性",localStorage.chi7="摘要：\n *結果數：",localStorage.chi8="\n\n*一些結果：",localStorage.chi9="查看所有內容？",localStorage.chi10="好像您操了！！錯誤：\n",localStorage.chi11="文件名\n\n示例：\n百度超鏈接",localStorage.chi12="擴展名\n\n示例：\ntxt",localStorage.chi13="頁面加載可能需要一些時間。請使用\"查看當前頁面\"進行加載";idioma;)1==(idioma=prompt("Idioma-Language-選擇語言：\n* 1. Español\n* 2. English\n* 3. 中文"))&&(actual="esp",idioma=0),2==idioma&&(actual="ing",idioma=0),3==idioma&&(actual="chi",idioma=0);function LiberarEspacioLocal(e){e&&(localStorage.removeItem("web"),localStorage.removeItem("tags"))}function GuardarContenido(e,a){links=document.querySelectorAll(e),tam=links.length;for(var t=0;t<tam;++t)mantenerResultados||(tags=""),tags+=links[t][a],tags+="\n",localStorage.tags=tags;return tags}function Descargar(e,a){var t=document.createElement("a");if(t.setAttribute("href","data:text/plain;charset=utf-8,"+encodeURIComponent(a)),t.setAttribute("download",e),document.createEvent){var o=document.createEvent("MouseEvents");o.initEvent("click",!0,!0),t.dispatchEvent(o)}else t.click()}function Menu(){for(;0!=menu;){menu=99;try{menu=prompt(localStorage[actual+1])}catch(e){alert(localStorage[actual+2])}if(0==menu&&LiberarEspacioLocal(1),1==menu&&(menu=0,setTimeout(function(){menu=99,Menu()},1e3*prompt(localStorage[actual+3]))),2==menu){primeraVuelta||(mantenerResultados=confirm(localStorage[actual+4])),primeraVuelta=!1;try{res=GuardarContenido(prompt(localStorage[actual+5]),prompt(localStorage[actual+6])),alert(localStorage[actual+7]+tam+localStorage[actual+8]+res),confirm(localStorage[actual+9])&&document.write(res)}catch(e){alert(localStorage[actual+10]+e)}}3==menu&&Descargar(prompt(localStorage[actual+11])+"."+prompt(localStorage[actual+12]),tags),4==menu&&(document.open("text/html"),document.write(localStorage.web),document.close,alert(localStorage[actual+13]))}}Menu();
