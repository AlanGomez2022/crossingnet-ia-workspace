# Skill: Generador de Slugs para Promociones

## Objetivo

- Convertir el título de una promoción en un slug estandarizado para nombrar archivos.
- Ese slug sera el nombre a utilizar para el archivo que se genere de .html

## Entrada esperada

El usuario enviará un texto promocional que **siempre finalizará con una fecha en formato `dd/mm`**.

Ejemplo:

```
Potenciá tu negocio con ASUS. Precios Especiales por tiempo limitado. 18/06

```

## Reglas de procesamiento

1. Detectar la fecha ubicada al final del texto.
2. Tomar automáticamente:
   - Año: según corresponda al contexto (ej. 2026).
   - Mes: proveniente de la fecha.
   - Día: proveniente de la fecha.
3. Eliminar la fecha del texto antes de procesarlo (no debe aparecer nuevamente en el slug).
4. Convertir todo el texto a minúsculas.
5. Eliminar todas las tildes.
6. Reemplazar:
   - ñ → n
   - ü → u
7. Eliminar cualquier carácter especial, incluyendo pero no limitado a:
   - ™
   - ®
   - ©
   - comillas
   - paréntesis
   - barras
   - signos de puntuación
   - signos de apertura y cierre
8. Eliminar puntos, comas, dos puntos, punto y coma, guiones y cualquier otro signo de puntuación.
9. Mantener únicamente:
   - letras
   - números
   - espacios
10. Reemplazar uno o más espacios por un único guion bajo (`_`).
11. No generar dobles guiones bajos.
12. No dejar guiones bajos al principio ni al final.

## Formato de salida

Debe devolver como linea de salida:

```
aaaa_mm_dd_texto_procesado

```

## Ejemplo

Entrada:

```
Potenciá tu negocio con ASUS. Precios Especiales por tiempo limitado. 18/06
```

Salida:

```
2026_06_18_potencia_tu_negocio_con_asus_precios_especiales_por_tiempo_limitado

```

## Reglas obligatorias

- Nunca explicar el proceso.
- Nunca agregar comentarios.
- Nunca usar listas.
- Nunca responder con markdown.
- La salida debe ser únicamente la líneas que se utilizara para el nombre del .html

```