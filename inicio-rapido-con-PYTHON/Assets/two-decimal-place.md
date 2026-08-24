Qué te piden?
Encontrar la forma correcta de formatear un valor numérico a dos decimales en Python, específicamente usando f-strings (cadenas formateadas).

Analicemos cada opción:

**A) “Multiply every result by 100 and print the raw value.”**

→ Multiplicar por 100 no redondea a dos decimales; solo desplaza el punto decimal. Por ejemplo, 3.14159 * 100 = 314.159, que sigue teniendo decimales. ❌

**B) “Use an f-string field such as {fuel_needed:.2f}.”**

→ Esta es la sintaxis correcta en Python para formatear un número con exactamente dos decimales.
Ejemplo:
```
fuel_needed = 123.456789
print(f"{fuel_needed:.2f}")  # Salida: 123.46
```

✅

**C) “Convert the result to text and retain only its first two characters.”**

→ Esto tomaría solo los primeros dos caracteres (ej. 12 de 123.45), lo cual no es lo mismo que dos decimales. ❌

**D) “Wrap every result with int() before printing.”**

→ int() elimina todos los decimales (trunca), no los redondea a dos. Por ejemplo, int(3.99) da 3. ❌

**Respuesta correcta: B) Use an f-string field such as {fuel_needed:.2f}.**

Explicación breve:
El formato :.2f dentro de un f-string indica:

: → comienza el especificador de formato
.2 → precisión de 2 decimales
f → formato de punto flotante (decimal)
Esto redondea el número al valor más cercano con dos decimales, que es exactamente lo que pide el enunciado.
