# Plan de ataque de errores del programa TEST-QA-BANRURAL en test-trategy.md

Error 1 en linea 44: El numero random esta utilizando Math.floor() * 10 y retorna un numero decimal y no entero.
````javascript
  let randomNumber = Math.random() * 10;```
````
Solucion en actual linea 37
```javascript
let randomNumber = Math.floor(Math.random() * 100 + 1);
```

Error 2 en linea 46: El valor de ATEEMPS es de 5 y se requiere 10.
```javascript
const ATTEMPS = 5;
```
Solucion en actual linea 38
```javascript
const ATTEMPS = 10;
```

Error 3 en linea 49: LowOrHi no tiene el punto al iniciar y la clase no se llamara.
```javascript
const lowOrHi = document.querySelector("lowOrHi");
```
Solucion en actual linea 41
```javascript
const lowOrHi = document.querySelector(".lowOrHi");
```

Agregado 1 en linea 48: Falta la validacion que sea un numero  y que se agregre si es valido el intento del usuario.
```javascript
if (!/^[1-9]/.test(userGuess)) {
    return alert('Solo puede ingresar numeros enteros');
}
console.log('Repetido', guessCount)
console.log('Random', randomNumber)
console.log(userGuess)
```

Error 4 en linea 59: La validacion del if esta mala, tiene que ser mayor a cero e igual a 10.
```javascript
if (guessCount === 1) {
  guesses.textContent = "Número aleatorio anterior: ";
}
```
Solucion en actual linea 54
```javascript
if (guessCount > 0 && guessCount < 11) {
  guesses.textContent = "Número aleatorio anterior: ";
}
```

Error 5 en linea 62: Ingresar al if el contador que va incrementando y quitar el salto.
```javascript
guesses.textContent += userGuess + ' ';
```
Solucion en actual linea 54
```javascript
if (guessCount > 0 && guessCount < 11) {
  guesses.textContent = "Número aleatorio anterior: ";
  guesses.textContent += userGuess;
}
```

Agregado 2 en actual linea 58: Pasar a Int el String ingresado.
```javascript
userGuess = parseInt(userGuess);
```

Error 6 en linea 64: El primer if valida que el numero ingresado es igual al numero generado, entonces el usuario gana y el black por green.
```javascript
if (userGuess === randomNumber) {
  lastResult.textContent = "!!!Pérdistes!!!";
  lastResult.style.backgroundColor = "black";
  lowOrHi.textContent = "";
  setGameOver();
}
```
Solucion en actual linea 59
```javascript
if (userGuess === randomNumber) {
  lastResult.textContent = "Felicitaciones! adivinaste el número!";
  lastResult.style.backgroundColor = "green";
  setGameOver();
}
```

Error 7 en linea 69: El usuario perdio el juego segun la validacion del else donde se compara con un if.
```javascript
else if(guessCount === ATTEMPS) {
      lastResult.textContent = 'Felicitaciones! adivinaste el número!';
      lastResult.style.backgroundColor = 'red';
      setGameOver();
}
```
Solucion en actual linea 63
```javascript
else if (guessCount === ATTEMPS) {
    lastResult.textContent = '!!!Pérdistes!!!';
    lastResult.style.backgroundColor = 'red';
    setGameOver();
}
```

Modificado 1 en linea 73-81: Cambio la forma de hacer la preguntas para tener de forma mas clara si el numero es mayor o menor y el green por black.
```javascript
else {
      lastResult.textContent = 'Incorrecto! ';
      lastResult.style.backgroundColor = 'green';
      if(userGuess < randomNumber) {
        lowOrHi.textContent = 'El número es mayor!';
      } else if(userGuess > randomNumber) {
        lowOrHi.textContent = 'El número es menor!';
      }
    }
```
Modificado en actual linea 67-75.
```javascript
else if (userGuess > randomNumber) {
    lastResult.textContent = 'Incorrecto! El número es mayor!';
    lastResult.style.backgroundColor = 'black';
    lowOrHi.textContent = '';
} else if (userGuess < randomNumber) {
    lastResult.textContent = 'Incorrecto! El número es menor!';
    lastResult.style.backgroundColor = 'black';
    lowOrHi.textContent = '';
}
```

Error 8 en linea 101: Se hace llamado a una clase con el punto lo cual generar error y no existe la clases resultParas p, se elimina la ultima letra p.
```javascript
const resetParas = document.querySelectorAll(".resultParas p");
```
Solucion en actual linea 91
```javascript
const resetParas = document.querySelectorAll("resultParas");
```

Error 9 en linea 114: Se estan generando numeros decimales.
```javascript
randomNumber = Math.floor(Math.random()) + 1;
```
Solucion en actual linea 101
```javascript
randomNumber = Math.floor((Math.random() * 100) + 1);
```