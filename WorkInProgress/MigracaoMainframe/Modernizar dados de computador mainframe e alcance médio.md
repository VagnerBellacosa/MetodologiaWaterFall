# Modernizar dados de computador mainframe e alcance médio

Cosmos DB - Data Lake - Banco de Dados SQL - Instância Gerenciada de SQL -Armazenamento

Soluções de armazenamento de dados atuais, como a plataforma de dados do Azure, oferecem escalabilidade e desempenho aprimorados em sistemas mainframe e midrange. Ao modernizar, você pode aproveitar esses benefícios. No entanto, a atualização de tecnologia, infraestrutura e práticas é complexa. O processo envolve uma investigação exaustiva das atividades de negócios e engenharia. O gerenciamento de dados é um aspecto a ser considerado ao modernizar. Mas você também precisa ver a visualização e a integração de dados.

Modernizações bem-sucedidas usam uma [estratégia de primeiro dados.](https://resources.syniti.com/data-quality/5-reasons-a-data-first-strategy-works) Com essa abordagem, as organizações se concentram nos dados, em vez do novo sistema. O gerenciamento de dados não é mais simplesmente um item na lista de verificação de modernização. Em vez disso, os dados se tornam a peça central. Sistemas sustentáveis resultam, como soluções de dados orientadas a qualidade, que substituem soluções de dados fragmentadas e mal governadas.

Essa arquitetura de referência descreve um plano de modernização de ponta a ponta para fontes de dados mainframe e midrange. A solução usa componentes da plataforma de dados do Azure em uma abordagem de dados primeiro. Especificamente, o plano envolve:

- **Conversão de**objeto: convertendo definições de objeto do armazenamento de dados de origem em objetos correspondentes no armazenamento de dados de destino.
- **Ingestão de dados:**conectando-se ao armazenamento de dados de origem e extraindo dados.
- **Transformação de dados:**transformando dados extraídos em estruturas de armazenamento de dados de destino apropriadas.
- **Armazenamento de**dados: carregando dados do armazenamento de dados de origem para o armazenamento de dados de destino, inicialmente e continuamente.

## Possíveis casos de uso

Os clientes de mainframe e de médio alcance podem se beneficiar dessa solução, especialmente ao direcionar essas metas:

- Modernizar cargas de trabalho críticas.
- Adquira business intelligence para melhorar as operações e obter uma vantagem competitiva.
- Escape dos altos custos e da rigididade associados aos armazenamentos de dados mainframe e midrange.

## Arquitetura

![Diagrama de arquitetura mostrando como modernizar sistemas mainframe e midrange migrando dados para o Azure.](https://docs.microsoft.com/pt-br/azure/architecture/reference-architectures/migration/images/modernize-mainframe-data-with-azure.png)

O diagrama contém duas partes, uma para componentes locais e outra para componentes do Azure. A parte local contém caixas que representam o sistema de arquivos, os bancos de dados relacionais e não relacionais e os componentes de conversão de objeto. As setas apontam dos componentes locais para os componentes do Azure. Uma dessas setas passa pela caixa de conversão de objeto e uma é rotulada como gateway de dados local. A parte do Azure contém caixas que representam ingestão e transformação de dados, armazenamento de dados, serviços do Azure e aplicativos cliente. Algumas setas apontam dos componentes locais para as ferramentas e serviços na caixa de transformação e integração de dados. Outra seta aponta dessa caixa para a caixa de armazenamento de dados, que contém bancos de dados e armazenamentos de dados. Setas adicionais apontam do armazenamento de dados para os serviços do Azure e para aplicativos cliente.



*Baixe um [Arquivo Visio](https://arch-center.azureedge.net/US-1785470-PR-1990-modernize-mainframe-data-with-azure.vsdx) dessa arquitetura.*

A modernização de dados envolve as etapas a seguir. Durante todo o processo, um gateway de dados local transfere dados de maneira rápida e segura entre sistemas locais e serviços do Azure (1).

### Conversão de objeto

O processo de conversão de objeto extrai definições de objeto de fontes. As definições são então convertidas em objetos correspondentes no armazenamento de dados de destino (2).

- Microsoft SQL Server SSMA (Migration Assistance) para Db2 migra esquemas e dados de bancos de dados IBM Db2 para bancos de dados do Azure.
- Provedor de Dados para Arquivos de Host converte objetos por:
  - Análise de layouts de registro COBOL e LTD ou *copybooks*.
  - Mapeando os copybooks para objetos C# que os aplicativos .NET usam.
- Ferramentas de terceiros executam a conversão de objeto automatizada em bancos de dados não relacionais, sistemas de arquivos e outros armazenamentos de dados.

### Transformação e ingestão de dados

Na próxima etapa, o processo migra dados.

#### Dados de arquivo

- Provedor de Dados se conecta remotamente a servidores do sistema de arquivos host IBM (3a). Com sistemas que não são mainframe, Provedor de Dados lê dados offline.

  Os sistemas mainframe e midrange armazenam dados em DASD ou fita no formato EBCDIC nesses tipos de arquivos:

  - Arquivos [VSAM indexados](https://www.ibm.com/support/knowledgecenter/zosbasics/com.ibm.zos.zconcepts/zconcepts_169.htm)
  - Arquivos [GDG](https://www.ibm.com/support/knowledgecenter/zosbasics/com.ibm.zos.zconcepts/zconcepts_175.htm) não indexados
  - [Arquivos simples.](https://www.pcmag.com/encyclopedia/term/flat-file)

  Os copybooks de linguagem COBOL, PL/I e assembly definem a estrutura de dados desses arquivos. Provedor de Dados converte os dados de EBCDIC em formato ASCII com base no layout do copybook.

- O FTP converte e transfere os conjuntos de dados mainframe e midrange com layouts individuais e campos desempacotamento para o Azure (3b).

#### Dados do banco de dados

- Os sistemas mainframe IBM e midrange armazenam dados em bancos de dados relacionais, incluindo:

  - [Db2 para z/OS](https://www.ibm.com/analytics/db2/zos)
  - [Db2 LUW](https://www.ibm.com/support/knowledgecenter/en/SSEPGG_10.5.0/com.ibm.db2.luw.kc.doc/welcome.html)
  - [Db2 para i](https://www.ibm.com/support/pages/db2-ibm-i)

  Esses serviços migram os dados do banco de dados (3c):

  - Azure Data Factory usa um conector Db2 para extrair e integrar dados desses bancos de dados.
  - SQL Server Integration Services (SSIS) lida com uma ampla variedade de tarefas [de ETL de](https://www.ibm.com/cloud/learn/etl) dados.

- Os sistemas mainframe IBM e midrange armazenam dados em bancos de dados não relacionais, incluindo:

  - [IDMS](https://www.broadcom.com/products/mainframe/databases-database-mgmt/idms), um [DBMS](https://web.archive.org/web/20060904190944/http://coronet.iicm.edu/wbtmaster/allcoursescontent/netlib/ndm1.htm) (Sistema de Gerenciamento de Banco de Dados) de modelo de rede
  - [IMS](https://www.ibm.com/it-infrastructure/z/ims), um DBMS de modelo hierárquico
  - [ADABAS](https://www.softwareag.com/en_corporate/platform/adabas-natural.html)
  - [Datacom](https://www.broadcom.com/products/mainframe/databases-database-mgmt/datacom)

  Produtos de terceiros integram dados desses bancos de dados (3d).

Serviços do Azure, como Data Factory e AzCopy, carregam dados em bancos de dados do Azure e armazenamento de dados (4). Soluções de terceiros e soluções de carregamento personalizado também podem carregar dados.

### Armazenamento de dados

O Azure oferece muitas soluções de armazenamento de dados gerenciados (5):

- Bancos de dados:
  - Banco de Dados SQL do Azure
  - Banco de Dados do Azure para PostgreSQL
  - Azure Cosmos DB
  - Banco de Dados do Azure para MySQL
  - Banco de Dados do Azure para MariaDB
  - Instância Gerenciada de SQL do Azure
- Armazenamento:
  - Armazenamento do Azure Data Lake
  - Armazenamento do Azure

### Camada de dados

- Uma variedade de Serviços do Azure usa a camada de dados modernizada para computação, análise, armazenamento e rede (6).
- Os aplicativos cliente existentes também usam a camada de dados modernizada (7).

## Componentes

A solução usa os componentes a seguir.

### Ferramentas

- [O SSMA para Db2](https://docs.microsoft.com/pt-br/sql/ssma/db2/sql-server-migration-assistant-for-db2-db2tosql) automatiza a migração do Db2 para os serviços de banco de dados da Microsoft. Durante a execução em uma VM (máquina virtual), essa ferramenta converte objetos de banco de dados Db2 em objetos SQL Server banco de dados e cria esses objetos em SQL Server. O SSMA para Db2 migra dados do Db2 para os seguintes serviços:
  - SQL Server 2012
  - SQL Server 2014
  - SQL Server 2016
  - SQL Server 2017 no Windows e no Linux
  - SQL Server 2019 no Windows e linux
  - Banco de Dados SQL do Azure
  - Instância Gerenciada de SQL do Azure
- [Provedor de Dados para Arquivos de Host](https://docs.microsoft.com/pt-br/host-integration-server/core/data-for-host-files) é um componente Host Integration Server [(HIS)](https://docs.microsoft.com/pt-br/host-integration-server/what-is-his) que usa conexões TCP/IP offline.
  - Com conexões offline, Provedor de Dados lê e grava registros em um arquivo binário local.
  - Com conexões SNA e TCP/IP, o Provedor de Dados lê e grava registros armazenados em conjuntos de dados remotos z/OS (ibm z series Mainframe) ou arquivos físicos remotos i5/OS (sistemas IBM AS/400 e iSeries). Somente sistemas i5/SO usam TCP/IP.
- [Os Serviços do Azure](https://azurecharts.com/overview) fornecem ambientes, ferramentas e processos para desenvolver e dimensionar novos aplicativos na nuvem pública.

### Integradores de dados

- [Data Factory](https://azure.microsoft.com/services/data-factory/) é um serviço de integração de dados híbrido. Você pode usar essa solução totalmente gerenciada sem servidor para criar, agendar e orquestrar fluxos de trabalho [ETL e ELT.](https://www.ibm.com/cloud/learn/etl#toc-etl-vs-elt-goFgkQcP)
- [O AzCopy](https://docs.microsoft.com/pt-br/azure/storage/common/storage-use-azcopy-v10) é um utilitário de linha de comando que move blobs ou arquivos para dentro e fora de contas de armazenamento.
- [SQL Server Integration Services (SSIS)](https://docs.microsoft.com/pt-br/sql/integration-services/sql-server-integration-services) é uma plataforma para criar soluções de transformação e integração de dados de nível empresarial. Você pode usar o SSIS para resolver problemas de negócios complexos:
  - Copiando ou baixando arquivos
  - Carregando data warehouses
  - Limpar e minerar dados
  - Gerenciando SQL Server dados e objetos

### Armazenamento de dados

- [Banco de Dados SQL do Azure](https://azure.microsoft.com/services/sql-database/) faz parte da família [de SQL Azure](https://azure.microsoft.com/services/azure-sql/) e é criado para a nuvem. Esse serviço oferece todos os benefícios de uma plataforma como serviço totalmente gerenciada e sempre bem-gerenciada. Banco de Dados SQL do Azure também fornece recursos automatizados e alimentados por IA que otimizam o desempenho e a durabilidade. Opções de computação sem servidor e armazenamento [de Hiperescala dimensionam](https://docs.microsoft.com/pt-br/azure/azure-sql/database/service-tier-hyperscale) automaticamente os recursos sob demanda.
- [Banco de Dados do Azure para PostgreSQL](https://azure.microsoft.com/services/postgresql/) é um serviço de banco de dados relacional totalmente gerenciado baseado na edição da comunidade do mecanismo de banco de [dados PostgreSQL](https://www.postgresql.org/) de código aberto. Com esse serviço, você pode se concentrar na inovação de aplicativos em vez do gerenciamento de banco de dados. Você também pode dimensionar sua carga de trabalho de forma rápida e fácil.
- [O BD Cosmos Azure](https://docs.microsoft.com/pt-br/azure/cosmos-db/introduction) é um banco de dados [multi-modelo](https://www.infoworld.com/article/2861579/the-rise-of-the-multimodel-database.html) distribuído globalmente. Com o Azure Cosmos DB, suas soluções podem dimensionar de forma elástica e independente a produtividade e o armazenamento em qualquer número de regiões geográficas. Esse serviço de banco de dados [NoSQL](https://www.infoworld.com/article/3240644/what-is-nosql-databases-for-a-cloud-scale-future.html) totalmente gerenciado garante latências de milissegundos de dígito único no nono percentil em qualquer lugar do mundo.
- [Banco de Dados do Azure para MySQL](https://docs.microsoft.com/pt-br/azure/mysql/overview) é um serviço de banco de dados relacional totalmente gerenciado com base na edição da comunidade do mecanismo de banco de [dados MySQL](https://www.mysql.com/products/community/)de código aberto .
- [Banco de Dados do Azure para MariaDB](https://docs.microsoft.com/pt-br/azure/mariadb/) é um serviço de banco de dados relacional baseado em nuvem. Esse serviço é baseado no mecanismo de banco [de dados do MariaDB](https://mariadb.org/) Community Edition.
- [O Azure SQL Instância Gerenciada](https://docs.microsoft.com/pt-br/azure/azure-sql/managed-instance/sql-managed-instance-paas-overview) é um serviço de banco de dados de nuvem inteligente e escalonável que oferece todos os benefícios de uma plataforma como serviço totalmente gerenciada e sempre bem-gerenciada. SQL Instância Gerenciada tem quase 100% de compatibilidade com o mecanismo de banco de SQL Server (Edição Enterprise) mais recente. Esse serviço também fornece uma implementação de rede virtual nativa que aborda preocupações comuns de segurança.
- [O Azure Data Lake Armazenamento](https://azure.microsoft.com/services/storage/data-lake-storage/) é um repositório de armazenamento que contém uma grande quantidade de dados em seu formato nativo e bruto. Os repositórios Data lake são otimizados para dimensionamento para terabytes e petabytes de dados. Os dados normalmente vêm de várias fontes heterogêneas e podem ser estruturados, semiestruturados ou não estruturados.
- [O Azure Armazenamento](https://docs.microsoft.com/pt-br/azure/storage/) é uma solução de armazenamento em nuvem que inclui o armazenamento de objetos, arquivos, discos, filas e tabelas. Os serviços incluem ferramentas e soluções de armazenamento híbrido para transferir, compartilhar e fazer o back-up de dados.

### Rede

- Um [gateway de dados local](https://docs.microsoft.com/pt-br/data-integration/gateway/service-gateway-onprem) atua como uma ponte que conecta dados locais com serviços de nuvem. Normalmente, você [instala o gateway em uma VM local dedicada.](https://docs.microsoft.com/pt-br/data-integration/gateway/service-gateway-install) Os serviços de nuvem podem usar dados locais com segurança.
- [As VMs do Azure](https://azure.microsoft.com/services/virtual-machines/) são recursos de computação escalonáveis e sob demanda que estão disponíveis com o Azure. Uma VM do Azure fornece a flexibilidade da virtualização. Mas elimina as demandas de manutenção de hardware físico. As VMs do Azure oferecem uma opção de sistemas operacionais, incluindo Windows e Linux.

## Recomendações

- Quando você usa o Provedor de Dados cliente de Arquivos de Host para converter dados, a ligue o [pool de conexões](https://docs.microsoft.com/pt-br/host-integration-server/core/data-for-host-files#configuringForPerformance) para reduzir o tempo de inicialização da conexão.
- Ao usar o Data Factory para extrair dados, tome medidas para [ajustar o desempenho da atividade de cópia](https://docs.microsoft.com/pt-br/azure/data-factory/copy-activity-performance#performance-tuning-steps).

## Considerações

Tenha esses pontos em mente ao considerar essa arquitetura.

### Considerações sobre capacidade de gerenciamento

Ao usar um gateway de aplicativo local, esteja ciente dos limites [em operações de leitura e gravação](https://docs.microsoft.com/pt-br/data-integration/gateway/service-gateway-onprem#considerations).

### Considerações de segurança

- O gateway de dados local fornece proteção de dados durante transferências do local para sistemas do Azure.
- Ao usar o Provedor de Dados arquivos host para converter dados, siga as recomendações em Provedores de Dados para Segurança e Proteção de Arquivos de [Host](https://docs.microsoft.com/pt-br/host-integration-server/core/data-providers-for-host-files-security-and-protection) para melhorar a segurança.

## Preços

Use a [calculadora de preços do Azure](https://azure.microsoft.com/pricing/calculator) para estimar o custo da implementação dessa solução.

## Próximas etapas

- Entre em [contato com a Engenharia de Dados do Azure – ](mailto:datasqlninja@microsoft.com)Modernização midrange de mainframe para obter mais informações.
- Leia o Guia [de migração](https://datamigration.microsoft.com/).

## Recursos relacionados

- [Guia de arquitetura de dados do Azure](https://docs.microsoft.com/pt-br/azure/architecture/data-guide/)
- [Plataforma de dados do Azure de ponta a ponta](https://docs.microsoft.com/pt-br/azure/architecture/example-scenario/dataplate2e/data-platform-end-to-end)

------

## Conteúdo recomendado

- [Replicar e sincronizar dados de mainframe no Azure - Azure architecture](https://docs.microsoft.com/pt-br/azure/architecture/reference-architectures/migration/sync-mainframe-data-with-azure)

  Replicar dados ao modernizar sistemas mainframe e midrange. Sincronizar dados locais com os dados do Azure durante a modernização.

- [Transformação de nuvem do sistema bancário no Azure - Azure Architecture Center](https://docs.microsoft.com/pt-br/azure/architecture/example-scenario/banking/banking-system-cloud-transformation)

  Use aplicativos simulados e reais e cargas de trabalho existentes para monitorar a reação da infraestrutura da solução quanto à escalabilidade e ao desempenho.

- [Computação multiparte com os serviços do Azure - Azure Architecture Center](https://docs.microsoft.com/pt-br/azure/architecture/guide/blockchain/multiparty-compute)

  Saiba mais sobre os serviços do Azure pode ajudá-lo a criar uma solução de computação multiparte, que pode incluir recursos baseados em nuvem e locais.

- [Soluções de armazenamento de dados médicos - Azure Solution Ideas](https://docs.microsoft.com/pt-br/azure/architecture/solution-ideas/articles/medical-data-storage)

  Armazene dados de saúde de maneira eficaz e acessível com as soluções baseadas em nuvem do Azure. Gerencie registros médicos com o mais elevado nível de segurança interna.

Mostrar mais