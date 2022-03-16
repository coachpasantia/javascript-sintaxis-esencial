## Prueba tus conocimientos

1. Escribir una función llamada contrasenaValida que reciba un string y retorne true si el string es igual a "2Fj(jjbFsuj" o "eoZiugBf&g9". De lo contrario debe retornar false.
    ejemplo
    ```javascript
        // código de prueba
        console.log(contrasenaValida("2Fj(jjbFsuj")) // true
        console.log(contrasenaValida("eoZiugBf&g9")) // true
        console.log(contrasenaValida("hola")) // false
        console.log(contrasenaValuda("")) // false
    ```
2. Escribir una función llamada calcularImpuestos que reciba dos argumentos numéricos: edad e ingresos. Si edad es igual o mayor a 18 y los ingresos son iguales o mayores a 1000 debe retornar ingresos * 40%. De lo contrario retornar 0.

    ejemplo
    ```javascript
        // código de prueba
        console.log(calcularImpuestos(18, 1000)) // 400
        console.log(calcularImpuestos(40, 10000)) // 4000
        console.log(calcularImpuestos(17, 5000)) // 0
        console.log(calcularImpuestos(30, 500)) // 0
    ```
3. Escribe una función llamada likes que reciba un número y retorne un string utilizando el formato de K para miles y M para millones.

    Por ejemplo:

    1400 se convierte en 1K
    34,567 se convierte en 34K
    7’456,345 se convierte en 7M.
    Si el número es menor a 1000 se debe devolver el mismo número como un string.

    ejemplo
    ```javascript
    // código de prueba
    console.log(likes(983)) // "983"
    console.log(likes(1900)) // "1K"
    console.log(likes(54000)) // "54K"
    console.log(likes(120800)) // "120K"
    console.log(likes(25222444)) // "25M"
    ```
4. El índice de masa corporal (IMC), o BMI por sus siglas en inglés, es un valor que       determina la cantidad de grasa de una persona.

    El BMI se calcula con la siguiente formula: peso / altura^2

    Escribir una función llamada bmi que reciba dos argumentos: peso y altura, y retorne un string con las siguientes posibilidades:

    "Bajo de peso" si el BMI < 18.5
    "Normal" si está entre 18.5 y 24.9
    "Sobrepeso" si está entre 25 y 29.9
    "Obeso" si es igual o mayor a 30
    
    ejemplo:
    ```javascript
        // código de prueba
        console.log(bmi(65, 1.8)) // "Normal"
        console.log(bmi(72, 1.6)) // "Sobrepeso"
        console.log(bmi(52, 1.75)) //  "Bajo de peso"
        console.log(bmi(135, 1.7)) // "Obeso"
    ```
# NOTA:
Utilice el archivo index.html pra ver sus resultados.