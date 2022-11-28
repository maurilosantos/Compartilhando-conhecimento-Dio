# Componentes e Props ⚛
<img src="https://img.shields.io/badge/status-em construção-yellow">



[Doc React](https://reactjs.org/docs/create-a-new-react-app.html)

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

**Nota:** Sempre inicie os nomes dos componentes com uma letra maiúscula.

O React trata componentes começando com letras minúsculas como tags do DOM. Por exemplo, `<div />` representa uma tag div do HTML, mas `<Welcome />` representa um componente e requer que `Welcome` esteja no escopo.

