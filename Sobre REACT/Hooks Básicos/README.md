# Hooks Básicos
<img src="https://img.shields.io/badge/status-em construção-yellow">

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

#### React Hook Forms

**O React Hook Forms é uma biblioteca que auxiliará a organizar e padronizar as validações dos formulários por toda a aplicação.**

React Hook Form cria validação de formulário simples, alinhado com os existentes dentro do próprio HTML, as validações suportadas são: required, min, max, maxlength, minlength, pattern, validate.

**O React Hook Form adota o uso de entradas não controladas em vez de depender do estado**. Essa abordagem torna os formulários mais eficientes e reduz o número de novas renderizações.

- **Instalação**: Para instalar a biblioteca React Hook Forms dentro do projeto React, basta executar o comando `npm install react-hook-form`
- **Usando**: Para utilizar o react hook form precisamos importar o hook chamado *useForm*: `import { useForm } from "react-hook-form";`

Depois que importamos o useForm da biblioteca react-hook-form podemos utilizar o processo de desestruturação para extrair duas funcionalidades chamadas `register` e `handleSubmit`.

```javascript
const { register, handleSubmit } = useForm();
```

O register pode ser usado para personalizar nossa validação em qualquer campo de input e o `handleSubmit` vai passar os dados do formulário quando a validação do formulário for bem-sucedida. Ele é inserido na propriedade onSubmit do formulário. 

Segue exemplo simples:

```javascript
import React from "react";
import { useForm } from "react-hook-form";

export default function App() {
  const { register, handleSubmit } = useForm();
  const onSubmit = (data) => console.log(data);

  return (
    <form onSubmit = { handleSubmit(onSubmit) } >
        <input name="primeiro_nome"  ref = { register({ required: true, maxLength: 20 }) } />
        <input name="ultimo_nome" ref = { register({ maxLength: 20 }) } />
        <input name="idade" type="number" ref = { register({ min: 18, max: 99 }) } />
        <input type="submit" />
      </form>
  );
}
```

##### Exibindo erros

o validar os campos queremos que o usuário saiba qual campo ele preencheu indevidamente. Para isso precisamos instalar a biblioteca `@hookform/error-message` 

```javascript
npm install @hookform/error-message
```

E modificamos assim o cód:

```javascript
import React from "react";
import { useForm } from "react-hook-form";
import { ErrorMessage } from "@hookform/error-message";

export default function App() {
  const { register, handleSubmit, errors } = useForm();
  const onSubmit = (data) => console.log(data);

  return (
    <div>
      <form onSubmit = { handleSubmit(onSubmit) } >
        <input name="primeiro_nome"
          ref = {
            register({
              required: "O campo precisa ter no máximo 20 caracteres.",
              maxLength: 20
            })
          }
        />

        <input name="ultimo_nome"
          ref = {
            register({
              required: "O campo precisa ter no máximo 20 caracteres.",
              maxLength: 20
            })
        }
        />

        <input name="idade" type="number"
          ref = { register({
            min: 18, max: 99,
            required: "A idade deve ser entre 18 e 99 ",
          })}
        />
        <input type="submit" />
      </form>
    </div>
  )
}
```

Para cada componente ErrorMessage passamos dois parâmetros: errors que vai receber a mensagem de erro representada pela variável errors (extraída de useForm) e name que é o mesmo do input ao qual queremos exibir a mensagem caso a validação não seja bem sucedida.
