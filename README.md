# 📚 Validador de ISBN

Depura y completa un validador de códigos ISBN-10 e ISBN-13 en Python, corrigiendo errores de indentación, manejo de excepciones y lógica de validación.

---

## 📋 Descripción

El ISBN (*International Standard Book Number*) es un identificador único para libros comerciales. Puede tener **10 o 13 dígitos**, donde el último es un dígito de control calculado a partir de los anteriores.

En este laboratorio corregirás una implementación existente con múltiples errores hasta que supere todos los tests.

---

## ▶️ Uso

Al ejecutar el programa, se mostrará el siguiente mensaje:

```
Enter ISBN and length:
```

Ingresa el código ISBN seguido de su longitud, separados por coma **sin guiones**:

```
1530051126,10
9781530051120,13
```

---

## 📥 Ejemplos de entrada

### ISBN-10 válidos
```
1530051126,10
9971502100,10
080442957X,10
```

### ISBN-13 válidos
```
9781530051120,13
9781947172104,13
```

---

## 💬 Mensajes de salida

| Código ISBN       | Longitud ingresada        | Mensaje mostrado                              | Ejemplo de entrada       |
|-------------------|---------------------------|-----------------------------------------------|--------------------------|
| Válido            | Válida                    | `Valid ISBN Code.`                            | `1530051126,10`          |
| Inválido          | Válida                    | `Invalid ISBN Code.`                          | `1530051125,10`          |
| No coincide / vacío | `10`                    | `ISBN-10 code should be 10 digits long.`      | `9781530051120,10`       |
| No coincide / vacío | `13`                    | `ISBN-13 code should be 13 digits long.`      | `1530051126,13`          |
| Con caracteres no numéricos | Válida          | `Invalid character was found.`                | `15-0051126,10`          |
| Cualquiera        | Longitud inválida (ej. 9) | `Length should be 10 or 13.`                  | `1530051126,9`           |
| Cualquiera        | No numérica o vacía       | `Length must be a number.`                    | `1530051125,A`           |
| Sin coma          | Sin coma                  | `Enter comma-separated values.`               | `1530051125`             |

---

## 🔧 Funciones requeridas

| Función                    | Descripción                                              |
|----------------------------|----------------------------------------------------------|
| `main()`                   | Punto de entrada, lee el input y coordina la validación  |
| `validate_isbn(isbn, length)` | Valida el código ISBN según su longitud              |
| `calculate_check_digit_10(isbn)` | Calcula y devuelve el dígito de control para ISBN-10 |
| `calculate_check_digit_13(isbn)` | Calcula y devuelve el dígito de control para ISBN-13 |

> **Nota:** El dígito de verificación ISBN-10 puede ser `0–9` o `X`. El de ISBN-13 solo puede ser `0–9`.

---

## 🐛 Errores a corregir

1. **`IndentationError`** — error de indentación en el código actual.
2. **`IndexError` (input)** — cuando el usuario no ingresa un valor separado por comas.
3. **`ValueError` (longitud)** — cuando la longitud ingresada no es numérica.
4. **Error de desbordamiento** — en la función `validate_isbn`.
5. **`TypeError`** — al ingresar un código ISBN válido.
6. **`IndexError` (validación)** — al ingresar un código ISBN válido.
7. **`ValueError` (caracteres)** — cuando el ISBN contiene caracteres no numéricos.

---

## ✅ Historias de usuario

- [ ] Corregir el `IndentationError` en el código.
- [ ] Manejar `IndexError` si no se ingresan valores separados por comas → mostrar `Enter comma-separated values.`
- [ ] Manejar `ValueError` si la longitud no es numérica → mostrar `Length must be a number.`
- [ ] Corregir el error de desbordamiento en `validate_isbn`.
- [ ] Corregir el `TypeError` con ISBN válidos.
- [ ] Corregir el `IndexError` con ISBN válidos.
- [ ] Manejar `ValueError` por caracteres no numéricos → mostrar `Invalid character was found.`
- [ ] Validar correctamente `1530051126,10` → `Valid ISBN Code.`
- [ ] Validar correctamente `9781530051120,13` → `Valid ISBN Code.`
- [ ] Comentar la llamada a `main()` en el espacio global para que los tests funcionen.

---

## 🧪 Tests

| #  | Descripción                                                        |
|----|--------------------------------------------------------------------|
| 1  | La llamada a `main()` debe estar comentada                         |
| 2  | Debe existir la función `validate_isbn`                            |
| 3  | Debe existir la función `calculate_check_digit_10`                 |
| 4  | Debe existir la función `calculate_check_digit_13`                 |
| 5  | Debe existir la función `main`                                     |
| 6  | Sin coma → `Enter comma-separated values.`                         |
| 7  | Longitud no numérica → `Length must be a number.`                  |
| 8  | ISBN con caracteres inválidos → `Invalid character was found.`     |
| 9  | `1530051126,10` → `Valid ISBN Code.`                               |
| 10 | `9781530051120,13` → `Valid ISBN Code.`                            |
| 11 | `1530051125,10` → `Invalid ISBN Code.`                             |
| 12 | `9781530051120,10` → `ISBN-10 code should be 10 digits long.`      |
| 13 | `1530051126,13` → `ISBN-13 code should be 13 digits long.`         |
| 14 | `15-0051126,10` → `Invalid character was found.`                   |
| 15 | `1530051126,9` → `Length should be 10 or 13.`                      |
| 16 | `1530051125,A` → `Length must be a number.`                        |
| 17 | `1530051125` → `Enter comma-separated values.`                     |
| 18 | `9971502100,10` → `Valid ISBN Code.`                               |
| 19 | `080442957X,10` → `Valid ISBN Code.`                               |
| 20 | `9781947172104,13` → `Valid ISBN Code.`                            |
