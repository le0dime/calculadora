# calculadora
### Trabajo práctico para Programación III
Este repositorio contiene código fuente y consignas a realizar en Java
### Estructura del proyecto
```
└───src
    ├───main
    │   ├───negocio -----> Clases con la lógica de negocio del proyecto
    │   └───interfaz ----> Clases con las interfaces visuales del proyecto
    └───test
        └───calculo -----> Tests para verificar la funcionalidad de Calculo
```
### Capa de negocio
#### Operacion
Es un `ENUM` con las cuatro operaciones básicas: `SUMA`, `RESTA`, `PRODUCTO` y `DIVISION`. <br>
Cada una de ellas devuelve una instancia de la clase que realiza la operación indicada en su nombre.
#### Calculo
Cuenta con los siguientes métodos públicos:
1. `Calculo(Operacion.[Opcion seleccionada])`: Constructor de la clase. Requiere una operación como parámetro.
   * Excepciones:
     * Tipo: `IllegalArgumentException`.
     * Descripción: _Operacion no puede estar vacío_.
2. `void cambiarOperador(Operacion.[Opcion seleccionada])`: Permite cambiar el operador actual.
3. `Operacion obtenerOperadorActual()`: Devuelve el operador actualmente establecido.
4. `double calcular(double, double)`: Realiza un cálculo entre dos terminos según el operador establecido.
   * Excepciones (`Operador.DIVISION`):
     * Tipo: `IllegalArgumentException`.
     * Descripción: _No se puede dividir por cero_.
#### Memoria
Es un `Singleton` que funciona como la memoria de la calculadora. Permite almacenar hasta 3 números. <br>
Cuenta con los siguientes métodos públicos:
1. `Memoria obtenerInstancia()`: Devuelve la instancia de la clase para poder acceder a los métodos.
2. `void agregar()`: Agrega un número a la memoria de la calculadora. Si la cantidad de items sobrepasa el límite, se remueve el primer número ingresado.
3. `ArrayList<Double> listar()`: Obtiene todos los números almacenados en la memoria.
4. `void vaciar()`: Vacía la memoria.
