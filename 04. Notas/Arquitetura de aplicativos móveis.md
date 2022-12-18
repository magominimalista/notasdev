# O que é isso?

A arquitetura móvel é um roteiro de como o aplicativo móvel é construído e consiste em várias regras e técnicas. Uma arquitetura móvel bem pensada pode permitir o rápido desenvolvimento dos recursos do aplicativo, seguindo os padrões do setor e garantindo produtos finais escaláveis, sustentáveis e de alta qualidade.

# Camadas

Em um nível básico, a arquitetura de aplicativos móveis consiste em três camadas: Apresentação, Negócios e Dados.

# Apresentação

A camada de apresentação consiste em componentes de interface do usuário, interfaces de usuário responsáveis pela aparência do aplicativo. É responsável pela experiência do usuário, que fornece aos usuários finais uma maneira de interagir com o aplicativo, utilizando botões, links, vídeo, imagens etc. A camada de apresentação é altamente influenciada pelas diretrizes e estratégias de marca do produto.

# Negócio

A camada de negócios é responsável por converter os dados de uma maneira significativa para o usuário final. Consiste em processos e regras relacionados a operações de dados, cache, validação, registro, tratamento de erros e exceções, etc. A camada de negócios pode estar no dispositivo do usuário, no servidor ou em ambos, dependendo dos requisitos.

# Dados

A camada de dados é responsável por gerenciar o acesso e as transações de dados. Essa camada pode ser dividida em duas camadas: Repositório e Rede. A camada de repositório é responsável por fornecer dados por meio de interfaces API e implementar a estratégia de persistência local, se necessário. A camada de rede é responsável por fornecer roteamento das APIs via comunicação em rede e manipular erros de rede.

# Arquiteturas

A arquitetura móvel correta pode ajudar a resolver muitos desafios de desenvolvimento móvel e pode levar a aplicativos móveis escaláveis e sustentáveis. Essas arquiteturas permitem a separação de responsabilidades e aumentam a modularidade, flexibilidade, testabilidade e manutenção. Abaixo estão padrões de arquitetura de aplicativos móveis amplamente usados que podem ajudar a resolver os desafios que acompanham o desenvolvimento de aplicativos.

# MVC

O MVC é uma das abordagens de arquitetura mais familiares. Ele separa o aplicativo móvel em três camadas com suas responsabilidades separadas. A visualização é responsável por renderizar elementos da interface do usuário e observar o modelo para quaisquer alterações de dados. Pode haver várias visualizações que podem ser mapeadas para o Controlador. O controlador lida com ações do usuário e processa dados através do modelo e atualiza a interface do usuário com base no modelo. O modelo gerencia a manipulação de dados com base nas regras de negócios.

![](https://miro.medium.com/max/700/0*zZAqpHxSnaF-1fLb)

# MVP

MVP é semelhante ao MVC. Ele substitui Controller pelo Presenter. A visualização é responsável por renderizar elementos da interface do usuário e observar o modelo para quaisquer alterações de dados. A visualização tem um mapeamento individual com o apresentador. O apresentador lida com ações do usuário e processa dados através do Model e atualiza a interface do usuário com base no modelo. O modelo gerencia a manipulação de dados com base nas regras de negócios. Compare com MVC, Model e View não interagem diretamente no MVP, permitindo uma melhor dissociação.

![](https://miro.medium.com/max/700/0*vrZtzQQOxhfTEEMY)

# MVVM

O MVVM é uma abordagem relativamente nova para a arquitetura móvel. Neste modelo e visualização, comportam-se da mesma maneira que MVC e MVP. Várias visualizações podem ser mapeadas para o ViewModel. O MVVM lida com ações do usuário e processa dados através do Model, no entanto, o fluxo de dados do Model para o ViewModel e o ViewModel para o View é tratado pelos observadores e fornece maior dissociação em comparação com o MVC e o MVP.

![](https://miro.medium.com/max/700/0*5kuijWDlRoZFRBVU)

# VIPER

O Viper é um padrão de arquitetura relativamente novo usado principalmente para o desenvolvimento de aplicativos iOS. Ele fornece maior separação de responsabilidades em comparação com o MVC, amplamente usado para aplicativos iOS. Nesta arquitetura, o View é responsável por renderizar elementos da interface do usuário. O apresentador lida com a entrada da interface do usuário e mantém a lógica da interface do usuário e aciona as alterações da interface do usuário. O interactor contém a lógica de negócios. O roteador é responsável pela navegação e a Entity é responsável pelo gerenciamento do objeto de dados usado pelos interatores.

![](https://miro.medium.com/max/700/0*Ykqfp8X_2gQ4Cdk4)

# Diferenças principais

# Arquitetura recomendada — MVVM, VIPER

As arquiteturas móveis estão em constante evolução. A chave para selecionar arquiteturas móveis exige que consideremos seguir critérios importantes.

# Manutenção / Extensibilidade

Os componentes do aplicativo devem ser fáceis de modificar para permitir correções de bugs e aprimoramentos de desempenho. Deve permitir a implementação rápida de alterações para oferecer suporte a novos aprimoramentos para oferecer suporte a novos recursos de plataforma ou requisitos de negócios

# Testabilidade

Vários componentes de aplicativos na arquitetura do aplicativo devem ser fáceis de testar individualmente, o que pode levar a um número reduzido de bugs e melhor confiabilidade.

# Reutilização

A arquitetura do aplicativo deve ser modular e deve suportar a reutilização dos vários componentes para desenvolvimentos mais rápidos de recursos e qualquer redesenho futuro.

# Segurança

A arquitetura do aplicativo deve ser robusta e deve ser capaz de proteger os dados do usuário

# Escalabilidade

A arquitetura do aplicativo deve ser escalável para oferecer suporte ao desenvolvimento paralelo dos vários recursos

Tendo em mente os critérios acima, duas arquiteturas realmente se destacam: MVVM e Viper. O MVVM pode ser adotado com muita facilidade para Android devido ao suporte fora de caixa com o componente ViewModel. O Viper é amplamente utilizado no desenvolvimento de aplicativos para iOS Viper e leva a separação de preocupações um passo além do MVVM. Essas são ótimas escolhas. O MVVM com um pouco menos de separação de preocupações pode reduzir a sobrecarga, no entanto, o Viper fornecerá melhor testabilidade devido à maior separação de preocupações.