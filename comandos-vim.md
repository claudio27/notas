#Comandos Vim

Algunos comandos básicos.

---

i, I : cambia a modo insertar

h, j, k, l : izq, abajo, arriba, der

[n][acción/movimiento] : hace n veces 3w (se mueve 3 palabras)

insertar 20 * { 20i* esc esc}

x, X : borra un caracter

a, A : concatena

f[char] : mueve el cursor al siguiente caracter en la linea

F[char]	: mueve el cursor al anterior caracter en la linea

; y ,	: repite el último f o F
 
/buscar y entonces n, N : busca el siguiente

d[movimiento] :	borra el movimiento ???

r[char] : reemplaza el caracter bajo el cursor

0, $ : mueve al principio o final de la línea

o, O	: agrega un nueva línea

%	: va al parentesis correspondiente 

ci[movimiento] : cambia dentro del moviento dado

D	: borra hasta el fin de linea 

S	: limpia la línea actual para el modo insertar

gg / G	: mueve al principio / final del buffer

yy	: copia la línea actual

p	: pega lo copiado después del cursor

*/#	: encontrar palabra sobre el cursor/ anterior

2G	: ir a la línea 2

dw	: borra la palabra, se puede pegar con p

d2e	: borrar dos palabras

.	: repetir el comando anterior

// borrar de dos en dos palabras

d2w .

u	: DESHACER
CTRL-R	: REHACER

:help   : ayuda ;D

# En modo visual


Se puede seleccionar texto antes de decidir qué hacer con el.
En modo normal presionar v, seleccionar la palabra con e. Después de seleccionar el texto se puede borrar con d

:w --- guardar
:q --- salir
:q! --- salir sin guardar


