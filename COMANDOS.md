# COMANDOS DEBIAN SERVER
## Comandos de Navegação
### `cd`
navegação de diretórios
ex: `cd /home/sysadmin`

obs: `cd ..` para voltar à pasta anterior
### `pwd`
exibe o caminho de diretórios
### `ls`
exibe a lista de arquivos do diretório

**Opções Úteis:**
- `-a` exibe todos os arquivos inclusive os que têm *.* na frente.
- `-l` exibe o author, o grupo e as permissões de cada arquivo.
- `-R` lista os arquivos dentro dos diretórios.
### `find`
exibe exatamente o que você está procurando.

**Fórmula:**
`find PASTA OPÇÕES ARGUMENTOS_DAS_OPÇÕES`

**Opções Úteis:**
- `-name` procura pelo nome dos arquivos
- `-size` procura pelo tamanho dos arquivos

**Exemplos:**
- `find /etc -name "*.conf"` exibe todos os *.conf* de */etc*
- `find / -size +100M` exibe os arquivos maiores que *100mb*
## Comandos de Manupulação de Diretórios e Arquivos
### `mkdir` / `rmdir`
criação de diretórios vazios. / remoção de diretórios VAZIOS.
### `touch`
cria um arquivo vazio.
### `file`
retorna o *tipo* do arquivo.
### `nano`
se existente, abre o editor de arquivos, se não, cria o arquivo e já abre o editor.
### `cat`
retorna o conteúdo do arquivo. (não recomendado para arquivos grandes)
### `less`
exibe o conteúdo de um arquivo com paginador. (recomendado para arquivos grandes)
### `head` / `tail`
exibe as primeiras / últimas linhas de um arquivo.

**obs:** `tail -f` exibe o conteúdo em *tempo real*.
### `wc`
exibe o número de *linhas*, *palavras* e *bytes*.

**obs:** `wc -l` exibe apenas o número de *linhas*.
### `grep`
exibe apenas o conteúdo filtrado.

**Exemplos:**
- `getent passwd | grep sysadmin` exibe apenas as linhas que contém *sysadmin*.
- `getent group | grep aluno1` exibe apenas os grupos nos quais *aluno1* faz parte.
### `cp`
copiar diretórios ou arquivos.

**Fórmula:**
`cp OPÇÕES PASTA/ARQUIVO DESTINO`

**Exemplos:**
- `cp arquivo.txt /home/sysadmin` move *arquivo.txt* para */home/sysadmin*.
- `cp -r diretorio/ diretorio2` copia o *diretorio/* e seu conteúdo para *diretorio2*.
- `cp diretorio/* diretorio2` copia apenas os arquivos de *diretorio/* para *diretorio2* (não inclui pastas).
- `cp -r diretorio/* diretorio2` copia todo o conteúdo de *diretorio/* para *diretorio2* (incluindo arquivos e pastas).
### `mv`
mudar a localização ou renomear diretórios ou arquivos.

**Fórmula (renomear):** `mv ARQUIVO.txt NOVO_NOME.txt`

**Fórmula (mover):** `mv ARQUIVO.txt DESTINO`

**Exemplos:**
- `mv batata.txt batatas/` move o arquivo *batata.txt* para dentro de *batatas/*.
- `mv -r flores/ batatas/` move a pasta *flores/* e todo o seu conteúdo para dentro de *batatas/*.
- `mv flores/* batatas/` move apenas os arquivos de *flores/* para dentro de *batatas/* (não inclui pastas).
- `mv flores/* batatas/` move todo o conteúdo de *flores/* para dentro de *batatas/* (inclui arquivos e pastas).
### `rm`
Deletar arquivos e pastas com arquivos.

**Opções:**
- `-I` pergunta antes de remover mais de 3 arquivos ou sub-pastas.
- `-r` remove diretórios e sub-pastas.
- `-v` informa o que está sendo removido.

**Exemplos:**
- `rm batatas/*` vai apagar apenas os arquivos de *batatas/* sem mexer nas sub-pastas.
- `rm -r batatas/*` vai apagar todo o conteúdo de *batatas/*, inclusive as sub-pastas.
- `rm -r batatas/` vai apagar *batatas/* e seu conteúdo.
### `ln`
criação de links/atalhos.

**Exemplos:**
- `ln arquivo1.txt arquivo2.txt` um *hard link* é criado, ambos são o mesmo arquivo. editando um, o outro é editado automaticamente. a exclusão de um não afeta o outro.
- `ln -s arquivo1.txt batata` um atalho para *arquivo1.txt* é criado. se *arquivo1.txt* for excluído, o atalho deixa de funcionar.
## Comandos de Usuários e Grupos
### `whoami`
retorna o nome de usuário de quem está executando.
### `id` 
retorna *UID*, *GID* e *Grupos* do usuário.
### `useradd`
criação de um usuário.

**Opções:**
- `-m` criar diretório home para o usuário.
- `-M` não criar diretório home pro usuário.
- `-N` não criar grupo do usuário.
- `-G` atribuir aquele usuário a tal grupo.
- `-s` definir bash (geralmente */bin/bash*).
- `-c` adiciona um comentário àquele usuário (geralmente seu nome completo).

**Exemplos:**
- `sudo useradd -m -s /bin/bash -G alunos aluno3` cria um usuário com diretório home e bash, dentro do grupo *alunos* e que se chama *aluno5*.
### `usermod`
edição de usuários.

**Opções:**
- `-s` atribuir um shell ao usuário.
- `-d` editar diretório home.
- `-G` define os grupos do usuário. (os grupos antigos são removidos)
- `-aG` atribui novos grupos ao usuário. (mantém os outros grupos)
### `deluser`
remoção de usuários.
### `groupadd`
criação de novos grupos.
### `groupdel`
remoção de grupos.
### `getent`
consulta de usuários e grupos.

**Exemplos:**
- `getent passwd aluno1` consulta o usuário *aluno1*.
- `getent group alunos` consulta o grupo de *alunos*.
## Permissões
### `chown`
mudança de dono e grupo de diretórios ou arquivos.

**Exemplos:**
- `chown aluno1:alunos diretorio_de_alunos` define o dono e grupo de *diretorio_de_alunos* para *aluno1* e *alunos*.
- `chown :funcionarios diretorio_de_funcionarios` retira o dono e atribui o grupo de *diretorio_de_funcionarios* para *funcionarios*.
- `chown -R sysadmin:administradores senhas/` define dono como sysadmin e grupo como administradores da pasta *senhas/* e todas as suas sub-pastas e arquivos recursivamente.
### `chmod`
modificação das permissões do diretório ou arquivo.

**Tutorial de Permissões**
- `750` ou `rwxr-x---` a posição do número *7* se refere ao *dono*, a posição do número *5* se refere ao *grupo*, e a posição do número *0* se refere à *qualquer outro usuário que não seja o dono e que não esteja no grupo selecionado*.
- `4` significa permissão de leitura de arquivos ou listagem de arquivos em diretórios. (r)
- `2` significa permissão de escrita em arquivos ou criação de arquivos/pastas em diretórios. (w)
- `1` significa permissão de execução de arquivos ou entrar em diretórios. (x)

**Explicação:**

o que vai no comando é a soma de permissões.
- `7` é a soma de 4 + 2 + 1, que resulta na permissão total. (rwx)
- `6` é a soma de 4 + 2, que resulta na permissão de ler e escrever, sem executar. (rw-)
- `5` é a soma de 4 + 1, que resulta na permissão de ler e executar, sem escrever. (r-x)

**Exemplos:**
- `chmod 754 diretorio/` forcene permissão total ao dono (7) (rwx), permissão de leitura e execução ao grupo (5) (rw-) e permissão de leitura aos outros (4) (r--).
- `chmod 770 diretorio/` fornece permissão total ao dono e ao grupo (77) (rwx) e deixa os outros sem permissões (0) (---).
- `chmod rwxr-xr-x diretorio/` fornece total permissão ao dono (7) (rwx) e permissão de ler e executar para grupo e outros (55) (r-xr-x).

**Outras Formas de usar `chmod`**
- `chmod u+x arquivo.sh` dono ganha permissão de executar o arquivo.
- `chmod g+w arquivo.txt` grupo ganha permissão de escrever no arquivo.
- `chmod go-r arquivo.txt` grupo e outros perdem permissão de ler o arquivo.
- `chmod u=rwx,go=r-x diretorio/` dono ganha permissão total, grupo e outros ganham permissão de ler e executar.
### `umask`
retorna as permissões que são *tiradas* ao criar um novo arquivo ou diretório.

**Exemplos:**
- `umask 0002` retira a permissão de escrever de outros.
- `umask 0077` retira todas as permissões de grupo e outros.
- `umask 0122` retira a permissão de executar do dono, e a permissão de escrever de grupo e outros.
