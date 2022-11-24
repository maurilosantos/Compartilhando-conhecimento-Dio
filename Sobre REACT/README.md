# Sobre REACT ⚛
<img src="https://img.shields.io/badge/status-em construção-yellow">

Breve introdução, sobre alguns conceitos extras importantes:

**O que é o Node?** Node.js é um runtime de JavaScript, criado pelo desenvolvedor Ryan Dahl em 2009. o Node.js, foi desenvolvido em cima do motor JavaScript V8 – engine criada pelo Google e utilizada nos navegadores Chrome.

**O que é NPM?** O NPM (Node Package Manager), é o gerenciador de pacote padrão do node. Ele é utilizado como gerenciamento de pacotes, fluxo de trabalho em linguagens de programação e ferramenta para construção de frontends em aplicativos e websites.

**O que é o Yarn?** O Yarn é um gerenciador de pacotes para aplicar comandos prontos ao código de uma aplicação.

**O que é o React DevTools? **É uma extensão disponível para o Chrome, Firefox e também como um aplicativo independente que permite inspecionar a hierarquia de componentes do React nas Ferramentas do desenvolvedor do navegador.

#### A história do REACT 

React JS é uma *biblioteca* JavaScript para a criação de interfaces de usuário. Criado em 2011 pelo time do Facebook, o React surgiu com o objetivo de otimizar a atualização e a sincronização de atividades simultâneas no feed de notícias da rede social, entre eles chat, status, listagem de contatos e outros.

A princípio, todas essas atividades, chamadas de estados, tinham uma descrição muito complexa. Com o React, esta descrição torna-se mais simples, bem como também é simplificada a conexão entre HTML, CSS e JavaScript e todos os componentes de uma página.

Por ter demonstrado grande eficiência, nos anos que se seguiram o React foi incorporado à interface de outras redes sociais do grupo, como o Instagram e, em 2013, seu código foi aberto à comunidade, dando início a sua popularização

**Framework x Biblioteca**

*Biblioteca*: Esse é o recurso mais utilizado no mundo da programação e muitas pessoas nem se dão conta do quanto utilizam. A ideia da biblioteca é compartilhar soluções por meio de funções ou métodos. Por Exemplo: Se você tiver que fazer um trabalho de matemática, por exemplo, poderá ir até uma biblioteca física, pegar um livro e utilizar equações desenvolvidas no livro. Então, não será preciso desenvolver as equações desde o início. Exemplo: Moment.js - Chart.js - Voca - mo.js - React.

*Framework*: O framework nada mais é do que uma ferramenta que vai te ajudar a ter como único objetivo focar em desenvolver o projeto, não em detalhes de configurações. Exemplo: Angular - Vuex - Ionic - Next - Express - LoopBack.

#### Componentes e Props

Componentes permitem você dividir a UI em partes independentes, reutilizáveis e pensar em cada parte isoladamente. Conceitualmente, componentes são como funções JavaScript. Eles aceitam entradas arbitrárias (chamadas “props”) e retornam elementos React que descrevem o que deve aparecer na tela.

**Componentes de Função e Classe**: 

A maneira mais simples de definir um componente é escrever uma função JavaScript:

```javascript
function Welcome(props) {
  return <h1>Olá, {props.name}</h1>;
}
```

Essa função é um componente React válido porque aceita um único argumento de objeto “props” (que significa propriedades) com dados e retorna um elemento React. Nós chamamos esses componentes de “**componentes funcionais**” porque são literalmente funções JavaScript.

Você também pode usar uma [classe ES6](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Classes) para definir um componente:

```javascript
class Welcome extends React.Component {
  render() {
    return <h1>Olá, {this.props.name}</h1>;
  }
}
```

Os dois componentes acima são equivalentes do ponto de vista do React.

