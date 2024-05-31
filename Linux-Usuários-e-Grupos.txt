# Usuários e Grupos

#### Arquivos
 - **/etc/passwd:** informações do usuário:
   nome:senha_onde_está(x!?):UID:GID:comentário:path_inicial:shell (sbin/bash = executa; bin/false ou sbin/nologin= fecha conexão).
 - **/etc/shadow:** possui as senhas criptografadas do usuário:
   nome:senha_criptografada:ultima_alteracao:dias_minimos_alterar_senha:dias_maximo_senha_validada:inativo:expiração.
 - **/etc/group:** lista de grupos; ou getent group; ou 1. getent group | awk -F: '{ print $1}'; 2. getent group | cut -d: -f1.

#### Adicionar (adduser)
 - sudo adduser [opções] usuario		//cria usuário
 - sudo adduser --group [opções] grupo 		//cria grupo ou o link simbolico ---> sudo addgroup grupo
 - sudo adduser [opções] grupo usuario          //cria usuario no grupo default

 - sudo adduser --group alunos
 - sudo adduser aluno
 - sudo adduser --home /hd2/alunos/aluno aluno //diretório default do usuário;

--conf <caminho do arquivo>: esta opção faz com que o adduser utilize outro arquivo de roteiro de criação diferente do default que é /etc/adduser.conf;
--group: informa que será criado um grupo e não um usuário;
--system: informa que será criado um usuário de sistema local;


#### Editar (usermod)
  sudo usermod [opções] usuario

[opções]    
   -g: sudo usermod -g GROUP USER (altera o GID do grupo default).
   -G: sudo usermod -a -G alunos,usuarios usuario (define o GID dos outros grupos).

   -c:sudo usermod -c "O aluno que faz a aula" aluno (comentário).
   -d e [-m]: sudo usermod -d /hd2/usuario/aluno aluno (cria um novo diretório home para o usuário e -m movimenta os arquivos.
   -l nome: sudo usermod -l aluno aprendiz (altera o nome de identificação do usuário (o usuário não pode estar logado)).
   -s shell: sudo usermod -s /usr/sbin/nologin aluno (altera o shell do usuário).
   -u uid: sudo usermod -u 1300 aluno (altera o número de UID do usuário).

   -e yyyy-mm-dd: altera a data de expiração da conta do usuário.
    sudo usermod -e "2022-02-21" usuario
    sudo usermod -e "" usuario(desativar a expiração).
    sudo chage -l usuario (ver a data de validade).

#### Bloqueio e desbloqueio
O comando deverá inserir um ponto de exclamação (!) na frente da senha criptografada no arquivo /etc/shadown, o usuário não poderá fazer login no sistema usando autenticação de senha.

 - Bloquear a conta e desabilitar todos os métodos de login, você também precisa definir a data de expiração para 1.
   sudo usermod -L usuario
   sudo usermod -L -e 1 usuario

 - Desbloquear: sudo usermod -U usuario

#### Alterar senhas
 - sua própria: passwd
 - de outro usuário: sudo passwd <nome_usuario>
 - terá que alterar na próxima sessão: sudo passwd --expire usuario



