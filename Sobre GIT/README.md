# Conhecimentos GIT :eight_pointed_black_star:
<img src="https://img.shields.io/badge/status-em construção-yellow">

Git é um sistema de controle de versão distribuído de código aberto. É muito leve e funciona em quase todos os sistemas operacionais.

Em 2005, Linus Torvalds criou o git como um sistema de controle de versão distribuído quando a equipe de desenvolvimento do kernel do Linux não podia mais usar o BitKeeper gratuitamente.

Agora, o git é o sistema de controle de versão de fato usado por desenvolvedores em todo o mundo. Sua natureza distribuída facilita o desenvolvimento, o rastreamento e a colaboração com alterações de código.

Plataformas como **GitHub ou Bitbucket** são construídas sobre o git com funcionalidades adicionais que ajudam engenheiros e organizações a hospedar e controlar a versão do código no repositório Git remoto. 

Relembrando... Alguns comando do Prompt úteis:

- **DIR**: – Listando arquivos e pastas
- **COPY**: – Copiar arquivos
- **MOVE**: Mover arquivos ou renomear pastas
- **MD**:– Criar uma Nova pasta
- **CD**: Entrar em uma pasta
- **CD ..** : Volta ao repositório base
- **.:**Retornar para a pasta anterior
- **RD**: Remover pastas
- **ERASE**: Deletar arquivos
- **DEL**: Deletar arquivos
- **CLS**: Limpa a tela
- Tecla TAB: auto-completa as palavras
- ...

### Entendendo a estrutura

**SHA1:** A sigla "SHA'' significa secure hash algorithm (algoritmo de hash seguro), esse sistema foi criado por nada mais nada menos que a NSA (Agência nacional dos EUA). Para que eu consiga passar da forma mais simples possível (pelo menos nesse início), o SHA1 embaralha determinado arquivo, imagem ou texto para que seja gerado um conjunto de caracteres identificadores, caracteres esses que possuem 40 dígitos. Esses quarenta dígitos são sempre únicos. Se você pegar um texto enorme e passar ele por esse algoritmo, ele vai gerar esse conjunto de caracteres, se você alterar uma vírgula que seja desse texto, já será gerado outro conjunto. É assim que funciona a cada commit gerado.

*Tipos de Objetos Internos do GIT:*

**Blobs**: Um blob (binary large object) do Git é o tipo de objeto usado para armazenar o conteúdo de cada arquivo em um repositório. O hash SHA-1 do arquivo é calculado e armazenado no objeto do blob. 

Blob é um termo comumente usado em computação para se referir a alguma variável ou arquivo que pode conter qualquer dado e cuja estrutura interna é ignorada pelo programa.

**Tree**: Uma Tree do Git cria a hierarquia entre arquivos em um repositório do Git. Você pode usar o objeto de Tree do Git para criar a relação entre diretórios e os arquivos que eles contêm.

Ele registra identificadores de blob, nomes de caminho e um pouco de metadados para todos os arquivos em um diretório. 

**Commit**: Contém metadados para cada mudança introduzida no repositório, incluindo o autor, committer, data de commit e mensagem de log. Cada commit aponta para um objeto de Tree que captura, em um snapshot completo, o estado do repositório no momento em que o commit foi executado. O commit inicial, ou *root commit* , não tem pai.

**Tag**: A tag atribui um nome arbitrário, mas presumivelmente legível por humanos, a um objeto específico, geralmente um commit. Embora `9da581d910c9c4ac93557ca4859e767f5caf5169` se refira a um commit exato e bem definido, um nome de tag mais familiar como `Ver-1.0-Alpha` pode fazer mais sentido pra nós!

![Versão simples do modelo de dados do Git.](https://git-scm.com/book/en/v2/images/data-model-1.png)

### Chave SSH e Token

SSH é um protocolo que pode se conectar a servidores e serviços remotos e se autenticar neles.
