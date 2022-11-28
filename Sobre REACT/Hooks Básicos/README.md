# Hooks Básicos
<img src="https://img.shields.io/badge/status-em construção-yellow">

#### Hooks Básicos

Hooks **é uma nova propost a que irá nos permitir utilizar estado, ciclo de vida, entre outras funcionalidades, sem a necessidade de escrevermos componentes com classe**. Organiza também a lógica utilizada dentro de cada componente. A proposta já foi aceita e está disponível na versão 16.8 do React.

*useState*

O `useState` nos permite criar estados em um componente criado a partir de uma função, assim como o `state` presente em componentes criados a partir de classes.

*useEffect*

O `useEffect` é um `Hook` que serve para lidar com os efeitos. Podemos usá-los como os lifeCycles `componentDidMount`, `componentDidUpdate` e `componentWillUnmount`.

*useCallback*

O Hook useCallback recebe como argumentos, uma função de callback e um array. Ele é utilizado para *memorizar funções*. Por causa da maneira como o javascript compara, a função que você cria na primeira vez que um componente é renderizado será diferente daquela criada nas próximas renderizações. Ao colocar essa função dentro do Hook `useCallback`, o React saberá que é a mesma função, assim ela não será criada novamente. Você ainda pode adicionar um array de dependências para acionar um recálculo da função se as dependências mudarem. Portanto, o Hook useCallback é muito útil para evitar *renderizações desnecessárias*.

*useMemo*

O Hook useMemo **é utilizado para memorizar valores**. Ao contrário do useCallback, que armazena em memória a instância da função fornecida, useMemo chama a função fornecida e armazena em memória o seu resultado. Em outras palavras, useMemo armazena em memória um valor calculado.
