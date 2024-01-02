# Repositorio com comandos GIT

Esse repositorio contem comandos utilizados no sistema de controle de versão GIT.

<details><summary><b>Comandos básicos</b></summary>

- **Comandos básicos**
    
    
    Configuração inicial:
    
    ```bash
    ## Configurações globais para seu nome e e-mail.
    git config --global user.name "Seu Nome"
    git config --global user.email "seu@email.com" 
    
    ## Gerar nova chave SSH 
    ssh-keygen -t ed25519 -C "seu@email.com" 
    cat ~/.ssh/id_ed25519.pub | clip

    ## Alterar editor de texto padrão do Git
    git config --global core.editor "code --wait" # Coloca o VSCode como editor padrão
    git config --global --unset core.editor # Volta o editor de texto para o padrão

    ## Comandos Vim
    Crtl + C
    :q # Sair
    :q! # Sair sem salvar
    :w # Salva
    :wq # Salva e sai

    ## Opcional
    # Hash do commit com 10 posições:
    git config --global log.abbrevcommit yes
    git config --global core.abbrev 10
    ```
    
    Inicializar repositório:
    
    ```bash
    git init
    ```
    
    Clonar repositório:
    
    ```bash
    git clone [URL]
    ```

    Verificar o status e histórico:
    
    ```bash
    git status  # Mostra o status das alterações
    git log     # Exibe o histórico de commits
    ```

    Ramificação e Mesclagem:
    
    ```bash
    git branch [nome_da_branch]         # Cria uma nova branch
    git branch                          # Lista branches locais
    git branch -a                       # Lista branches locais e remotas
    git checkout [nome_da_branch]       # Altera para a branch selecionada
    git checkout -b [nome_da_branch]    # Criar e mudar para a nova branch
    git merge [nome_da_branch]          # Mescla o conteúdo de uma branch específica para a branch atual
    ```

    Atualizar e Publicar:
    
    ```bash
    git pull    # Obtém e mescla as alterações do repositório remoto
    git push    # Envia alterações locais para o repositório remoto
    ```

    Visualizar Diferenças:
    
    ```bash
    # Mostra as diferenças entre alterações não confirmadas
    git diff [nome_do_arquivo]   # Em um arquivo específico
    git diff                     # Em todos os arquivos
    ```

    Descartar alterações:
    
    ```bash
    git checkout -- [nome_do_arquivo]   # Descarta alterações locais em um arquivo
    git checkout -- .                   # Descarta alterações em todos os arquivos
    ```

    Adicionar um repositório remoto:
    
    ```bash
    git remote add origin [URL]   # Adiciona um repositório remoto
    ```
    
    Commit de alterações:
    
    ```bash
    git commit -m "Mensagem do commit"
    ```

</details> 

<details><summary><b>Logs</b></summary>

- **Logs**
    
    
    Log básico:
    
    ```bash
    git log
    ```

    Limitar o número de commits exibidos:
    
    ```bash
    git log -n 5    # Exibe os últimos 5 commits
    ```

    Apenas o hash do commit e a mensagem:
    
    ```bash
    git log --oneline
    ```

    Hash, autor e mensagem do commit:
    
    ```bash
    git log --pretty=short
    ```

    Detalha o número de linhas e arquivos alterados em cada commit:
    
    ```bash
    git log --stat
    ```

    Exibe alterações de um autor específico:
    
    ```bash
    git log --author="Nome do Autor"
    ```

    Exibe commits em um intervalo especificado:
    
    ```bash
    git log --since="2024-01-01" --until="2024-12-31"
    ```

    Exibi commits que modificaram uma palavra-chave:
    
    ```bash
    git log -S "palavra-chave"
    ```

    Exibi commits que modificaram uma palavra-chave:
    
    ```bash
    git log -- [path/arquivo-ou-diretorio]
    ```

    Exibir o histórico utilizando gráfico ASCII:
    
    ```bash
    git log --graph
    git log --graph --oneline --all # Gráfico resumido
    ```

    Imprimir log em um arquivo:
    
    ```bash
    git log > LOGs.txt
    ```

</details> 

<details><summary><b>Úteis</b></summary>

- **Úteis**
    
    
    Guardar alterações temporariamente:
    
    ```bash
    # Stash utiliza um comportamento de pilha, onde o ultimo stash sempre é o índice 0
    git stash                               # Guardar alterações temporariamente
    git stash save "Mensagem descritiva"    # Guardar alterações com uma mensagem descritiva
    git stash list                          # Lista stashes existentes
    git stash apply                         # Recupera informações guardadas
    git stash apply stash@{2}               # Substitua "2" pelo índice do stash desejado
    git stash drop                          # Remove stash
    git stash drop stash@{1}                # Substitua "1" pelo índice do stash que deseja remover
    git stash clear                         # Limpar todos os stashes
    ```

    Git add . e Git commit em um comando:

    ```bash
    git commit -am "Descrição do commit"
    ```

    Detalha quem fez alteração em cada linha de um arquivo:

    ```bash
    git blame [nome_do_arquivo]
    ```

    Renomear uma Branch:

    ```bash
    git branch -m [nome-novo]
    ```

    Mostra as diferenças entre duas branches:

    ```bash
    git diff [branch1] [branch2]
    ```

    Edita a mensagem do último commit:

    ```bash
    git commit --amend                              # Edita a mensagem pelo editor no terminal
    git commit --amend -m "Nova mensagem do commit" # Mensagem escrita diretamente
    git push --force origin sua_branch
    ```

    Lista arquivos rastreados:

    ```bash
    git ls-files
    ```
   
    Tags:

    ```bash
    git tag -a nome_da_tag -m "Mensagem descritiva" # Criar uma tag
    git tag nome_da_tag commit_hash # Criar uma tag apontando para um commit específico
    git tag # Lista todas as tags
    git show nome_da_tag # Exibe informações de uma tag específica.

    # Enviar tags para um repositório remoto
    git push origin nome_da_tag
    git push origin --tags

    # Deletar tags
    git tag -d nome_da_tag # Local
    git push origin --delete nome_da_tag # Remota


    git checkout -b nova_branch nome_da_tag # Criar uma nova branch a partir de uma tag
    ```

    Remover arquivos do stage:
    ```bash
    git reset  # Todos
    git reset nome_do_arquivo # Arquivo específico
    ```
    
    Apagar ou reverter commits:
    ```bash
    git reset --hard HEAD~1 # Apaga o ultimo commit
    git reset HEAD~1 # Apaga o commit, as alterações ficam como modificações não rastreadas
    git reset --hard HEAD~3 # Apaga os últimos 3 commits
    ```

    Pull em todas as branches:
    ```bash
    git pull --all
    ```

</details> 

<details><summary><b>Resolvendo Conflitos</b></summary>

- **Resolvendo Conflitos**

    Comandos que geralmente provocam um conflito:
    ```bash
    git pull
    git merge
    git rebase
    git push
    ```

    Os trechos conflitantes serão marcados no arquivo. Abra o editor de sua preferencia para resolver o conflito:
    ```bash
    vim [nome_do_arquivo]   # Abre o arquivo utilizando o Vim
    code [nome_do_arquivo]  # Abre o arquivo utilizando o VS Code
    ```

    Dentro do(s) arquivo(s), você verá marcações que indicam as alterações conflitantes. Normalmente, essas seções são cercadas por <<<<<<<, =======, e >>>>>>>. As alterações do branch atual estão entre <<<<<<< HEAD e =======, enquanto as alterações do outro branch (que você está mesclando) estão entre ======= e >>>>>>> branch_name.

    Edite o(s) arquivo(s) para resolver o conflito. Remova as marcações de conflito <<<<<<<, =======, e >>>>>>> e ajuste o conteúdo para a versão desejada. Você também pode optar por manter ambas as versões ou mesclar as alterações manualmente.

    Exemplo:

    Código com conflito
    ```bash
    <<<<<<< HEAD
    Este é o conteúdo da branch atual.
    1 + 1 = 2
    =======
    Este é o conteúdo da branch que está sendo mesclada.
    2 + 3 = 5
    >>>>>>> branch_name
    ```

    Conflito resolvido
    ```bash
    Este é o conteúdo da branch que está sendo mesclada.
    2 + 3 = 5
    ```

    Após resolver o conflito o arquivo deve ser adicionado ao staged:
    ```bash
    git add [nome_do_arquivo]
    ```

    E concluída a operação. Exemplo:
    ```bash
    git merge --continue
    ```

    Para cancelar uma tentativa de resolução de conflito:
    ```bash
    git merge --abort
    ```
 
</details> 