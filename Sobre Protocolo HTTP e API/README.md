# Protocolo HTTP e API :dromedary_camel:
<img src="https://img.shields.io/badge/status-em construção-yellow">

### Índice

- [O que é HTTP?](#o-que-é-http?)
- [O que é um método HTTP?](#o-que-é-um-método-http?)
- [Request headers](#request-headers)
- [Request body](#request-body)
- [Status Code](#status-code)
- [Response Headers](#response-headers)
- [Response Body](#response-body)
- [Estrutura URL](#estrutura-url)

#### O que é HTTP?

Hypertext Transfer Protocol (**HTTP**) é o Transmission Control Protocol/Internet Protocol (TCP/IP) protocolo que padroniza como o cliente e o servidor se comunicam entre si. O HTTP segue um "modelo **cliente-servidor**" clássico com um cliente abrindo uma solicitação de conexão e aguardando até receber uma resposta. O HTTP é um protocolo sem estado, o que significa que o servidor não mantém nenhum dado (estado) entre duas requisições.

![A Web document is the composition of different resources](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview/fetching_a_page.png)



Clientes e servidores se comunicam trocando mensagens individuais (ao contrário de um fluxo de dados). As mensagens enviadas pelo cliente, geralmente um navegador da Web, são chamadas de **solicitações** *(requests)*, ou também **requisições**, e as mensagens enviadas pelo servidor como resposta são chamadas de **respostas** *(responses)*.

![HTTP as an application layer protocol, on top of TCP (transport layer) and IP (network layer) and below the presentation layer.](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview/http-layers.png)

O HTTP é um protocolo cliente-servidor: as requisições são enviados por uma entidade, o agente-usuário (ou um *proxy* em nome dele). A maior parte do tempo, o agente-usuário é um navegador da Web, mas pode ser qualquer coisa, como por exemplo um robô que varre a Web para preencher e manter um índice de mecanismo de pesquisa e coletar informações.

Cada requisição individual é enviada para um servidor, que irá lidar com isso e fornecer um resultado, chamado de *resposta*. Entre a solicitação e a resposta existem várias entidades, designadas coletivamente como [proxies](https://developer.mozilla.org/pt-BR/docs/Glossary/Proxy_server), que executam operações diferentes e atuam como *gateways* (intermediários) ou [caches](https://developer.mozilla.org/pt-BR/docs/Glossary/Cache), por exemplo.

![Client server chain](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview/client-server-chain.png)

Na realidade, existem muitos outros computadores entre o navegador e o servidor que está tratando a requisição: existem roteadores, modems e muito mais. Graças ao modelo de camadas da Web, essas funcionalidades estão escondidas nas camadas de rede e transporte, respectivamente. O HTTP está no topo da camada de aplicação. Apesar de ser importante diagnosticar problemas de conectividade, as camadas subjacentes são irrelevantes para a descrição do HTTP.

##### Proxies

Entre o navegador Web e o servidor, vários computadores e máquinas transmitem as mensagens HTTP. Devido a estrutura em camadas da pilha Web, a maioria dessas máquinas operam em alguma das camadas: de transporte, de rede ou física, sendo transparente na camada da aplicação HTTP, e potencialmente exercendo um grande impacto na performance. Essas máquinas que operam na camada de aplicação são normalmente conhecidas como ***proxies* **(ou representantes, ou procuradores, etc). Eles podem ser transparentes ou não (alterações nas requisições não passam por eles), e podem desempenhar várias funções:

- cacheamento (o *cache* pode ser público ou privado, como o *cache* dos navegadores)
- filtragem (como um *scanner* de antivírus, controle de acesso, etc)
- balanceamento de carga (para permitir que vários servidores possam responder a diferentes requisições)
- autenticação (para controlar quem tem acesso aos recursos)
- autorização (para controlar quem tem acesso a determinada informação)
- registro de informação (permite o armazenamento de informações de histórico)



#### O que é um método HTTP?

Um método HTTP, às vezes chamado de verbo HTTP, indica a ação que a solicitação HTTP espera do servidor consultado. Por exemplo, dois dos métodos HTTP mais comuns são 'GET' e 'POST'; um pedido 'GET' espera informações de volta (geralmente na forma de um site), enquanto um pedido 'POST' normalmente indica que o cliente está enviando informações para o servidor web (como informações de formulário, por exemplo, um nome de usuário e senha enviados ).

URL: ${IP}/${Path = caminho de identificação dos recursos}

![A basic HTTP request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview/http_request.png)

#### Request headers

Os cabeçalhos HTTP contêm informações de texto armazenadas em pares chave-valor e são incluídos em todas as solicitações HTTP. Esses cabeçalhos comunicam informações essenciais, como qual navegador o cliente está usando e quais dados estão sendo solicitados.

Exemplo de cabeçalhos de solicitação HTTP do Google Chrome's network tab:

![HTTP request headers](https://www.cloudflare.com/img/learning/ddos/glossary/hypertext-transfer-protocol-http/http-request-headers.png)

#### Request body

O Request Body, ou corpo da requisição, **é onde geralmente enviamos dados que queremos gravar no servidor**. Não é muito utilizado em requisições do tipo GET, mas sim nas do tipo POST e PUT. É no corpo da requisição onde você envia dados de um formulário de cadastro em seu site, por exemplo.

#### Status Code

Status-code **são os três dígitos que indicam qual o erro para o servidor e navegador** enquanto a frase razão é uma curta descrição do que este erro significa para melhor compreensão dos usuários.

As respostas são agrupadas em cinco classes:

- Respostas de informação ( 100 - 199 ),
- Respostas de sucesso ( 200 - 299 ),
- Redirecionamentos ( 300 - 399 )
- Erros do cliente ( 400 - 499 )
- Erros do servidor ( 500 - 599 ).

#### Response Headers 

É um [cabeçalho HTTP](https://developer.mozilla.org/en-US/docs/Glossary/HTTP_header) que pode ser usado em uma resposta HTTP e que não está relacionado ao conteúdo da mensagem. Cabeçalhos de resposta, como [`Age`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Age), [`Location`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Location)ou [`Server`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Server)são usados para fornecer um contexto mais detalhado da resposta.

#### Response Body

A Response (resposta) nada mais é do que a resposta que o servidor envia ao cliente. Essa resposta pode conter os dados que realmente o cliente esperava receber ou uma resposta informando que alguma coisa deu errado.

#### Estrutura URL

##### Path Params e QueryString

Path é usado para corresponder uma parte da URL como um parâmetro. Por exemplo, em uma URL no formato http://example.com/tables/{id}

Já Query é usado para acessar pares de chave / valor na sequência de consulta da URL (a parte após o "**?**" ): http://example.com/cadastro?tipo=PF

Existe uma diferença sutil entre `Path params` e `params Query` pode-se traduzir para `Parâmetros do caminho da Url` e `Parâmetros de Consulta`

Ambas fazem a mesma coisa porém de formas diferentes.

**Parâmetros da URL**

- Deixa a url amigável (SEO, usuário, etc)

- Em teoria, é algo importante na url, algo de valor

- Caso o parâmetro passado seja invalido pode ocorrer 404

  ex: `GET parentes/avo/detalhes`

**Parâmetros de Query (Ou Querystring)**

- Urls menos amigáveis para SEO (difícil entendimento do usuário)
- Em teoria é algo supérfluo para execução da url, como filtros, ordenações, etc.
- Não causa 404, caso o parametro seja inválido
- ex: `GET parentes/detalhes?tipo=avo`

O padrão para parâmetros para querystring é:

```
| Tipo    | Descrição                                         |
|---------|---------------------------------------------------|
| ?       | antes do primeiro valor                           |
| {param} | Nome do parâmetro                                 |
| =       | separação do parâmetro e valor com sinal de igual |
| {value} | valor do parâmetro                                |
| &       | para separar demais parâmetros                    |
```

ex: `url/pagina?parametro1=valor&parametro2=valor`
