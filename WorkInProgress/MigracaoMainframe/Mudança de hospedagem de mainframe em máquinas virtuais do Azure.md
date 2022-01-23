Rehosting de mainframe



Pesquisar

- Visão geral
  - [Introdução](https://docs.microsoft.com/pt-br/azure/virtual-machines/workloads/mainframe-rehosting/overview)
  - [Cargas de trabalho](https://docs.microsoft.com/pt-br/azure/virtual-machines/workloads/mainframe-rehosting/partner-workloads)
- Conceitos
- Micro Focus
- TmaxSoft OpenFrame
- IBM
- Recursos

# Mudança de hospedagem de mainframe em máquinas virtuais do Azure

- Artigo - 29/01/2022

  A migração de cargas de trabalho de ambientes de mainframe para a nuvem permite modernizar sua infraestrutura e, muitas vezes, economizar em custos. Muitas cargas de trabalho podem ser transferidas para o Azure com apenas pequenas alterações de código, como atualizar os nomes dos bancos de dados.

Em geral, o termo *mainframe* significa um sistema grande de computador. Especificamente, a grande maioria atualmente em uso são os servidores IBM System Z ou sistemas compatíveis com IBM que executam MVS, DOS, VSE, OS/390, ou z/OS.

Uma VM (máquina virtual) do Azure é usada para isolar e gerenciar os recursos de um aplicativo específico em uma instância única. Mainframes como IBM z/OS usam partições lógicas (LPARs) para essa finalidade. Por exemplo, um mainframe pode usar uma partição lógica (LPAR) para uma região do CICS com programas associados de COBOL, e um LPAR separado para banco de dados Db2. Um [aplicativo típico de n camadas no Azure](https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/n-tier/n-tier-sql-server) implanta VMs do Azure em uma rede virtual que pode ser segmentada em sub-redes para cada camada.

As VMs do Azure podem executar ambientes de emulação de mainframe e compiladores que dão suporte a cenários de comparação de precisão e de deslocamento. O desenvolvimento e teste geralmente estão entre as primeiras cargas de trabalho para migrar de um mainframe para um ambiente de desenvolvimento/teste do Azure. Componentes de servidor comuns que você pode emular incluem processo de transação online (OLTP), lotes e sistemas de ingestão de dados, como ilustra a imagem a seguir.

![Os ambientes de emulação no Azure permitem que você execute sistemas baseados em z/OS.](https://docs.microsoft.com/pt-br/azure/virtual-machines/workloads/mainframe-rehosting/media/01-overview.png)

Algumas cargas de trabalho de mainframe podem ser migradas para o Azure com certa facilidade, enquanto outras podem ser re-hospedadas no Azure usando uma solução de um parceiro. Para ver diretrizes detalhadas sobre como escolher uma solução de parceiro, consulte o [centro de Migração de Mainframe do Azure](https://azure.microsoft.com/migration/mainframe/).

## Migração de mainframe

Re-hospedar, recompilar, substituir ou desativar? IaaS ou PaaS? Para determinar a estratégia de migração correta do aplicativo de mainframe, consulte o guia de [Migração do Mainframe](https://docs.microsoft.com/en-us/azure/architecture/cloud-adoption/infrastructure/mainframe-migration/overview) no Centro de Arquitetura do Azure.

## Plataforma de re-hospedagem Micro Focus

O Enterprise Server da Micro Focus é uma das maiores plataformas de hospedagem de mainframe disponíveis. Você pode usá-lo para executar suas cargas de trabalho do z/OS em uma plataforma x86 mais barata no Azure.

Introdução:

- [Instalar o Enterprise Server e o Enterprise Developer no Azure](https://docs.microsoft.com/pt-br/azure/virtual-machines/workloads/mainframe-rehosting/microfocus/set-up-micro-focus-azure)
- [Configurar o CICS BankDemo para Enterprise Developer no Azure](https://docs.microsoft.com/pt-br/azure/virtual-machines/workloads/mainframe-rehosting/microfocus/demo)
- [Executar o Enterprise Server em contêineres do Docker no Azure](https://docs.microsoft.com/pt-br/azure/virtual-machines/workloads/mainframe-rehosting/microfocus/run-enterprise-server-container)

## TmaxSoft OpenFrame no Azure

O TmaxSoft OpenFrame é uma solução popular de re-hospedagem de mainframe usada em cenários de lift-and-shift. Um ambiente OpenFrame no Azure é adequado para desenvolvimento, demonstrações, testes ou cargas de trabalho de produção.

Introdução:

- [Introdução ao TmaxSoft OpenFrame](https://docs.microsoft.com/pt-br/azure/virtual-machines/workloads/mainframe-rehosting/tmaxsoft/get-started)
- [Baixe o ebook](https://azure.microsoft.com/resources/install-tmaxsoft-openframe-on-azure/)

## IBM zD&T 12.0

O IBM Z Development and Test Environment (IBM zD&T) configura um ambiente de não produção no Azure que pode ser usado para desenvolvimento, teste e demonstrações de aplicativos baseados em z/SO.

O ambiente de emulação no Azure pode hospedar diferentes tipos de instâncias Z por meio de ADCDs (Distribuições Controladas por Desenvolvedores de Aplicativos). É possível executar o zD&T Personal Edition, o zD&T Parallel Sysplex e o zD&T Enterprise Edition no Azure e no Azure Stack.

Introdução:

- [Configure o IBM zD](https://docs.microsoft.com/pt-br/azure/virtual-machines/workloads/mainframe-rehosting/ibm/install-ibm-z-environment)T 12.0 no Azure
- [Configure o ADCD no zD](https://docs.microsoft.com/pt-br/azure/virtual-machines/workloads/mainframe-rehosting/ibm/demo)T

## IBM DB2 pureScale no Azure

O ambiente IBM DB2 pureScale fornece um cluster de banco de dados para o Azure. Ele não é idêntico ao ambiente original, mas oferece disponibilidade e escala semelhantes ao IBM DB2 para z/OS em execução em uma configuração do Parallel Sysplex.

Para começar, consulte [IBM DB2 pureScale no Azure](https://docs.microsoft.com/pt-br/azure/virtual-machines/workloads/mainframe-rehosting/ibm/ibm-db2-purescale-azure).

## Considerações

Ao migrar cargas de trabalho de mainframe para a IaaS (infraestrutura como serviço) do Azure, você pode escolher entre vários tipos de recursos de computação sob demanda e escalonáveis, incluindo VMs do Azure. O Azure oferece uma variedade de VMs do [Windows](https://docs.microsoft.com/pt-br/azure/virtual-machines/linux/overview) e do [Linux](https://docs.microsoft.com/pt-br/azure/virtual-machines/windows/overview).

### Computação

A potência de computação do Azure se compara de forma favorável com a capacidade de um mainframe. Se você estiver pensando em mover uma carga de trabalho de mainframe para o Azure, compare as métricas de mainframe de um milhão de MIPS (instruções por segundo) com CPUs virtuais.

Aprenda a [mover a computação do mainframe para o Azure](https://docs.microsoft.com/pt-br/azure/virtual-machines/workloads/mainframe-rehosting/concepts/mainframe-compute-azure).

### Failover e alta disponibilidade

O Azure oferece SLAs (contratos de nível de serviço) baseados em compromisso. A alta disponibilidade, com vários noves, é o padrão, e os SLAs podem ser otimizados com a replicação dos serviços, local ou geograficamente. O [SLA completo do Azure](https://azure.microsoft.com/support/legal/sla/virtual-machines/) explica a disponibilidade garantida do Azure como um todo.

Com a IaaS do Azure, como uma VM, as funções específicas do sistema fornecem suporte a failover – por exemplo, instâncias de clustering de failover e conjuntos de disponibilidade. Quando você usa recursos de PaaS (plataforma como serviço) do Azure, a plataforma manipula o failover automaticamente. Os exemplos incluem o [Banco de Dados SQL do Azure](https://docs.microsoft.com/pt-br/azure/azure-sql/database/sql-database-paas-overview) e o [Azure Cosmos DB](https://docs.microsoft.com/pt-br/azure/cosmos-db/introduction).

### Escalabilidade

Os mainframes normalmente aumentam verticalmente, enquanto os ambientes de nuvem são expandidos horizontalmente. O Azure oferece uma variedade de tamanhos do [Linux](https://docs.microsoft.com/pt-br/azure/virtual-machines/sizes) e do [Windows](https://docs.microsoft.com/pt-br/azure/virtual-machines/sizes) para atender às suas necessidades. A nuvem também é dimensionada para corresponder às especificações exatas do usuário. A capacidade de computação, o armazenamento e os serviços são [dimensionados](https://docs.microsoft.com/en-us/azure/architecture/best-practices/auto-scaling) sob demanda em um modelo de cobrança baseado no uso.

### Armazenamento

Na nuvem, você tem uma variedade de opções de armazenamento flexíveis e escalonáveis, e paga apenas pelo que precisa. O [Armazenamento do Azure](https://docs.microsoft.com/pt-br/azure/storage/common/storage-introduction) oferece um armazenamento de objetos altamente escalonável para objetos de dados, um serviço de sistema de arquivos para a nuvem, armazenamento de mensagens confiáveis e armazenamento de NoSQL. Para VMs, discos gerenciados e discos não gerenciados fornecem armazenamento em disco persistente e seguro.

Aprenda a [mover o armazenamento do mainframe para o Azure](https://docs.microsoft.com/pt-br/azure/virtual-machines/workloads/mainframe-rehosting/concepts/mainframe-storage-azure).

### Backup e descoberta

Manter seu próprio site de recuperação de desastre pode ser custar caro. O Azure tem opções fáceis de implementar e econômicas para [backup](https://docs.microsoft.com/pt-br/azure/backup/backup-overview), [recuperação](https://docs.microsoft.com/pt-br/azure/site-recovery/site-recovery-overview), e [redundância](https://docs.microsoft.com/pt-br/azure/storage/common/storage-redundancy) nos níveis locais ou regionais, ou por meio de redundância geográfica.

## Azure Governamental para migrações de mainframe

Muitas entidades do setor público adorariam mover seus aplicativos de mainframe para uma plataforma mais moderna e flexível. O Microsoft Azure Governamental é uma instância fisicamente separada da plataforma global do Microsoft Azure, empacotada para sistemas governamentais federais, estaduais e municipais. Fornece segurança de nível mundial, proteção e serviços de conformidade especificamente para agências governamentais dos Estados Unidos e seus parceiros.

O Azure Governamental ganhou uma licitação (Provisional Authority to Operate, P-ATO) para o FedRAMP High Impact para sistemas que precisam desse tipo de ambiente.

Para começar, baixe o [Nuvem do Microsoft Azure Governamental para aplicativos de mainframe](https://azure.microsoft.com/resources/microsoft-azure-government-cloud-for-mainframe-applications/en-us/).

## Próximas etapas

Peça aos nossos [parceiros](https://docs.microsoft.com/pt-br/azure/virtual-machines/workloads/mainframe-rehosting/partner-workloads) para ajudá-lo a migrar ou re-hospedar seus aplicativos de mainframe.

Consulte também:

- [White papers sobre tópicos de mainframe](https://docs.microsoft.com/pt-br/azure/virtual-machines/workloads/mainframe-rehosting/mainframe-white-papers)
- [Migração de mainframe](https://docs.microsoft.com/en-us/azure/architecture/cloud-adoption/infrastructure/mainframe-migration/overview)
- [Solução de problemas](https://docs.microsoft.com/en-us/troubleshoot/azure/virtual-machines/welcome-virtual-machines)
- [Desmistificando a migração de mainframe para o Azure](https://azure.microsoft.com/resources/demystifying-mainframe-to-azure-migration/)