# Expresiones regulares
> las expresiones regulares no son sencillas, pero son sumamente potentes 

1. Que son?
> Las expresiones regulares son patrones de caracteres que te permiten ir seleccionando o descartando datos en un archivo de texto como por ejemplo csv, o en una línea o un input, según coincidan o nó con este patrón.
* Web Scrapping: comparación de precios en tiendas, la monitorización de datos relacionados con el clima de cierta región, la detección de cambios en sitios webs y la integración de datos en sitios webs.

## Modificadores
``` bash
//g - global (todas las veces que aparezca)
//i - Insensitive (no dif entre CAPS)
#corchetes
/[eo][0-5]/ - opciones a buscar
/[^0-9]/ - negacion diferente de 0-9
/[.h]/ - . cualquier caracter
#Meta caracteres
/\s/ - space espacios en blanco
/\d/ - Digito 
/\D/ - no sea digito
/\w/ - word solo busca letras y digitos
/\W/ - contrario, solo busca caracteres 
/\babc/ - begin con abc
/abc\b/ - acabe con abc
#cuantificadores
/abc+/ - cuantas veces se repita (almenos 1 vez) "c" 
/0*55/ - no se tiene por que encontrar el 0
/abz?/ - o ninguna o una vez que se repita z
/(lol){n}/, /5{3}/ - n veces que quiero buscar lol, 3 5 consecutivos
/(com)$/ - final de una cadena de texto
/^(www)/ - incial de la cadena
/(?=)/- no trae la cadena que defina /\w(?=\.\w+$)/ - este ejemplo trae los nombre de los archivos antes de un punto
``` 

## Paginas para practicar
- https://regex101.com/
- https://regexr.com/
- https://regexone.com/