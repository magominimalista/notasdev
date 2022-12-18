Serverless é um modelo de desenvolvimento nativo em nuvem para criação e execução de aplicações sem o gerenciamento de servidores.

O _provedor de nuvem_¹ fica responsável pelas tarefas rotineiras de _provisionamento²_, manutenção e escala da infraestrutura do servidor.

Os desenvolvedores só precisam empacotar o código em _containers³_ para fazer a implantação.

Depois da implantação, **as aplicações serverless atendem à demanda e aumentam ou diminuem a escala automaticamente de acordo com as necessidades.** As soluções serverless dos provedores de nuvem pública costumam ser oferecidas sob demanda por meio de um modelo de execução orientado a eventos (apenas quando um recurso é solicitado). Por isso, não há cobrança pelas funções serverless não utilizadas.

> Em termos menos técnicos temos um duplicação de recursos em vários servidores espalhados por alguns continentes e quando esses são solicitados o sistema pega o endereço de ip do usuário e fornece o recurso no endereço mais próximo a ele. Esses processamento disparam eventos na nuvem que medem o consumo desses recursos e garantem, uma maior entregabilidade, e escalabilidade por um preço por uso.

Na abordagem tradicional muitas vezes se paga por recursos que não são utilizados, gerando um valor muitas vezes superior para atender uma demanda.

# Quais são os prós e contras da computação serverless?

**Prós**

-   A computação serverless aumenta a produtividade dos desenvolvedores e reduz os custos operacionais. Ela livra os desenvolvedores das tarefas rotineiras de provisionamento e gerenciamento de servidores. Assim, eles têm mais tempo para se concentrar nas aplicações.
-   Com a computação serverless, é mais fácil adotar práticas de DevOps, porque os desenvolvedores não precisam mais descrever explicitamente a infraestrutura que eles querem que a equipe de operações provisione.
-   É possível incorporar componentes completos de soluções de BaaS (Bank as a service) de terceiros para otimizar ainda mais o desenvolvimento de aplicações.
-   Os custos operacionais são reduzidos no modelo serverless porque você paga o tempo de computação baseado em nuvem conforme necessário. Isso não acontece quando você executa e gerencia os próprios servidores o tempo todo.

**Contras**

-   Deixar de executar o seu próprio servidor ou controlar a sua própria lógica no lado dele tem algumas desvantagens.
-   É possível que os provedores de nuvem tenham restrições sobre como as pessoas podem interagir com os componentes. Por sua vez, isso afeta a flexibilidade e a personalização dos sistemas. No caso de ambientes de BaaS, os desenvolvedores podem depender de serviços com código que não pode ser controlado por eles.
-   Abrir mão de controlar esses aspectos do stack de TI também aumenta as chances de dependência de fornecedor. Além disso, quando você decide trocar de provedor, isso pode gerar custos. Você precisará fazer upgrade dos sistemas para que eles atendam às especificações do novo provedor.

Por fim a grande vantagem do Serveless é sua disponibilidade e seu baixo custo. A lembrar que tudo tem seus prós e contras. Resta avaliar se este serviço atende aos requisitos do produto ou serviço em questão.

> ¹ Provedores de serviços de nuvem são empresas que estabelecem nuvens públicas, gerenciam nuvens privadas ou oferecem componentes de cloud computing sob demanda (também conhecidos como serviços de cloud computing), como infraestrutura como serviço (IaaS), plataforma como serviço (PaaS) e software como serviço (SaaS). Os serviços de nuvem podem reduzir os custos de processos empresariais quando comparados à TI on-premise.
> 
> ² O provisionamento **é o processo de definição da infraestrutura de TI**. Ele também se refere às etapas necessárias para gerenciar o acesso aos dados e recursos e para disponibilizá-los a usuários e sistemas.
> 
> ³ Container nada mais é do que um ambiente isolado contido em um servidor que, diferentemente das máquinas virtuais, divide um único host de controle.
