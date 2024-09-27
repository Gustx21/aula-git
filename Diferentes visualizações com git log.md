# Diferentes visualizações com git log

- **Alterando a Visualização do log**
    
    Imagine que desejamos apenas **visualizar as mensagens dos *commits***, de forma simplificada. Não estamos interessados em quem foi o autor do `commit`, em qual *branch* ele está, ou outros detalhes. Não desejamos verificar o *hash* completo do `commit`, apenas uma lista das mensagens, de forma mais compacta, linha por linha.
    
    No terminal, digitaremos `git log`, mas com a *flag* `--oneline`
    
    ```powershell
    git log --oneline
    ```
    
    Com `git log --oneline`, teremos nosso histórico de *commits* exibido com os *hashes* reduzidos, mostrando apenas os primeiros caracteres do *hash*. Isso já é suficiente para identificarmos algum *commit*.
    
- **Visualizando a Alteração do *commit***
    
    No entanto, o oposto pode ocorrer. Estamos interessados em examinar o commit e suas alterações, não apenas sua mensagem, mas também seu conteúdo. Portanto, ao retornar ao terminal, limpamos a tela e digitamos o comando `git log -p`.
    
    ```powershell
    git log -p
    ```
    
    Essa opção `-p` vai nos fornecer, além das informações padrão, o hash completo, o autor ou autora, a data e a mensagem do *commit*.
    
    Além disso, ele mostrará um `diff`, que é essencialmente um formato que o *git* utiliza para exibir as **alterações** de um *commit* específico.
    
- **Outras Formas de Exibição do *log***
    
    E várias outras opções também, como o `git log --graph`, que exibirá uma linha do nosso *log*, e isso será ainda mais útil quando falarmos um pouco sobre *branches*.
    
    Mas, essencialmente, se percorro isso até a parte em que temos um `merge`, que ele representa graficamente uma linha do tempo se desviando para outro ponto e depois retornando à nossa linha principal.
    
    Há ainda uma opção interessante, que é o `--pretty` ou `--format`. Ambos são sinônimos.
    
    ```powershell
    git log --pretty
    git log --format
    ```
    
    Com `--format` ou `--pretty`, podemos exibir o *commit* da maneira que desejar. Por exemplo, utilizarmos `--format=""` e dentro das aspas digitar `%H %an`.
    
    ```powershell
    git log --format="%H %an"
    ```