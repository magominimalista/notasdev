## Versão curta

-   A mesclagem pega todas as alterações em uma ramificação e as mescla em outra ramificação em uma confirmação.
-   Rebase diz que quero o ponto em que me ramifiquei para passar para um novo ponto de partida

Então, quando você usa um?

### Mesclar

-   Digamos que você tenha criado uma filial com o objetivo de desenvolver um único recurso. Quando você deseja trazer essas alterações de volta ao mestre, provavelmente deseja **mesclar**.

### Rebase

-   Um segundo cenário seria se você começasse a desenvolver e outro desenvolvedor fizesse uma alteração não relacionada. Você provavelmente quer puxar e depois **rebase** para basear suas alterações na versão atual do repositório.

**Esmagamento**: Todas as confirmações são preservadas nos dois casos ( por exemplo: "adicionar recurso", depois "tipos" e "oops erro de digitação novamente" ... ). As confirmações podem ser combinadas em uma única confirmação esmagando. A eliminação pode ser feita como parte de uma operação de mesclagem ou rebase ( - sinalizador de squash ); nesse caso, é frequentemente chamado de mesclagem de squash ou resbase de squash.

**Puxar solicitações**: Servidores git populares ( Bitbucket, GitLab, GitHub, etc ... ) permitem configurar como as solicitações pull são mescladas por repositório. a interface do usuário pode mostrar uma "mistura" botão por convenção, mas o botão pode executar qualquer operação com sinalizadores ( palavras-chave: mesclar, rebase, squash, avanço rápido ).


----

É simples. Com o rebase, você diz para usar outra ramificação como a nova **base** pelo seu trabalho.

Se você tem, por exemplo, uma filial `master`, você cria uma ramificação para implementar um novo recurso e diz que o nome `cool-feature`, é claro, o ramo principal é a base do seu novo recurso.

Agora, em um determinado momento, você deseja adicionar o novo recurso implementado no `master` ramo. Você poderia simplesmente mudar para `master` e mesclar o `cool-feature` ramo:

```
$ git checkout master
$ git merge cool-feature
```

Mas desta forma um novo commit fictício é adicionado. Se você quiser evitar a história do espaguete, pode **rebase**:

```
$ git checkout cool-feature
$ git rebase master
```

E então mesclar `master`:

```
$ git checkout master
$ git merge cool-feature
```

Desta vez, como o ramo de tópicos tem as mesmas confirmações de mestre e as confirmações com o novo recurso, a mesclagem será apenas um avanço rápido.

#Git 