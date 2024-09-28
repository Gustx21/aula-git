![Ícone de Git](https://img.icons8.com/?size=100&id=20906&format=png&color=000000)

# Git

O Git é um sistema de controle de versão distribuído, usado principalmente para rastrear alterações no código fonte durante o desenvolvimento de software. Foi criado por Linus Torvalds em 2005. O Git rastreia as alterações feitas no código, permitindo que os desenvolvedores voltem para versões anteriores do seu projeto, que é essencial para encontrar o momento em que bugs foram introduzidos.

Já o GitHub é uma plataforma de hospedagem de código-fonte e desenvolvimento de software que usa o Git. Ele permite que os desenvolvedores trabalhem juntos em projetos, independentemente de onde estejam localizados, fornecendo ferramentas para gerenciar e acompanhar o trabalho em um projeto de software.

## Comandos Principais do Git

- git **init**
    
    Este comando é usado para iniciar um novo repositório local do Git.
    Exemplo: `git init`
    
- git **add**
    
    Este comando adiciona as mudanças ao repositório.
    Exemplo: `git add nome_do_arquivo`
    
- git **status**
    
    Este comando verifica quais arquivo foram modificados, adicionados ou removidos.
    Exemplo: ``git status``
    
- git **commit**
    
    Este comando registra as alterações feitas no repositório.
    Exemplo: `git commit -m "mensagem do commit"`
    
- git **push**
    
    Este comando envia as alterações para um repositório remoto.
    Exemplo: `git push origin master`
    
- git **pull**
    
    Este comando busca e integra alterações de um repositório remoto.
    Exemplo: `git pull origin master`
    

# Inicializando o Diretório

O comando `git init` deve ser utilizado para converter um diretório existente no computador, que geralmente é o diretório de algum projeto, em um repositório Git. No entanto, seu uso requer atenção e cuidado para evitar problemas indesejados. O comando é utilizado, devendo ser executado apenas **uma vez**. Quando executado, ele configura o diretório atual para ser rastreado pelo Git, inicializando um repositório vazio.

## Executando o Comando git init

Suponha que no seu computador exista um diretório chamado **meu-projeto**, que represente um projeto pessoal seu e que você deseja transformar em um repositório do Git. Para isso, você pode abrir esse diretório no VSCode, abrir uma janela do terminal e executar o comando `git init`. A saída será algo como:

![Terminal exemplificando a resposta de criação do repositório](https://cdn1.gnarususercontent.com.br/1/4341/ea145a08-0114-4a5f-bb96-537fff10d7b5.png)

Repare na imagem anterior que o comando `git init` foi executado no terminal do VSCode. Observe também que no terminal é indicado qual o diretório no qual o comando foi executado, que no exemplo foi em: **~/Projetos/alura/meu-projeto**. É importante se atentar a isso, pois o comando `git init` transforma o diretório atual em um repositório do Git, logo ele deve ser executado **dentro** do diretório do projeto e não em outros diretórios do computador.

Ao executar o comando, note que a saída no terminal foi a mensagem **Initialized empty Git repository in /home/rodrigo/Projetos/alura/meu-projeto/.git/**. Essa mensagem indica que o comando foi executado corretamente e um repositório local do Git foi criado com sucesso nesse diretório. A partir desse ponto, já podemos trabalhar no projeto, adicionando arquivos, realizando modificações e registrando as mudanças no Git.


>### :warning:
>
> Aprendemos que o comando *`git init`* serve para criar um novo repositório Git e por isso deve ser executado apenas uma única vez. Ou seja, se um diretório já for um repositório Git, não faz sentido rodar novamente o comando ***git init***. Esse é um erro bastante comum de ser cometido.
>
> Se você executar o comando *`git init`* em um diretório que já foi inicializado como um repositório Git, a seguinte mensagem será exibida:
>
>```powershell
>
>Reinitialized existing Git repository in /home/rodrigo/Projetos/alura/meu-projeto/.git/
>
>```
>
> Isso indica que o Git **reinicializou** um repositório já existente, ou seja, o comando *`git init`* foi executado em um diretório que já era um repositório Git.
>
> Caso você tenha cometido esse equívoco, não precisa se preocupar, pois todo o histórico de mudanças e commits no projeto não será apagado. O Git detecta que o diretório já era um repositório Git e com isso o comando não tem efeito nenhum.
>
> Na dúvida, antes de executar o comando *`git init`*, execute primeiramente o comando ***git status***. Se aparecer a mensagem:
>```powershell
>
>fatal: not a git repository (or any of the parent directories): .git
>
>```
> isso significa que o diretório atual **não é** um repositório Git e você pode então executar o comando ***git init***.

# Configurando o Git
Para configurar Git na sua máquina com nome de usuário e e-mail, você usará os seguintes comandos:

1. **Defina seu nome de usuário**:
   ```bash
   git config --global user.name "Seu Nome"
   ```

2. **Defina seu e-mail**:
   ```bash
   git config --global user.email "seuemail@example.com"
   ```

Esses comandos vão configurar seu nome e e-mail para todos os repositórios no seu sistema. Se quiser configurar para um repositório específico, remova a opção `--global`.

3. **Para verificar suas configurações**:
   ```bash
   git config --global --list
   ```

# Repositório Remoto

Esse comando tem algumas variações e parâmetros opcionais que podem ser úteis em certas situações. Confira a seguir exemplos de uso desse comando:

:link: [Chave SSH](./Chave-SSH.md)

1.  Adicionar um repositório remoto:
    
    Quando você deseja estabelecer uma conexão entre seu repositório local e um repositório remoto, como aquele hospedado no GitHub, o comando `git remote add` é a ferramenta essencial. Essa etapa é crucial para possibilitar a colaboração e o compartilhamento de código com outras pessoas, bem como para fazer backup de seu trabalho em um servidor remoto.
    
    A sintaxe básica do comando é a seguinte:
    
    ```powershell

    git remote add apelido url

    ```
    
    ***'apelido'***: Este é um nome que você atribui ao repositório remoto. Geralmente, se utiliza nomes descritivos, como "origin" para o repositório principal no GitHub, mas você pode escolher nomes que façam sentido para o seu projeto.
    
    ***'url'***: Aqui, você insere a URL do repositório remoto. Esta URL é única para cada repositório remoto e serve como o endereço para acessar e interagir com ele pela internet. Certifique-se de copiar a URL correta do repositório que deseja adicionar.
    
2. Listar os repositórios remotos:
    
    Para listar os repositórios remotos associados ao seu projeto local, você pode utilizar o comando `git remote -v`. Isso exibirá uma lista de todos os repositórios remotos vinculados ao seu projeto, juntamente com suas URLs. Veja um exemplo:
    
    ```powershell

    git remote -v

    ```
    
    A saída será algo semelhante a:
    
    ```powershell

    origin   https://github.com/seu-usuario/seu-projeto.git (fetch)
    origin   https://github.com/seu-usuario/seu-projeto.git (push)

    ```
    
    Essa lista é útil para verificar se os repositórios remotos estão configurados corretamente. Obs: Vai aparecer duplicado mesmo, pois o Git separa a url de envio de commits (push) da url de baixar commits (fetch).
    
3. Remover um repositório remoto:
    
    Caso você não precise mais de um repositório remoto específico, pode removê-lo com o comando `git remote remove <apelido>`. Substitua 'apelido' pelo nome do repositório remoto que deseja remover. Aqui está um exemplo:
    
    ```powershell

    git remote remove origin

    ```
    
    Após a execução deste comando, o repositório remoto chamado "origin" será desvinculado do seu projeto local.
    
4. Alterar a URL de um repositório remoto:
    
    Às vezes, é necessário atualizar a URL de um repositório remoto, como quando a URL do servidor do GitHub é modificada ou quando você copiou a URL incorreta ao adicionar o repositório remoto. Use o comando `git remote set-url <apelido> <nova_url>` para realizar essa atualização. Substitua ***'apelido'*** pelo nome do repositório remoto e ***'nova_url'*** pela nova URL que você deseja associar a ele. Aqui está um exemplo:
    
    ```powershell

    git remote set-url origin https://github.com/seu-usuario/seu-repositorio.git

    ```
    
    Isso atualizará a URL do repositório remoto "origin" para a nova URL especificada.
    
5. Alterar o apelido de um repositório remoto:
    
    Se você deseja renomear um repositório remoto, use o comando `git remote rename <apelido-atual> <novo_apelido>`. Substitua ***'apelido-atual'*** pelo nome atual do repositório remoto e ***'novo_apelido'*** pelo novo nome que você deseja atribuir a ele. Aqui está um exemplo:
    
    ```powershell

    git remote rename origin novo-origin
    
    ```
    
    Isso renomeará o repositório remoto de "origin" para "novo-origin".
    
    > Lembre-se de que o comando git remote é fundamental para a gestão de conexões entre seu repositório local e repositórios remotos, permitindo a colaboração eficiente e o controle de versão. Praticar esses comandos em seu ambiente de desenvolvimento ajudará a consolidar seu trabalho.
    > 

# Clonando Repositório

O comando `git clone` é utilizado para criar uma cópia local de um repositório que está hospedado remotamente. Este comando é muito útil quando você quer trabalhar em um projeto que já foi iniciado e está disponível em um repositório remoto, como o GitHub.

A sintaxe básica para clonar um repositório é:

```powershell

git clone https://github.com/rodrigoalura87/numero-secreto.git

```

Ao executar este comando, o Git criará uma nova pasta no seu diretório atual com o mesmo nome do repositório remoto. Dentro desta pasta, você encontrará uma cópia do código do projeto, bem como o histórico completo de commits do repositório.

Lembre-se que, ao clonar um repositório, você também está criando uma conexão entre o repositório local e o repositório remoto. Isso significa que você pode puxar atualizações do repositório remoto para o seu repositório local (com o comando `git pull`), ou enviar suas alterações locais para o repositório remoto (com o comando `git push`).

# Salvando Alterações

O `git commit` é um comando que é usado para salvar suas alterações no repositório local. Ele basicamente tira uma "cópia" do seu código no momento atual e salva um ponto de referência que você pode reverter para mais tarde, se necessário.

Um **commit** deve ser realizado sempre que você **finalizar uma tarefa** específica ou **resolver algum bug**. Isso mantém o histórico de commits claro e rastreável, de modo que seja possível entender o que foi feito em cada commit.

Assim, é importante realizar commits frequentemente. Porém, evite realizar commits muito pequenos ou muito grandes, pois isso pode tornar difícil o seu entendimento.

Lembre-se de **nunca realizar um commit de um código que você sabe que contém bugs**. O ideal é que o commit contenha somente código funcional.

Para fazer um commit, você pode usar o seguinte comando:

```powershell

git commit -m "Sua mensagem de commit"

```

A mensagem de commit ajuda a documentar as alterações que você fez para você ou outras pessoas que possam estar trabalhando no mesmo projeto.

## Alterando commit

Em certos momentos fazemos alterações onde cometemos alguns pequenos erros de digitação da mensagem do commit e para resolver esse tipo de problema do dia a dia, usamos o:

```powershell

git commit --amend -m <mensagem>

```

O comando indica ao Git que não queremos fazer um novo commit, mas alterar o anterior. Então é só passar o ***-m***, com o texto da mensagem correta.

>⚠️
>
>É importante destacar que os comandos do Git que permitem modificar o histórico de commits devem ser utilizados com **prudência** e apenas quando o commit em questão ainda **não foi enviado ao repositório remoto**, ou seja, quando ele existe apenas no seu repositório local.
>
>Modificar um commit que já se tornou público, ou seja, aquele que já foi enviado ao GitHub ou a qualquer outro repositório remoto, pode acarretar problemas consideráveis na colaboração com as outras pessoas e na integridade do histórico de um projeto.
>
>Em situações de colaboração em equipe, é essencial manter a integridade do histórico de commits, pois qualquer modificação em um commit que outras pessoas estejam trabalhando pode resultar em conflitos e dificuldades na colaboração.
>
>É recomendável evitar a modificação excessiva do histórico de commits, uma vez que isso pode tornar o histórico confuso. O histórico deve ser uma representação precisa do progresso do projeto ao longo do tempo.


:link: [Commits semânticos](./Commits%20Semâticos.md)

## Exibindo Alterações

1. **Git Log**

    O `git log` é um comando que mostra um histórico de *commits* para o repositório atual. Para cada commit, ele mostra o autor do commit, a data e hora do commit e a mensagem do commit.
    
    Para ver o log, você pode usar o seguinte comando:
    
    ```powershell

    git log

    ```
    
    Você verá uma lista de commits em ordem reversa (o commit mais recente aparece primeiro).
    
    :link: [Diferentes visualizações com git log](./Diferentes%20visualizações%20com%20git%20log.md)
    
2. **Git Diff**
    
    O `git diff` é um comando que mostra as diferenças entre commits, commit e árvore de trabalho, etc. Ele pode ser usado para ver o que mudou entre duas versões do seu código.
    
    Para ver as diferenças entre o seu código atual e o último commit, você pode usar o seguinte comando:
    
    ```powershell

    git diff

    ```
    
    Isso mostrará as linhas de código que foram adicionadas (marcadas com um `+`) e as linhas que foram removidas (marcadas com um `-`).
    
    Para analisar a diferença entre esses dois *commits* específicos, precisamos incluir os três *commits* em nossa análise. Podemos fazer isso utilizando o comando `git diff`.
    
    Primeiro, copiamos o *hash* do *commit* mais antigo que desejamos comparar. Em seguida, copiamos o *hash* do *commit* mais recente que queremos comparar.
    
    ```powershell

    git diff 5880fc1 5bc160e

    ```
    
3. **Git Status**
    
    O comando `git status` é uma ferramenta essencial para gerenciar alterações no controle de versão Git. Ele fornece uma visão geral do estado atual do repositório, indicando quais arquivos foram modificados, adicionados ou excluídos desde o último commit. Essa informação é crucial para compreender o progresso do desenvolvimento e tomar decisões de gerenciamento de alterações.
    
    ```powershell

    git status

    ```
    
    A saída do comando `git status` geralmente contém três seções principais:
    
    - **Modificados:** Lista os arquivos que foram modificados desde o último commit, mas ainda não foram adicionados à área de preparação (Stage).
    - **Adicionados:** Indica os arquivos que foram adicionados à área de preparação, mas ainda não foram confirmados no histórico de commits.
    - **Modificados, adicionados ou excluídos:** Exibe os arquivos que não foram rastreados pelo Git, ou seja, que não foram adicionados ao índice de modificações (Staging Area).
    
    Além disso, o comando git status pode fornecer informações adicionais sobre as ramificações atuais, como a ramificação atual e as ramificações que estão à frente ou atrás da atual.
    
4. **Analisando um `commit` específico**
    
    Desejamos compreender as alterações realizadas neste *commit* específico, independentemente de quem o tenha feito. Solicitaremos ao *Git* que nos apresente o conteúdo e os detalhes desse *commit*.
    
    Para isso, copiaremos o *hash* correspondente e digitaremos `git show`, seguido do respectivo *hash*: `git show {hash do commit}`
    
    ```powershell

    git show 2ad48c0

    ```

> :pushpin: Quando estamos trabalhando em um projeto utilizando o versionamento Git e a IDE VSCode, ao adicionar ou alterar algum arquivo aparece uma sinalização ao lado do nome desses arquivos no VSCode. Essa sinalização nos ajuda a entender o estado atual dos nossos arquivos do projeto no versionamento Git:
>
> - **M**: A letra M representa o estado *Modified*, do português modificado. Isso significa que o arquivo já existia no repositório, mas que recebeu alguma modificação que ainda não foi registrada no Git.
> - **U**: A letra U representa o estado *Untracked*, do português não rastreado. Isso significa que o arquivo ainda não existia no repositório e que ainda não teve seu registro (commit) feito no Git.
>

## Enviando e Puxando Alterações

1. **Git Push**
    
    O comando `git push` é usado para enviar as alterações locais para o repositório remoto. Este comando é fundamental para compartilhar o progresso do código com outros colaboradores e para fazer backup do trabalho local no servidor remoto. O comando `git push` é normalmente seguido pelo nome do repositório remoto (geralmente `origin`) e pelo nome do branch que você deseja atualizar.
    
    Exemplo de uso:
    
    ```powershell

    git push origin master

    ```
    
    Neste exemplo, `origin` é o repositório remoto e `master` é o branch para o qual você está enviando suas alterações.
    
2. **Git Pull**
    
    O comando `git pull` é usado para buscar as alterações do repositório remoto e mesclar essas alterações no branch local. Este comando é essencial para manter o código local atualizado com o repositório remoto, permitindo que você veja o trabalho mais recente dos outros colaboradores.
    
    Exemplo de uso:
    
    ```powershell

    git pull origin master

    ```
    
    Neste exemplo, `origin` é o repositório remoto e `master` é o branch do qual você está recebendo as alterações.
    

# Desfazendo Modificações

1. **Git Revert**
    
    O comando `git revert [<commit>]` é utilizado para desfazer as alterações de um commit específico. Este comando cria um novo commit que desfaz as alterações feitas no commit que está sendo revertido. O commit original e o novo commit revertido coexistem no histórico do projeto.
    
    Exemplo de uso:
    
    ```powershell

    git revert <commit_id>

    ```
    
    Neste exemplo, `<commit_id>` é o identificador único do commit que você deseja reverter. Você pode obter o `commit_id` usando o comando `git log`.
    
2. **Git Reset**
    
    O comando **`*git reset [<modo>] [<commit>]`** move a referência do branch atual para um commit específico, podendo alterar o estado do índice (staging area) e do diretório de trabalho. Melhor para desfazer commits locais que ainda não foram compartilhados com outros. Pode ser usado para remover commits da história. Este comando pode ser usado de três formas diferentes, dependendo do argumento que você passar:
    
    ```powershell

    git reset --hard <commit_id>

    ```
    
    Neste exemplo, `<commit_id>` é o identificador único do commit ao qual você deseja reverter o seu repositório. Você pode obter o `commit_id` usando o comando `git log`.
    
    :link: [Diferentes modos do git reset](./Diferentes%20modos%20do%20git%20reset%20.md)
    

# Ramificação

O comando `git branch` é usado para criar, listar e excluir branches. Um branch é essencialmente um ponteiro para um commit específico. Trabalhar com branches permite que você isole seu trabalho sem afetar o branch principal.

```powershell

git branch nome-do-branch

```

Neste exemplo, `nome-do-branch` é o nome do novo branch que você está criando.

- **git branch**: Lista todos os branches no seu repositório.
- **git branch <nome-do-branch>**: Cria um novo branch com o nome especificado.
- **git branch -d <nome-do-branch>**: Exclui o branch especificado.

# Mesclagem

O comando `git merge` é usado para combinar as alterações de dois branches diferentes. Quando você executa `git merge`, o Git procura o commit mais recente que é comum aos dois branches. Em seguida, ele cria um novo "commit de merge" que inclui as alterações de ambos os branches.

```powershell

git merge nome-do-branch

```

Neste exemplo, `nome-do-branch` é o nome do branch que você deseja mesclar com o branch atual.

- **git merge nome-do-branch**: Mescla o branch especificado com o branch atual.
- **git merge --abort**: Cancela a operação de merge.

# Git Checkout

O comando `git checkout` é usado para alternar entre diferentes branches ou commits específicos. Ao fazer checkout em um branch ou commit, o Git atualiza os arquivos no diretório de trabalho para refletir o conteúdo desse branch ou commit.

```powershell

git checkout nome-do-branch

```

Neste exemplo, `nome-do-branch` é o nome do branch para o qual você deseja alternar.

- **git checkout nome-do-branch**: Alterna para o branch especificado.
- **git checkout -b nome-do-branch**: Cria um novo branch e imediatamente alterna para ele.
- **git checkout commit_id**: Alterna para o commit especificado.

# Git Switch

podemos utilizar também o `git switch`, também seguido do nome da branch desejada. "*Switch*" significa **trocar**, ou seja, esse comando basicamente alterna entre branches.

Porém, se digitarmos simplesmente `git switch nova-funcionalidade`, será informado que essa branch não existe. Então, vamos executar `git switch -c nova-funcionalidade` (`-c` referente a "*create*").

```powershell

git switch -c nova-funcionalidade

```

# Git Rebase

Ao realizar o `rebase`, todos os commits da outra *branch* são adicionados **antes** do primeiro commit da nossa *branch* atual, reescrevendo a história. Isso faz com que novas alterações possam ser integradas à nossa branch e permite que quando formos realizar o `merge`, não seja necessário um *merge commit*, garantindo o *fast forward*.

Para utilizar o `git rebase`, primeiro precisamos mudar para o branch principal. Suponha que temos dois branches, `master` e `feature`. Se mesclar o branch `feature` na `master:
```powershell

git checkout feature
git rebase master

```

Isso fará com que o branch `feature` pareça que foi criado a partir do último commit no branch `master`, mesmo se o branch `feature` foi criado a partir de um commit mais antigo.

- **--continue**
    
    Quando um rebase encontra um erro, ele vai parar e permitir que você corrija o problema. Depois que a correção é feita, você pode usar `git rebase --continue` para continuar o rebase onde parou.
    
- **--abort**
    
    Se você quiser parar completamente o rebase e voltar para o estado em que estava antes de tentar o rebase, você pode usar `git rebase --abort`.
    
- **--skip**
    
    Se um commit específico está causando problemas durante o rebase, você pode usar `git rebase --skip` para ignorar esse commit.
    
- **--interactive ou -i**: Este modo permite que tenha mais controle sobre o processo de rebase. Ele vai abrir um editor onde decide o que fazer com cada commit (mantê-lo, ignorá-lo, combiná-lo com outro, etc.).

Note que o rebase é uma ferramenta poderosa, mas também pode ser perigoso se mal utilizada. É importante entender como ele funciona antes de começar a usá-lo no seu fluxo de trabalho.

# Git Stash

O comando `git stash` é usado quando você quer registrar o estado atual do seu diretório de trabalho e do índice, para voltar a ele mais tarde. Em outras palavras, quando está no meio de algo e precisa mudar de contexto, o `git stash` leva o trabalho sujo e o guarda, permitindo que aplique as mesmas mudanças mais tarde.

- Push
    
    O comando `git stash push -m "<mensagem>"` é utilizado para fazer um stash de suas alterações e dar a ele uma descrição personalizada. Este comando é útil para quando você tem múltiplos stashes e quer ser capaz de distinguir entre eles facilmente.
    
    ```powershell

    git stash push -m "descrição do stash"

    ```
    
- Apply
    
    O comando `git stash apply` espera um índice de um item na *stash* e o aplica ao repositório, porém, esse comando **não remove** o item da *stash*, ou seja, se após executar o comando `git stash apply 1` você executar `git stash list`, o item referente ao índice 1 continuará na *stash*.
    
    ```powershell

    git stash apply

    ```
    
- Pop
    
    O comando `git stash pop` é usado para reaplicar as alterações registradas no último stash criado e ao mesmo tempo remover esse stash da sua lista de stashes. Este comando é útil quando você quer aplicar as alterações que você stashed e não precisa mais dessas alterações no seu stash. Portando, se fizermos um `git stash pop`, ele sempre vai aplicar a última alteração que adicionamos. Portanto, ele sempre pega esse de índice zero. Ele sempre vai empilhando modificações.
    
    ```powershell

    git stash pop

    ```
    
- Clear
    
    O comando `git stash clear` é usado para remover todos os stashes. Este comando é útil quando você quer limpar a sua lista de stashes.
    
    ```powershell

    git stash clear

    ```
    
- **Git Stash Drop**
    
    O comando `git stash drop` é usado quando você deseja descartar uma stash que você salvou anteriormente. Este comando permite que você limpe a sua lista de stashes, removendo as stashes que você não precisa mais.
    
    Neste exemplo, `<nome-da-stash>` é o nome da stash que você deseja descartar. Se nenhum nome de stash for especificado, a stash mais recente será descartada.
    
    ```powershell

    git stash drop <nome-da-stash>

    ```
    
- **List**
    
    O comando `git stash list` é usado para listar todas as stashes que foram salvas. Este comando é útil quando se deseja ver quais stashes estão atualmente disponíveis e recuperar uma stash específica.
    
    ```powershell

    git stash list

    ```
    

# Descartando Alterações

O comando `git restore` vai fazer um `Ctrl + Z` no projeto. Assim, as linhas que foram adicionadas sumirão.

```powershell

git restore .
git restore --staged .

```

- **--staged**
    
    Note que o próprio `git` já nos mostra que podemos fazer um `restore` do que está em nossa "staging area". Se fizermos `git restore --staged`, significa que foi modificado algo que está dentro dessa "staging area".
    
- **--source**
    
    ```powershell

    git restore --source = 5081a55bc92af2917c8519f16a7412b86ba3b1c2 index.html

    ```
    
    E o `git restore` é um dos comandos que veio para substituir o `git checkout`. Uma das coisas que ele fazia é o `restore`. Com          o `git checkout -- .`, temos o mesmo resultado.

# Criando commits com tags

Queremos marcar um ponto no commit `Quebrando a linha do script` e torná-lo um *save point*, indicando que ele representa o lançamento da nossa versão 0.1.0, por exemplo. Ou qualquer outra versão. Portanto, conseguimos nomear pontos específicos do nosso código, e, **no Git, chamamos esse processo de tag**.

Uma tag no Git é criada através do comando `git tag nome_da_tag`, que rodamos no Terminal. Por exemplo, vamos rodar o comando `git tag v0.1.0`. Assim, criamos uma tag na nossa `HEAD`, ou seja, no momento mais recente da branch que tivermos feito o commit. Após criarmos a tag e rodarmos o comando `git log` de novo, recebemos as informações do commit com a nossa tag

```powershell

502afbc6 (HEAD -> main) Removendo quebra de linha
c53eb16c (tag: v0.1.0, origin/nova-funcionalidade, origin/main, origin/HEAD, nova-funcionalidade) Quebrando linha do script
bc493a6c Corrigindo indentação

```

## **Criando tags para commits fora da HEAD**

Se rodarmos simplesmente `git tag v.0.1.1`, ele cria um commit no nosso `HEAD`. Porém, se quisermos, podemos **criar uma tag para algum commit específico**. Criaremos para o último commit: o "Removendo quebra de linha", tem o código `502afb6`.

Com o código que aparece no começo da linha de commit, podemos criar uma tag para qualquer commit no nosso histórico, através da estrutura: `git tag <nome_da_tag> <código_do_commit>`. No caso, executamos o `git tag v0.1.1 502afb6` e, em seguida, ao executarmos o `git log` encontraremos as tags `v0.1.0` e `v0.1.1`.

```powershell

commit 502afbb6235b26346a0efefec0a6b73431bf7d4703 (HEAD -> main, tag: v0.1.1, origin/main, origin/HEAD)
Author: Vinicius Dias <carlosv775@gmail.com>
Date:   Sat Dec 23 15:12:41 2023 -0300

    Removendo quebra de linha

```

Se quisermos, podemos enviar a nossa tag para o nosso repositório remoto, o GitHub, com o comando `git push origin v.0.1.0`, que fará o `push` da tag que passamos o nome. Ou podemos executar `git push origin --tags`, que fará o `push` de todas as tags.

## **Criando uma Annotated tag**

Agora queremos criar uma nova tag com uma informação a mais, por exemplo, uma mensagem. Para isso, podemos usar o comando `git tag -a nome_da_tag -m "mensagem da tag"`, sendo o `-a` de *annotated* (anotação) e o `-m` de *message* (mensagem). Chamaremos a tag de `v0.1.1` e passaremos a mensagem `"Lançamento da versão 0.1.1"`.

```powershell

git tag -a v0.1.1 -m "Lançamento da versão 0.1.1"

```

Ao executarmos esse comando, temos uma tag com tem informações a mais do que apenas um commit. Faremos o *push* dessa tag, com o comando `git push origin v0.1.1` e retornaremos a página de tags do GitHub.

## Para saber mais:
- [Aprenda Git em 30 minutos](https://youtu.be/Zwv9qRyVeU4?feature=shared)
- [O que é Git com Raffaela - Parte 1](https://youtu.be/DqTITcMq68k?feature=shared)
- [Como usar Git na prática com Raffaela - Parte 2](https://youtu.be/UBAX-13g8OM?feature=shared)
- [Aprenda Git do zero](https://youtu.be/pyM5QLS2h6M?feature=shared)

## Crédito
Copyright (C) 2024 by Gustavo André
