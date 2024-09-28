![Ícone de Git](https://img.icons8.com/?size=100&id=20906&format=png&color=000000)

# Diferentes visualizações com git log

- **Alterando a Visualização do log**
    
    Imagine que desejamos apenas **visualizar as mensagens dos *commits***, de forma simplificada. Não estamos interessados em quem foi o autor do `commit` , em qual *branch* ele está, ou outros detalhes. Não desejamos verificar o *hash* completo do `commit` , apenas uma lista das mensagens, de forma mais compacta, linha por linha.
    
    No terminal, digitaremos `git log`, mas com a *flag* `--oneline`
    
    ```powershell
    git log --oneline
    ```
    
    Com `git log --oneline`, teremos nosso histórico de *commits* exibido com os *hashes* reduzidos, mostrando apenas os primeiros caracteres do *hash*. Isso já é suficiente para identificarmos algum *commit*.
    
- **Visualizando a Alteração do *commit***
    
    O comando é utilizado para exibir o histórico de commits com as diferenças completas de cada commit.
    
    ```powershell
    git log -p
    ```
    
    Essa opção `-p` vai nos fornecer, além das informações padrão, o hash completo, o autor ou autora, a data e a mensagem do *commit*. Além disso, ele mostrará um `diff`, que é essencialmente um formato que o *git* utiliza para exibir as **alterações** de um *commit* específico.
    
- **Outras Formas de Exibição do *log***
    
    E várias outras opções também, como o `git log --graph`, que exibirá um gráfico do nosso *log*, e isso será ainda mais útil quando falamos um pouco sobre *branches*.
  ```powershell
  git log --graph
  ```
    Mas, essencialmente, se percorre isso até a parte em que temos um `merge`, que ele representa graficamente uma linha do tempo se desviando para outro ponto e depois retornando à nossa linha principal.
    
    Há ainda uma opção interessante, que é o `--pretty` ou `--format`.
    
    ```powershell
    git log --pretty=oneline
    ```
    
  O `--pretty` permite que você escolha um dos formatos predefinidos para exibir os logs de commit. Alguns dos formatos disponíveis são:
    - **oneline**: Mostra cada commit em uma única linha.
    - **short**: Exibe o hash do commit, o autor e a mensagem do commit.
    - **medium**: Inclui o hash do commit, o autor, a data e a mensagem do commit.
    - **full**: Adiciona informações completas do autor e do committer.
    - **fuller**: Inclui datas completas do autor e do committer.
    - **reference**: Formato usado para referenciar outro commit em uma mensagem de commit¹.
      
    ```powershell
    git log --format="%ae"
    ```
  O `--format` oferece ainda mais flexibilidade, permitindo que você crie seu próprio formato de saída usando placeholders. Por exemplo:
    - `%H`: Hash completo do commit.
    - `%h`: Hash abreviado do commit.
    - `%an`: Nome do autor.
    - `%ae`: Email do autor.
    - `%ad`: Data do autor (formato pode ser personalizado com `--date`).
    - `%s`: Mensagem do commit².
