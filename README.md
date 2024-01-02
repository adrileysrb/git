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
    
</details> 