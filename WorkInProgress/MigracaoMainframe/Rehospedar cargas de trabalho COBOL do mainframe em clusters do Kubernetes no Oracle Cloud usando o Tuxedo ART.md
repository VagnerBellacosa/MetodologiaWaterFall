# Rehospedar cargas de trabalho COBOL do mainframe em clusters do Kubernetes no Oracle Cloud usando o Tuxedo ART



Conteúdo

- 

  [Rehospedar Cargas de Trabalho COBOL do Mainframe para Clusters do Kubernetes no Oracle Cloud Usando o Tuxedo ART](https://docs.oracle.com/pt-br/solutions/mainframe-to-oke/index.html#GUID-62C2D618-F3D3-4A9F-BF80-A70B8751A3B6)

  - [Arquitetura](https://docs.oracle.com/pt-br/solutions/mainframe-to-oke/index.html#GUID-201AA3BB-BBD6-47D5-AC9A-AC524FB047E7)
  - [Recomendações](https://docs.oracle.com/pt-br/solutions/mainframe-to-oke/index.html#GUID-CF66CD1D-6890-489F-802F-7E81CC3E7011)
  - [Considerações](https://docs.oracle.com/pt-br/solutions/mainframe-to-oke/index.html#GUID-F2E75A8C-B120-43AD-85D8-C1E664AE3C87)
  - [Explorar Mais](https://docs.oracle.com/pt-br/solutions/mainframe-to-oke/index.html#GUID-BD212B6E-FF5B-4F40-A8BD-54A13626FCD5)

Help us improve the Oracle Architecture Center

[Take this survey](https://surveys.oracle.com/ci/documents/detail/5/462/12/d8347b9ff0cdd3cc9e34fdc61eb75259ddd2dc16)



Modernize suas cargas de trabalho de mainframe e torne-as mais ágeis, abertas e econômicas, reinicializando os clusters do Kubernetes no Oracle Cloud. Aproveite as tecnologias de ponta, como aprendizado de máquina e bancos de dados na memória para obter insights mais profundos sobre seus clientes e operações.



### Arquitetura

Esta arquitetura mostra os aplicativos de mainframe migrados para contêineres gerenciados pelo Oracle Cloud Infrastructure Container Engine for Kubernetes (OKE). A camada de dados consiste em um par de sistemas de BD Exadata de trimestre stand-by ativo.

O Tuxedo Application Rehosting (ART) Workbench ajuda a simplificar e acelerar a reinicialização do mainframe automatizando a migração de código e dados. Com base na tecnologia avançada de processamento de linguagem usada em migrações em larga escala, a bancada integra as ferramentas necessárias para adaptar o código COBOL, DB2 SQL e transformar a linguagem de controle de cargo (JCL). Ele também inclui ferramentas de migração de dados, que executam análise completa das definições de dados e acesso para gerar esquemas de dados e módulos de acesso lógico. Essas ferramentas criam ferramentas de descarga, recarga e validação de dados para migração automatizada de conjuntos de dados VSAM, arquivos simples e tabelas do DB2 a partir do mainframe.

Um balanceador de carga fornece acesso da internet pública aos seus aplicativos. Para conectividade privada com sua implantação local, você pode usar o Oracle Cloud Infrastructure FastConnect ou o IPSec VPN.

O diagrama a seguir ilustra essa arquitetura de referência.



![A descrição de ibm-mainframe-oke.png é exibida a seguir](https://docs.oracle.com/pt-br/solutions/mainframe-to-oke/img/ibm-mainframe-oke.png)
[Descrição da ilustração ibm-mainframe-oke.png](https://docs.oracle.com/pt-br/solutions/mainframe-to-oke/img_text/ibm-mainframe-oke.html)



A arquitetura tem os seguintes componentes:

- Região

  Uma região do Oracle Cloud Infrastructure é uma área geográfica localizada que contém um ou mais data centers, chamados domínios de disponibilidade. As regiões são independentes de outras regiões e grandes distâncias podem separá-las (entre países ou mesmo continentes).

  Todos os recursos dessa arquitetura são implantados em uma única região.

- Domínios de disponibilidade

  Os domínios de disponibilidade são data centers independentes e independentes em uma região. Os recursos físicos em cada domínio de disponibilidade são isolados dos recursos nos outros domínios de disponibilidade, o que fornece tolerância a falhas. Os domínios de disponibilidade não compartilham infraestrutura, como energia ou resfriamento, ou a rede de domínio de disponibilidade interna. Portanto, é improvável que uma falha em um domínio de disponibilidade afete os outros domínios de disponibilidade na região.

  Todos os recursos desta arquitetura são implantados em um único domínio de disponibilidade.

- Domínios com falha

  Um domínio de falha é um agrupamento de hardware e infraestrutura em um domínio de disponibilidade. Cada domínio de disponibilidade tem três domínios de falha com energia e hardware independentes. Quando você distribui recursos entre vários domínios de falha, seus aplicativos podem tolerar falhas físicas do servidor, manutenção do sistema e falhas de energia dentro de um domínio de falha.

  Para garantir alta disponibilidade, os recursos de camada intermediária nesta arquitetura são distribuídos por todos os domínios de falha no domínio de disponibilidade.

- Rede virtual na nuvem (VCN) e sub-redes

  Um VCN é uma rede personalizável definida por software que você configura em uma região do Oracle Cloud Infrastructure. Como as redes tradicionais de data center, as VCNs oferecem controle total sobre seu ambiente de rede. Um VCN pode ter vários blocos CIDR não sobrepostos que você pode alterar depois de criar o VCN. Você pode segmentar uma VCN em sub-redes, que podem ter escopo para uma região ou para um domínio de disponibilidade. Cada sub-rede consiste em uma faixa contígua de endereços que não se sobrepõem às outras sub-redes na VCN. Você pode alterar o tamanho de uma sub-rede após a criação. Uma sub-rede pode ser pública ou privada.

  A arquitetura tem duas VCNs:

  - Uma das VCNs tem uma sub-rede pública para o balanceador de carga e duas sub-redes privadas para a camada intermediária.

  - A outra VCN tem uma única sub-rede privada para a camada de dados.

    Esta VCN também serve como uma rede hub, para roteamento em trânsito de conexões privadas do data center local para a outra VCN.

- FastConnect

  O Oracle Cloud Infrastructure FastConnect fornece uma maneira fácil de criar uma conexão privada dedicada entre seu data center e o Oracle Cloud Infrastructure. O FastConnect oferece opções de largura de banda mais altas e uma experiência de rede mais confiável quando comparado a conexões baseadas na Internet.

- IPSec VPN

  O VPN Connect fornece conectividade IPSec VPN site a site entre sua rede local e VCNs no Oracle Cloud Infrastructure. O conjunto de protocolos IPSec criptografa o tráfego IP antes que os pacotes sejam transferidos da origem para o destino e decriptografa o tráfego quando ele chega.

- Balanceador de carga

  O serviço Oracle Cloud Infrastructure Load Balancing fornece distribuição de tráfego automatizada de um único ponto de entrada para vários servidores no back-end.

  Essa arquitetura inclui um balanceador de carga público.

- Listas de segurança

  Para cada sub-rede, você pode criar regras de segurança que especifiquem a origem, o destino e o tipo de tráfego que devem ser permitidos dentro e fora da sub-rede.

- Tabelas de rotas

  As tabelas de rota virtuais contêm regras para rotear o tráfego de sub-redes para destinos fora de uma VCN, geralmente por meio de gateways.

- Gateway de pareamento local (LPG)

  Um LPG permite que você pare um VCN com outro VCN na mesma região. Pareamento significa que as VCNs se comunicam usando endereços IP privados, sem o tráfego que atravessa a Internet ou roteamento através de sua rede local.

  As duas VCNs nesta arquitetura estão interligadas de forma privada usando LPGs.

- Gateway de Internet

  O gateway de internet permite o tráfego entre as sub-redes públicas em uma VCN e a internet pública.

  Nessa arquitetura, a VCN usada para o balanceador de carga tem um gateway de internet.

- Gateway NAT

  O gateway NAT permite que recursos privados em uma VCN acessem hosts na Internet, sem expor esses recursos a conexões de internet de entrada.

  Ambas as VCNs nesta arquitetura têm um gateway NAT.

- Gateway de roteamento dinâmico (DRG)

  A DRG é um roteador virtual que fornece um caminho para o tráfego de rede privada entre uma VCN e uma rede fora da região, como uma VCN em outra região Oracle Cloud Infrastructure, uma rede local ou uma rede em outro provedor de nuvem.

  O VCN usado para a camada de dados nesta arquitetura tem um DRG para ativar a conectividade privada com seu data center local usando o FastConnect ou VPN Connect.

- Adaptador de mainframe Tuxedo (TMA)

  Você pode usar o TMA para conectividade entre a nuvem e o mainframe local. Essa conectividade é privada e usa o recurso de roteamento de trânsito do Oracle Cloud Infrastructure. O tráfego da FastConnect ou IPSec VPN é roteado pelo DRG da camada de dados VCN, que serve como hub para o VCN falado usado para a camada intermediária do Tuxedo.

- Gateway de serviço

  O gateway de serviço fornece acesso de uma VCN a outros serviços, como Oracle Cloud Infrastructure Object Storage. O tráfego da VCN para o serviço Oracle percorre a malha de rede Oracle e nunca atravessa a Internet.

  A VCN usada para a camada de dados nesta arquitetura tem um gateway de serviço.

- Volumes em blocos

  Com os volumes de armazenamento em blocos, você pode criar, anexar, conectar e mover volumes de armazenamento e alterar o desempenho do volume para atender aos requisitos de armazenamento, desempenho e aplicativo. Depois de anexar e conectar um volume a uma instância, você pode usar o volume como um disco rígido regular. Você também pode desconectar um volume e anexá-lo a outra instância sem perder dados.

- Armazenamento de objetos

  O armazenamento de objetos fornece acesso rápido a grandes quantidades de dados estruturados e não estruturados de qualquer tipo de conteúdo, incluindo backups de bancos de dados, dados analíticos e conteúdo rico, como imagens e vídeos. Use o armazenamento padrão para armazenamento "quente" que você precisa acessar de forma rápida, imediata e frequente. Use o armazenamento de arquivos para armazenamento "frio" que você retém por longos períodos de tempo e raramente ou raramente acessa.

- Vault

  O Oracle Cloud Infrastructure Vault permite gerenciar centralmente as chaves de criptografia que protegem seus dados e as credenciais secretas que você usa para proteger o acesso aos seus recursos na nuvem.

- Protetor de nuvem

  Você pode usar o Oracle Cloud Guard para monitorar e manter a segurança de seus recursos na nuvem. O Cloud Guard examina seus recursos quanto à fraqueza de segurança relacionada à configuração e monitora operadores e usuários quanto a atividades arriscadas. Quando qualquer problema de segurança ou risco é identificado, o Cloud Guard recomenda ações corretivas e ajuda você a tomar essas ações, com base nas receitas de segurança que você pode definir.

- Zonas de segurança

  As zonas de segurança garantem as melhores práticas de segurança da Oracle desde o início, impondo políticas como criptografia de dados e impedindo o acesso público a redes para um compartimento inteiro. Uma zona de segurança é associada a um compartimento com o mesmo nome e inclui políticas de zona de segurança ou uma "receita" que se aplica ao compartimento e seus subcompartimentos. Não é possível adicionar ou mover um compartimento padrão para um compartimento de zona de segurança.

  Nesta arquitetura, o compartimento que contém os bancos de dados é uma zona de segurança.

- OKE clusters

  O Oracle Cloud Infrastructure Container Engine for Kubernetes é um serviço totalmente gerenciado, escalável e altamente disponível que você pode usar para implantar seus aplicativos em contêiner na nuvem. Você especifica os recursos de computação necessários às suas aplicações e o Container Engine for Kubernetes provisiona-os no Oracle Cloud Infrastructure em uma tenancy existente. O Container Engine for Kubernetes usa o Kubernetes para automatizar a implantação, o dimensionamento e o gerenciamento de aplicativos em contêiner entre clusters de hosts.

  Você pode iniciar os nós OKE com formas que atendam aos seus requisitos de recursos: CPU, memória, largura de banda de rede e armazenamento. A arquitetura tem vários nós OKE que hospedam os seguintes componentes. Para alta disponibilidade, os nós OKE são distribuídos por todos os domínios de falha no domínio de disponibilidade e por duas sub-redes privadas.

  - Quatro nós OKE cada para servidores Tuxedo CICS/IMS e Tuxedo Batch.

    O Oracle Tuxedo Application Runtime for CICS and Batch executa aplicativos de mainframe IBM reimplantados para o Oracle Tuxedo sem alteração na lógica de negócios. O tempo de execução ajuda os aplicativos de mainframe on-line e em lote a serem executados inalterados, preservando décadas de investimento em lógica e dados de negócios e fornecendo os seguintes recursos:

    - Modelos e serviços de programação CICS
    - Contêineres COBOL
    - Suporte a 3270 BMS
    - Funções JCL padrão e utilitários comuns
    - Acesso ao VSAM migrado, DB2
    - Dados de arquivo simples
    - Acesso remoto ao mainframe DB2

    O Oracle Tuxedo Application Runtime for IMS executa aplicativos de mainframe IBM reimplantados para o Oracle Tuxedo sem alteração na lógica de negócios. Ele fornece ambientes IMS MPP e BMP e suporte à tela 3270 MFS. Ele suporta componentes IMS em várias máquinas, semelhante ao IMSplex.

  - Dois nós OKE para o Oracle Tuxedo System and Application Monitor (TSAM).

    O gerenciamento eficaz da pilha de aplicativos é fundamental para reduzir o custo total de propriedade dos aplicativos essenciais da sua empresa. O Oracle Tuxedo System and Application Monitor Plus (TSAM Plus) fornece recursos de gerenciamento de desempenho de aplicativos, gerenciamento de nível de serviço e automação de operações, que você pode usar para melhorar o desempenho e a disponibilidade de aplicativos Tuxedo. Usando um único console, você gerencia e monitora todos os produtos da família Tuxedo.

  - Quatro nós OKE para Conectores do Oracle WebLogic Tuxedo.

    O WebLogic Tuxedo Connector fornece interoperabilidade entre as aplicações do WebLogic Server e os serviços Tuxedo. O conector permite que os clientes do WebLogic Server chamem serviços Tuxedo e que os clientes Tuxedo chamem EJBs (WebLogic Server Enterprise Java Beans) em resposta a uma solicitação de serviço.

- Sistemas de BD Exadata

  O Exadata Cloud Service permite que você aproveite o poder do Exadata na nuvem. Você pode provisionar sistemas X8M flexíveis que permitem adicionar servidores de computação de banco de dados e servidores de armazenamento ao seu sistema à medida que suas necessidades crescem. Os sistemas X8M oferecem rede RoCE (RDMA over Converged Ethernet) para alta largura de banda e baixa latência, módulos de memória persistente (PMEM) e software Exadata inteligente. Os sistemas X8M podem ser provisionados usando uma forma equivalente a um sistema X8 de quarto de rack e, em seguida, os servidores de banco de dados e armazenamento podem ser adicionados a qualquer momento após o provisionamento.

  Esta arquitetura tem um par de sistemas de BD Exadata stand-by ativo. Eles estão conectados a duas sub-redes privadas para tráfego de cliente e backup. O Oracle Data Guard é usado para sincronização e failover de dados.



### Recomendações

Use as recomendações a seguir como ponto de partida para planejar sua arquitetura no Oracle Cloud. Seus requisitos podem ser diferentes da arquitetura descrita aqui.

- Cloud guard

  Clone as receitas padrão fornecidas pela Oracle para criar receitas personalizadas de detector e resposta. Em suas receitas, você pode especificar o tipo de problemas de segurança a serem detectados e a resposta para cada tipo de problema detectado. Por exemplo, você pode considerar um bucket visível publicamente no Oracle Cloud Infrastructure Object Storage como um risco de segurança que deve ser detectado e corrigido.

  A Oracle recomenda que você ative o Cloud Guard no nível da tenancy, abrangendo o escopo mais amplo. Com essa abordagem, você pode reduzir a carga administrativa de manter configurações de segurança separadas para compartimentos individuais.

  Você também pode usar o recurso *de lista gerenciada* para facilitar a definição do escopo de suas regras de monitoramento e resposta de segurança.

  Para obter mais informações, consulte a documentação do Cloud Guard.

- Zonas de segurança

  Um compartimento de zona de segurança impõe políticas de segurança pré-configuradas rigorosas que não podem ser modificadas. Por exemplo, quaisquer dados em uma zona de segurança devem ser criptografados usando chaves gerenciadas pelo cliente que você gerencia no serviço Oracle Cloud Infrastructure Vault.

  A Oracle recomenda que você use um compartimento de zona de segurança para recursos que exigem uma sub-rede privada. Não é possível criar sub-redes públicas em um compartimento de zona de segurança.

  Para obter mais informações, consulte a documentação de Zonas de Segurança.

- VCN

  Ao criar uma VCN, determine o número de blocos CIDR necessários e o tamanho de cada bloco com base no número de recursos que você planeja anexar a sub-redes na VCN. Use blocos CIDR que estejam dentro do espaço de endereço IP privado padrão.

  Selecione blocos CIDR que não se sobreponham a nenhuma outra rede (no Oracle Cloud Infrastructure, seu data center local ou outro provedor de nuvem) para a qual você pretenda configurar conexões privadas.

  Depois de criar um VCN, você poderá alterar, adicionar e remover seus blocos CIDR.

  Ao projetar as sub-redes, considere o fluxo de tráfego e os requisitos de segurança. Anexe todos os recursos em uma camada ou função específica à mesma sub-rede, que pode servir como um limite de segurança.

- Clusters OKE

  Se você criar os clusters usando a console da Web, use a opção Criação Personalizada para especificar uma VCN e uma sub-rede para implantação. Use uma forma Flex, que permite personalizar o processador e os recursos de memória ao criar ou redimensionar os nós. Para uma implantação grande, você pode usar clusters maiores do OKE.

- Registro do contêiner

  O Oracle gerencia o registro, para que você não precise escolher o tamanho ou quaisquer outras opções. A Oracle recomenda que você crie um registro privado, como melhor prática de segurança.

- Banco de Dados

  Essa arquitetura usa sistemas de BD Exadata de trimestre. Se você precisa de mais poder de processamento, você pode habilitar núcleos extras em múltiplos de dois. Dependendo das cargas de trabalho do banco de dados e do poder de processamento necessário, você pode ampliar o banco de dados.

- Balanceador de carga

  Use a forma de 100 Mbps.

- Armazenamento de objetos

  Use o Oracle Cloud Infrastructure Object Storage para armazenar backups do banco de dados. Crie seus buckets em um compartimento de zona de segurança para que sua visibilidade seja garantida como privada.

- Volumes em blocos

  Comece com um tamanho de 50 GB e a opção de desempenho balanceado. Você pode dimensionar o tamanho e ajustar a opção de desempenho com base nas necessidades do seu negócio.



### Considerações

Ao projetar a topologia para reinicializar cargas de trabalho do mainframe no Oracle Cloud, considere os seguintes fatores:

- Escalabilidade

  - Camada de aplicações:

    Você pode escalar os servidores de aplicativos verticalmente alterando a forma das instâncias de computação. Uma forma com maior contagem de núcleos fornece mais memória e largura de banda de rede. Se precisar de mais armazenamento, aumente o tamanho dos volumes em blocos anexados ao servidor de aplicativos.

  - Camada de banco de dados:

    Você pode escalar os bancos de dados verticalmente ativando mais núcleos para o sistema de BD Exadata. Você pode adicionar OCPUs em múltiplos de dois para um quarto de rack. Os bancos de dados permanecem disponíveis durante uma operação de dimensionamento. Se sua carga de trabalho exceder as CPUs e o armazenamento disponíveis, você poderá migrar para um rack maior.

- Disponibilidade

  Para cargas de trabalho implantadas em um único domínio de disponibilidade, você pode garantir a resiliência distribuindo os recursos pelos domínios de falha, conforme mostrado nesta arquitetura. Se você planeja implantar sua carga de trabalho em uma região que tenha mais de um domínio de disponibilidade, poderá distribuir os recursos entre vários domínios de disponibilidade.

  Na camada de dados, use o Oracle Data Guard para sincronização de dados e failover entre os bancos de dados principal e stand-by.

- Custo

  - Camada de aplicações:

    Selecione formas de computação com base nos núcleos, memória e largura de banda de rede de que seus aplicativos precisam. Você pode começar com uma forma de quatro núcleos para os servidores de aplicativos. Se você precisar de mais desempenho, memória ou largura de banda da rede, poderá alterar para uma forma maior.

  - Camada do banco de dados:

    Cada OCPU ativada no rack do Exadata precisa de licenciamento para o Oracle Database Enterprise Edition e as opções de banco de dados e os pacotes de gerenciamento que você planeja usar.

- Backups

  - Aplicativo:

    O Oracle Cloud Infrastructure faz backup automático de bancos de dados autônomos e retém os backups por 60 dias. Você pode restaurar e recuperar seu banco de dados a qualquer momento durante o período de retenção. Você também pode criar backups manuais para complementar os backups automáticos. O bucket do Oracle Cloud Infrastructure Object Storage criado armazena backups manuais e os retém por 60 dias.

  - Banco de Dados:

    O serviço Oracle Cloud Infrastructure Block Volumes permite criar backups pontuais de dados em um volume em blocos. Você pode restaurar esses backups para novos volumes a qualquer momento.

    Você também pode usar o serviço para fazer um backup pontual e consistente com falhas de um volume de inicialização sem interrupção ou tempo de inatividade do aplicativo. Os volumes de inicialização e em blocos têm os mesmos recursos de backup.

- Segurança

  - Controle de acesso:

    Use as políticas do Oracle Cloud Infrastructure Identity and Access Management para restringir quem pode acessar seus recursos na nuvem e as ações que eles podem executar.

  - Segurança da rede:

    O serviço Networking oferece dois recursos de firewall virtual que usam regras de segurança para controlar o tráfego no nível do pacote: listas de segurança e grupos de segurança de rede (NSG). Um NSG consiste em um conjunto de regras de segurança de entrada e saída que se aplicam somente a um conjunto de VNICs de sua escolha em um único VCN. Por exemplo, você pode escolher todas as instâncias de computação que atuam como servidores Web na camada Web de uma aplicação de várias camadas no seu VCN.

    As regras de segurança NSG funcionam da mesma forma que as regras da lista de segurança. No entanto, para a origem ou destino de uma regra de segurança NSG, você pode especificar um NSG em vez de um bloco CIDR. Dessa forma, você pode gravar facilmente regras de segurança para controlar o tráfego entre dois NSGs na mesma VCN ou o tráfego dentro de um único NSG. Ao criar um sistema de banco de dados, você pode especificar um ou mais NSGs. Você também pode atualizar um sistema de banco de dados existente para usar um ou mais NSGs.



### Explorar Mais

Saiba mais sobre como reinicializar cargas de trabalho do mainframe para o Oracle Cloud.

- [Folha de Dados: *Oracle Tuxedo em Contêineres Docker*](https://docs.oracle.com/pls/topic/lookup?ctx=pt-br/solutions/mainframe-to-oke&id=tuxedo-on-docker-containers-datasheet)
- [Planilha de Dados: *Oracle Tuxedo Application Rehosting Workbench*](https://docs.oracle.com/pls/topic/lookup?ctx=pt-br/solutions/mainframe-to-oke&id=tuxedo-art-workbench-datasheet)
- [Rehospedar cargas de trabalho COBOL do mainframe no Oracle Cloud usando o Tuxedo ART](https://docs.oracle.com/pls/topic/lookup?ctx=pt-br/solutions/mainframe-to-oke&id=MCFXF)
- [*Visão Geral do Cloud Guard*](https://docs.oracle.com/pls/topic/lookup?ctx=pt-br/solutions/mainframe-to-oke&id=oci-using-cloud-guard)
- [*Visão Geral das Zonas de Segurança*](https://docs.oracle.com/pls/topic/lookup?ctx=pt-br/solutions/mainframe-to-oke&id=oci-using-security-zones)
- [Estrutura de práticas recomendadas para o Oracle Cloud Infrastructure](https://docs.oracle.com/pls/topic/lookup?ctx=pt-br/solutions/mainframe-to-oke&id=GVVGQ)

[Título e Informações de Copyright](https://docs.oracle.com/pt-br/solutions/mainframe-to-oke/index.html#copyright-information)

[Acessibilidade da Documentação](https://docs.oracle.com/pt-br/solutions/mainframe-to-oke/index.html#oracle-accessibility)