#Funciones básicas de Ruby

	"string".reverse
	(+,-,*,/)operaciones matemáticas
	40.to_s.reverse

	to_s : convierte valores a strings
	to_i : convierte valores a integers(números)
	to_a : convierte valores a arreglos (listas simples)
	
	[] : lista vacía

Arreglos, guardan información en secuencia
	[12, 23, 12].max
	tickets = [12, 2, 4]

Invocar a la variable
	
	tickets : retorna la variable recién creada
	tickets.sort! : ! indica a ruby que modifique el mismo array 

Si no sólo retorna el array ordenado.
Si tenemos un string, con distintas palabras.

	str = "un string con distintas palabras"
	str['string'] = 'cadena' : cambia la palabra
	print str
	=> "un cadena con distintas palabras"

Los `[]` indican que está buscando
	str.reverse
	str.lines.to_a.reverse : revierte las líneas si las tuviera

	print str.lines.to_a.reverse.join

El método join toma una lista de líneas al revés y las junta en un único string(también se pudo haber usado to_s )


* Puntos de exclamación : 'algo.max!' significa que impacata a los datos actuales
* Paréntesis cuadrado [] : Se puede fijar un objetivo para buscarlo
* Métodos encadeanados 'Chaining' : poem.lines.to_a.reverse.join


	poem.include? "my hand", return true or false
	poem.downcase
	poem.delete
	books = {} , empty hash aka. dictionary

Hashes guardan información relativa dandoles etiquetas a piezas de nuestros datos.

	books["Gravity's Rainbow"] = :splendid
	=> :splendid
	books
	=> {"Gravi...."=>:splendid}

Si se usa "dos puntos", ":" delante de una palabra obtienes un símbolo de Ruby,
estos usan menos memoria. Si se necesita usar una palabra una y otra vez en el programa mejor usar un simbolo, En vez de tener miles de copias de una palabra en memoria, el computador almacena el simbolo una sola vez para referirse a él una y otra vez.

	books.lenght
	=> 3
	books["Gravity's Rainbow"]
	=> :splendid
	books.keys
	ratings = Hash.new(0)

	
	

	
Ver funciones `bytes, chars`

