# Sobre REACT ⚛
<img src="https://img.shields.io/badge/status-em construção-yellow">

Breve introdução, sobre alguns conceitos extras importantes:

**O que é o Node?** Node.js é um runtime de JavaScript, criado pelo desenvolvedor Ryan Dahl em 2009. o Node.js, foi desenvolvido em cima do motor JavaScript V8 – engine criada pelo Google e utilizada nos navegadores Chrome.

**O que é NPM?** O NPM (Node Package Manager), é o gerenciador de pacote padrão do node. Ele é utilizado como gerenciamento de pacotes, fluxo de trabalho em linguagens de programação e ferramenta para construção de frontends em aplicativos e websites.

**O que é o Yarn?** O Yarn é um gerenciador de pacotes para aplicar comandos prontos ao código de uma aplicação.

**O que é o React DevTools? ** É uma extensão disponível para o Chrome, Firefox e também como um aplicativo independente que permite inspecionar a hierarquia de componentes do React nas Ferramentas do desenvolvedor do navegador.

[Doc React](https://reactjs.org/docs/create-a-new-react-app.html)

### Indice

- [História do React](#a-historia-do-react)
- [Componentes e Props](#componentes-e-props)
- [Ciclo de Vida](#estado-e-ciclo-de-vida)
- [React CLI](#react-cli)
- [Styled-Components 💅](#styled-components)
- [Hooks Básicos](#hooks-basicos)



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

**Nota:** Sempre inicie os nomes dos componentes com uma letra maiúscula.

O React trata componentes começando com letras minúsculas como tags do DOM. Por exemplo, `<div />` representa uma tag div do HTML, mas `<Welcome />` representa um componente e requer que `Welcome` esteja no escopo.

#### Estado e Ciclo de Vida 

O estado de um componente é um objeto que guarda as informações que podem mudar ao longo do seu ciclo de vida, e esses estados permitem que o componente acompanhe as mudanças de informação a cada renderização.

Para usar um estado, precisamos que ele sempre exista no componente, por isso começamos definindo um estado inicial, e isso pode ser feito em um construtor de um Class Component. Para atualizar ele, precisamos primeiro entender que ele nunca deve ser explicitamente atualizado, o correto é usar o método setState(), que atualiza o estado e depois chama o método `render()`.

Bom, e o ciclo de vida? Entendemos um ciclo de vida como algo que nasce, se desenvolve e morre, e os componentes seguem essa lógica no React. Eles são criados (montados do DOM), se desenvolvem (updates), e morrem (desmontados do DOM), e em cada fase desse ciclo temos alguns métodos disponíveis.

Separamos o ciclo de vida do React em 4 etapas em que podemos fazer ações durante a montagem e desmontagem de um componente, são elas:

1. **Inicialização:** quando estamos definindo estados e props, normalmente ocorre dentro de um método construtor;
2. **Mounting:** momento em que o React “monta” o componente no DOM, é quando temos o primeiro render. No exemplo, estamos configurando um temporizador utilizando o método componentDidMount();

![Não foi fornecido texto alternativo para esta imagem](https://media-exp1.licdn.com/dms/image/C4E12AQEOzQaJsjmR5Q/article-inline_image-shrink_400_744/0/1642426839074?e=1674691200&v=beta&t=tbnW7ZwfrYHxeneIr-7F-jedI03AFGNe_BJCxRzAoXg)

3. **Updating:** após o componente ser criado, começam as mudanças de estado e a re-renderização, e as alterações ocorrem de acordo com ações do usuário, como cliques ou digitar;
4.  **Unmouting:** momento em que o componente é “desmontado” do DOM. No exemplo, estamos zerando o tempo no nosso contador utilizando o método componentWillUnmount();

![Não foi fornecido texto alternativo para esta imagem](https://media-exp1.licdn.com/dms/image/C4E12AQH_PMWmZEomKw/article-inline_image-shrink_400_744/0/1642426854926?e=1674691200&v=beta&t=qw6c_QgGM_iTAEwpWYj9nFti2F7yK7BBnTalRHyoHAg)



![](https://github.com/maurilosantos/Compartilhando-conhecimento-Dio/blob/main/Sobre%20REACT/assets/ciclo%20de%20vida.png?raw=true)

#### **React CLI**

Create React App é um ambiente confortável para aprender React, e é a melhor maneira de começar um single-page application em React.

Além de configurar seu ambiente de desenvolvimento para utilizar as funcionalidades mais recentes do JavaScript, ele fornece uma experiência de desenvolvimento agradável, e otimiza o seu app para produção. 

Para criar no terminal use: 

```txt
npx create-react-app nome-do-app
cd nome-do-app
npm start
```

**Adicionando** **navegação** **na** **aplicação**

Em um site acessamos várias páginas, como por exemplo, página inicial, contatos, sobre e perfil. Para navegar entre as páginas de uma aplicação React.JS precisaremos criar rotas, onde cada rota vai representar uma tela.

Para trabalhar com rotas no React vamos utilizar um pacote chamado **React Router Dom** que precisa ser instalado no projeto. É ele que nos auxiliará na criação da navegação.

Com o projeto React já criado, faça:

```tex
npm install react-router-dom
```

[Doc Router](https://v5.reactrouter.com/web/guides/quick-start)

#### Styled-Components 💅

Basicamente, styled components **é uma biblioteca que possibilita escrever códigos CSS dentro do JavaScript**. Com ele, você pode criar websites bonitos e funcionais. Além disso, ganhar mais agilidade e precisão no desenvolvimento web.

E **para escrever CSS em JavaScript é necessário usar Tagged Templates Literals.** 

**Vantagens**  :

1. Os componentes são renderizados juntamente com a página, dessa maneira, apenas o CSS que será utilizado será injetado. Você carregará, portanto, somente o necessário. 

2. Os nomes das classes são gerados automaticamente, assim, você não terá problemas de gerar nomes duplicados e abrir brechas para que bugs ocorram. 

3. Todo o CSS fica no arquivo JavaScript, dessa maneira, **você encontra mais fácil o que precisa remover.** 

[Doc Styled-components](https://styled-components.com)

#### Hooks Básicos

Hooks **é uma nova proposta que irá nos permitir utilizar estado, ciclo de vida, entre outras funcionalidades, sem a necessidade de escrevermos componentes com classe**. Organiza também a lógica utilizada dentro de cada componente. A proposta já foi aceita e está disponível na versão 16.8 do React.

*useState*

O `useState` nos permite criar estados em um componente criado a partir de uma função, assim como o `state` presente em componentes criados a partir de classes.

*useEffect*

O `useEffect` é um `Hook` que serve para lidar com os efeitos. Podemos usá-los como os lifeCycles `componentDidMount`, `componentDidUpdate` e `componentWillUnmount`.

*useCallback*

O Hook useCallback recebe como argumentos, uma função de callback e um array. Ele é utilizado para *memorizar funções*. Por causa da maneira como o javascript compara, a função que você cria na primeira vez que um componente é renderizado será diferente daquela criada nas próximas renderizações. Ao colocar essa função dentro do Hook `useCallback`, o React saberá que é a mesma função, assim ela não será criada novamente. Você ainda pode adicionar um array de dependências para acionar um recálculo da função se as dependências mudarem. Portanto, o Hook useCallback é muito útil para evitar *renderizações desnecessárias*.

*useMemo*

O Hook useMemo **é utilizado para memorizar valores**. Ao contrário do useCallback, que armazena em memória a instância da função fornecida, useMemo chama a função fornecida e armazena em memória o seu resultado. Em outras palavras, useMemo armazena em memória um valor calculado.
