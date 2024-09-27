![Ícone de Git](https://img.icons8.com/?size=100&id=20906&format=png&color=000000)

# Diferentes modos do git reset

- **--soft**
    
    Este comando move a cabeça do branch para o commit especificado, mas deixa o índice e a área de trabalho intactos. Isso significa que as suas alterações permanecerão na área de trabalho como mudanças não consolidadas.
    
    Não toca no arquivo de índice ou na árvore de trabalho (mas redefine o cabeçalho para `<commit>`, assim como todos os modos fazem). Isso deixa todos os seus arquivos alterados como "Changes to be committe" (Alterações onde serão realizados os commits), como o `git status` colocaria.
    
- **--mixed**
    
    Este comando move a cabeça do branch para o commit especificado e atualiza o índice, mas deixa a área de trabalho intacta (ou seja, os arquivos alterados são preservados, mas não marcados para um commit). Isso significa que as suas alterações permanecerão na área de trabalho como mudanças não consolidadas. Caso `-N` seja especificado, os caminhos removidos serão marcados como uma intenção de adicionar.
    
- **--hard**
    
    Este comando move a cabeça do branch para o commit especificado e atualiza tanto o índice quanto a área de trabalho para corresponder ao estado do commit especificado. Quaisquer alterações nos arquivos rastreados na árvore de trabalho desde `<commit>` serão descartados. Isso significa que todas as suas alterações serão descartadas e o seu repositório será exatamente igual ao estado do commit especificado.
    
- **--merge**
    
    Redefine o índice e atualiza os arquivos na árvore de trabalho que sejam diferentes entre o `<commit>` e o `HEAD`, mas mantém aqueles que são diferentes entre o índice e a árvore de trabalho (ou seja, que têm alterações que não foram adicionadas). Caso haja um arquivo diferente entre `<commit>` e o índice tiver alterações sem etapas, a redefinição será abortada.
    Em outras palavras, `--merge` faz algo como um `git read-tree -u -m <commit>`, mas carrega as entradas do índice não mescladas adiante.
    
- **--keep**
    
    Redefine as entradas do índice e atualiza os arquivos na árvore de trabalho que sejam diferentes entre `<commit>` e `HEAD`. Caso haja uma diferença entre `<commit>` e `HEAD`, assim como houver alterações locais, a redefinição será abortada.
    
- **--recurse-submodules**
    
    Quando a árvore de trabalho é atualizada, utilizando a opção `--recurse-submodules` também redefinirá recursivamente a árvore de trabalho de todos os submódulos ativos de acordo com o commit registrado no superprojeto, também configurando o `HEAD` do submódulo a ser desanexado neste commit.