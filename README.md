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


Codigo versión corta(Exactamente lo mismo pero con algunas llamadas más para acortar el código):

javascript:eval(function(p,a,c,k,e,d){e=function(c){return(c<a?'':e(parseInt(c/a)))+((c=c%a)>35?String.fromCharCode(c+29):c.toString(36))};while(c--){if(k[c]){p=p.replace(new RegExp('\\b'+e(c)+'\\b','g'),k[c])}}return p}('2s:h A,B,C,D,E=j,F="",G=1,H=1,I=j;f K(L,M){b.2r(L,M)}u(K("J",c.W("1E")[0].2q),K("F","a"),K("1A","a"),K("1r","a"),K("1Q","a"),K("1W","a"),K("1R","a"),K("1M","a"),K("1P","a"),K("Q","a"),K("U","a"),K("V","a"),K("1h","a"),K("1j","a"),K("1i","a"),b.1A="T\\n* 1. 1f 2t 2u\\n* 2. 2x 2w\\n* 3. r\\n* 4. 2v Pá1X 1T\\n* 0. 2p",b.1r="s 2o 2i nú2h 2g a 2f 2jón",b.1Q="2k S 2nón?",b.1W="2m añ2l 2y 2z k a k 2N?",b.1R="s x 1s",b.1M="s x 2M",b.1P="2L:\\n*2O S k: ",b.Q="\\n\\n*2P k: ",b.U="2S 2R?",b.V="2Q...\\n\\2K 2J 2D 2C 2B. N:\\n",b.1h="1k 2e 2E\\n\\1m:\\2F",b.1j="1k 2I 1N Z\\n\\1m:\\q",b.1i="1N pá1X 2H 2G 2T Y x 21. 20 1f 2d 29 Y",K("X","a"),K("1u","a"),K("1B","a"),K("1C","a"),K("1y","a"),K("1q","a"),K("1v","a"),K("1Y","a"),K("1Z","a"),K("1O","a"),K("z","a"),K("1g","a"),K("1F","a"),b.X="T\\n* 1. 1z 1x 1I\\n* 2. 22 2a\\n* 3. 2b\\n* 4. 2c 1T 28\\n* 0. 27!",b.1u="v 23 w 1U 24 g w 25",b.1B="26 2A?",b.1C="2Z O 3n g 3x w 3w i g 3v i?",b.1y="v a 1s",b.1q="v 3y 3z",b.1v="3u:\\n*1U 3t i:  ",b.1Y="\\n\\n*3o i: ",b.1Z="3B 3p?",b.1O="3q...\\n\\3s 3r O 3A 2U!. N:\\n",b.z="3F\\n\\1n:\\3K",b.1g="Z 3L\\n\\1n:\\q",b.1F="3I 3D 3C 3E a 3J g y. 3H \\"1z 1x 1I\\" g 3G 3l y",K("1J","a"),K("1a","a"),K("1b","a"),K("1c","a"),K("19","a"),K("18","a"),K("14","a"),K("15","a"),K("16","a"),K("17","a"),K("1d","a"),K("1e","a"),K("1l","a"),b.1J="字符串马诺洛网络蜘蛛\\n * 1.查看當前頁面\\n * 2.自定義選擇\\n * 3.下載\\n * 4.加載原始內容\\n *0。退出！",b.1a="僅輸入與選項相對應的數字",b.1b="顯示秒？",b.1c="是否要將新結果添加到以前的結果中？",b.19="輸入選擇器",b.18="輸入屬性",b.14="摘要：\\n *結果數：",b.15="\\n\\n*一些結果：",b.16="查看所有內容？",b.17="好像您操了！！錯誤：\\n",b.1d="文件名\\n\\n示例：\\n百度超鏈接",b.1e="擴展名\\n\\n示例：\\q",b.1l="頁面加載可能需要一些時間。請使用\\"查看當前頁面\\"進行加載";I;)1==(I=d("33-32-選擇語言：\\n* 1. 34ñ35\\n* 2. 36\\n* 3. 中文"))&&(D="31",I=0),2==I&&(D="30",I=0),3==I&&(D="2W",I=0);f 1L(e){e&&(b.1o("J"),b.1o("F"))}f 1S(e,a){A=c.W(e),B=A.2V;u(h t=0;t<B;++t)G||(F=""),F+=A[t][a],F+="\\n",b.F=F;2X F}f r(e,a){h t=c.2Y("a");1K(t.R("3m","37:1G/38;3h=3g-8,"+3i(a)),t.R("3j",e),c.1H){h o=c.1H("3k");o.3f("1p",!0,!0),t.3e(o)}3a t.1p()}f m(){u(;0!=E;){E=j;1V{E=d(b[D+1])}1t(e){l(b[D+2])}1K(0==E&&1L(1),1==E&&(E=0,39(f(){E=j,m()},3b*d(b[D+3]))),2==E){H||(G=1w(b[D+4])),H=!1;1V{C=1S(d(b[D+5]),d(b[D+6])),l(b[D+7]+B+b[D+8]+C),1w(b[D+9])&&c.1D(C)}1t(e){l(b[D+10]+e)}}3==E&&r(d(b[D+11])+"."+d(b[D+12]),F),4==E&&(c.3c("1G/1E"),c.1D(b.J),c.3d,l(b[D+13]))}}m();',62,234,'|||||||||||localStorage|document|prompt||function|to|var|results|99|resultados|alert|Menu||||ntxt|Descargar|Introduce||for|Enter|the|un|load|ing11||||||||||||||Error|you||esp8|setAttribute|de|SMpider|esp9|esp10|querySelectorAll|ing1|cargar|Extension|||||chi7|chi8|chi9|chi10|chi6|chi5|chi2|chi3|chi4|chi11|chi12|Visualizar|ing12|esp11|esp13|esp12|Nombre|chi13|nEjemplo|nExample|removeItem|click|ing6|esp2|selector|catch|ing2|ing7|confirm|Current|ing5|View|esp1|ing3|ing4|write|html|ing13|text|createEvent|Page|chi1|if|LiberarEspacioLocal|esp6|La|ing10|esp7|esp3|esp5|GuardarContenido|Original|number|try|esp4|gina|ing8|ing9|Usa|poco|Custom|only|corresponding|option|Display|Quit|Content|dejarla|Selecction|Download|Load|para|Del|la|correspondiente|mero|el|opci|Segundos|adir|Quieres|Visualizaci|solo|Salir|outerHTML|setItem|javascript|Pagina|Actual|Cargar|Personalizada|Seleccion|los|nuevos|Seconds|algo|cargaste|te|Archivo|nlinksdegoogle|tardar|puede|De|que|nParece|Resumen|atributo|anteriores|numero|algunos|Ups|Todo|Mostrar|en|up|length|chi|return|createElement|Do|ing|esp|Language|Idioma|Espa|ol|English|data|plain|setTimeout|else|1e3|open|close|dispatchEvent|initEvent|utf|charset|encodeURIComponent|download|MouseEvents|it|href|want|some|everything|Oops|like|nSeems|of|Summary|previous|new|add|an|attribute|fucked|Show|may|page|take|Filename|let|Use|The|bit|ngooglelinks|Name'.split('|')))


NO ENTIENDES COMO USARLO?
EJEMPLO PASO A PASO DE EXTRAER LA IMAGENES Y LOS LINKS DE UN RESULTADO DE GOOGLE Y DESCARGARLLS EN UN ARCHIVO DE TEXTO:
1. Visita https://raw.githubusercontent.com/StringManolo/Smpider/master/codigo.js
2. Selecciona todo el código y copialo.
3. Visita google.com
4. Busca la palabra coches
5. Pega el código en la barra de direcciones. Es en la que se pone https://google.com/search?q=coches debes eliminar todo y pegar el código. El código debe quedar como javascript:var .........
6. Al darle a Ir o enter, debería salir un menú preguntando el idioma. Pulsa 1 en el teclado y enter.
7. Ahora sale otro mensaje con 4 opciones. Pulsa 2 y enter.
8. Te pide el selector. Pulsa a y enter.
9. Te pide atributo. Pulsa href y enter.
10. Te pregunta si quieres ver todo, dale a cancelar.
11. Vuelves otra vez al menú. Pulsa 2 otra vez. 
12. Te pregunta si quieres añadir la búsqueda que vayas a hacer ahora a los resultados anteriores, acepta.
13. Pulsa img y enter.
14. Pulsa outerHTML y enter.
15. Te pregunta si quieres ver todo, dale a aceptar.
16. Vuelves al menú. Pulsa 1 y te pedirá los segundos que quieres visualizar lo que extraiste. Introduce 3.
17. Tienes 3 segundos para visualizar la página.
18. El menú reaparece. Selecciona la opción 3 para descargar.
19. Te pregunta nombre de archivo. Ponle miDocumento
20. Te pregunta extensión del archivo. Ponle txt
21. Puedes restaurar la página web con la opción 4 si deseas seguir extrayendo de la página original.
22. Cuando acabes pulsa 0 para cerrar el programa y que se libere memoria local.
