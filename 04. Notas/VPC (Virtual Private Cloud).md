A **VPC**, ou _Virtual Private Cloud_ (em português, Nuvem Virtual Privada), é uma parte muito importante da computação na AWS e em outros serviços de Cloud: ajuda a separar aplicações com uma camada a mais de isolamento e protege os dados de aplicações, além de permitir uma proteção extra para a aplicação, ao utilizar redes privadas.

A VPC é um recurso complexo com várias partes que devem se comunicar perfeitamente, que são:

-   Redes públicas
-   Redes privadas
-   Internet gateway
-   NAT gateway
-   Route Tables
-   VPC

Nas redes públicas, encontram-se todos os recursos criados que ganham um endereço de IP público, ou seja, que se conectam diretamente à internet. Porém, esse IP pode mudar quando ligamos e desligamos as máquinas. Se queremos um IP público fixo, podemos usar o Elastic IP, que é pago. Esse tipo de rede é recomendada para os load balancers, e também se a nossa aplicação recebe as requisições diretamente dos clientes; ou em casos de alguns recursos específicos, como o NAT gateway.

Nas redes privadas, todas as máquinas têm um IP privado que só pode ser usado dentro da própria VPC, dando assim uma camada a mais de segurança para as máquinas, já que não estão conectadas diretamente na internet. Para acessarmos essas máquinas via SSH, é necessário usar uma máquina pública como ponte de acesso. Nessa rede, colocamos as nossas aplicações, podendo ser instâncias do EC2, instâncias docker, como o ECS ou o beanstalk, e as instâncias do kubernetes.

O internet gateway permite que os recursos na rede pública possam acessar à internet como se fosse o modem que a operadora instala nas casas, fazendo a ligação das redes com a internet.

O NAT gateway é um recurso que deve ficar na rede pública para receber todas as requisições que vêm da rede privada e enviá-las para o internet gateway, como se fosse um roteador de uma casa, interligando a sua rede ao modem (muitos aparelhos hoje já tem as duas função de modem e roteador; então se você tiver apenas um aparelho em casa saiba que ele faz as duas funções).

Como decidir para onde enviar as requisições? Esse é o trabalho da Route Table, que faz a interligação entre os recursos e permite que tudo se comunique. Então, a rede privada vai ter como alvo o NAT gateway, e a rede pública o internet gateway.

A VPC é o recurso que vai conter todos os outros e permitir com que eles trabalhem em sincronia, cada um realizando uma tarefa.

São vários recursos diferentes. Muitas vezes, temos que criar múltiplos de cada recurso, como as redes públicas e privadas, uma em cada zona de disponibilidade, e garantir assim uma maior resiliência da aplicação.

Para mais informações sobre a VPC, acesse a [documentação oficial](https://docs.aws.amazon.com/pt_br/vpc/latest/userguide/what-is-amazon-vpc.html) da AWS.

Além disso, temos um excelente curso também, específico para você se aprofundar em [VPC](https://cursos.alura.com.br/course/amazon-vpc).

#AWS 