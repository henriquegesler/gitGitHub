## Git e GitHub - Comandos e conceitos.
Comando: |	Descrição:
------------ | -------------
git config --local user.name | "Seu nome"	Define o nome localmente.
git config --local user.email | "Seu e-mail"	Define o endereço de e-mail localmente.
git config --global user.name | "Seu nome"	Define o nome globalmente.
git config --global user.email | "Seu e-mail"	Define o endereço de e-mail globalmente.
git config --global --list |	Lista as configurações globais.
git config --global core.editor | "code --wait"	Define o Visual Studio Code como editor padrão.
git config --global core.editor | "vim"	Define o vim como editor padrão.
git config --global --unset core.editor |	Volta para o editor padrão.
git init |	Cria um repositório Git.
git status |	Analisa o estado do repositório.
git add nomeDoArquivo |	Marcar o arquivo para ser salvo (commitado).
git add . |	Coloca todos arquivos (novos, modificados e removidos) no index/stage. Usando o ponto, será adicionado ao stagging somente os arquivos a partir do diretório que você está, e os sub-diretórios deste.
git add --all |	Coloca todos arquivos (novos, modificados e removidos) no index/stage. Adiciona ao staging arquivos desde a raiz do repositório passando por todos os subdiretórios, e aqui está a diferença, não importa se você está na raiz ou no sub-diretório.
git commit -m "Mensagem" |	Realiza o commit com o título.
git commit -m "Mensagem" -m "Descrição" |	Realiza o commit com o título e descrição.
git commit -a -m "Mensagem" |	Adiciona todos os arquivos e realiza o commit.
git log --oneline |	Lista os logs em linhas de forma mais limpa.
git log -p |	Lista os logs com mais detalhes, mostrando o que aconteceu no projeto.
git log --graph --oneline --all |	Todos os logs super detalhados.
git log --help |	Ver algumas opções disponíveis.
git log cheatsheet |	Comandos para personalizar a busca de logs.
gitk |	Visualizador de histórico gráfico.
git init --bare |	Cria um repositório que não terá a working tree, ou seja, não conterá uma cópia dos arquivos. Como o repositório servirá apenas como servidor, para que outros membros da equipe sincronizem seus trabalhos, poupa espaço de armazenamento desta forma.
git remote add nome-repositorio caminho/para/o/repositorio	Desta forma teremos um link do repositório local com o repositório remoto, que chamamos de nome-repositorio, que está armazenado em caminho/para/o/repositorio.
git remote |	Lista os remotes.
git remote -v |	Lista os nomes e endereços.
git remote rename nome-atual novo-nome |	Renomea o remote.
git remote add origin https://github.com/usuario/projeto.git |	Adiciona o repositório remoto no diretório local.
git remote set-url origin https://github.com/usuario/projeto.git |	Outra maneira de adicionar o repositório remoto no diretório local.
git clone url nome |	Baixa o repositório localmente. Nome é opcional caso queira definir um nome diferente do original.
git clone -b nome-branch repositorio-remoto-url |	Baixa o repositório localmente em um branch específico.
git clone --branch nome-branch repositorio-remoto-url |	Outra maneira de baixar o repositório localmente em um branch específico.
git push origin main |	Envia os dados para o repositório remoto. Se utilizar git push -u origin main ficará salvo e na próxima vez rodar somente: git push.
git pull |	Atualiza as informações do repositório local.
git branch nome-branch |	Cria uma branch.
git branch |	Lista as branches.
git checkout nome-branch |	Muda de branch.
git switch nome-branch |	Muda de branch.
git checkout -b nome-branch |	Cria e entra na branch.
git checkout - |	Volta para a branch anterior sem escrever o nome.
git branch -m novo-nome |	Renomeia a branch, se estiver dentro dela.
git branch -m nome-atual novo-nome |	Renomeia a branch, dentro de outra branch.
git branch -D nome-branch |	Deleta a branch.
git merge nome-branch-secundaria |	Caso tenha commits fora da branch principal e ocorreu um BUG na branch principal. Acessar a branch principal, corrigir o erro e rodar o comando.
git rebase nome-branch-secundaria |	O merge junta os trabalhos e gera um merge commit. O rebase aplica os commits de outra branch na branch atual.
git rebase -i |	Deixa o usuário editar a lista de commits para liberar.
git checkout -- nome-arquivo |	Descarta alterações de em arquivo.
git reset HEAD nome-arquivo |	Desmarcar o arquivo para ser commitado.
git reset --soft HEAD^ |	Configura HEAD para o commit anterior e deixa as mudanças do commit desfeito no stage/index.
git revert nome-hash |	Remove as alterações no código do commit.
git stash |	Salva os dados modificados para depois.
git stash save "mensagem" |	Salva os dados modificados para depois com contexto.
git stash list |	Lista os estados salvos.
git stash clear |	Limpa os estados.
git stash apply numero-array |	Aplica as modificações.
git stash drop numero-array |	Remove as modificações.
git stash pop numero-array |	Aplica e remove do stash.
git checkout nome-hash |	Viajando no tempo. Não é possível editar e salvar, apenas se criar uma nova branch ou entrar dentro da master.
git diff nome-commit..nome-commit |	Mostra as diferenças entre dois commits.
git rm -rf --cached nome-diretorio/ |	Remove o arquivo/diretório dos arquivos monitorados.
git diff |	Mostra o que foi alterado e o que ainda não foi adicionado para ser commitado.
git tag -a versao-0.1.0 -m "Lançando a primeira versão." |	Cria um ponto que não pode ser mais modificado.
git tag |	Lista as versões.
git push origin main versao-0.1.0 |	Subindo a versão.
git cherry-pick id-commit |	Selecionar commit específico para trazer ao branch desejado.
git config --global init.defaultBranch main |	Configurando o git para iniciar sempre com a branch main ao invés da master (git init). A partir da versão 2.28.
<table>
 <tr>
    <td>
      git bisect start<br>
      git bisect good commit<br>
      git bisect bad commit<br>
      git bisect reset
    </td>
    <td>
      Achar um commit que quebra o build do projeto. <br>Indica um commit que contém um estado bom do seu repositório (good) e um commit que contém um estado ruim do seu repositório (bad). Com isso o git vai realizando checkouts, seguindo uma busca binária, e você pode indicar se o estado é bom ou ruim. Ao final, o git lhe diz qual commit danificou o repositório.
    </td>
  </tr>
</table>
