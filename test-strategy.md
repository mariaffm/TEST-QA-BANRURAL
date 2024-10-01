# Plan de Ataque para Pruebas del Juego "Adivina tu Número"

## Introducción
Este documento detalla la estrategia de pruebas para el juego denominado "Adivina tu Número" implementado en el banco financiero. En el cual ser realizaron pruebas funcionales para asegurar que la aplicación cumpla con cada uno de los requerimientos especificados previamente.

## Requerimientos Funcionales
**1** El número a adivinar debe pertenecer al conjunto de los enteros (e.g. 1, 2, 3...)
**2** El número que ingresará el jugador debe pertenecer al conjunto de los enteros (e.g. 1, 2, 3...), en caso que no ingrese un número entero, debe mostrarse una alerta al usuario y no se debe incrementar un intento de prueba.
**3** Sí el número que ingresó el jugador es mayor al número a adivinar, se debe mostrar el siguiente mensaje en color negro: "Incorrecto! El número es mayor!", en caso que sea menor, se debe mostrar: "Incorrecto! El número es menor!".
**4** Si después de 10 intentos, el usuario no adivina el número, se debe mostrarse el mensaje de color rojo: "!!!Pérdistes!!!"
**5** Si el usuario adivina el número antes de los 10 intentos, se debe mostrar el mensaje de color verde: "Felicitaciones! adivinaste el número!".


## Estrategia de Pruebas
Debido a los antecendentes del programa donde ya se había verificado por el cliente que el sistema no funciona, se realizan algunas validaciones y correcciones en base a los requerimientos para asegurad la funcionalidad y la calidad del sistema.


### 2. Casos de pruebas
 Al ejecutar el programa en uno o mas navegadores para verificar la funcionalidad, además de validar en consola los mensajes de error, se detectó un error en el codigo sobre una funcion no reconocida con el siguiente mensaje:
    "index.html:89 Uncaught TypeError: guessSubmit.addeventListener is not a function at index.html:89:15"
haciendo referencia a la linea de codigo "guessSubmit.addeventListener('click', checkGuess);" debido a un error sintactico, posterior a su correción al agregar "E" mayuscula en Event, se prosiguió a validad la funcionalidad del sistema en base a los requerimientos.
    **1 Validacion de Entrada No Numerica** 
        *-ID del Caso de Prueba: CP001
        *-Resultado Esperado: Verificar que muestre una alerta cuando se ingresa un valor no numérico, además de no incrementar el contador de intentos de prueba del usuario
        *-Precondiciones:
            El juego está en la pantalla de inicio y esperando una entrada del usuario.
        *-Pasos a Seguir:
            Abrir el juego en el navegador.
            En el campo de entrada, se ingresa una letra, cadena o caracter no numérico
            Hacer clic en el botón "Ingresar el número aleatorio".

        *-RESULLTADO OBTENIDO: El sistema reconoce la letra y las cadenas de letra como un número entero, mostrando un mensaje en color verde con la descripción de "Incorrecto!" 
        *-Estado: No Funcional

- **Caso 2 Ingreso de numeros enteros**
        *-ID del Caso de Prueba: CP002
        *-Resultado Esperado: Validar el ingreso de numeros enteros positivos, 
        *-Precondiciones:
            El juego está en la pantalla de inicio y muestra la lista de numeros ingresados anteriormente
        *-Pasos a Seguir:
            Abrir el juego en el navegador.
            En el campo de entrada, se ingresa un numero entero positivo en el rango de 0 a 100
            Hacer clic en el botón "Ingresar el número aleatorio".

        *-RESULLTADO OBTENIDO: El sistema valida el numero entero positivo, sin embargo, no muestra ningun mensaje de color negro que indique si es mayor o menor al numero que se debe adivinar. Unicamente muestra el mensaje de color verde de "Incorrecto!"
        *-Estado: No Funcional

  - **Caso 3 Ingresar un número fuera del rango**: 
        *-ID del Caso de Prueba: CP003
        *-Resultado Esperado: Visualizacion de advertencias que se debe de ingresar un numero entero al juego y no incrementar el contador de intentos del usuario. 
        *-Precondiciones:
            El juego está en la pantalla de inicio y muestra la lista de numeros ingresados anteriormente
        *-Pasos a Seguir:
            Abrir el juego en el navegador.
            En el campo de entrada, se ingresa un numero mayor a 100 y menor de 0 
            Hacer clic en el botón "Ingresar el número aleatorio".

        *-RESULLTADO OBTENIDO: El sistema no muestra ningún mensaje de advertencia con respecto a los numeros fuera del limite ingresados, mostrando el mensaje de color verde de "Incorrecto!" cuando se ingresa el numero. 
        *-Estado: No Funcional
  
- **Caso 4 Ingresar un número mayor que el número a adivinar.**: 
     *-ID del Caso de Prueba: CP004
        *-Resultado Esperado: Al ingresar un numero mayor que el numero a adivinar se debe visualiza el mensaje "Incorrecto! El número es menor!" en negro.
        *-Precondiciones:
            El juego está en la pantalla de inicio y muestra la lista de numeros ingresados anteriormente
        *-Pasos a Seguir:
            Abrir el juego en el navegador.
            En el campo de entrada, se ingresa un numero menor al numero ingresado anteriormente
            Hacer clic en el botón "Ingresar el número aleatorio".

        *-RESULLTADO OBTENIDO: El sistema muestra un mensaje de "Incorrecto!" en color verde al no coincidir con el numero a adivinar.
        *-Estado: No Funcional

- **Caso 5 Ingresar un número menor que el número a adivinar.**: 
      *-ID del Caso de Prueba: CP005
        *-Resultado Esperado: Al ingresar un numero menor que el numero a adivinar se debe visualiza el mensaje "Incorrecto! El número es mayor!" en negro.
        *-Precondiciones:
            El juego está en la pantalla de inicio y muestra la lista de numeros ingresados anteriormente
        *-Pasos a Seguir:
            Abrir el juego en el navegador.
            En el campo de entrada, se ingresa un numero mayor al numero ingresado anteriormente
            Hacer clic en el botón "Ingresar el número aleatorio".

        *-RESULLTADO OBTENIDO: El sistema muestra un mensaje de "Incorrecto!" en color verde al no coincidir con el numero a adivinar.
        *-Estado: No Funcional

- **Caso 6 Agotar los 10 intentos sin adivinar.**: 
    *-ID del Caso de Prueba: CP006
        *-Resultado Esperado: Al agotar los 10 intentos permitidos de adivinar, se debe mostrar el mensaje "!!!Pérdistes!!!" en color rojo.
        *-Precondiciones:
            El juego está en la pantalla de inicio y muestra la lista de los 9 numeros positivos ingresados anteriormente
        *-Pasos a Seguir:
            Abrir el juego en el navegador.
            En el campo de entrada, se ingresa un numero mayor o menor al numero ingresado anteriormente
            Hacer clic en el botón "Ingresar el número aleatorio".

        *-RESULLTADO OBTENIDO: El sistema muestra un mensaje de "Incorrecto!" en color verde al no coincidir con el numero a adivinar, permitiendo mas de 10 intentos al usuario
        *-Estado: No Funcional


- **Caso 7  Adivinar el número**:
    *-ID del Caso de Prueba: CP007
        *-Resultado Esperado: Al ingresar el numero correcto, se debe mostrar "Felicitaciones! adivinaste el número!" en color verde. 
        *-Precondiciones:
            El juego está en la pantalla de inicio para ingresar un numero
        *-Pasos a Seguir:
            Abrir el juego en el navegador.
            En el campo de entrada, se ingresa un numero en el rango de 0 a 100
            Hacer clic en el botón "Ingresar el número aleatorio".

        *-RESULLTADO OBTENIDO: Debido a que el sistema no muestra ningun indicador si el numero es mayor o menor al ingresado, se dificulta adivinar el numero, mostrando como unico mensaje "Incorrecto!" en color verde al no coincidir con el numero a adivinar
        *-Estado: No Funcional

- **Caso 8. Pruebas de Reseteo del Juego**:
     *-ID del Caso de Prueba: CP008
        *-Resultado Esperado: Al finalizar los 10 intentos permitidos de adivinar el numero, el sistema debe de reiniciarse automaticamente, reseteando los campos y los mensajes mostrados
        *-Precondiciones:
            El usuario ha ingresado los 10 intentos permitidos o ya ha ganado el juego
        *-Pasos a Seguir:
            Abrir el juego en el navegador.
            En el campo de entrada, se ingresan los intentos para adivinar el numero
            Al acertar con el número a adivinar o al terminar los 10 intentos permitidos, el sistema automaticamente de actualiza para un nuevo juego.

        *-RESULLTADO OBTENIDO: El sistema no valida el limite de los 10 intentos realizados por el usuario, por lo que el juego no tiene limite de oportunidades. 
        *-Estado: No Funcional



#### 2. Pruebas de Caja Blanca 
Al tener acceso al codigo del programa se realizaron pruebas de caja blanca para verificar la estrucutra del sistema y la lógica utilizada para su creación, encontrando los siguientes errores sintacticos y lógicos:

   - **Asignación de numero Aleatorio** La línea de codigo "let randomNumber = Math.random() * 10;" genera un número entre 0 y 10, sin embargo, el requerimiento especifica que el numero aleatorio generado debe de ser entre el rango de 0 a 100
        Solución: Cambiar a "let randomNumber = Math.floor(Math.random() * 100) + 1;" para generar un número entre 1 y 100.

    -**Intentos Permitidos**  
    Descripcion: La constante ATTEMPS está definida en 5, pero el requerimiento del juego indica que deberían ser 10 intentos permitidos al usuario por lo que no cumple con la lógica del juego.
    Solución: Modificar a const ATTEMPS = 10;

    -**Errores Sintacticos** 
    Descripción: El método de addeventListener tiene un error sintactico.
    Solución: Corregirlo a addEventListener con "E" mayúscula.

    -**Selector Incorrecto** 
    Descripción: En const lowOrHi = document.querySelector('lowOrHi');, hace falta agregar un punto al inicio de lowOrhi para poder acceder al ser una clase.
    Solución: Cambiar a const lowOrHi = document.querySelector('.lowOrHi');

    -**Lógica de Juego** 
    Descripción: El mensaje "!!!Pérdistes!!!" se muestra cuando el usuario acierta, en lugar de ser mostrado cuando el usuario se queda sin intentos.
    Solución: Modificar la lógica en checkGuess() para que "Felicitaciones! adivinaste el número!" sea mostrado al acertar y el mensaje "!!Pérdistes!!" cuando se agoten los intentos del usuario.

    -**Conversión de Tipo**
    Descripción: la linea de codigo let userGuess = guessField.value; no convierte la entrada del usuario a un número.
    Solución: Cambiar a let userGuess = Number(guessField.value); para asegurar comparaciones correctas.

    -**Reseteo del Juego**
    Descripción: La línea de codigo randomNumber = Math.floor(Math.random()) + 1; no genera el numero aleatorio entre 0 a 100 debido a la falta de lógica de las operaciones qeu conlleva al función, en este caso le hace falta la multiplicaión* 100.
    Solución: Modificar a randomNumber = Math.floor(Math.random() * 100) + 1; 



## Conclusiones
Las pruebas se realizarón en el navegador de Chrome Y Brave utilizando la consola de desarrollador para poder identificar y reportar errores. Se documentó cada uno de los hallazgos que se encontrarón como la solución respectiva que se le dió a cada uno. Posterior a la corrección de errores en el código, se ejecutó nuevamente cada uno de los casos de prueba,dando como resultado el cambio de estado a funcional de cada una por cumplir con el resultado esperado de los requerimientos del cliente. 

