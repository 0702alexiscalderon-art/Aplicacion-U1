# Aplicacion-U1
Analice, Diseñe e Implemente una Clase llamada Natural, para verificar su funcionalidad use Interfaces Gráficas para que realice la siguientes operaciones:

Operaciones sobre Dígitos

insertar,
obtener,
eliminar,
cantidad,
sumar,
pares,
impares,
primos,
mayor,
menor.

Operaciones sobre Enteros

invertir,
Capicua,
Par,
Impar,
Primo,
Conversión a Binario,
Conversión a Octal,
Conversión a Hexadecimal,
Conversión a Base N,
Conversión a Romano,
Conversión a Literal.

1.1 ANÁLISIS (MATEMÁTICO / LÓGICO)
 Operaciones sobre Dígitos

insertar(d, pos): dígito d y posición pos. Condición: d dígito y 1 ≤ pos ≤ cantidad+1. num ← num[1..pos-1] + d + num[pos..fin], luego normalizar. Devuelve Boolean.

obtener(pos): Condición: 1 ≤ pos ≤ cantidad. Resultado: num[pos]. Si pos inválida devuelve '*'.

eliminar(pos): Condición: 1 ≤ pos ≤ cantidad. Borra el carácter de la posición pos; si queda vacía → "0"; normalizar.

cantidad: Cantidad de dígitos = longitud(num).

sumar: s = Σ (Ord(num[i]) − 48) para i = 1..cantidad.

pares / impares: Cuentan dígitos con d mod 2 = 0 / = 1.

primos: Cuenta dígitos en {2,3,5,7}.

mayor / menor: Máximo / mínimo de los dígitos recorriendo la cadena.

Operaciones sobre Enteros

invertir: Recorre la cadena de fin a principio; se quitan ceros a la izquierda del resultado.
Capicua: capicua ⇔ invertir() = num.
Par / Impar: Se mira solo el último dígito: num[cantidad] mod 2 = 0.
Primo: n<2 no primo; n=2 primo; n par no primo; si no, probar divisores impares hasta i ≤ n div i.
Bin/Oct/Hex/BaseN: Divisiones sucesivas d = n mod b; n = n div b; restos leídos al revés. Dígitos >9 con letras (Chr(55+d)). Una sola implementación aBaseN(b), 2≤b≤16.
Romano: Válido 1..3999. Método ávido con tablas de valores y símbolos, formas sustractivas incluidas.
Literal: Descomposición en millones/miles/centenas/decenas/unidades con tablas de palabras. Corrección aplicada: literalCentenas(n) con n<100 delega en literalDecenas(n) para evitar el acceso fuera de rango en centenas[0]. Soporta hasta 999.999.999.

1.2. Diseño formal
Atributo: num : String — Privado (−). El número natural guardado como cadena de dígitos, normalizada (sin ceros a la izquierda).
Comportamientos

Crear: + ,constructor(n: String)
Crea el objeto; si la cadena es inválida queda "0"

setNum: + ,función(n: String): Boolean
Valida (solo dígitos) y carga el número

getNum: + ,función(): String
Devuelve el número

aEntero: + ,función(): Int64
Convierte la cadena a entero largo (-1 si no cabe)

insertar: + ,función(d: Char; pos: Integer): Boolean
Inserta un dígito en una posición

obtener: + ,función(pos: Integer): Char
Devuelve el dígito de una posición ('*' si inválida)

eliminar: + ,función(pos: Integer): Boolean
Elimina el dígito de una posición

cantidad: + ,función(): Integer
Cantidad de dígitos

sumar: + ,función(): Integer
Suma de los dígitos

pares/impares/primos: + ,función(): Integer
Cuentan dígitos pares, impares y primos

mayor/menor: + ,función(): Integer
Mayor / menor dígito

invertir: + ,función(): String
Número invertido

capicua/par/impar/primo: + ,función(): Boolean
Predicados sobre el entero

aBinario/aOctal/aHexadecimal: + ,función(): String
Conversión a base fija

aBaseN: + ,función(b: Integer): String
Conversión a base N (2≤N≤16)

aRomano: + ,función(): String
Conversión a número romano (1..3999)

aLiteral: + ,función(): String
Conversión a letras (hasta 999.999.999)

normalizar: − ,procedimiento
Quita ceros a la izquierda

esDigito/digito: − ,función
Validación y valor de un carácter dígito

apocopar: − ,función(s: String): String
"uno" final → "un"

literalDecenas: − ,función(n: Integer): String
0..99 en letras

literalCentenas: − ,función(n: Integer): String
0..999 en letras (n<100 delega en literalDecenas)

literalMiles: − ,función(n: Integer): String
0..999999 en letra
