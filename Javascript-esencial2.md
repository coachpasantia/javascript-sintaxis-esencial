# Javascript-esencial 2
## Funciones
- Estructura básica:
    ```javascript
        "use strict"

        //********************************
        //*** Estructura básica de una función

        function saludar() {
            var saludo = "Hola Mundo";
            //console.log(saludo);
            return saludo;
        }

        saludar();
    ```
- Parametros de una funcion:
    ```javascript
        "use strict"

        //********************************
        //*** Parámetros de una función

        function saludar(nombre, edad) {
	        console.log('Hola: ', nombre);
	        console.log('Edad: ', edad);
	        var resultado = nombre + " tiene " + edad + " años";
	        return resultado;
        }

        var mensaje = saludar("Juan", 34);

        console.log(mensaje)
    ```
- Inicialización Parametros:
    ```javascript
        "use strict"
        //********************************
        //*** Inicialización de parámetros

        function contar(cantidad = 20) {
	        console.log('Total: ', cantidad);
        }

        contar(100);
    ```
- Parametro tipo REST
    ```javascript
        "use strict"

        //********************************
        //*** Parámetros REST

        function cocinar(...masIngredientes) {
            console.log('Ingrediente1: ', ingrediente1);
            console.log('Ingrediente2: ', ingrediente2);
            console.log("masIngredientes", masIngredientes);
        }

        cocinar("Pollo", "Tomate", "Arroz", "Frijoles", "Pescado", "Chile");
    ```
- Parámetros tipo SPREAD
    ```javascript
        "use strict"

        //********************************
        //*** Parámetros SPREAD
        function cocinar(ingrediente1, ingrediente2, ingrediente3, ...otros) {
            console.log('Ingrediente1: ', ingrediente1);
            console.log('Ingrediente2: ', ingrediente2);
            console.log('Ingrediente3: ', ingrediente3);
            console.log('Otros: ', otros)
        }

        var ingredientesBase = ["Pollo", "Tomate"];

        cocinar(...ingredientesBase, "Arroz", "Pescado", "Chile");
    ```
- Funciones anónimas
    ```javascript
        "use strict"

        //********************************
        //*** Función Anonima
        (
            function(){
            var mensaje = "Hola de nuevo";
            console.log(mensaje);
            }
        )();

        var saludar = function(nombre){
        var mensaje = "Hola " + nombre;
        return mensaje;
        }
    ```
- Callbacks
    ```javascript
        "use strict"

        //********************************
        //*** Calllbacks

        function calcular(datoA, datoB, sumarCB, restarCB) {
            let suma = datoA + datoB
            let restar = datoA - datoB;
            sumarCB(suma);
            restarCB(restar);
        }

        calcular(2, 3, function (resultado) {
            console.log('Suma', resultado)
        },function (resultado) {
        console.log('Resta', resultado)
        })

        calcular(d1, d2, func, func)
    ```
- Funciones arrow
    ```javascript
        "use strict"
        //********************************
        //*** Función Arrow | Fat Arrow | Lambda

        var saludar = nombre => "Hola " + nombre;

        console.log(saludar("Susana"));

        var sumar = cantidad => cantidad + 10
        console.log(sumar(10));

        var calcular = (datoA, datoB) => datoA + datoB
        console.log(calcular(10, 15));

        var generar = (datoA, datoB) => {
        var datoC = 5;
        return datoA + datoB + datoC;
        }
        console.log(generar(10, 15));

        var validar = () => {
        return 'Validación correcta';
        }
        console.log(validar())
    ```
- Uso del operador this
    ```javascript
        "use strict"

        //********************************
        //*** Uso del operador this

        const boton = document.querySelector('.boton');

        
        boton.addEventListener('click', function () {
            console.log(this.innerHTML);
        })
        

        boton.addEventListener('click', () => {
            console.log(this)
            this.location = "http://www.google.com";

        })
    ```
## Eventos
- Eventos del mouse
    ```javascript
        "use strict"

        //********************************
        //*** Eventos del mouse

        const boton = document.querySelector('.boton');

        boton.addEventListener('click', function () {
            console.log("El boton se ha pulsado");
        })

        boton.addEventListener('mouseover', function () {
            console.log("El mouse esta sobre el botón");
        })

        boton.addEventListener('mouseout', function () {
            console.log("El mouse esta fuera del botón");
        })
    ```
- Eventos del teclado
    ```javascript
        "use strict"
        //********************************
        //*** Eventos del teclado
        // keydown
        // keypress
        // keyup

        window.addEventListener("keydown", function (event) {
	        console.log('Pulsando tecla');
	        console.log(String.fromCharCode(event.keyCode))
        })

        window.addEventListener("keypress", function (event) {
	        console.log('Tecla pulsada')
        })

        window.addEventListener("keyup", function (event) {
        	console.log('Tecla liberada')
        })
    ```
- Eventos de Carga del documento
    ```javascript
        "use strict"

        //********************************
        //*** Carga de documento

        window.addEventListener('load', function() {
            console.log('El contenido de la ventana se ha cargado');

  
        });
    ```
- Eventos multimedia
    ```javascript
        "use strict"
        //********************************
        //*** Eventos multimedia

        const video = document.querySelector('.bostonVideo');

        video.addEventListener("play", function () {
            console.log('El video ha iniciado');
        });

        video.addEventListener("seeking", function () {
            console.log('Se esta buscando en el video', this.currentTime);
        });

        video.addEventListener("ended", function () {
            console.log('El video ha terminado');
        });
    ```
- Uso de Temporizador
    ```javascript
        "use strict"

        //*** Temporizadores o timers
        //********************************

        // setInterval
        // setTimeout

          var temporizador = setInterval(function () {
              setColor();
          }, 2000);


        setTimeout(function () {
            setColor();
        }, 3000);

        function setColor() {
            var pagina = document.body;
            pagina.style.backgroundColor = pagina.style.backgroundColor == "blue" ? "green" : "blue";
        }

        function stopChangeColor() {
            clearInterval(temporizador)
        }
    ```
## Ventanas emergentes
- Ventana de alerta
    ```javascript
            "use strict"
            //********************************
            //*** Ventana de alerta

            const video = document.querySelector('.bostonVideo');

            video.addEventListener("ended", function () {
               alert("MENSAJE \n\n El video ha terminado");
            });
        
    ```
- Ventana de confirmación
    ```javascript
        "use strict"

        //********************************
        //*** Ventana de confirmación

        const video = document.querySelector('.bostonVideo');

        video.addEventListener("ended", function () {
            let resultado = confirm("¿Deseas ver el video nuevamente?");
            console.log(resultado);
            if (resultado) {
                video.play();
            }else {
                window.location = "http://www.google.com";
            }
        });
    ```
- Ventana ingreso de datos
    ```javascript
        "use strict"

        //********************************
        //*** Ventana para ingreso de datos

        const video = document.querySelector('.bostonVideo');

        video.addEventListener("ended", function () {
            let email = prompt("Escribe tu correo para ver mas videos",  "data@info.com");
  
            if (email == null || email == "") {
                console.log("Sin datos");
            } else {
                console.log(email);
            }
        });
    ```
## Trabajando con números
- Propiedades númericas
    ```javascript
        "use strict"

        //********************************
        //*** Propiedades númericas

        console.log("MAX_VALUE: ", Number.MAX_VALUE);

        console.log("MIN_VALUE: ", Number.MIN_VALUE);

        console.log("NEGATIVE_INFINITY: ", Number.NEGATIVE_INFINITY);

        console.log("NEGATIVE_INFINITY: ", Number.POSITIVE_INFINITY);

        console.log("NaN: ", Number.NaN);
    ```
- Métodos númericos
    ```javascript
        "use strict"
        //********************************
        //*** Métodos númericos
        var numero = "10";

        console.log('Number: ', typeof numero, typeof Number(numero));
        console.log('parseInt: ',  parseInt(numero));
        console.log('parseFloat: ', Number.parseFloat(numero));
        console.log('isNaN: ', isNaN(numero));
        console.log('isInteger: ', Number.isInteger(numero));
    ```
- Metodos de instancias
    ```javascript
        "use strict"

        //********************************
        //*** Métodos númericos
        var numero = "10";

        console.log('Number: ', typeof numero, typeof Number(numero));
        console.log('parseInt: ',  parseInt(numero));
        console.log('parseFloat: ', Number.parseFloat(numero));
        console.log('isNaN: ', isNaN(numero));
        console.log('isInteger: ', Number.isInteger(numero));
    ```
## Trabajando con Texto
- Creando cadenas texto
    ```javascript
    "use strict"

        //********************************
        //*** Creando cadena de texto

        var pais = 'México';

        var comida = new String("Ceviche");
    ```


- Medir una cadena
    ```javascript
        "use strict"

        //********************************
        //*** Medir una cadena de texto

        var mensaje = "Estoy aprendiendo JavaScript";

        console.log("La cadena de texto tiene: " + mensaje.length + " letras");
    ```
- Metodo de busqueda
    ```javascript
        "use strict"
        //********************************
        //*** Métodos búsqueda 

        var mensaje = "Estoy aprendiendo JavaScript y estoy aprendiendo mucho";

        var resultado;

        // indexOf
        resultado = mensaje.indexOf("aprendiendo");


        // lastIndexOf
        resultado = mensaje.lastIndexOf("aprendiendo");


        // search:
        //resultado = mensaje.search("aprendiendo");

        // search | Expresión regular
        resultado = mensaje.search(/ja/i);

        console.log(resultado);
        /*-------------------------------------------------------**/
        "use strict"

        //********************************
        //*** Métodos búsqueda | Parte 2

        var mensaje = "Estoy aprendiendo JavaScript y estoy Aprendiendo mucho";

        var resultado;

        // match:
        resultado = mensaje.match(/aprendiendo/gi);

        // substr:
        resultado = mensaje.substr(6,11);

        // substring:
        resultado = mensaje.substring(6,17);

        // charAt:
        resultado = mensaje.charAt(0);
        console.log(resultado);
        /*-----------------------------------------------*/

        //********************************
        //*** Métodos búsqueda | Parte 3

        var mensaje = "Estoy aprendiendo JavaScript";
        var resultado;


        // startsWith
        resultado = mensaje.startsWith("es");

        var textoEn =  mensaje.indexOf("JavaScript")
        resultado = mensaje.startsWith("Ja", textoEn);

        //endsWith
        resultado = mensaje.endsWith("JavaScript");

        // includes
        resultado = mensaje.includes("Estoy", 6);
        console.log(resultado);
    ```
- Metodo generación,reemplazo y separación
    ```javascript
        "use strict"

        //********************************
        //*** Métodos de generación, reemplazo y separación

        var mensaje = "      Estoy aprendiendo JavaScript        ";

        var resultado;

        // repeat
        resultado = mensaje.repeat(200);

        // replace
        resultado = mensaje.replace("JavaScript", "a programar");

        // slice
        resultado = mensaje.slice(6);
        resultado = mensaje.slice(6, 11)

        // split
        resultado = mensaje.split(" ");

        // trim
        resultado = mensaje.trim();
        console.log(resultado);
    ```
- Transformación de Texto
    ```javascript
        "use strict"

        //********************************
        //*** Métodos de transformación

        var mensaje = "Estoy aprendiendo JavaScript";
        var mensaje2 = " y programación";
        var total = 123456;

        var resultado;

        resultado = total.toString();
        resultado = mensaje.toLowerCase();
        resultado = mensaje.toUpperCase();

        resultado = mensaje.concat(mensaje2, ' y tengo muchas ideas', ' 123', ' 123', ' 123', ' 123', ' 123', ' 123', ' 123');

        console.log(resultado);
    ```
- Plantillas y literales
    ```javascript
        "use strict"

        //********************************
        //*** Plantillas y literales

        var lenguaje = 'JavaScript';

        var lenguaje2 = 'HTML';

        var mensaje = `Me gusta ${lenguaje} y su integración con ${lenguaje2}`;

        console.log(mensaje);


        //---- Mensaje multilinea
        var mensajeMultilinea = `
            Hola mundo,
	        estoy aprendiendo
	        ${lenguaje} y me gusta
	        como se integra con HTML y CSS`;

        console.log(mensajeMultilinea);
    ```