# JavaScript :duck:
<img src="https://img.shields.io/badge/status-em construção-yellow">

## Índice
* [Funções](#funções)

* [Objetos e Classes](#objetos-e-classes)

  

#### Objetos e Classes

> Na programação orientada a objetos (POO), uma classe é um modelo de código de programa extensível para criar objetos, fornecendo valores iniciais para o estado (variáveis dos membros) e implementações de comportamento (funções ou métodos dos membros). - Wikipédia.

Na prática, muitas vezes precisamos criar muitos objetos do mesmo tipo, como usuários, bens ou qualquer outra coisa. As classes portanto generalizam e definem uma instância (ocorrência).

*Sintaxe básica*: 

```javascript
class MyClass{  
    // class methods  
    constructor() { ... }  
    method1() { ... }  
    method2() { ... }  
    method3() { ... } 
        ...
}
```

Em seguida, use `new MyClass()` para criar um novo objeto com todos os métodos listados,  em seguida o método `constructor()` é invocado automaticamente por `new`, portanto podemos inicializar o objeto lá.

Exemplo:

```javascript
class User {

  constructor(name) {
    this.name = name;
  }

  sayHi() {
    alert(this.name);
  }

}

// Criando usuário:
let user = new User("Maurilo");
user.sayHi();
```

Quando `new User("Maurilo")` é chamado:

1. Um novo objeto é criado.
2. O `constructor` é executado com o argumento fornecido e o atribui a `this.name`.

…Então podemos chamar os métodos do objeto, como `user.sayHi()`.
