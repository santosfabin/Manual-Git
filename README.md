# Desvendando o GIT

## Índice
- [Nomenclaturas](#nomenclaturas)
- [Índice dos comandos](#índice-dos-comandos)
- [Objetivo](#objetivo)
- [Baixando Git](#baixando-git)
- [Pré-Configuração](#pré-configuração)
- [Ajeitando Github](#ajeitando-github)
- [Primeiro envio](#primeiro-envio)
- [Próximos envios](#próximos-envios)
- [Aprendendo a usar uma Branch](#aprendendo-a-usar-uma-branch)
- [Juntando Branchs](#juntando-branchs)
- [Pegando do repositório](#pegando-do-repositório)
- [Baixando e mesclando do repositório git](#baixando-e-mesclando-do-repositório-git)
- [Atualizando o repositório git](#atualizando-o-repositório-git)
- [Alterações temporárias](#alterações-temporárias)
- [Criando Fork](#criando-fork)
- [Vendo commits](#vendo-commits)
- [Concertando commits](#concertando-commits)
- [Um commit por conteúdo](#um-commit-por-conteúdo)
- [Diferentes commits por um arquivo](#diferentes-commits-por-um-arquivo)
- [Diferença entre local e remoto](#diferença-entre-local-e-remoto)
- [Apaguei meus commits](#apaguei-meus-commits)
- [Reorganização do Histórico](#reorganização-do-histórico)
- [Selecionando Commits específicos](#selecionando-commits-específicos)
- [Encontrando bug](#encontrando-bug)
- [Atribuindo tags](#atribuindo-tags)

---

## Nomenclaturas

### md

Significa Markdown, é uma linguagem de marcação leve com uma sintaxe fácil de ler e escrever. Ela é comumente usada para formatar texto em plataformas de escrita colaborativa, como GitHub, GitLab, Bitbucket e muitos outros.

### README.md

O README.md é um tipo específico de arquivo Markdown que serve como uma introdução e guia para um projeto, geralmente encontrado em repositórios Git. "README" significa "read me" em inglês, ou seja, "leia-me". O ".md" indica que o arquivo está formatado usando Markdown.

O README.md é muitas vezes o primeiro ponto de contato que os colaboradores e usuários têm com um projeto. Ele fornece informações básicas sobre o que o projeto faz, como configurá-lo e usá-lo, bem como qualquer outra informação relevante.

### Git Bash

O Git Bash é uma interface de linha de comando (CLI) que fornece uma emulação do ambiente Bash.

### Branch

Um "branch" em Git é uma linha de desenvolvimento independente.

Ele permite que você trabalhe em novas funcionalidades, correções de bugs ou experimentos sem afetar diretamente o código principal do projeto.

---

## Índice dos comandos

- [git --version](#versão-do-git)
- [git init](#iniciando-um-repositório)
- [git add](#staging-area)
- [git status](#status)
- [git commit](#usando-um-commit)
- [git remote](#hospedado-em-outro-local)
- [git push](#enviando-conteúdo)
- [git branch](#aprendendo-a-usar-uma-branch)
- [git switch](#trocando-para-a-branch-criada)
- [git checkout](#criando-e-usando)
- [git merge](#juntando-branchs)
- [git clone](#pegando-do-repositório)
- [git pull](#puxando-e-mesclando-alterações)
- [git fetch](#puxando-alterações)
- [git stash](#alterações-temporárias)
- [git log](#vendo-commits)
- [git revert](#desfazendo-commits-sem-mudar-o-histórico)
- [git reset --soft](#desfazendo-commits-mudando-o-histórico-sem-apagar-as-modificações-já-feitas)
- [git reset --hard](#desfazendo-commits-mudando-o-histórico-apagando-os-selecionados)
- [git diff](#vendo-modificações)
- [git add -p](#explicação)
- [git reflog](#pelo-terminal)
- [git rebase](#reorganização-do-histórico)
- [git cherry-pick](#selecionando-commits-específicos)
- [git bisect](#encontrando-bug)
- [git tag](#atribuindo-tags)

---

## Objetivo

### **Controle de Versão:**

- Rastreia e registra as alterações feitas nos arquivos ao longo do tempo.
- Permite visualizar o histórico de alterações e voltar a versões anteriores, se necessário.

### **Facilitação da Colaboração:**

- Permite que várias pessoas trabalhem em um mesmo projeto simultaneamente.
- Coordena as contribuições de diferentes membros da equipe de forma eficiente.
- Identifica quem fez quais alterações, quando foram feitas e por que foram feitas.

### **Gerenciamento de Ramificações (Branches):**

- Facilita o trabalho em diferentes ramos de desenvolvimento.
- Permite testar novas funcionalidades ou fazer correções sem afetar o código principal do projeto.

### **Flexibilidade e Desempenho:**

- Oferece um sistema distribuído que funciona de forma rápida e eficiente, mesmo em projetos grandes e complexos.

---

## Baixando Git

### Instalando GIT

- No site deles baixe o arquivo de instalação correspondente ao seu sistema operacional
    - [https://git-scm.com/downloads](https://git-scm.com/downloads)
- Na instalação a algo para se notar, no fim marque a caixa onde diz “Launch [Git Bash](#git-bash)”
    
    ![Untitled](Desvendando%20o%20GIT/Untitled.png)
    
- Que é terminal do git

---

### Versão do git

- Para saber se realmente instalou e também ver sua versão podemos usar o comando `git --version`
- Veja se a versão é compatível com a que está no site

---

## Pré-Configuração

- Clique com o botão direito na pasta que deseja usar e clique em abrir o GIT bash, ou simplesmente abra da forma que desejar.

### Usuário

- Para configurar seu usuário que está no github por exemplo, use o comando:
    
    ```bash
    git config --global user.name "Seu nome de usuário entre aspas"
    ```
    

### Email

- Para configurar o email do seu usuário correspondente, use o comando:
    
    ```bash
    git config --global user.email seuemailaqui@dominio.com
    ```
    

### Trocando editor padrão

- Caso queira trocar o editor padrão pelo VS Code, rode o comando abaixo:
    
    ```bash
    git config --global core.editor "code -w"
    ```
    

### Verificações

- Para verificar se as informações inseridas estão corretas, use o comando:
    
    ```bash
     git config --list
    ```
    

---

## Ajeitando Github

### Criando um repositório no Github

- Ela pode ser facilmente encontrada quando você loga na sua conta e entra em Repositórios.
- Lá geralmente tem um botão `🔖**New**` para criar um repositório.
- Ao clicar você pode dar um nome e uma descrição.
- Então clique em `Create repository`

---

## Primeiro envio

### Iniciando um repositório

- Com seu terminal ou git bash aberto devidamente na paste que estará seus arquivos que deseja enviar, usaremos o comando `git init` para iniciar um novo repositório Git em um diretório existente.
- Dentro do diretório do projeto, o Git cria um diretório oculto chamado ".git", que contém todos os metadados e configurações do repositório Git (recomendado não apagar).
- Perceba que apareceu um `(main)` no terminal, isso indica que estamos na [branch](#branch) principal.

### Não esta “main”?

- Para resolver esse problema, ou renomear uma branch você pode usar esse comando na branch que deseja mudar seu nome:
    
    ```bash
    git branch -M "main"
    ```
    

### Staging area

- Nada mais é do que a Área de preparação, onde ele vai ficar preparado para ser usado como deve.
- Então o `git add` nada mais é do que mandar para esse Área de preparação, onde ficará ao aguardo para ser enviado.
- O `git add` tem basicamente 3 jeitos de ser usado:
    - Para mandar 1 único arquivo
        
        ```bash
        git add arquivo.txt
        ```
        
    - Para mandar 2 ou mais arquivos
        
        ```bash
        git add arquivo.txt arquivo2.txt
        ```
        
    - Para mandar tudo que está na pasta
        
        ```bash
        git add .
        ```
        

### Status

- Com o `git status` é possível ver como está o andamento do que a gente fez.

### Removendo da Staging area

- Você pode usar o comando:
    
    ```bash
    git add <file>
    ```
    
- Isso removerá do `git add`

### **Registro de Alterações**

- Um commit registra um conjunto específico de alterações feitas nos arquivos do seu projeto desde o último commit. Isso inclui adições, modificações e remoções de arquivos.
- Cada commit cria um snapshot do estado atual do seu projeto. Isso permite que você reverta para um estado anterior do seu projeto se necessário, usando o histórico de commits.
- Além das mudanças nos arquivos, um commit também inclui metadados como o autor do commit, a data e hora em que o commit foi feito e uma mensagem de commit que descreve as alterações realizadas.

### Usando um commit

- Então para fazer esse registro você pode usar o comando:
    
    ```bash
    git commit -m "Primeiro commit"
    ```
    
    - Sendo o `-m` a mensagem.

### Hospedado em outro local

- Quando foi criado um repositório no Github lá mostra um “passo a passo” de como deve ser feito a hospedagem la.
- Lá mostra o comando para fazer isso:
    
    ```bash
    git remote add origin <seu link>
    ```
    
    1. **remote**: Indica que estamos trabalhando com repositórios remotos. No Git, um "remote" é um repositório hospedado em outro local, como um servidor na nuvem.
    2. **add**: Este subcomando é usado para adicionar um novo remote ao seu repositório local. Você pode ter vários remotes associados a um único repositório local.
    3. **origin**: É o nome do remote. "Origin" é um nome comum usado para denotar o repositório remoto principal de onde o repositório local foi clonado. No entanto, você pode escolher outro nome se desejar.
    4. **<seu link**>: Este é o URL do repositório remoto que estamos adicionando como "origin". O URL indica o endereço do repositório no GitHub, no caso específico. É importante fornecer o URL correto do repositório remoto que você deseja conectar ao seu repositório local.

### Enviando conteúdo

- Mesmo se atualizarmos a página no github, ele continuará igual.
- Então temos mais um ultimo comando para usar, igual mostra no próprio exemplo do github, o `git push`
    
    ```bash
    git push -u origin main
    ```
    
    1. **push**: Este é o comando para enviar (push) commits locais para um repositório remoto.
    2. **-u**: A opção "-u" é uma abreviação de "--set-upstream". Quando você usa esta opção pela primeira vez com um push para um remote, o Git associa automaticamente a branch local com a branch remota correspondente e define-a como upstream. Isso significa que, após o uso desta opção, você pode usar simplesmente **`git push`** ou **`git pull`** sem a necessidade de especificar o remote e a branch.
    3. **origin**: Este é o nome do remote para o qual você está enviando (pushing) os commits. "origin" é frequentemente usado para se referir ao repositório remoto principal de onde o repositório local foi clonado ou inicializado. No entanto, você pode ter outros remotes configurados e usá-los aqui se desejar.
    4. **main**: Este é o nome da branch local que você está enviando para o remote. Você está enviando os commits da branch local "main" para a branch correspondente no repositório remoto.
- Provavelmente se você nunca logou, aparecerá uma telinha para você logar em sua conta, então basta conectar.

---

## Próximos envios

### Enviando

- Para enviar os próximos envios, é simples, basta seguir os comandos a baixo:
    
    ```bash
    git add .
    git commit -m "segundo envio"
    git push origin main
    ```
    
- Então perceba que não teve usar o comando `git remote` e também  parte de colocar seu link.
- No github você pode atualizar a página e ver as mudanças, mas como?

### Vendo alterações

- Vou mostrar 2 jeitos simples de você ver as alterações.
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%201.png)
    
- Se você clicar no nome do commit, que no meu caso é “Criando projeto”, você vai ver a alteração feita com esse ultimo commit.
- Se você clicar no “Commits” ele vai mostrar todos os commits que você fez, podendo ver as alterações feitas em cada uma.

---

## Aprendendo a usar uma Branch

### Criar

- Para criar uma branch é simples:
    
    ```bash
    git branch nome_da_branch
    ```
    
- Porém lembre-se que, ele somente CRIA e não cria e te move para ela automaticamente.

### Trocando para a Branch criada

- Para isso temos o comando `git switch` para poder alternar da Branch que está em uso, para outra que deseja usar.
    
    ```bash
    git switch outra_branch
    ```
    

### Criando e Usando

- Para fazer isso temos o comando `git checkout`.
- Lembrando que se não for usando nenhum parâmetro, ele irá simplesmente trocar de branch igual o `git switch`, por exemplo.
    
    ```bash
    git checkout main
    ```
    
- Assim como ele troca de branch, ele também troca para um commit passado, para poder visualizar-lo.
- Quando você utiliza o comando **`git checkout`** para visualizar um commit específico, ele altera temporariamente o ponteiro de visualização (**`HEAD`**) e o estado do diretório de trabalho para corresponder ao estado do código naquele commit específico. Isso permite que você veja como era o código naquele momento no histórico de commits.
- No entanto, quaisquer alterações que você fizer após essa visualização serão realizadas no contexto da branch atual, não no commit específico que você estava visualizando. Se você fizer um commit ou push, essas operações serão realizadas na branch atual, não no commit visualizado.
- Portanto, é importante ter em mente que o **`git checkout`** para visualização é apenas uma operação temporária e não afeta permanentemente o estado do seu repositório.
- Para ver as hashs dos commits use [git log](#vendo-commits)
    
    ```bash
    git checkout hash-do-commit
    ```
- Para alternar de volta para a última branch, como um “back” use:
    
    ```bash
    git checkout -
    ```

- Agora para criar e usar deixando as outras coisas como **<remote> e o<branch>** como padrão, ficando <origin> e <branch_que_voce_esta> use a opção `-b`.
    
    ```bash
    git checkout -b nova_branch
    ```
    
    Lembrando que o `-b` cria e imediatamente muda para ela.
    

### Depois de criar uma nova Branch

- É de extrema importância lembrar que, se você quer mandar para a nova branch que você criou, você deve mudar o nome da branch para a correta no `git push` por exemplo:
    
    ```bash
    git add .
    git commit -m "push para a nova branch"
    git push origin nova_branch
    ```
    

### Listando de um jeito simples

- Simplesmente o `git branch` ou com a adição do `--list`.
    
    ```bash
    git branch
    # ou
    git branch --list
    ```
    
- Se `--list` for fornecido, ou se não houver argumentos de não-opção, as ramificações existentes serão listadas.

### Vendo local e remoto

- Existe duas opção importantes que podem ser usada com o `git branch`, o `-a` e o `-r`.
- `-a`
    
    ```bash
    git branch -a
    ```
    
    mostra as ramificações locais e remotas.
    
- `-r`
    
    ```bash
    git branch -r
    ```
    
    Faz com que as ramificações de rastreamento remoto sejam listadas
    

### Apagando uma Branch

- `-D` ou `--delete --force`
- Apaga forçando sua branch
    
    ```bash
    git branch -D <nome_da_branch>
    ```
    
    Este comando é usado para excluir uma ramificação localmente no seu repositório Git **local**. 
    
- Ou então:
    
    ```bash
    git push origin --delete <nome_da_branch>
    ```
    
    Este comando é usado para excluir uma ramificação específica no repositório **remoto**.

### Movendo ou Renomear uma Branch

- `-M` ou `--move --force`
- Movendo ou Renomear de uma maneira forçada
- Para renomear a branch de uso basta usar da seguinte forma:
    
    ```bash
    git branch -M nome_alterado
    ```
    
- Para renomear outra branch basta usar da seguinte forma:
    
    ```bash
    git branch -M branch_atual novo_nome_da_branch
    ```
    

### Vendo as Branchs pelo Github

- No seu repositório no Github você pode ver um botão onde ficará as Branchs.
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%202.png)
    
- Se você colocou ou modificou algo e deu `push` em outra branch, ela estará na branch correspondente, então ela so será vista la.

---

## Juntando Branchs

### Mesclando 2 Branchs

- Para isso usamos o comando `git merge`.
- Então para juntar 2 Branchs, basta você ir para a Branch principal onde você irá atribuir a outra Branch usando o `git checkout` ou `git switch`.
- Use o comando `git merge <branch_que_sera_adicionado>`.
- Faça um commit.
- Então finalmente envie para a branch que deseja para salvar a alteração.
- Exemplo prático:
    
    ```bash
    git checkout main
    git merge feature1
    # Resolva conflitos, se houver
    git commit -m "Merge feature1 into main"
    git push origin main
    ```
    

### Mesclando mais Branchs

- O processo é exatamente o mesmo, porém para colocar 2 ou mais basta dar outro `git merge <branch_que_sera_adicionado>`
- Exemplo prático:
    
    ```bash
    git checkout main
    git merge feature1
    git merge feature2
    git merge feature3
    # Resolva conflitos, se houver
    git commit -m "Merge feature1, feature2, and feature3 into main"
    git push origin main
    ```
    

---

## Pegando do repositório

### Clonando repositório

- Caso tenha que pegar do github seu repositório ou de outra pessoa, é possível usar o comando `git clone <link.git>`.
- Esse link é simples de se achar, pode ser copiado, estando no repositório que deseja clonar, e clicando no botão `Code` e em HTTPS mesmo você pode copiar o link que está disponível.
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%203.png)
    
- Ou então você copia a URL e adiciona um .git no final, por exemplo minha url do meu repositório é [https://github.com/santosfabin/GIT](https://github.com/santosfabin/GIT), então adicionando o .git no final da no mesmo [https://github.com/santosfabin/GIT.git](https://github.com/santosfabin/GIT)
- Agora vamos usar o comando:
    
    ```bash
    git clone https://github.com/santosfabin/GIT.git
    ```
    
- Agora entre na pasta e faça o que você precisa:
    
    ```bash
    cd <nome da pasta>
    ```
    
- Perceba que ele já mostra a Branch correspondente, então você pode usar isso como parâmetro para sabe se está correto.

---

## Baixando e mesclando do repositório git

### Puxando e mesclando alterações

- O `git pull` baixando e mesclando as alterações do repositório remoto na sua branch local em um único comando.
- Para isso, devemos estar dentro da pasta do repositório e usar o comando `git pull`.
- Simples assim:
    
    ```bash
    git pull origin main
    # ou
    git pull
    ```
    

---

## Atualizando o repositório git

### Puxando alterações

- O `git fetch` baixa as **atualizações** do repositório remoto para o seu repositório local, atualizando as referências remotas (como **`origin/main`**, **`origin/nova-branch`**), mas não mescla automaticamente as alterações na sua branch local.
- Basicamente ela serve para quando quiser apenas baixar as atualizações do repositório remoto para revisá-las antes de decidir como integrá-las no seu trabalho local.
- Simples assim:
    
    ```bash
    git fetch origin
    ```
    

### Mesclando

- Depois de você já ter feito o fetch e queria queira mesclar com sua branch existem alguns casos.
1. Você está dentro da Branch correta.
    1. Neste caso você pode simplesmente usar o `git merge`:
        
        ```bash
        git merge
        ```
        
2. Você está em outra branch.
    1. Neste caso você deverá especificar o repositório e a branch, por exemplo `origin/main`:
        
        ```bash
        git merge origin/main
        ```
        
3. Você está em outra branch e vai dar merge para outra branch.
    1. Neste caso você fará semelhante ao exemplo passado, porém ao invés de `main` será a branch que você fará o merge:
        
        ```bash
        git merge origin/branch
        ```
---

## Alterações temporárias

### O que é o `git stash`

- Gerenciar temporariamente alterações no seu diretório de trabalho enquanto você trabalha em diferentes tarefas ou branches, sem a necessidade de fazer commits.
- Então para cada stash ele apaga temporariamente o que você tem, até o ultimo commit.
- Por exemplo, você salvou um texto e já fez o commit dele, ai você escreve um segundo texto e em seguida usa o `git stash`, ele vai apagar temporariamente o segundo texto, e voltar no commit passado, onde somente existia o primeiro texto, o segundo texto voltará quando você chamar de volta.

### Salvando

- Ele salva as alterações no diretório de trabalho em um stash **temporário**.
- Você pode usar de duas maneiras:
1. Sem título
    
    ```bash
    git stash
    ```
    
2. Com título
    
    ```bash
    git stash save "Alterações temporárias"
    ```
    

### Listando

- Com o `git stash list` ele vai listar as `git stash` que existem.
    
    ```bash
    git stash list
    ```
    

### Restaurando sem apagar ponto de salvamento

- Aplica as alterações do último stash no diretório de trabalho sem remover o stash.
- Isso quer dizer que, ele vai voltar o que você tinha feito, sem apagar esse ponto de salvamento que ele usou.
- Você pode usar de duas maneiras:
1. Pegando o ultima stash feito:
    
    ```bash
    git stash apply
    ```
    
2. Escolhendo a stash:
    
    ```bash
    git stash apply stash@{1}
    ```
    

### Restaurando apagando ponto de salvamento

- Aplica as alterações do último stash no diretório de trabalho removendo o stash usado.
- Isso quer dizer que, ele vai voltar o que você tinha feito, apagando esse ponto de salvamento que ele usou.
1. Pegando o ultima stash feito:
    
    ```bash
    git stash pop
    ```
    
2. Escolhendo a stash:
    
    ```bash
    git stash pop stash@{1}
    ```
    

### Apagando ponto de salvamento

- Cuidado antes de usar o `git stash clear`, porque se você não tiver voltado seu salvamento, você perderá TUDO que fez, ou seja, você vai voltar a ter somente o que seu ultimo commit tem.
    
    ```bash
    git stash clear
    ```
    

### Diferenças entre stashs

- O `git stash show` vai mostra as diferenças entre o stash mais recente e o commit anterior.
    
    ```bash
    git stash show
    ```
    
- Com a adição do `-p` ele via mostrar as diferenças entre o stash mais recente e o commit anterior, com detalhes.
    
    ```bash
    git stash show -p
    ```

---

## Criando Fork

### Fork no Github

- Fazer um fork em um contexto de desenvolvimento de software significa criar uma cópia independente de um repositório de código-fonte de outro usuário ou organização em uma plataforma de hospedagem de código, como GitHub, GitLab ou Bitbucket. O fork cria uma ramificação separada do projeto original, permitindo que você trabalhe nele de forma independente, sem afetar o projeto original.
- Basicamente a gente vai copiar o repositório, para depois se quisermos fazer um `pull request`, isso quer dizer que, iremos modificar LOCALMENTE algo de outra pessoa, então mandar para ela, se ela aceitar, ela muda o original que esta com ela, caso contrário nada acontecerá e você só terá um copia do projeto original.

### Fazendo um Fork

- Então no Github vá até o repositório que deseja e clique em `Fork`,que normalmente fica na parte superior direita da tela.
- Então selecione para onde ele irá copiar o repositório, seja para você ou para uma organização sua. Essa cópia é feita pois você não consegue fazer commits por exemplo na conta da outra pessoa, somente na sua, então a pessoa tem a escolha de fazer a alteração que você mandar ou não.

### Fazendo mudanças na nossa cópia

- Para isso você pode fazer um git clone simples somente para baixar o conteúdo do repositório clonado com o `git clone <link.git>`.
- Faça suas alterações que você acha necessário.
- Faça um `git add <arquivo ou arquivos>`.
- Faça um `git commit`.
- Então um `git push origin <branch ou HEAD>`
- Isso será alterado somente no seu repositório.

### Fazendo a Pull request

- No nosso repositório já devidamente modificado com o nosso conteúdo, clique em `Pull request`, que deve estar perto do `Code` na parte superior direita, ao lado de `Fetch upstream` dentro de `Contribute`.
- Então crie e mande sua pull request, colocando um comentário do que você fez.

### Aceitando uma Pull request

- Para fazer isso, entre no seu repositório que deseja ver as Pull requests que foram enviados.
- Elas devem estar em “Pull requests”.
- Lá você pode aceitar ou recusar.
- Para aceitar seria um “Merge”

---

## Vendo commits

### Logs dos commits

- O comando **`git log`** é usado para exibir o histórico de commits de um repositório Git. Ele mostra uma lista detalhada de todos os commits feitos no repositório, incluindo informações como o hash do commit, autor, data e hora do commit, e a mensagem de commit.
- Exemplos de `git log`:
    - **Exibir o histórico completo de commits**:
        
        ```bash
        git log
        ```
        
    - **Exibir um resumo compacto dos commits**:
        
        ```bash
        git log --oneline
        ```
        
    - **Exibir o histórico de commits de um arquivo específico**:
        
        ```bash
        git log arquivo.txt
        ```
        
    - **Limitar o número de commits exibidos**:
        
        ```bash
        git log -n 5
        ```

---

## Concertando commits

### Desfazendo commits sem mudar o histórico

- O comando **`git revert`** é usado para desfazer as alterações introduzidas por um ou mais commits específicos.
- **Criando um novo commit que reverte essas alterações sem apagar elas, preservando o histórico.**
- O **`git revert`** é uma operação segura e não destrutiva, pois não reescreve o histórico de commits. Isso torna uma escolha preferível quando você deseja desfazer alterações em commits anteriores sem afetar o histórico do repositório.
- **Exemplos práticos:**
    1. **Desfazer o último commit**:
        
        ```bash
        git revert HEAD
        ```
        
        Este comando cria um novo commit que desfaz as alterações introduzidas pelo último commit.
        
    2. **Desfazer um commit específico**:
        
        ```bash
        git revert <hash-do-commit>
        ```
        
        Este comando cria um novo commit que desfaz as alterações introduzidas pelo commit com o hash especificado.
        
        Use o `git log` para pegar a hash.
        
    3. **Desfazer múltiplos commits**:
        
        ```bash
        git revert <hash-do-commit1> <hash-do-commit2> [...]
        ```
        
- Agora você deve fazer o `push` forçando ou não.
    
    ```bash
    git push --force
    ```
    

### Desfazendo commits mudando o histórico sem apagar as modificações já feitas

- O `git reset --soft` move o ponteiro HEAD para um commit anterior, desfazendo os commits subsequentes, mas mantendo as alterações do commit mais recente no staging area (área de preparação). Isso significa que as alterações do commit desfeito ainda estarão prontas para serem commitadas novamente.
- Então ele volta em um certo commit, apagando os commits deis do atual até o commit escolhido, porém sem mexer em nada, somente nas marcações de commits, então seus arquivos continuaram e não serão apagados.
- Exemplo prático do `git reset --soft` com hash:
    
    ```bash
    git reset --soft abc123
    ```
    
    Isso moverá o ponteiro **`HEAD`** para o commit com o hash **`abc123`**, mantendo as alterações do commit desfeito no working directory e no staging area. Essencialmente, desfaz os commits subsequentes, mas mantém as alterações prontas para serem commitadas novamente.
    
- Exemplo prático do `git reset --soft` com HEAD:
    
    ```bash
    git reset --soft HEAD~5
    ```
    
    Isso moverá o ponteiro **`HEAD`** para 5 commits anteriores ao commit atual, mantendo as alterações do commit desfeito no working directory e no staging area. Neste caso, ele desfaz os últimos 5 commits, mas mantém as alterações prontas para serem commitadas novamente.
    
- Agora você deve fazer o `push` forçando ou não.
    
    ```bash
    git push --force
    ```
    

### Desfazendo commits mudando o histórico apagando os selecionados

- O `git reset --hard` move o ponteiro HEAD para um commit anterior, desfazendo os commits subsequentes, e também remove as alterações do commit mais recente tanto da staging area quanto do working directory. Isso significa que as alterações desfeitas serão permanentemente removidas e não poderão ser recuperadas facilmente.
- Então ele volta em um certo commit, apagando os commits deis do atual até o commit escolhido.
- Exemplo prático do `git reset --hard` com hash:
    
    ```bash
    git reset --hard abc123
    ```
    
    Isso moverá o ponteiro **`HEAD`** para o commit com o hash **`abc123`**, desfaz os commits subsequentes, apagando alterações commitadas permanentemente.
    
- Exemplo prático do `git reset --hard` com HEAD:
    
    ```bash
    git reset --hard HEAD~5
    ```
    
    Isso moverá o ponteiro **`HEAD`** para 5 commits anteriores ao commit atual, apagando as alterações do commit desfeito no working directory e no staging area. Neste caso, ele desfaz os últimos 5 commits, apagando alterações commitadas permanentemente.
    
- Agora você deve fazer o `push` forçando ou não.
    
    ```bash
    git push --force
    ```
    

### Faltou um arquivo ou modificação no commit?

- **Adicionar alterações ao commit anterior**: Se você já fez um **`git add`** para adicionar arquivos ao staging area e, em seguida, executa **`git commit --amend`**, essas alterações serão incluídas no commit anterior, em vez de criar um novo commit separado. Isso é útil se você esqueceu de incluir algumas alterações no commit anterior e quer adicioná-las sem criar um novo commit.
    
    ```bash
    git add arquivo1.txt arquivo2.txt arquivo-modificado.txt
    git commit --amend
    ```
    

### Concertando mensagem do commit

- **Alterar a mensagem de commit**: Se você especificar a opção **`-m`** seguida de uma nova mensagem de commit, o **`git commit --amend`** reescreverá a mensagem de commit do commit mais recente. Isso é útil se você perceber que a mensagem do seu commit anterior não está clara ou contém erros de digitação que você gostaria de corrigir.
    
    ```bash
    git commit -m "Primerio connit"
    git commit --amend -m "Primeiro commit"
    ```

---

## Um commit por conteúdo

### Cenário

- Você programa sobre uma coisa, por exemplo um botão, ai você teve que parar para programar a nav bar, mas você precisa dar um commit.
- Cada commit tem que ser para uma única coisa.

### Suposição 1

- Vamos partir do ponto que você deu um `git add .` e foram todos os arquivos, porém você precisava tirar um arquivo.
    
    ```bash
    git reset -- arquivo.txt
    ```
    
- Você também pode deixar em branco para tirar todos os arquivos.
    
    ```bash
    git reset --
    ```
    

### Suposição 2

- Vamos partir do ponto que você deu um `git add .` e foram todos os arquivos, porém como são muitos arquivos e você precisava tirar alguns arquivos, pode acabar ficando chato escrever todos os arquivos para ser retirado ou adicionado.
- Então temos o `git add -i` que é a opção interativa do git.
- Nela você usará números para fazer o que você precisa, para para remover da lista.
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%204.png)
    
- Já que foi feito um `git add .` vamos usar a opção `3` para reverter os arquivos adicionados.
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%205.png)
    
- Agora use os números correspondentes para retirar os arquivos que você deseja.
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%206.png)
    
- Para voltar para o menu anterior aperte a tecla "ENTER”.
- Para adicionar é da mesma forma, porém usando a opção 4.
- Então para colocar seria do mesmo jeito, porem é a opção 2.
- E para sair aperte a tecla “Q”.

### Após esses 2 cenários

- Você deve selecionar somente os arquivos correspondentes para fazer um bom commit, contendo somente um tipo de conteúdo, por exemplo, somente os arquivos que mexem com a interface, o próximo seria por exemplo, uma correção do back-end e assim por diante.
- Então separe os arquivos corretos para fazer um commit por conteúdo.

---

## Diferentes commits por um arquivo

### Cenário

- Vamos supor que existe um arquivo já feito, depois de um tempo você modificou ele e depois adicionou algo a mais.
- Logo você pode fazer um commit só para a modificação e outra para aquilo que você adicionou.

### Vendo Modificações

- Você pode ver as mudanças que teve nos arquivos usando o comando `git diff`.
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%207.png)
    
- Para ver somente o que vai ser adicionado, use o `git diff --staged`.
- Também ver as mudanças com o `git status`.

### Explicação

- Então antes de tudo você fez um commit (sem o push), depois você mexe no arquivo como já foi falado, para fazer um commit separado para cada conteúdo dentro do arquivo.
- Após essa modificação, usaremos o comando `git add -p`.
- O git vai perguntar um hunk de modificação de cada vez.
    - Um "hunk" no Git se refere a uma seção de mudanças em um arquivo.
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%208.png)
    
- Existem essas letras com seu significado próprio
    
    
    | y | encenar esse pedaço |
    | n | não encena esse pedaço |
    | q | sair; não encene este pedaço ou qualquer um dos restantes |
    | a | prepare este pedaço e todos os pedaços posteriores no arquivo |
    | d | não prepare este pedaço ou qualquer um dos pedaços posteriores no arquivo |
    | s | divide o pedaço atual em pedaços menores |
    | e | edite manualmente o pedaço atual |
    | ? | imprimir ajuda |

### Executando

- Agora que sabemos o que cada letra do `git add -p` faz, podemos usar.
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%209.png)
    
- Então a opção `s` vai dividir cada modificação.
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%2010.png)
    
- Então escolheremos separadamente com `y` ou com `n` se ele vai entrar no commit.
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%2011.png)
    
- Vendo o que está sendo adicionado
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%2012.png)
    
- A partir disso você cria seus commits do jeito que quiser.

---

## Diferença entre local e remoto

- Já que você sabe que existem diferenças do remoto e local, você pode usar o `fetch` para pegar o que tem no remoto:
    
    ```bash
    git fetch origin
    ```
    
- Agora você pode ver as mudanças usando o `diff`:
    
    ```bash
    git diff main origin/main
    ```
    
    Ele compara a nossa main local com o origin/main remoto.
    
- Se estiver tudo bem fazer uma mesclagem, você pode fazer o `merge`:
    
    ```bash
    git merge origin/main main
    ```
    
    Ele vai mesclar o origin/main remoto com nossa main local.
    
- Ele vai mostrar onde ele fez as alterações por meio de um comentário, então é so apagar o comentário.
- Se você estiver no vs code você pode clicar em uma das opções, então ele irá apagar automaticamente.

---

## Apaguei meus commits

### Cenário do ocorrido

- Vamos supor que você apagou muitos commits sem querer.
- Você pode restaurar de 2 jeitos seus commits.

### Pelo Github

- Você pode usar os commits remotos do github e ir até o commit que você precisa, ou simplesmente para o ultimo commit que você tem remoto.
- Basta ir no seu repositório e copiar o hash do commit que você deseja voltar até aquele ponto.
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%2013.png)
    
- Agora vamos usar o `reset --hard` para forçar apagando tudo o que você fez até aquele ponto daquele commit:
    
    ```bash
    git reset --hard <commit_hash>
    ```
    
- Se você não quiser apagar as alterações que você fez, você pode fazer a mesma coisa, porém usando o `--soft` no lugar do `--hard`:
    
    ```bash
    git reset --soft <commit_hash>
    ```
    

### Pelo terminal

- Aqui entra um ponto super importante, o `git reflog`.
- Ele é uma ferramenta muito poderosa, pois nele é onde a gente tem nosso histórico de atividades, esse histórico é feito a partir da mudança do ponto do `HEAD`.
- Ele também mostra pontos de reset, checkout e outros.
- Então podemos pegar diversos pontos para voltar até ele, bastando copiar a hash, que é o primeiro valos a ser mostrado.
- Depois de copiar a hash de um commit que deseja voltar até aquele ponto, vamos usar o `git reset --hard <hash>` ou `gir reset --soft <hash>`:
    - `reset --hard` para forçar apagando tudo o que você fez até aquele ponto daquele commit:
        
        ```bash
        git reset --hard <hash>
        ```
        
    - Se você não quiser apagar as alterações que você fez, você pode fazer a mesma coisa, porém usando o `--soft` no lugar do `--hard`:
        
        ```bash
        git reset --soft <hash>
        ```

---

## Reorganização do Histórico

### Reposicionando a base de uma branch

- O `git rebase` tem o poder de reposicionar uma branch, por exemplo para o ponto mais atual da main.
- Isso fará que essa ramificação seja atualizada, então isso pode ser facilmente usado de atualização.
- Isso seria feito da seguinte forma:
- Imagine que existe a `main` e a partir do ponto de commit (`main2`) ele teve uma ramificação `efieto` e a `main` continuou tendo atualizações.
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%2019.png)
    
- main
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%2014.png)
    
- efeito
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%2015.png)
    
- Se for preciso fazer um merge dos conteúdos vai dar divergências.
- Para evitar isso, precisamos concertar essa branch `efeito` para depois fazer um merge sem problemas, pois se mandarmos assim vai ter um conflito.
- O que precisamos fazer é deixar a base do `efeito` para o mais atual, assim ele terá tudo que a main tem + o próprio conteúdo.
- Ficando assim:
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%2020.png)
    
- Então após essa atualização, não terá mais conflitos para resolver.
- Então vamos aos comandos.
- Primeiro precisamos ir para a branch que será atualizada LOCALMENTE.
- Depois usaremos o comando:
    
    ```bash
    git rebase <branch>
    ```
    
- Perceba que no seu editor ele marca onde ocorreu as divergências, então basta você editar o que você precisa.
- Isso tudo somente do primeiro commit do `efeito`.
- É possível saber disso no seu terminal.
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%2016.png)
    
- Após editar seu arquivo editando as modificações, no seu terminal você pode continuar a usar o `rebase`.
- Mas antes disso é obrigatório usar o `git add` para confirmar as alterações e conseguir editar o histórico.
    
    ```bash
    git add arquivo.txt
    git rebase --continue
    ```
    
- Ou você pode dar um `--skip` e pular para o ultimo commit, mas cuidado, pode ter alterações que podem ser passado despercebido, então tenha cuidado ao fazer isso, e veja antes de pular se as alterações estão OK para você.
- Também ele sumirá com o commit caso você o pule, então tenha mais cuidado ainda.
    
    ```bash
    git rebase --skip
    ```
    
- Ao chegar no ultimo arquivo e você ainda desejar continuar com esse processo para atualizar, apague os comentários do git, então ajeite seus arquivos e de continuidade.
    
    ```bash
    git rebase --continue
    ```
    
- Perceba que ele abriu no seu terminal um editor para você mudar o nome do commit, então mude ou deixe o mesmo, e se for o VIM saia da seguinte maneira.
    - `ESC` -> `:wq` -> `ENTER`
- Agora no seu próximo push ele fará essa alteração na sua branch.
- Exemplo usando o `--skip`:
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%2017.png)
    
- Exemplo sem o `--skip` fazendo um por um:
    
    ![Untitled](Desvendando%20o%20GIT/Untitled%2018.png)

### Mesclando commits

- Vamos imaginar que acabou acontecendo de ser feito 2 commits sem muito sentido e eles poderiam claramente serem um commit só.
- Lembrando que essa mesclagem acontecerá e o commit da mesclagem vai substituir os commits mesclados, ficando no lugar do commit mais atual.
- Então se exister commits do A até o J, e a mesclagem for do D e G, o ponto de commit da mesclagem vai ficar no G
- Agora vamos fazer a mesclagem.
- Precisamos saber o ponto que o HEAD vai ficar, ou a hash do commit mais antigo, pois assim ele vai conseguir englobar o resto dos commits.
    
    ```bash
    git log --oneline
    ```
    
- Vamos usar o `git rebase` com a adição do `-i` a opção interativa.
    
    ```bash
    git rebase -i HEAD~4
    ```
    
- Isso abrirá o editar VIM.
- Nela você pode apertar `INSERT` e perceba que na parte inferior ele esta `-- INSERT --`, então agora basta ir diretamente editar o que precisamos.
- Então para os commits que deseja troque o `pick` por `squash`(esmagar) e salve o arquivo.
- Porém para o primeiro que será mesclado, não precisa trocar de pick para squash.
    - `ESC` → `:wq` → `ENTER`
- Agora mude o nome do commit afim de refletir as alterações.
- Finalize o rebase:
    
    ```bash
    git rebase --continue
    ```
    
- Você tem a opção de forçar esse envio, sem commit ou novos arquivos:
    
    ```bash
    git push origin main -f
    ```
    
- Ou você pode fazer o que você precisa fazer, depois você envia o que você precisa com um commit, então ele vai arrumar para você a alteração que você fez.

### Mudando nomes de commits passados

- Imagine que você fez um commit e ele saiu com a escrita errada.
- Você não precisa apagar ele e mandar outro commit arrumando.
- O `git rebase` com a adição do `-i` tem a opção interativa.
- Então para renomear, vamos precisar de algumas coisas, começando pelo hash do commit.
    
    ```bash
    git log --oneline
    ```
    
- Agora com o hash ou com a marcação de quanto você precisa para usar o HEAD, vamos usar o `git rebase`:
    
    ```bash
    git rebase -i HEAD~6
    ```
    
- Perceba que ele abriu uma telinha para configuração usando o VIM.
- Nela você pode apertar `INSERT` e perceba que na parte inferior ele esta `-- INSERT --`, então agora basta ir diretamente editar o que precisamos.
- No commit que deseja editar, troque de `pick` para `edit` e salve o arquivo.
    - `ESC` → `:wq` → `ENTER`
- Agora basta usar o `--amend` do commit para editar o texto:
    
    ```bash
    git commit --amend -m "Commit certo"
    ```
    
- Agora que você já arrumou, use:
    
    ```bash
    git rebase --continue
    ```
    
- Você tem a opção de forçar esse envio, sem commit ou novos arquivos:
    
    ```bash
    git push origin main -f
    ```
    
- Ou você pode fazer o que você precisa fazer, depois você envia o que você precisa com um commit, então ele vai arrumar para você a alteração que você fez.

---

## Selecionando Commits específicos

### Explicação

- Um motivo para usar o comando **`git cherry-pick`** é quando você precisa aplicar uma correção ou feature específica de um branch para outro, sem precisar mergear toda a branch.
- Por exemplo, imagine que você tem dois desenvolvedores trabalhando em duas branches diferentes, `branch-A` e `branch-B`. O desenvolvedor da `branch-A` descobriu e corrigiu um bug importante, mas o desenvolvedor da `branch-B` já fez muito progresso em seu trabalho e não quer mergear a `branch-A` inteira. Neste caso, você pode usar o comando `git cherry-pick` para pegar o commit específico que contém a correção do bug da `branch-A` e aplicá-lo na `branch-B`.Isso permite que você corrija o bug na `branch-B` sem precisar mergear toda a `branch-A`.

### Prática

- Primeiro tem que ficar claro que caso já houver o commit na branch que você quer, ele não fará.
- Então isso é só para casos de commits q não existe na branch que você esta, exemplo: uma desatualização.
- É necessário duas coisas, você está na branch que deseja copiar um commit para ela, e a hash do commit que você vai copiar.
- Na branch que tem o commit:
    
    ```bash
    git log --oneline
    ```
    
- Copie a hash então vá para a branch que você quer copiar o commit e use o `git cherry-pick`:
    
    ```bash
    git switch outra_branch
    git cherry-pick abcdefg
    ```
    
- Agora para confirmar as alterações, use o `git add` que é obrigatório para fazer essa confirmação.
- No arquivo que houve a mudança, corrija os conflitos, então no terminal prossiga com o `--continue`, ou caso queria cancelar `--abort`:
    
    ```bash
    git cherry-pick --continue
    ```

---

## Encontrando bug

### Explicação

- O **`git bisect`** é uma ferramenta do Git que automatiza o processo de busca pelo commit que introduziu um determinado problema, permitindo que você isole rapidamente o commit culpado.
- Ao marcar um commit como bom e outro como ruim, o Git usa uma busca binária para identificar o commit que introduziu a mudança problemática.
- Isso pode economizar muito tempo e esforço, especialmente em projetos grandes com muitos commits.

### Prática

- Vamos fazer por etapas.
1. Iniciar o `bisect`:
    
    ```bash
    git bisect
    ```
    
2. Ver os hashs dos commits:
    
    ```bash
    git log --oneline
    ```
    
3. Falar onde está o commit sem o bug, ou seja, um commit bom `good`:
    
    ```bash
    git bisect good f8a20e8
    ```
    
4. Falar onde está o ultimo commit, ou um recente que tenha o bug, ou seja, um commit ruim `bad`:
    
    ```bash
    git bisect bad 10a04d3
    ```
    
5. Identificar se o commit mostrado tem o bug, para isso você vai olhar o(s) arquivo(s) para ver se existe esse bug, se tiver COM o bug você marcará como `bad`, se tiver SEM o bug você marcará como `good`:
    
    ```bash
    git bisect good
    ```
    
    ```bash
    git bisect bad
    ```
    
- Você testará até le falar que aquele commit tal existe o bug.
- Agora você pode concertar o bug e salvar.
- Para sair basta resetar:
    
    ```bash
    git bisect reset
    ```

---

## Atribuindo tags

### Por que usar tags?

- Elas simplificam a organização, comunicação e reversão do código, além de servirem como documentação automática e seguirem um padrão da indústria.
- As tags podem substituir o uso direto de hashes de commits, oferecendo uma abordagem mais amigável e legível para identificar momentos importantes no histórico do projeto.

### Usando

- Você pode simplesmente já colocar uma tag no commit que você está:
    
    ```bash
    git tag v1.0.0
    ```
    
- Caso precise colocar em outro commit, apenas adicione a hash dele ao fim:
    
    ```bash
    git tag v1.0.0 1a2b3c4d
    ```
    

### Vendo as tags

- Listando as tags:
    
    ```bash
    git tag
    ```
    

### Comparação de usar e não usar tags

- Sem usar Tag:
    
    ```bash
    git checkout 1a2b3c4d
    ```
    
- Usando Tag:
    
    ```bash
    git checkout v1.0.0
    ```