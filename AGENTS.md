# Instrucciones para Codex - CrossingNet HTML

Este workspace se usa únicamente para generar los newsletters de Stylus.

## Objetivo

- Crear código HTML para newsletters a partir de un nombre base y una cantidad exacta de bloques.
- Actualizar el archivo `knowledge/output/ssi_promos_2024.php` agregando la nueva promo, para eso leer "promos.md"

## Reglas obligatorias newsletter

- En base a un nombre que ingrese el usuario utilizar /texto_acomodado.md
- antes que nada mostrar el slug armado y luego preguntar lo que falte.
- Utilizar el slug creado con ese .md y generar un archivo .html
- El nombre de ese HTML será ese slug obtenido
- Responder con código HTML dentro de ese archivo.
- No agregar explicaciones.
- No agregar comentarios HTML.
- No inventar enlaces.
- No modificar nombres base.
- En el archivo .html respetar exactamente la cantidad de bloques solicitada. Preguntar la cantidad si no se dá.
- preguntar tambien el link si va con un link especifico y en que bloques.
- preguntar si hay bloques en linea
- preguntar si sube o no a promos
- Guardar los HTML finales en `/output`.

## sube a promos
- en caso de que el usuario diga "No sube a promos" significa que no se modifica el `output/ssi_promos_2024.php`

## Bloques alineados horizontalmente

- Cuando el pedido indique que ciertos bloques están “alineados”, “en línea”, “horizontalmente” o “con display flex”, esos bloques deben generarse dentro de un único `<tr>` y un único `<td style="display:flex;">`.
- Dentro de ese `<td>` deben ir todos los `<a>` correspondientes a esos bloques, uno al lado del otro.
- No generar un `<tr>` separado para cada bloque alineado.
- No agregar estilos extra: usar únicamente `style="display:flex;"` en el `<td>`.

## Archivo base
- Partir desde el archivo base que figura en `html/plantilla.html`.
- el slug generado debe colocarse y reemplazar en la linea 9 donde dice "NEWS".
- entre los comentarios "News Inicio" y "NewsFin" se generarn los bloques de html respetando lo que acontinuacion se datallan.



## Estructura estándar de cada bloque

en html: 
<tr>
    <td>
        <a href="LINK" target="_blank">
            <img src="RUTA_IMAGEN" alt="" style="margin-top: 0px; display: block;">
        </a>
    </td>
</tr>

## Ruta base de imágenes 

Usar siempre:

http://www.stylus.com.ar/n_e_cross/piezas/images/

esto va en cada bloque generado en el lugar de src donde dice "RUTA_IMAGEN" seguido del slug generado y luego un guion bajo y el
numero de bloque en 2 digitos. 

Ejemplo: 

http://www.stylus.com.ar/n_e_cross/piezas/images/slug_generado_01.jpg


## Link por defecto

Usar siempre:

https://www.stylus.com.ar

salvo que el usuario indique otro link para bloques específicos en los bloques determinados.

esto va dentro del bloque en donde dice "LINK"

## mailto listado de personas

El usuario puede indicar en lugar de un "LINK" un "mailto" pero lo solicita por nombre de la persona. 
El listado de las personas y sus mails a colocar alli son: 

- Sebastián Teruel: steruel@stylus.com.ar
- Florencia Cabrera: asistentelenovo@stylus.com.ar
- Alejandro Cáceres: acaceres@stylus.com.ar
- Fernando Miranda: fmiranda@stylus.com.ar
- Sergio Moyano: smoyano@stylus.com.ar
- Javier Barba: javierb@stylus.com.ar
- Jonatan Piovanelli: jonatanp@stylus.com.ar
- Julio Prado: juliop@stylus.com.ar

## footer y pie_sucursales
- se debe consultar al usuario si el pie sucursales ("pie_stylus_sucursales2.jpg") queda igual o se modifica por alguno que aclare el usuario. Preguntar "y/n"
- Se debe consular al usuario si el footer redes ("footer_redes_bco.jpg") queda igual  o se modifica por alguno que aclare el usuario. Preguntar "y/n"
