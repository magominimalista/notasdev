
## O Git é uma ferramenta poderosa que é ótima para usar quando você sabe como usá-lo.

Eu uso esses recursos do Git há anos em equipes e projetos. Ainda estou desenvolvendo opiniões em torno de alguns fluxos de trabalho ( que gostam de esmagar ou não ), mas as ferramentas principais são poderosas e flexíveis ( e com scripts! ).

# Passando por logs do Git

Os logs do Git são nojentos para sair da caixa.

## git log é básico

Usando `git log` fornece algumas informações. Mas é de resolução extremamente alta e geralmente não é o que você está procurando.

git log

![](https://miro.medium.com/max/700/1*c98MmRRHROTav94yXKNMYw.png)

git log

Sejamos reais. Esses logs não estão impressionando ninguém. Eles são chatos. E eles estão cheios de informações que você realmente não precisa no momento. Você está tentando obter uma compreensão de alto nível do que está acontecendo no seu projeto.

Existe uma maneira melhor.

## git log com mais visibilidade

Usando `--graph` e `--format` podemos obter rapidamente uma visão resumida dos commits do git em nosso projeto.

git log --graph --format = format: '% C ( azul negrito )% h% C ( redefinir ) -% C ( verde negrito )% ar (% C ) redefin (%d% C ( redefinir )% C ( branco mínimo ) -% s% C ( redefinir ) '- all

![](https://miro.medium.com/max/700/1*4ehBjIu4R4ZpjplInGbing.png)

git log --graph --format = format: ’ < > ’ - all

Uau! Estes são alguns registros bonitos! Há até uma aparência de uma árvore ramificada ao lado.

Esses registros mostram quem está trabalhando no quê, quando foram feitas alterações e onde suas alterações se encaixam na imagem maior.

`--graph` adiciona o gráfico da árvore à esquerda. Não é o gráfico mais elegante, mas ajuda a visualizar as alterações nas ramificações do projeto. ([Leia os documentos aqui.](https://git-scm.com/docs/git-log#Documentation/git-log.txt---graph))

`--format` permite personalizar o formato dos seus logs. Existem formatos predefinidos para escolher ou você pode escrever seu próprio formato como este exemplo. ([Leia os documentos aqui.](https://git-scm.com/docs/git-log#_commit_formatting))

`--all` inclui todas as referências, tags e ramificações nos logs (, incluindo ramificações remotas ). Você pode não querer _tudo_ então ajuste isso como achar melhor. ([Leia os documentos aqui.](https://git-scm.com/docs/git-log#Documentation/git-log.txt---all))

[Consulte os documentos do git-log para obter mais informações sobre como você pode nivelar seus logs do git. →](https://git-scm.com/docs/git-log)

# Compreendendo um commit específico

Você geralmente deseja entender o que está acontecendo com um commit específico. `git show` pode mostrar uma visão de alto nível das alterações em um commit, mas também permite ver alterações em arquivos específicos.

## Veja o resumo de uma confirmação

git show < commit > --stat

![](https://miro.medium.com/max/700/1*4Xv0zjyg7aIM7JxQI3usWg.png)

git show < commit > --stat

Usando o `--stat` sinalize que você verá o resumo de confirmação junto com os arquivos alterados e detalhes sobre como eles foram alterados.

## Veja alterações específicas de arquivo para uma confirmação

Quando você quiser mergulhar nas alterações específicas de linha em um arquivo específico, use `git show` com o caminho do arquivo.

git show < commit > - < filepath >

![](https://miro.medium.com/max/700/1*rSKMbIJtmHpGD0shauM-OQ.png)

git show < commit > - < filepath >

Isso fornece alterações específicas de linha para o seu arquivo. Por padrão, ele mostrará alterações de linha, juntamente com 3 linhas adicionais em cada extremidade, para fornecer o contexto de onde as linhas alteradas estão no arquivo.

[Consulte os documentos do git-show para obter mais informações sobre como você pode nivelar seu entendimento de commit do git. →](https://git-scm.com/docs/git-show)

# Fazendo alterações

Você fez uma ramificação no projeto, cometeu algumas alterações em sua ramificação e está pronto para mesclar essas alterações novamente `main`. Desde que você se ramificou, outro engenheiro fez alterações nos mesmos arquivos. 😱

Se você estiver usando um serviço como o GitHub, seu PR informará se você mesclou conflitos.

![](https://miro.medium.com/max/590/0*TChg4N9xfFPE_fbS.png)

Conflito de mesclagem do GitHub

O Git solicitará que você resolva esses conflitos de mesclagem antes de inserir suas alterações novamente `main`. Isso é bom, pois você não quer gastar todo o trabalho duro que os outros estão fazendo.

Para começar a resolver isso localmente, você geralmente seguirá um dos dois caminhos: `merge` ou `rebase`.

## git merge vs git rebase

Quando há alterações no `main` ramo que você deseja incorporar ao seu ramo, você pode _mesclar_ as mudanças em ou _rebase_ seu ramo de um ponto diferente.

**mesclar** pega as alterações de um ramo e as mescla em outro ramo em um _mesclar confirmação_.

git merge origin / main your-branch

**rebase** ajusta o ponto em que uma ramificação realmente ramificou ( i.e. move a ramificação para um novo ponto de partida a partir da ramificação base ).

origem da rebase git / principal seu ramo

_Geralmente,_você vai usar `rebase`quando houver alterações em uma ramificação a montante (, como `main`) que você deseja incluir em sua filial. Você vai usar `merge`quando houver alterações em uma ramificação na qual você deseja colocar novamente `main`.

## Esmagar ou não esmagar

Eu costumava ser pró-agitação. Mas um artigo de 

[Dr. Derek Austin 🥳](https://medium.com/u/e5294c417caf?source=post_page-----ef6d741c898e--------------------------------)

mudei de opinião sobre isso. Eu recomendo o artigo e não acho que tenho algo útil para adicionar além do que ele disse.

[

## Por que eu prefiro compromissos regulares de mesclagem em compromissos de squash

### Eu costumava pensar que os commits de abóbora eram tão legais, e então eu tinha que usá-los o dia todo, todos os dias. Eis por que você deve evitar…

bestprogramming.pub



](https://betterprogramming.pub/why-i-prefer-regular-merge-commits-over-squash-commits-cadd22cff02c)

# Recursos

-   [documentação git-log](https://git-scm.com/docs/git-log)
-   [documentação do git-show](https://git-scm.com/docs/git-show)
-   [Quando você usa o Git rebase em vez do Git merge? ( Fluxo de pilha )](https://stackoverflow.com/a/804156)

#Git 