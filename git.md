# Comandos Git 

### Configurar o git
 - git config --global user.email "<email>"
 - git config --global user.name <nome>

### Criando o repositório
 - echo "# <nome_do_repositorio>" >> README.md
 - git init

### Adicionar na área stage
 - git add <file>
 - git status (ver o que precisa adicionar)
 - git rm <file> -rf --cache (limpar a área stage)

### Realizando o commit
 - git commit -m "mensagem"
 - git log (lista todos os commits)

### Repositório remoto
 - git remote add origin <https://github.com/... .git>
 - git push -u origin main (enviando para o repositório remoto)
 - git remote -v (lista os links do repositório remoto)

### Clonar repositorios ou atualizar versão
 - git pull origin main


#### Objetos internos do Git----------------------
 - Blob = arquivo = tamanho + SHA1 + conteúdo
 - Tree = diretórios = com o sue SHA1 aponta para os arquivos ou outros diretórios
 - Commit = imagem do estado = seu SHA1 + aponta para a árvore + parente (commit anterior) + autor + mensagem + tempo (data e hora).





