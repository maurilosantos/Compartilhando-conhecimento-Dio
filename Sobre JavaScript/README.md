# JavaScript :duck:
<img src="https://img.shields.io/badge/status-em construção-yellow">

### Índice
* [Funções](#funções)

* [Objetos e Classes](#objetos-e-classes)

* [Arrays e Estruturas de Repetição](#arrays-e-estruturas-de-repetição)

  

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



### Arrays e Estruturas de Repetição

Antes de começar com **Arrays** é bom lembrar sobre *estrutura de dados*: Uma estrutura de dados é um formato para organizar, gerenciar e armazenar dados de uma maneira que permita acesso e modificação eficientes. JavaScript tem estruturas de dados primitivas (incorporadas) e não primitivas (não incorporadas). Estruturas de dados primitivas vêm por padrão com a linguagem de programação e você pode implementá-las imediatamente (como **arrays** e **objetos**). Estruturas de dados não primitivas não vêm por padrão e você precisa codificá-las se quiser usá-las.

#### Arrays

Arrays são objetos que armazenam uma coleção de itens e podem ser atribuídos a uma variável. Eles têm seus próprios métodos que podem realizar operações no array.

Os objetos permitem que você armazene coleções de valores com chave. Isso é bom.

Mas muitas vezes descobrimos que precisamos de uma *coleção ordenada* , onde temos um 1º, um 2º, um 3º elemento e assim por diante. Por exemplo, precisamos disso para armazenar uma lista de algo: usuários, mercadorias, elementos HTML etc.

Não é conveniente usar um objeto aqui, porque ele não fornece métodos para gerenciar a ordem dos elementos. Não podemos inserir uma nova propriedade “entre” as já existentes. Objetos simplesmente não são feitos para tal uso.

Existe uma estrutura de dados especial chamada `Array`, para armazenar coleções ordenadas.

Sintaxe básica:

```javascript
let arr = new Array();
let arr = [];
```

Quase o tempo todo, a segunda sintaxe é usada... Podemos fornecer elementos iniciais entre colchetes e são indexados começando com zero.

```javascript
let fruits = ["Apple", "Orange", "Plum"];

alert( fruits[0] ); // Apple
alert( fruits[1] ); // Orange
alert( fruits[2] ); // Plum
```

E pode armazenar elementos de qualquer tipo.

```javascript
// mix de valores
let arr = [ 'Maçã', { name: 'Maurilo' }, true, function() { alert('Olá, mundo!'); } ];

// pegue o objeto no index 1 e mostre o nome dele
alert( arr[1].name ); // Maurilo

// pegue a função no index 3 e execute
arr[3](); // Olá, mundo!
```

- **Obtenha os últimos elementos com "at"**

Digamos que queremos o último elemento do array.

```javascript
let fruits = ["Apple", "Orange", "Plum"];

// funciona da mesmo forma que explicitamente como fruits[fruits.length-1]
alert( fruits.at(-1) ); // Plum
```

Em outras palavras, `arr.at(i)`:

- é exatamente o mesmo que `arr[i]`, se i >= 0.
- para valores negativos de i, ele recua do final da matriz.

Vamos os métodos:

`pop`
Extrai o último elemento do array e também pode o retornar:

```javascript
let fruits = ["Apple", "Orange", "Pear"];

alert( fruits.pop() ); // remove "Pear" e o mostra em alert 

alert( fruits ); // Apple, Orange
```

`push`

Anexe o elemento ao final do array:

```javascript
let fruits = ["Apple", "Orange"];

fruits.push("Pear");

alert( fruits ); // Apple, Orange, Pear
```

A chamada `fruits.push(...)` é igual a `fruits[fruits.length] = ....`

`shift`
Extrai o primeiro elemento do array e também pode o retorna:

```javascript
let fruits = ["Apple", "Orange", "Pear"];

alert( fruits.shift() ); // remove Apple e o mostra em alert

alert( fruits ); // Orange, Pear
```

`unshift`
Adicione o elemento ao início do array:

```javascript
let fruits = ["Orange", "Pear"];

fruits.unshift('Apple');

alert( fruits ); // Apple, Orange, Pear
```

Métodos `push` e `unshift` pode adicionar vários elementos de uma só vez:

```javascript
let fruits = ["Apple"];

fruits.push("Orange", "Peach");
fruits.unshift("Pineapple", "Lemon");

// ["Pineapple", "Lemon", "Apple", "Orange", "Peach"]
alert( fruits );
```

#### Repetições (loops)

Uma das maneiras mais triviais de alternar itens de matriz é o `for` loop sobre índices:

```javascript
let arr = ["Apple", "Orange", "Pear"];

for (let i = 0; i < arr.length; i++) {
  alert( arr[i] );
}
```

Mas para arrays existe outra forma de loop, `for..of`:

```javascript
let fruits = ["Apple", "Orange", "Plum"];

for (let fruit of fruits) {
  alert( fruit );
}
```

O `for..of` não dá acesso ao número do elemento atual indexado, apenas seu valor, mas na maioria dos casos isso é suficiente. E é mais rápido de fazer.

### Importação e Exportação com JavaScript

- Importando o código em um arquivo

Como o back-end é escrito em node.js, podemos fazer uso de uma função chamada **require** que vai ser responsável por chamar o nosso módulo (arquivo) para dentro de outro arquivo js, assim a gente pode reutilizar uma função, objeto,classe... sem reescrever.

```javascript
const { gets, print } = require('./funcoes-auxiliares');

```

Porém para a função `require` funcionar devemos exportar lá o nosso outro arquivo de referência também pois só assim ficará visível ao outro.

```javascript
module.exports = { gets, print };
```

Com a utilização do `module.export` 

O sistema de módulos do `Node.js` é responsável por criar o objeto `module.export` e o **export** aponta para esse objeto, podendo ser usado para **retornar funções, objetos e classes** bastando somente adicioná-los ao `module.export`.
