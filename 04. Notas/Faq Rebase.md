
Acabei de criar uma FAQ para minha equipe com minhas próprias palavras, que responde a essa pergunta. Deixe-me compartilhar:

## O que é um `merge`?

Um commit, que combina todas as alterações de um ramo diferente no atual.

## O que é um `rebase`?

Re-cometer todos os commits da ramificação atual em um commit base diferente.

## Quais são as principais diferenças entre `merge` e `rebase`?

1.  `merge` executa apenas **um** novo commit. `rebase` normalmente executa **múltiplo** ( número de confirmações na ramificação atual ).
2.  `merge` produz um **novo** confirmação gerada ( o chamado compromisso de mesclagem ). `rebase` apenas se move **existente** comete.

## Em que situações devemos usar um `merge`?

Usar `merge` sempre que desejar adicionar alterações de uma ramificação ramificada **de volta** no ramo base.

Normalmente, você faz isso clicando no botão "Mesclar" em Solicitações de puxar / mesclar, por exemplo no GitHub.

## Em que situações devemos usar um `rebase`?

Usar `rebase` sempre que você quiser adicionar **alterações de uma ramificação base** de volta a um ramo ramificado.

Normalmente, você faz isso em `feature` ramificações sempre que houver uma mudança no `main` ramo.

## Por que não usar `merge` mesclar alterações do ramo base em um ramo de recurso?

1.  A história do git incluirá muitos **confirmações de mesclagem desnecessárias**. Se várias mesclagens forem necessárias em um ramo de recurso, o ramo de recurso poderá conter ainda mais confirmações de mesclagem do que confirmações reais!
    
2.  Isso cria um loop que **destrói o modelo mental pelo qual o Git foi projetado** o que causa problemas em qualquer visualização da história do Git.
    
    Imagine que há um rio ( por exemplo. o "Nilo" ). A água está fluindo em uma direção ( direção do tempo na história do Git ). De vez em quando, imagine que há um ramo naquele rio e suponha que a maioria desses galhos se funde de volta ao rio. É assim que o fluxo de um rio pode parecer naturalmente. Faz sentido.
    
    Mas imagine que há um pequeno ramo daquele rio. Então, por algum motivo, **o rio se funde no ramo** e o ramo continua a partir daí. O rio agora desapareceu tecnicamente, agora está no ramo. Mas então, de alguma forma magicamente, esse ramo é fundido de volta ao rio. Qual rio você pergunta? Eu não sei. O rio deveria estar no ramo agora, mas de alguma forma ele ainda continua a existir e eu posso fundir o ramo de volta ao rio. Então, o rio está no rio. Meio que não faz sentido.
    
    É exatamente o que acontece quando você `merge` o ramo base em um `feature` ramificar e depois quando o `feature` ramificação concluída, você mescla isso de volta ao ramo base novamente. O modelo mental está quebrado. E por isso, você acaba com uma visualização de ramificação que não ajuda muito.
    

## Exemplo de histórico de Git ao usar `merge`:

[![Exemplo de histórico de Git ao usar mesclar](https://i.stack.imgur.com/Oqqmm.png)](https://i.stack.imgur.com/Oqqmm.png)

Observe as muitas confirmações começando com `Merge branch 'main' into ...`. Eles nem existem se você rebase ( lá, você só terá confirmações de mesclagem de solicitações de puxar ). Também muitos loops de mesclagem de ramificação visual (`main` para `feature` para `main`).

## Exemplo de histórico de Git ao usar `rebase`:

[![Exemplo de histórico de Git ao usar rebase](https://i.stack.imgur.com/0ZVla.png)](https://i.stack.imgur.com/0ZVla.png)

Um histórico do Git muito mais limpo, com muito menos confirmações de mesclagem e nenhum ramo visual desordenado, mescla loops.

## Existem desvantagens / armadilhas com `rebase`?

Sim:

1.  Porque um `rebase` os movimentos confirmam ( os executam tecnicamente ), a data de confirmação de todos os commits movidos será a hora do rebase e **o histórico do git pode parecer que perdeu o tempo de confirmação inicial**. Portanto, se a data exata de um commit for necessária em todas as ferramentas por algum motivo `merge` é a melhor opção. Mas, normalmente, um histórico limpo de git é muito mais útil do que as datas exatas de confirmação. E o [data do autor](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/managing-contribution-settings-on-your-profile/troubleshooting-commits-on-your-timeline#how-github-uses-the-git-author-date-and-commit-date) O campo continuará mantendo a data de confirmação original, quando necessário.
    
2.  Se a ramificação rebase tiver várias confirmações que alteram a mesma linha e essa linha também foi alterada na ramificação base, pode ser necessário resolver conflitos de mesclagem para a mesma linha várias vezes, o que você nunca precisa fazer ao mesclar. Então, em média, há mais conflitos de mesclagem a serem resolvidos.
    

## Dicas para reduzir conflitos de mesclagem ao usar `rebase`:

1.  **Rebase frequentemente**. Normalmente, recomendo fazê-lo pelo menos uma vez por dia.
2.  Tente **mudanças de abóbora** na mesma linha em um commit, tanto quanto possível.

#Git