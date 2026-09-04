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
- `-l` exibe o author e o grupo de cada arquivo.
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
### `groupadd`
criação de novos grupos.
### `getent`
consulta de usuários e grupos.

**Exemplos:**
- `getent passwd aluno1` consulta o usuário *aluno1*.
- `getent group alunos` consulta o grupo de *alunos*.
