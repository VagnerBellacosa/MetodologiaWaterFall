# Migração de aplicativos de mainframe

- Artigo - 04/01/2022

  

Ao migrar aplicativos de ambientes de mainframe no Azure, a maioria das equipes segue uma abordagem pragmática: reutilizar onde e quando possível, e, em seguida, iniciar implantação em fases, em que os aplicativos sejam reconfigurados ou substituídos.

Migração de aplicativos normalmente envolvem uma ou mais das seguintes estratégias:

- **Hospedar novamente:** Você pode mover o código existente, os programas e os aplicativos do mainframe e, em seguida, recompilar o código para ser executado em um emulador de mainframe hospedado em uma instância de nuvem. Essa abordagem normalmente inicia com aplicativos de movimento para um emulador baseado em nuvem e, em seguida, migrar o banco de dados para um banco de dados baseado em nuvem. Alguma engenharia e refatoração são necessárias, juntamente com conversões de dados e arquivo.

  Como alternativa, você pode hospedar novamente usando um provedor de hospedagem tradicional. Um dos principais benefícios da nuvem é terceirizar o gerenciamento da infraestrutura. Você pode encontrar um provedor de datacenter que irá hospedar suas cargas de trabalho de mainframe para você. Esse modelo pode comprar o tempo, reduzir o bloqueio de fornecedor e produzir economia de custo provisório.

- **Desativar:** Todos os aplicativos que não são mais necessários devem ser desativados antes da migração.

- **Recompilação:** Algumas organizações optam por reescrever completamente os programas usando técnicas modernas. Devido ao custo e à complexidade adicionais dessa abordagem, isso não é tão comum quanto uma abordagem de comparação de precisão e deslocamento. Muitas vezes após esse tipo de migração, faz sentido começar substituindo módulos e o código usando mecanismos de transformação de código.

- **Substituir:** Essa abordagem substitui a funcionalidade de mainframe por recursos equivalentes na nuvem. Software como serviço (SaaS) é uma opção que está usando uma solução criada especificamente para uma preocupação de empresa, como finanças, recursos humanos, fabricação ou planejamento de recursos empresariais. Além disso, muitos aplicativos específicos do setor agora estão disponíveis para resolver problemas que as soluções de mainframe personalizadas usaram anteriormente para resolver.

Você deve considerar a partir do planejamento das cargas de trabalho que deseja migrar inicialmente e, em seguida, determinar os requisitos para mover os aplicativos associados, as bases de código herdado e os bancos de dados.

## Emulação de mainframe no Azure

Os serviços do Azure podem emular ambientes de mainframe tradicionais, permitindo que você reutilize aplicativos e código de mainframe existentes. Componentes de servidor comuns que você pode emular incluem transação online (OLTP), lotes e sistemas de ingestão de dados.

### Sistemas OLTP

Muitos mainframes têm sistemas OLTP que processam milhares ou milhões de atualizações para grandes números de usuários. Esses aplicativos geralmente usam o processamento de transações e o software de manuseio de formulário de tela, como CICS (sistema de controle de informações do cliente), IMS (sistema de gerenciamento de informações) e TIP (processador de interface de terminal).

Ao mover aplicativos OLTP no Azure, emuladores para monitores (TP) de processamento de transações de mainframe estão disponíveis para serem executado como infraestrutura como serviço (IaaS) usando máquinas virtuais (VMs) no Azure. A funcionalidade de tratamento e a funcionalidade de formulário também podem ser implementados pelo servidores web. essa abordagem pode ser combinada com APIs de banco de dados, como ActiveX Data Objects (ADO), conectividade aberta de banco de dados (ODBC) e Java Database Connectivity (JDBC) para acesso a dados e transações.

### Atualizações em lotes de restrição de tempo

Muitos sistemas de mainframe executam atualizações mensais ou anuais de milhões de registros de conta, como aqueles usados em serviços bancários, seguros e governamentais. Mainframes lidam com esses tipos de cargas de trabalho, oferecendo a sistemas de manipulação de dados de alta taxa de transferência. Trabalhos em lotes de mainframes são normalmente seriais por natureza e dependem das operações de entrada/saída por segundo (IOPS) fornecidas pelo backbone do mainframe para desempenho.

Ambientes de lote baseados em nuvem usam a computação paralela e redes de alta velocidade para o desempenho. Se você precisa o desempenho do lote, o Azure fornece várias opções de rede, armazenamento e computação.

### Sistemas de ingestão de dados

Os mainframes ingerem lotes grandes de dados de varejo, serviços financeiros, fabricação e outras soluções para o processamento. Com o Azure, você pode usar os utilitários de linha de comando simples, como [AzCopy](https://docs.microsoft.com/pt-br/azure/storage/common/storage-use-azcopy-v10) para cópia de dados de local de armazenamento. Você também pode usar o serviço do [Azure Data Factory](https://docs.microsoft.com/pt-br/azure/data-factory/introduction), permitindo a ingestão de dados de armazenamentos de dados diferentes para criar e agendar fluxos de trabalho orientados a dados.

Além dos ambientes de emulação, o Azure fornece plataforma como serviço (PaaS) e análise de serviços que podem melhorar os ambientes existentes do mainframe.

## Migre cargas de trabalho OLTP para o Azure

A abordagem de elevação e deslocamento é a opção sem código para migrar rapidamente os aplicativos existentes para o Azure. Cada aplicativo é migrado “no estado em que se encontra”, o que oferece os benefícios da nuvem sem os riscos ou custos de realização de alterações no código. Usar um emulador para monitores de processamento de transação de mainframe (TP) no Azur com suporte a essa abordagem.

Os monitores TP estão disponíveis de vários fornecedores e executados em máquinas virtuais, uma infraestrutura como uma opção de serviço (IaaS) no Azure. Os diagramas a seguir de antes e depois mostram uma migração de um aplicativo online apoiado por IBM DB2, um sistema de gerenciamento de banco de dados relacionais (DBMS) em um mainframe IBM z/OS. o DB2 para z/OS usa arquivos de VSAM (Virtual Armazenamento access method) para armazenar os dados e o método de acesso sequencial (ISAM) indexado para arquivos simples. Essa arquitetura também usa CICS para monitoramento de transação.

![img](https://docs.microsoft.com/pt-br/azure/cloud-adoption-framework/_images/mainframe-migration/mainframe-vs-azure.png)

No Azure, ambientes de emulação são usados para executar o Gerenciador de TP e os trabalhos em lotes que usam JCL. Na camada de dados, o DB2 é substituído pelo [Banco de Dados SQL do Azure](https://docs.microsoft.com/pt-br/azure/azure-sql/database/sql-database-paas-overview), embora o banco de dados Oracle, DB2 LUW ou Microsoft SQL Server também possa ser usado. Um emulador dá suporte a IMS, VSAM e SEQ. As ferramentas de gerenciamento do sistema do mainframe são substituídas pelos serviços do Azure e por software de outros fornecedores, que são executados em VMs.

O manuseio de tela e a funcionalidade de entrada de formulário são comumente implementados usando servidores da web, que podem ser combinados com APIs de banco de dados, como ADO, ODBC e JDBC para acesso a dados e transações. A linha exata de componentes de IaaS do Azure para usar depende do sistema operacional que você preferir. Por exemplo:

- **VMs baseadas em Windows:** IIS (servidor de informações da Internet) junto com ASP.NET para o manuseio de tela e a lógica de negócios. Use o ADO.NET para acesso a dados e transações.
- **VMs baseadas em Linux:** Os servidores de aplicativos baseados em Java que estão disponíveis, como Apache Tomcat para manipulação de tela e funcionalidade comercial baseada em Java. Use o JDBC para transações e acesso a dados.

## Migre cargas de trabalho de lote para o Azure

Operações em lote no Azure são diferentes do ambiente de lote típico em mainframes. Trabalhos em lotes de mainframes são normalmente seriais por natureza e dependem dos IOPS fornecidos pelo backbone de mainframe por desempenho. Ambientes de lote baseados em nuvem usam a computação paralela e redes de alta velocidade para o desempenho.

Para otimizar o desempenho do lote usando o Azure, considere as opções de [computar](https://docs.microsoft.com/pt-br/azure/virtual-machines/windows/overview), [armazenar](https://docs.microsoft.com/pt-br/azure/storage/blobs/storage-blobs-introduction), [rede](https://azure.microsoft.com/blog/maximize-your-vm-s-performance-with-accelerated-networking-now-generally-available-for-both-windows-and-linux/), e [monitoramento](https://docs.microsoft.com/pt-br/azure/azure-monitor/overview) da seguinte maneira.

### Computação

Use:

- VMs com a velocidade de relógio mais alta. Aplicativos de mainframe são geralmente de thread único e CPUs de mainframe têm um relógio de velocidade muito alta.
- VMs com capacidade de memória grande para permitir o armazenamento em cache de dados e áreas de trabalho do aplicativo.
- VMs com maior densidade vCPUs para aproveitar o processamento multi-threaded se o aplicativo der suporte a vários threads.
- Processamento paralelo, como Azure facilmente pode ser dimensionado para processamento paralelo, oferecendo mais poder de computação para um execução de lote.

### Armazenamento

Use:

- o [azure Premium SSDs](https://docs.microsoft.com/pt-br/azure/virtual-machines/disks-types#premium-ssd) ou o [Ultra Armazenamento em Disco do azure](https://docs.microsoft.com/pt-br/azure/virtual-machines/disks-types#ultra-ssd-preview) para o IOPS máximo disponível.
- Particionamento com vários discos para mais IOPS por tamanho de armazenamento.
- particionamento de armazenamento para distribuir e/s em vários dispositivos Armazenamento do Azure.

### Rede

- Use a [rede acelerada do Azure](https://docs.microsoft.com/pt-br/azure/virtual-network/create-vm-accelerated-networking-powershell) para minimizar a latência.

### Monitoramento

- Use ferramentas de monitoramento, [Azure Monitor](https://docs.microsoft.com/pt-br/azure/azure-monitor/overview), [Application Insights](https://docs.microsoft.com/pt-br/azure/azure-monitor/app/app-insights-overview)e logs do Azure permitem que os administradores monitorem qualquer desempenho de execuções em lotes e ajudem a eliminar afunilamentos.

## Migrar os ambientes de desenvolvimento

As arquiteturas distribuídas da nuvem dependem de um conjunto diferente de ferramentas de desenvolvimento que fornecem a vantagem das práticas modernas e linguagens de programação. Para facilitar essa transição, você pode usar um ambiente de desenvolvimento com outras ferramentas que são projetadas para emular os ambientes do IBM z/OS. A lista a seguir mostra as opções da Microsoft e outros fornecedores:

| Componente     | Opções do Azure                                              |
| :------------- | :----------------------------------------------------------- |
| z/OS           | Windows, Linux ou Unix                                       |
| CICS           | Serviços do Azure oferecidos pelos dados micro Focus, Oracle, GT software (Fujitsu), TmaxSoft, Raincode e NTT, ou reescreva usando o kubernetes |
| IMS            | Serviços do Azure oferecidos pela Micro Focus e Oracle       |
| Assembler      | Serviços do Azure de Raincode e TmaxSoft; ou COBOL, C ou Java, ou são mapeados para funções do sistema operacional |
| JCL            | JCL, PowerShell ou outras ferramentas de script              |
| COBOL          | COBOL, C ou Java                                             |
| Natural        | Natural, COBOL, C ou Java                                    |
| Fortran e PL/I | Fortran, PL/I, COBOL, C ou Java                              |
| REXX e PL/I    | REXX, PowerShell ou outras ferramentas de script             |

## Migre bancos de dados e dados

A migração de aplicativo geralmente envolve a nova hospedagem da camada de dados. você pode migrar SQL Server, software livre e outros bancos de dados relacionais para soluções totalmente gerenciadas no azure, como o [azure SQL Instância Gerenciada](https://docs.microsoft.com/pt-br/azure/azure-sql/managed-instance/sql-managed-instance-paas-overview), o [banco de dados do azure para PostgreSQL](https://docs.microsoft.com/pt-br/azure/postgresql/overview)e o [banco de dados do azure para MySQL](https://docs.microsoft.com/pt-br/azure/mysql/overview) com o [serviço de migração de banco de dados do azure](https://docs.microsoft.com/pt-br/azure/dms/dms-overview).

Por exemplo, você pode migrar se a camada de dados de mainframe usa:

- IBM DB2 ou um banco de dados do IMS, use Banco de Dados SQL do Azure, SQL Server, DB2 LUW ou Oracle Database no Azure.
- VSAM e outros arquivos simples, use arquivos simples de ISAM (método de acesso sequencial indexado) para Banco de Dados SQL do Azure, SQL Server, DB2 LUW ou Oracle.
- GDGs (grupos de datas de geração), migre para arquivos no Azure que usam uma Convenção de nomenclatura e extensões de nome de arquivo que fornecem funcionalidade semelhante à GDGs.

A camada de dados do IBM inclui vários componentes principais que também devem migrar. Por exemplo, ao migrar um banco de dados, você também migrar uma coleção de dados contidos em pools, cada um contendo dbextents, que são conjuntos de dados z/OS VSAM. A migração deve incluir o diretório que identifica os locais de dados nos pools de armazenamento. Além disso, o plano de migração deve considerar o log de banco de dados, que contém um registro das operações executadas no banco de dados. Um banco de dados pode ter um, dois (duplo ou alternativo) ou quatro logs (duplo ou alternativo).

A migração de banco de dados também inclui os seguintes componentes:

- **Gerenciador de banco de dados:** Fornece acesso aos dados no banco de dado. O gerenciador de banco de dados é executado em sua própria partição em um ambiente de z/OS.
- **Solicitante do aplicativo:** Aceita solicitações de aplicativos antes de passá-las para um servidor de aplicativos.
- **Adaptador de recursos online:** Inclui componentes de solicitação de aplicativo para uso em transações CICS.
- **Adaptador de recursos do lote:** Implementa componentes do solicitante de aplicativo para aplicativos de lote z/OS.
- **SQL interativo (ISQL):** é executado como um aplicativo e uma interface CICS, permitindo que os usuários insiram SQL instruções ou comandos de operador.
- **Aplicativo CICS:** É executado sob o controle de CICS, usando recursos disponíveis e fontes de dados no CICS.
- **Aplicativo do lote:** Executa a lógica do processo sem comunicação interativa com os usuários para, por exemplo, produzir atualizações de dados em massa ou gerar relatórios de um banco de dado.

## Otimizar a taxa de transferência e escala para o Azure

Em termos gerais, os mainframes são escalados verticalmente, enquanto a nuvem é dimensionada. Para otimizar a escala e a taxa de transferência de aplicativos em estilo de mainframe em execução no Azure, é importante entender como os mainframes podem separar e isolar aplicativos. Um mainframe z/OS usa um recurso chamado de partições lógicas (LPARs) para isolar e gerenciar os recursos de um aplicativo específico em uma única instância.

Por exemplo, um mainframe pode usar um LPAR para uma região CICS com programas COBOL associados e um LPAR separado para DB2. LPARs adicionais geralmente são usados para o desenvolvimento, teste e ambientes de preparo.

No Azure, é mais comum usar VMs separadas para atender a essa finalidade. Normalmente, as arquiteturas do Azure implantam VMs para a camada de aplicativo, um conjunto separado de VMs para a camada de dados, outro conjunto para o desenvolvimento e assim por diante. Cada camada de processamento pode ser otimizada usando o tipo mais adequado de VMs e recursos para esse ambiente.

Além disso, cada camada também pode fornecer serviços de recuperação de desastres apropriados. Por exemplo, VMs do banco de dados e produção podem requerer uma recuperação ativa ou passiva, enquanto as VMs de desenvolvimento e teste dão suporte a uma recuperação fria.

A figura a seguir mostra uma possível implantação do Azure usando um site principal e um secundário. No site primário, as VMs de produção, preparo e teste são implantadas com alta disponibilidade. O site secundário é feito para backup e recuperação de desastres.

![A possible Azure deployment using a primary and a secondary site](https://docs.microsoft.com/pt-br/azure/cloud-adoption-framework/_images/mainframe-migration/migration-backup-dr.png)

## Executar uma migração em etapas para o Azure

Migrar soluções de um mainframe para o Azure pode envolver uma migração *preparada*, na qual alguns aplicativos são movidos pela primeira vez e outros permanecem no mainframe temporariamente ou permanentemente. Normalmente, essa abordagem requer sistemas que permitem que aplicativos e bancos de dados para fins de interoperabilidade entre o mainframe e o Azure.

Um cenário comum é mover um aplicativo no Azure enquanto mantém os dados usados pelo aplicativo no mainframe. Software específico é usado para permitir que os aplicativos no Azure acessem dados de mainframe. Felizmente, uma ampla gama de soluções fornece integração entre o Azure e os ambientes existentes de mainframe, suporte para cenários híbridos e migração ao longo do tempo. Parceiros da Microsoft, fornecedores independentes de software e integradores de sistema podem ajudá-lo em seu percurso.

uma opção é o [Microsoft Host Integration Server](https://docs.microsoft.com/pt-br/host-integration-server/), uma solução que fornece a DRDA (arquitetura de banco de dados relacional distribuída) necessária para que aplicativos no Azure acessem dados no DB2 que permanecem no mainframe. Outras opções de integração entre mainframe e Azure incluem soluções da IBM, Attunity, Codit, outros fornecedores e opções de código aberto.

## Soluções de parceiros

Se você estiver considerando uma migração de mainframe, o ecossistema de parceiros está disponível para ajudá-lo.

O Azure fornece uma infraestrutura comprovada, altamente disponível e escalonável para sistemas que atualmente executam em mainframes. Algumas cargas de trabalho podem ser migradas com relativa facilidade. Outras cargas de trabalho que dependem do software de sistema herdado, como o CICS e IMS, podem ser hospedadas novamente usando soluções de parceiros e migrados para o Azure ao longo do tempo. Independentemente da opção escolhida, a Microsoft e nossos parceiros estão disponíveis para ajudá-lo a otimizar o Azure enquanto mantém a funcionalidade de software do sistema de mainframe.

## Saiba mais

Para saber mais, consulte os recursos a seguir:

- [Introdução ao Azure](https://docs.microsoft.com/pt-br/azure/)
- [Implantar o IBM DB2 pureScale no Azure](https://azure.microsoft.com/resources/deploy-ibm-db2-purescale-on-azure/)
- [documentação do Host Integration Server](https://docs.microsoft.com/pt-br/host-integration-server/)

------

## Conteúdo recomendado