# Javascript esencial
## Conociendo el lenguaje
### Comentarios

 ```javascript
    // comenteario de linea
    /*
       comentario en bloque
    */
 ```
### Strict Mode

 ```javascript
    "use strict"

    // Este es un mensaje de la consola
    console.log('Hola consola');

    var x; 

    x = "3.1416";

    var publicData = "Hola";
 ```
### Variables

```javascript
    "use strict"
    var nombre = "Maria";
```
### Contenedor let

```javascript
    "use strict"

    var nombre = 'Maria';

    console.log(nombre)

    function saludo() {
      let nombre = 'Juan';
        console.log(nombre)
    
      let edad = 34; 
        console.log(edad)
    }

    console.log(edad)

    saludo();
```
### Contenedor const

```javascript
    "use strict"

    const pi = 3.1416;
```
## Tipos de datos
- Numéricos
    ```javascript
        "use strict"
        var edad = 35;
        var cantidad = "100";
        var nuevaCantidad = Number(cantidad);
        parseInt()
        parseFloat()
    ```
- Texto
    ```javascript
        "use strict"

        var bebida = "agua";

        var comida = 'ceviche';

        var instrucción = "El platillo se llama 'ceviche' ";
    ```
- Booleanos
    ```javascript
        "use strict"

        var activo = false;

        var estado = Boolean( 10 > 9)
    ```
- Date
    ```Javascript
        "use strict"
        var fecha = new Date();
    ```
- Symbol
    ```javascript
        var simbolo1 = Symbol();
        var simbolo2 = Symbol();

        var ambiente = Symbol('dev');
    ```
- Json
    ```javascript
        "use strict"

        // JSON => JavaScript Object Notation

        var persona = {nombre: 'Juan', twitter: 'j502'};

        var personas = [
            {nombre: 'Hugo', twitter: 'dcHugo'},
            {nombre: 'Paco', twitter: 'dcPaco'},
            {nombre: 'Luis', twitter: 'dcLuis'},
        persona
        ]

        var personaJSON = JSON.stringify(persona);

        var nuevaPersona = JSON.parse(personaJSON)
    ```
## Operadores
- Artméticos
    ```javascript
        "use strict"
        //*** Operadores aritméticos
        var datoA = 10;
        var datoB = 20;

        // SUMA +
        var suma = datoA + datoB;
        // RESTA -
        var resta = datoA - datoB;
        // MULTIPLICACIÓN *
        var multiplicacion = datoA * datoB;
        // DIVISIÓN /
        var division = datoA / datoB;
        // MODULO O RESIDUO %
        var modulo = datoA % datoB;
        // INCREMENTO ++
        var incremento = datoA;
        incremento++;
        // DECREMENTO --
        var decremento = datoA;
        decremento--;
    ```
- Operadores Relaciones
    ```javascript
        "use strict"

        //********************************
        //*** Operadores relacionales

        var datoA = 10;
        var datoB = 20;

        // MAYOR QUE >
        var mayorQue = datoA > datoB;
        // MENOR QUE <
        var menorQue =  datoA < datoB;
        // MAYOR O IGUAL QUE >=
        var mayorOIgualQue =  datoA >= datoB;
        // MENOR O IGUAL QUE <=
        var menorOIgualQue =  datoA <= datoB;
        // IGUAL QUE ==
        var igualQue =  datoA == datoB;
        // NO ES IGUAL QUE O ES DIFERENTE QUE !=
        var noEsIgualQue =  datoA != datoB;
    ```
- Operadores de asignación
   ```javascript
        "use strict"
        //********************************
        //*** Operadores de asignación

        var datoA = 10;

        // ASIGNACIÓN SIMPLE
        var igual = datoA;
        // SUMAR Y ASIGNAR
        var masIgual = 10;
        masIgual += datoA;
        // RESTAR Y ASIGNAR
        var menosIgual = 10;
        menosIgual -= datoA;
        // MULTIPLICAR Y ASIGNAR
        var porIgual = 10;
        porIgual *= datoA;
        // DIVIDIR Y ASIGNAR
        var entreIgual = 20;
        entreIgual /= datoA;
   ```
- Operador negativo
    ```javascript
        "use strict"
        //********************************
        //*** Operador negativo

        var datoA = 10;
        var datoB = -datoA;
    ```
- Operador de concatenación
    ```javascript
        "use strict"
        //********************************
        //*** Operadores de concatenación

        var datoA = 10;
        var datoB = 20;

        var nombre = "Juan";
        var apellido = "Perez";

        // CONCATENACIÓN DE NÚMEROS
        var concatNumeros = datoA + datoB;

        // CONCATENACIÓN DE CADENAS DE TEXTO
        var concatTexto = nombre + " " + apellido ;
        console.log("Los textos "+ nombre +" y "+ apellido +" se unen para formar: ", concatTexto);

        // CONCATENACIÓN DE NÚMEROS COMO TEXTO
        var concatNumComoTxt  = "2"+"8" ;
        console.log("Los números 2 y 8 usados como texto se unen para formar: ", concatNumComoTxt);

        // CONCATENACIÓN DE TEXTO Y NUMERO
        var concatTxtNum = datoA + "8" ;
        console.log("El número "+ datoA +" usado como número y 8 como texto se unen para formar: ", concatTxtNum);
    ```
- Operador ternario o condicional
    ```javascript
        "use strict"
        //********************************
        //*** Operador ternario o condicional

        var datoA = 110;
        var datoB = 20;
        // Condición ? TRUE : FALSE
        var resultado = datoA > datoB ? "Si es mayor" : "No es mayor";

        console.log("El resultado con el operador ternario u operador condicional es: ", resultado);
    ```
- Operador de tipo deatos
    ```javascript
        "use strict"

        //********************************
        //*** Operador de tipo de datos

        var datoA = 10; // Número

        var nombre = "Playa"; // Cadena de texto

        var activo = true // Boleano

        var persona = {
	        edad: 34, // Número
	        deporte: 'Correr' // Cadena de texto
        } // Objeto

        console.log(typeof datoA);
        console.log(typeof nombre);
        console.log(typeof activo);

        console.log(typeof persona);

        console.log(typeof persona.edad);
        console.log(typeof persona.deporte);
    ```
## Condiciones o decisiones
- Condicion IF
    ```javascript
        "use strict"

        //********************************
        //*** Condición IF
        var datoA = 110;
        var datoB = 20;
        var resultado = "Sin datos";

        if( datoA > datoB ){
            resultado = "La condición se cumplió";
        }

        console.log("El resultado de la evaluación if es: ", resultado);
    ```
- Condición IF-ELSE
    ```javascript
        "use strict"
        //********************************
        //*** Condición IF-ELSE

        var datoA = 10;
        var datoB = 20;
        var resultado = "Sin datos";

        if (datoA > datoB){
	        resultado = "La condición se cumplió";
        } else {
            resultado = "La condición no se cumplió";
        }

        console.log("El resultado de la evaluación if-else es: ", resultado);
    ```
- Condición IF-ELSE-IF
    ```javascript
        "use strict"
        //********************************
        //*** Condición IF-ELSE-IF

        var datoA = 10;
        var datoB = 20;
        var resultado = "Sin datos";

        if (datoA > datoB){
	        resultado = "La primer condición se cumplió";
        } else if (datoB == datoA){
            resultado = "La segunda condición se cumplió";
        }  else if (datoB == datoA){
            resultado = "La Tercera condición se cumplió";
        } else if (datoB >= datoA){
            resultado = "La Cuarta condición se cumplió";
        } else if (datoB <= datoA){
            resultado = "La Quinta condición se cumplió";
        } else if (datoB != datoA){
            resultado = "La Sexta condición se cumplió";
        } else {
	    resultado = "No se cumplieron las condiciones";
        }

        console.log("El resultado de la evaluación if-else-if es: ", resultado);
    ```
- Condiciones anidada
    ```javascript
        "use strict"

        //********************************
        //*** Condiciones anidadas

        var datoA = 110;
        var datoB = 20;
        var datoC = 5;
        var resultado = "Sin datos";

        if (datoA > datoB){
        resultado = "La condición se cumplió";
    
            if (datoC < datoB){
		        if (datoC < datoB){
		        resultado = "Evaluación anidada verdadera";
            } else { 
                resultado = "No se cumplió la evaluación anidada";
            }
	        } else { 
		        resultado = "No se cumplió la evaluación anidada";
	        }

        } else { 
	    resultado = "No se cumplió la evaluación";
        }

        console.log("El resultado de la evaluación anidada es: ", resultado);
    ```
- Estructura SWITCH
    ```javascript
        "use strict"

        //********************************
        //*** Estructura SWITCH
        // Evaluación con números
        var edad = 40;
        var resultado = "";

        switch (edad) {
            case 10:
		        resultado = "La edad es 10 años";
	        break;
	        case 20:
		        resultado = "La edad es 20 años";
	        break;
            case 30:
		        resultado = "La edad es 30 años";
            break;
            case 40:
		        resultado = "La edad es 40 años";
	        break;
            default:
    	        resultado = "Ningún caso coincide";
            break;
        }


        console.log("El resultado de la evaluación con números es: "+ resultado)

        // Evaluación con cadena de texto
        var producto = "Radio";

        switch (producto) {
            case "TV":
		        resultado = "Se eligió la TV";
	        break;
	        case "Radio":
		        resultado = "Se eligió el Radio ";
	        break;
            case "Teléfono":
		        resultado = "Se eligió el teléfono ";
	        break;
            default:
    	        resultado = "No se eligió ningún producto";
            break;
        }

        console.log("El resultado de la evaluación con texto es: "+ resultado)
    ```
## Ciclos
- Ciclo FOR
    ```javascript
        "use strict"

        /***** CICLOS *****/
        // 
        // Ciclos | Loops | Iteradores
        // 
        // 2 tipos: Definidos e indefinidos
        //
        // Definidos: Ciclo FOR
        //  
        // Indefinidos: Ciclo WHILE y Ciclo DO...WHILE
        //
        /******************/

        //********************************
        //*** Ciclo FOR | Ciclo Definido
        // Repetición = iteración

        // COMPONENTES DE UN CICLO FOR
        // Contador
        // Condición o evaluación
        // Paso | incrementador o decrementador

        var productos = 5;

        for (let contador = 0; contador < productos; contador++) {
            console.log("Producto #"+ contador);
        }
    ```
- Ciclo While
    ```javascript
        "use strict"

        //********************************
        //*** Ciclo WHILE | Ciclo Indefinido
        // Iteración indeterminada o desconocida

        var productos = 5; 

        while(productos > 0) { 
   	        console.log( 'Producto vendido');
   	        productos--;
        debugger;
        }
    ```
- Ciclo Do While
    ```javascript
        "use strict"

        //********************************0
        //*** Ciclo DO..WHILE | Ciclo Indefinido
        // Iteración indeterminada o desconocida

        var productos = 5; 

        do { 
   	        console.log( 'Producto vendido');
   	        productos--;
            debugger;
        } 
        while(productos>=1)
    ```
- Control de ciclos
    ```javascript
        "use strict"

        //********************************0
        //*** Control de ciclos
        // break | continue

        var contador = 0 
        var cuenta = 0;

        for(contador = 0;contador<= 20;contador++) { 
            if(contador == 5){
                break
            }
            if (contador % 2 == 0) { 
                continue;
            } 
            cuenta++;
        debugger;
        } 

        console.log("Hay" + cuenta + " números impares");
    ```