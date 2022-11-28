# Estado e Ciclo de Vida
<img src="https://img.shields.io/badge/status-em construção-yellow">

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

