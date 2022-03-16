## Objetos en Javascript
    Un objeto de JavaScript tiene propiedades asociadas a él. Una propiedad de un objeto se puede explicar como una variable adjunta al objeto. Las propiedades de un objeto básicamente son lo mismo que las variables comunes de JavaScript

Creación de objetos:
```javascript
    var myCar = new Object();
    myCar.make = 'Ford';
    myCar.model = 'Mustang';
    myCar.year = 1969;

    var myCar = {
    make: 'Ford',
    model: 'Mustang',
    year: 1969
    };
```
Crear mediante funcion constructura
```javascript
    function Car(make, model, year) {
      this.make = make;
      this.model = model;
      this.year = year;
    }
```
Accediendo a las propiedades de un objeto
```javascript
    // Se crean y asignan cuatro variables de una sola vez,
    // separadas por comas
    var myObj = new Object(),
        str = 'myString',
        rand = Math.random(),
        obj = new Object();

    myObj.type                 = 'Sintaxis de puntos';
    myObj['fecha de creación'] = 'Cadena con espacios';
    myObj[str]                 = 'Valor de cadena';
    myObj[rand]                = 'Número aleatorio';
    myObj[obj]                 = 'Object';
    myObj['']                  = 'Incluso una cadena vacía';
    console.log(myObj);
```    

## Programación Orientada a Objetos
- Clases
    ```javascript
        "use strict";

        //********************************
        //*** Trabajando con Clases

        class Pantalla {
            constructor() {

            }
        }

        const tvSala = new Pantalla();
        const tvHabitacion = new Pantalla();

        function Pantalla(marca, modelo, pulgadas) {
             this.marca = marca;
             this.modelo = modelo;
             this.pulgadas = pulgadas;
        }


         Pantalla.prototype.encendido = function () {
             console.log(`La pantalla ${this.marca} se ha encendido`);
         };


        Pantalla.prototype.volumen = function () {
             console.log(`El volumen se ha modificado`);
        };

        Pantalla.prototype.info = function () {
            console.log(`La pantalla ${this.marca} de modelo ${this.modelo} es de ${this.pulgadas} pulgadas`);
        }

         const tvSala = new Pantalla('Master', 'Oasis', 55);
         const tvHabitacion = new Pantalla('Origin', 'Artemis', 80);
    ```
- Objetos y sus metodos
    ```javascript
        "use strict";
        //********************************
        //*** Objetos, sus métodos y sus propiedades

        class Pantalla {
            constructor(marca, modelo, pulgadas) {
                this.marca = marca;
                this.modelo = modelo;
                this.pulgadas = pulgadas;
            }

            encendido() {
                console.log(`La pantalla ${this.marca} se ha encendido`);
            }

            volumen() {
                console.log(`El volumen se ha modificado`);}

            info() {
            console.log(`La pantalla ${this.marca} de modelo ${this.modelo} es de ${this.pulgadas} pulgadas`);
            }

            set peso(value) {
                this.kgs = value.trim();
            }

            get peso() {
                return this.kgs;
            }
        }

        const tvSala = new Pantalla('Master', 'Oasis', 55);
        const tvHabitacion = new Pantalla('Origin', 'Artemis', 80);
    ```
- Herencia de metódos y propiedades
    ```javascript
        "use strict";
        //********************************
        //*** Herencia de  metódos y propiedades

        class Producto {
            constructor(numSerie) {
                this.numSerie = numSerie;
                this.tiempoGarantia = 100;
            }

            static get infoTienda() {
                console.log(`Productos de la tienda Patito Inc`);
            }

            set garantia(value) {
                this.tiempoGarantia -= value;
            }

            get garantia() {
            return this.tiempoGarantia;
            }
        }

        class Pantalla extends Producto  {
            constructor(numSerie, marca, modelo, pulgadas) {
                super(numSerie)
                this.marca = marca;
                this.modelo = modelo;
                this.pulgadas = pulgadas;
            }

            encendido() {
                this.garantia = 1;
                console.log(`La pantalla ${this.marca} se ha encendido`);
            }

            volumen() {
                console.log(`El volumen se ha modificado`);
            }

            info() {
                console.log(`La pantalla ${this.marca} de modelo ${this.modelo} es de ${this.pulgadas} pulgadas`);
            }

            set peso(value) {
                this.kgs = value.trim();
            }

            get peso() {
                return this.kgs;
            }
        }

        const tvSala = new Pantalla('13579','Master', 'Oasis', 55);
        const tvHabitacion = new Pantalla('24680','Origin', 'Artemis', 80);
    ```
## Solución y manejo de errores
- Manejo de errores
    ```javascript
        "use strict";
        //********************************
        //*** Manejo de errores

        try {
             var array = new Array(10000000000);
             var x = y;
             decodeURIComponent("http://%ominio.com");
        } catch (error) {
            console.log(error.message)
             console.log(error.name)
        }
    ```
- Errores personalizados
    ```javascript
        "use strict";

        //********************************
        //*** Errores personalizados

        var valor1 = 10;
        var valor2 = 20;

        try {
            if (valor1 > valor2) {
            console.log(`Mensaje de validación: ${valor1} si es mayor que ${valor2}`);
        } else {
            throw new Error(`${valor1} no es mayor que ${valor2} :(`)
        }

        } catch (error) {
            console.log(error);
        }
    ```
- Uso del debugger
    ```javascript
        "use strict";
        //********************************
        //***  Uso de debugger

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

        function mostrarBanderas(countries) {
            contBanderas.innerHTML = '';
            countries.map((country, i) => {
            let bandera = document.createElement('img');
            bandera.src = country.flag;
            bandera.width = '20';
            bandera.height = '20';
            contBanderas.appendChild(bandera);
         })
        }

        function mostrarDatos(posts) {
            contBanderas.innerHTML = '';
            posts.map((post, i) => {
        
                debugger;
        
                let titulo = document.createElement('h1');
                let contenido = document.createElement('p');

                titulo.innerHTML = (i + 1) + " - " + post.title;
                contenido.innerHTML = post.body;

                contenedor.appendChild(titulo);
                contenedor.appendChild(contenido);
            })
        }
    ```