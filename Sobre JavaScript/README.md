# JavaScript :duck:
<img src="https://img.shields.io/badge/status-em construção-yellow">

### Índice
* [Funções](#funções)

* [Objetos e Classes](#objetos-e-classes)

  

### Objetos e Classes

#### Objetos

Pensando em estrutura de dados... sabemos que em JS temos 8 tipos de dados: 7 primitivos e 1 não-primitivo: esse é o Objeto.

 O `object` é um tipo de dado especial, pois armazenam coleções de dados e entidades mais complexas que são coleções/conjuntos de pares `key:value` .

*Sintaxe básica:*

```javascript
let user = new Object(); // sintaxe "object constructor" 
let user = {};  // sintaxe "object literal"
```

Usualmente usamos a declaração literal `{}`.

Por exemplo:

```javascript
let user = {         // o objeto
  name: "Maurilo",  // chave:valor name:Maurilo
  age: 25          // chave:valor 
};
// neste objeto há duas propriedades com chave:valor.
// caso armazenasse alguem função, esta propriedade teria o nome de Método.
```

Os valores de propriedade são acessíveis usando a notação de *ponto*:

```javascript
// pegando os valores das propriedades do objeto
alert( user.name ); // Maurilo
alert( user.age ); // 25
```

Para remover uma propriedade, pode-se usar o operador `delete user.age`

A última propriedade da lista pode terminar com uma vírgula:

```javascript
let user = {
  name: "John",
  age: 30,
}
```

 Torna mais fácil adicionar/remover/mover propriedades, pois todas as linhas se tornam iguais :wink:.

- A palavra `this` em métodos.

`this` é uma palavra reservada em JS que se refere ao contexto em que ela está inserida. É comum que em um método do objeto ele precise acessar as informações armazenadas do objeto para fazer seu trabalho.

Por exemplo, o código interno `user.sayHi()`pode precisar do *name* no objeto`user`:

```javascript
let user = {
  name: "Maurilo",
  age: 25,

  sayHi() {
    // "this" é o objeto user em questão
    alert(this.name);
  },

};

user.sayHi(); // Maurilo
```

Tecnicamente, também é possível acessar o objeto sem `this`, referenciando-o por meio de `user`:

```javascript
let user = {
  name: "Maurilo",
  age: 25,

  sayHi() {
    alert(user.name); // "user" ao invés de "this"
  },

};
```

…Mas esse código não é confiável. Se decidirmos copiar `user` para outra variável, por exemplo, `admin = user` e sobrescrever `user` com outra variável, ela acessará o objeto errado.

```javascript
let user = {
  name: "John",
  age: 30,

  sayHi() {
    alert( user.name ); // user gerará erro
  },

};

let admin = user;
user = null; // subscrevendo para facilitar

admin.sayHi(); // TypeError: Cannot read property 'name' of null
```

Se usássemos `this.name` em vez de `user.name` dentro do `alert`, o código funcionaria.

#### Classes

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
