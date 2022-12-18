“Observabilidade” descreve o quão bem você pode entender o que está acontecendo em um sistema, frequentemente instrumentando-o para coletar métricas, logs ou rastreamentos. Na nuvem, a observabilidade pode ser difícil de alcançar devido à grande complexidade do sistema. Seja em data centers ou na nuvem, para atingir a excelência operacional e atender aos objetivos de negócios, você precisa entender o desempenho de seus sistemas. As soluções de observabilidade permitem que você colete e analise dados de aplicativos e infraestrutura para que possa entender seus estados internos e ser alertado, solucionar e resolver problemas com disponibilidade e performance de aplicativos para melhorar a experiência do usuário final.

O modelo monolito a princípio é bem simples de administrar pois lida com um banco de dados, um servidor apenas e não possui integração com outros serviços, desse modo, nesse modelo fica fácil para fazer essa observação de logs e erros gerados pelo mesmo, até porque estamos tratando de uma fonte de observabilidade.

![](https://miro.medium.com/max/700/1*C8tnO9zaCbJs5rqPqpm9ug.jpeg)

Agora imagina em um sistema distribuído onde lidamos com vários micro serviços, diversos bancos de dados diferentes, sistemas de mensagerias, sistemas voltados somente para armazenamento de arquivos (Bucket por exemplo). Imagina um sistema de e-commerce onde temos a separação de estoque, envio do produto … nos dias de hoje isso não é realizado em um único sistema, muitas vezes algumas etapas são comunicações com sistemas de terceiro e gera-se este grande desafio da observabilidade nos cenários de micro serviços.

Pegando esse exemplo da loja virtual, se acontecer um problema de logística, então somente esse setor será afetado e você precisará de uma observabilidade muito boa para encontrar esse problema e tratar ele.

# Desafio

Agir proativamente (recebeu um alerta que algo deu errado) ou reativamente (quando olhamos para os logs e detectamos um problema) em métricas e logs de sistemas distribuídos.

# Pilares da observabilidade

-   Métricas (Contagem de acessos, acessos a recursos, picos de acesso…)
-   Traços distribuídos (Traço de onde vem a requisição até onde chega o problema, conseguir rastrear todo o percurso daquela requisição e por onde passou.)
-   Logs (Através de um sistema de gerenciamento de log é possível extrair informações de um traço distribuído e entender quando aconteceu, qual a mensagem enviada ao usuário…)

# Métricas

Uma das maneiras de fazer esse acompanhamento de métricas no sistema é reunir esses logs para leitura em uma ferramenta que consiga entregar outras funcionalidades de métricas.

E duas dessas ferramentas são Prometheus e Grafana. No Prometheus são definidas os tipos de métricas que se deseja alcancar. Temos as métricas padrão (uso de cpu, disco, memória…) e as métricas personalizadas (contagens de acessos, contagem de logs por tipo de log, por status [404, 500, 201…] …) e as visualizações gráficas dessa computação fica por conta do Grafana.

Pense no Prometheus como uma base de dados para as métricas e o Grafana como o front-end para visualizar essas métricas.


## Prometheus - Monitoring system & time series database
https://prometheus.io/

## Grafana: The open observability platform
https://grafana.com/

Vou deixar aqui um vídeo mais técnico ensinando um pouco mais sobre essas ferramentas.

# Traços distribuídos

Um traço distribuído irá acompanhar uma requisição até o fim dela, pegando todos os caminhos que o usuário passou. Existem 2 maneiras de gerar esses dados, de modo manual através de um script em sua aplicação e de modo automático nos próprios sidecar de kubernets/docker onde sua aplicação estiver rodando. Essa ferramenta é o Jaeger desenvolvida em GO.

## Jaeger: open source, end-to-end distributed tracing

### Monitor and troubleshoot transactions in complex distributed systems

www.jaegertracing.io


E aqui um tutorial simples para entender como funciona caso você queira se familiarizar com a ferramenta.

# Logs

É interessante que os logs do sistema possam ser exportados para consumo por uma ferramenta que irá fazer essa leitura. Vou deixar um vídeo complementar a esse assunto logo abaixo:

Continuando: A maioria das ferramentas para análise de logs são pagas, mas podem ser cruciais para o seu tipo de negócio.

[https://www.graylog.org/](https://www.graylog.org/)


## Kibana: Explore, Visualize, Discover Data | Elastic

https://www.elastic.co/pt/kibana/

![](https://miro.medium.com/max/700/1*qwKKsC-6wyVShTyGNCp_1Q.png)

https://newrelic.com/

Recomendo a leitura desse artigo complementar maravilhoso sobre esse assunto:

https://medium.com/dev-cave/gerenciamento-de-log-com-elk-69133859ca86

# Conclusão

Essa temática é muito importante na vistoria de sistemas distribuídos. Existe muita coisa para se aprender sobre este assunto. O intuito deste texto é criar uma abordagem de contextualização com a Observabilidade.