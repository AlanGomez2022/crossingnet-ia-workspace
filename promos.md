# Skill: Generador de Slugs para Promos

## Objetivo

- Modificar e archivo que se encuentra en `output/ssi_promos_2024.php`
- es agregar codigo sin eliminar nada. 
- utiliza el slug creado del texto.

 ## Reglas basicas de las Promos
 
 Esta skill utiliza el slug generado por "texto_acomodado.md
 Pero tambien utiliza un slug generado por este mismo skill "promos.md" que se compone por: 
 
 - Año actual (segun contexto) en 4 digitos ,`aaaa`
 - Mes: que viene del slug de "texto_acomodado.md" en 2 digitos, `mm`
 - Dia: que viene del slug de  "texto_acomodado.md" en 2 digitos, `dd`
 - finalmente la palabra "promo" en minusculas.
 - entre cada uno de estos se coloca un guion bajo: _

 Ejemplo: 
 
    2026_07_02_promo


## Estructura estándar de cada bloque de promo

- html de la promo: 
 <div class="col-xs-12 col-sm-6 col-md-4">
    <a href="https://www.stylus.com.ar/n_e_cross/piezas/SLUG.html" target="_blank" alt="" title="">
        <img src="images/promos/SLUG-PROMO.jpg" style="width: 350px;" />
        <div class="titpromo-wrapper">
            <span class="titpromo">TEXTO</span>
        </div>
    </a>
 </div>

 - Donde dice "SLUG" va el slug generado por este entorno de AGENT.md
 - En la img la ruta queda como está solo se modifica donde dice "SLUG-PROMO" por el slug creado por "promos.md"
 - en la etiqueda span en lugar de "TEXTO" reemplazamos por el texto que se ingreso en el prompt sin convertir en slug ni ponerle la fecha. El texto literal. 
 
 - html del mes:

 <div class="row">
    <div class="col-12">
        <div class="promo-mes">MES</div>
    </div>
 </div>
 
 - El mes cambia cuando se solicita desde el texto del slug y en los 2 digitos del mes es el mes siguinte de lo contrario se coloca dentro del mismo mes el bloque de promo. 
 - Va en forma de texto en mayusculas en el div se reemplaza donde dice "MES".

## Reglas obligatorias de Promos

- Cada vez que generamos un "html de la promo" nueva va debajo del bloque del mes que figura primero, siempre y cuando estemos dentro del mismo mes (chequear el mes en los slug). 
- Debajo del bloque del mes hay siempre un:
    <div class="row">
alli dentro van los "html de la promo" nuevas y siempre se insertan primero, corrriendo los viejos hacia abajo.
- No se debe eliminar nada sino correrse hacia abajo.
- En caso de que el slug tenga un nuevo mes, se corre el bloque del mes hacia abajo, se genera un "html del mes" y debajo un nuevo  <div class="row"> donde se insetaran los "html de la promo" de ese mes. 
- Siempre se trabaja con el `ssi_promos_2025.php` que esta dentro del "knowledge/html/". No se genera ningun archivo nuevo. 