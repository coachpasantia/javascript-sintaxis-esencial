## Trabajando con arreglos
- Crear un Arreglo
    ```javascript
        "use strict"

        //********************************
        //*** Creando tu primer arreglo

        var platillos = [ "ceviche", "tacos", "pasta"];

        var bebidas = new Array( "Jamaica", "Chicha Morada", "Pozol" );

        console.log(Array.isArray(platillos), bebidas)
    ```
- Medir y acceder a un array
    ```javascript
        "use strict"
        //********************************
        //*** Medir y acceder a un arreglo
        var platillos = ["ceviche", "tacos", "pasta", "tostadas"];

        console.log("Hay "+ platillos.length + " platillos en el menú");

        var platillo = platillos[platillos.length -1];

        console.log("El platillo seleccionado es: ", platillo)
    ```
- Arreglo multidimensional
    ```javascript
        "use strict"
        //********************************
        //*** Arreglos multidimensionales | Arreglo de arreglos

        var platillos = ["ceviche", "tacos", "pasta"];
        var paises = ["Perú", "México", "Italia"];

        var menu = [ platillos, paises ];

        console.log( menu[1][0]  )
    ``` 
- Operaciones básicas
    ```javascript
        "use strict"
        //********************************
        //*** Operaciones básicas de un arreglo
        var platillos = ["ceviche", "tacos", "pasta"];

        console.log('Antes:', platillos);

        platillos.push("Tostadas");

        platillos.push("Queso");

        platillos.pop();
        platillos.pop();

        var mensaje = platillos.join();
        console.log( mensaje);
        //console.log('Después:', platillos);
    ```
- Generación de arreglos
    ```javascript
            "use strict"
            //********************************
            //*** Generación de arreglos con split() from() y of()


            //--- split()

             var mensaje = "ceviche, tacos, pasta";

             var platillos = mensaje.split(', ');

            //--- Array.from();
            var platillosHTML = Array.from(document.querySelectorAll('.platillos p'))

            var platillos = platillosHTML.map( platillo => platillo.textContent )

            //--- Array.of();

            var platillos = Array.of("ceviche", "tacos", "pasta");

            console.log(platillos)    
    ```
- Ordenamiento de arreglos
    ```javascript
        "use strict"

        //********************************
        //*** Ordenando un arreglo

        var platillos = ["Ceviche", "Tacos", "Pasta"];

        console.log('Antes: ', platillos);

        platillos.sort(); 

        console.log('Ordenado: ', platillos);

        platillos.reverse(); 

        console.log('Después: ', platillos);


        platillos.reverse(); 

        console.log('Reversa de nuevo: ', platillos);
    ```
- Destructuración de arreglos
    ```javascript
        "use strict"

        //********************************
        //*** Desestructuración de arreglos

        var platillos = ["ceviche", "tacos", "pasta", "tostadas"];

         var platillo1 = platillos[0];
         var platillo2 = platillos[1];
         var platillo3 = platillos[2];

        // var platillo1 = null;
        // var platillo2 = null;
        // var platillo3 = null;
        // var platillo4 = null;

        var [platillo1, platillo2, platillo3, platillo4] = platillos;

        console.log(platillo1, platillo2, platillo3, platillo4)
    ```
## Busqueda en arreglo
- Iteración arreglos con for.. in
    ```javascript
        "use strict"
    //********************************
    //*** Iterando arreglos con for...in

    var platillos = ["ceviche", "tacos", "pasta"];

    for ( let i in platillos) {
        console.log(platillos[i])
    }
    ```
- Iterando con forEach
    ```javascript
        "use strict"
        //********************************
        //*** Iterando arreglos con forEach

        var platillos = ["ceviche", "tacos", "pasta"];

        // platillos.forEach( platillo => console.log(platillo) )

        platillos.forEach( (platillo, index) => console.log(index, platillo) )
    ```
- Buscando un arreglo
    ```javascript
        "use strict"
        //********************************
        //*** Buscando en un arreglo
        var platillos = ["ceviche", "tacos", "pasta"];

        var pElegido = platillos.find( platillo => platillo == "tostadas");

        var menu = [
	        {nombre: 'Ceviche', precio: 20, pais: 'Perú'},
	        {nombre: 'Tacos', precio: 10 , pais: 'México'},
	        {nombre: 'Pasta', precio: 50, pais: 'Italia'}
        ];

        var pElegido = menu.find( platillo => platillo.nombre == 'Tacos');


        console.log(pElegido)
    ```
- Busqueda de indice de elementos
    ```javascript
        "use strict"
        //********************************
        //*** Busqueda de índice de elementos

        var platillos = ["ceviche", "tacos", "pasta"];

        var menu = [{
                nombre: 'Ceviche',
                precio: 20,
                pais: 'Perú'
            },
            {
                nombre: 'Tacos',
                precio: 10,
                pais: 'México'
            },
            {
                nombre: 'Pasta',
                precio: 50,
                pais: 'Italia'
            }
        ]


        var numPlatillo = platillos.findIndex( platillo => platillo == 'tacos' );

        var numPlatillo = menu.findIndex( platillo => platillo.nombre == 'Pasta' );

        console.log("Platillo número: ", numPlatillo);
    ```
- Filtrar arreglos
    ```javascript
        "use strict"
        //********************************
        //*** Filtrar arreglos

        var menu = [{
                nombre: 'Ceviche',
                precio: 20,
                pais: 'Perú'
            },
            {
                nombre: 'Tacos',
                precio: 10,
                pais: 'México'
            },
            {
                nombre: 'Pasta',
                precio: 50,
                pais: 'Italia'
            },
            {
                nombre: 'Quesadillas',
                precio: 15,
                pais: 'México'
            }
        ];

        var resultado = null;


        resultado =  menu.find(platillo => platillo.pais == 'México');


        resultado =  menu.filter(platillo => platillo.pais == 'México');

        console.log(resultado);
    ```
- Validación de elementos de un array
    ```javascript
        "use strict"
        //********************************
        //*** Validación de elementos de un arreglo

        var resultado = null;

        var menu = [{
                nombre: 'Ceviche',
                precio: 20,
                pais: 'Perú'
            },
            {
                nombre: 'Tacos',
                precio: 10,
                pais: 'México'
            },
            {
                nombre: 'Pasta',
                precio: 50,
                pais: 'Italia'
            },
            {
                nombre: 'Quesadillas',
                precio: 15,
                pais: 'México'
            }
        ]


        resultado = menu.some( platillo => platillo.precio <= 10);
        
        console.log('¿Hay platillos abajo de 20? ', resultado);

        resultado = menu.every( platillo => platillo.precio <= 60);
        console.log('¿Todos los platillos cuestan menos de 10? ', resultado);
    ```
 ## Trabajando con datos Remotos
 - Obteniendo datos con fetch
    ```javascript
            "use strict";
            //********************************
            //*** Obteniendo datos con fetch

            var boton = document.getElementById('boton');
            var contenedor = document.getElementById('contenedor');
            var posts = null;

            boton.addEventListener('click', function () {

            fetch('http://jsonplaceholder.typicode.com/posts')
                .then(data => data.json())
                .then(data => {
                      posts = data;
                mostrarDatos(posts)
                })
            });
    ```
- Trabajando con promesa
    ```javascript
        "use strict";

        //********************************
        //*** Trabajando con promesas


        var boton = document.getElementById('boton');
        var contenedor = document.getElementById('contenedor');
        var contBanderas = document.getElementById('banderas');

        boton.addEventListener('click', function () {

            getPosts()
                .then(data => data.json())
                .then(posts => {
                    mostrarDatos(posts);
                return getCountries();
            })
            .then(data => data.json())
            .then(countries => {
                mostrarBanderas(countries);
            });

        });

        function getPosts() {
            return fetch('http://jsonplaceholder.typicode.com/posts');
        }

        function getCountries() {
            return fetch('https://restcountries.eu/rest/v2/all');
        }
    ```
- Manejo de errores
    ```javascript
        "use strict";
        //********************************
        //*** Manejo de errores

        var boton = document.getElementById('boton');
        var mensajes = document.getElementById('mensajes');
        var contenedor = document.getElementById('contenedor');
        var contBanderas = document.getElementById('banderas');

        boton.addEventListener('click', function () {
            getPosts()
                .then(data => data.json())
                .then(posts => {
                    mostrarDatos(posts);
                    return getCountries();
            })
                .then(data => data.json())
                .then(countries => {
                mostrarBanderas(countries);
            })
            .catch(error => {
                 mensajes.classList.toggle('hide');
                 mensajes.innerHTML = error;
                 setTimeout(() => mensajes.classList.toggle('hide'), 6000);
            })
        });

        function getPosts() {
            return fetch('http://jsonplaceholder.typicode.com/posts');
        }

        function getCountries() {
        return fetch('https://restcountries.eu/rest/v2/all');
            }
        }
    ```