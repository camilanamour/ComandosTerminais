# Sistema de Arquivos

#### Navegando no sistema de arquivos
 - pwd (saber em que diretório está);
 - cd  (entrar num diretório);
 - ls  (listar o que tem no diretório):
     - l (permissão de acesso  +i (lista o número do i-node) ou +h (mais humana));
     - a (mostra tudo até diretório oculto);
     - S (ordena arquivos por tamanho);
     - X (ordena os arquivos por extensão);
     - t (ordena por tempo de modificação do arquivo);
     - r (ordem inversa/contrária).

#### Copiar (cp)
 - cp <arquivo> <para o path> --> apenas copiar;
 - cp <path+arquivo> <para path+novo_nome_arquivo> --> renomear;
     - r (recursivo) --> cp -r /pasta <para path> --> copia pasta e arquivos;
                     --> cp -r /pasta/* <para path> --> copia apenas os arquivos que estão dentro.

#### Movimentar (mv)
 - mv <path+arquivo> <para path> --> apenas mover e/ou renomear;

#### Leitura e Escrita
Ler apenas 
 - cat <path>
    - marcação de arquivo $ (-e);
    - concatenar arquivos <path+arquivo1> <path+arquivo2> > <para path>.
 - tac <path> (contrário -- fim do arquivo);
 - more <path>(ver arquivo gigantes -- navegar <ctrl + pgup> <ctrl + pgdown> -- enter para ver mais;
 - tail -f <path> -- logs;
 - split -l <nº de linhas> <path> -- quebra e cria os arquivos com as partes do texto;
 - sed?

Escrever --> nano, touch (apenas cria arquivo), cat 'conteudo' arquivo, echo 'conteudo' > arquivo.

#### Informações do arquivo
 - file <arquivo> (o que é?);
 - cksun <arquivo> (hash do linux - como o sha1);
 - cmp <arquivo1> <arquivo2> (faz a comparação das diferenças entre dois arquivos).

#### Diretório
 - rm (remove arquivos e diretórios) -r(remove recursivo -- ./diretorio ou ./diretorio/* só arquivos de dentro).
 - rmdir (remove apenas diretórios).
 - mkdir (cria diretório; -p recursivo de criação).

#### Permissão de Acesso

 - chmod <usuarios> +||- <o que fazer> <nome_arquivo>
   u-dono; g-grupo; o-outros;      --- usuários.
   r-leitura; w-escrita; x-executa. - o que faz.

                      OU

 - chmod <nºdono><nºgrupo><nºoutros> <nome_arquivo>
   0 - Nenhuma permissão de acesso
   1 - Permissão de execução
   2 - Permissão de gravação
   3 - Permissão de gravação e execução
   4 - Permissão de leitura
   5 - Permissão de leitura e execução
   6 - Permissão de leitura e gravação
   7 - Permissão de leitura, gravação e execução

 - chown <novo_dono> <arquivo> //trocar o dono do arquivo.
 - chgrp <novo_grupo> <arquivo> // troca o grupo do arquivo.


#### Permissões especiais
//COMO FOSSE O ROOT
 - bit setID --> sudo chmod u+s <arquivo>
 - bit setGID --> sudo chmod g+s <arquivo>

// Diretório compartilhado, mas só o dono renomeia ou exclui o arquivo.
 - bit sticky --> sudo chmo -t <diretório>

#### Links
 - soft (simbólico): ln -s <path_original> <path_para_lincar> --> aponta para o arquivo (virtual)
 - hard: ln <path_original> <path_para_duplicar> --> mesmo i-node, mesma mudança nas permissões, arquivo está en dois pontos. (físico)