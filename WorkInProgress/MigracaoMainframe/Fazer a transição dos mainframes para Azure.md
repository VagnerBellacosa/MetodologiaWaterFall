# Fazer a transição dos mainframes para Azure

- Artigo - 04/01/2022

  

Como uma plataforma alternativa para a execução de aplicativos de mainframe tradicionais, o Azure oferece computação de hiperescala e armazenamento em um ambiente de alta disponibilidade. Você obtém o valor e a agilidade de uma plataforma moderna, com base em nuvem sem os custos associados a um ambiente de mainframe.

Esta seção fornece orientações técnicas para fazer a mudança de uma plataforma de mainframe no Azure.

![Mainframe and Azure](https://docs.microsoft.com/pt-br/azure/cloud-adoption-framework/_images/mainframe-migration/make-the-switch.png)

## MIPS vs. vCPUs

Não há fórmula de mapeamento universal que exista para determinar o número de vCPUs (unidades de processamento central virtual) necessárias para executar cargas de trabalho de mainframe. No entanto, a métrica de um milhão de instruções por segundo (MIPS) geralmente é mapeada para vCPUs no Azure. MIPS mede a potência de computação geral de um mainframe, fornecendo um valor constante do número de ciclos por segundo para uma determinada máquina.

Uma organização de pequeno porte pode exigir menos de 500 MIPS, enquanto uma grande organização normalmente usa mais de 5.000 MIPS. Em 1.000 dólares por MIPS únicos, uma grande organização gasta aproximadamente 5 milhões de dólares por ano para implantar uma infraestrutura de 5.000 MIPS. A estimativa de custo anual de uma implantação típica do Azure dessa escala é de aproximadamente um décimo do custo de uma infraestrutura de MIPS. Para obter detalhes, consulte a *tabela 4* na White Paper.

Um cálculo preciso de MIPS para vCPUs com o Azure depende do tipo de vCPU e a carga de trabalho exata que você está executando. No entanto, estudos de benchmark fornecem uma boa base para estimar o número e tipo de vCPUs que será necessário. Um parâmetro de comparação HPE zRef recente fornece as seguintes estimativas:

- 288 MIPS por núcleo baseado em Intel em execução em HPE ProLiant Servers para trabalhos online (CICS).
- 170 MIPS por núcleo da Intel para trabalhos em lotes de COBOL.

Este guia estima MIPS 200 por vCPU para processamento online e MIPS 100 por vCPU para processamento em lotes.

 Observação

Essas estimativas estão sujeitas a alterações, conforme a nova série de máquina virtual (VM) fica disponível no Azure.

## Failover e alta disponibilidade

Muitas vezes, sistemas de mainframe oferecem disponibilidade de 9s (99,999 por cento) quando são usados o acoplamento de mainframe e Sysplex paralelo. Ainda assim, operadores de sistema precisam agendar o tempo de inatividade para manutenção e carregamentos de programas iniciais (IPLs). A disponibilidade real se aproxima de dois ou três noves, comparáveis a servidores baseados em Intel de alto nível.

Por comparação, o Azure oferece SLAs (contratos de nível de serviço) baseados em compromisso, em que a disponibilidade de vários noves é o padrão, otimizada com a replicação local ou baseada em geografia dos serviços.

O Azure fornece disponibilidade adicional ao replicar dados de vários dispositivos de armazenamento, localmente ou em outras regiões geográficas. Caso ocorra uma falha com base no Azure, recursos de computação podem acessar dados replicados no nível do local ou regional.

quando você usa recursos de PaaS (plataforma como serviço) do azure, como [Banco de Dados SQL do Azure](https://docs.microsoft.com/pt-br/azure/azure-sql/database/sql-database-paas-overview) e [Azure Cosmos DB](https://docs.microsoft.com/pt-br/azure/cosmos-db/introduction), o Azure pode lidar automaticamente com failovers. quando você usa a IaaS (infraestrutura como serviço) do Azure, o failover depende de uma funcionalidade específica do sistema, como SQL Server recursos de Always On, instâncias de clustering de failover e grupos de disponibilidade.

## Escalabilidade

Os mainframes normalmente aumentam, enquanto os ambientes de nuvem são expandidos. Os mainframes podem escalar horizontalmente com o uso de uma instalação de acoplamento (CF), mas o alto custo do hardware e do armazenamento torna os mainframes caros de expandir.

Um CF também oferece computação rigidamente acoplada, enquanto os recursos de expansão do Azure são livremente acoplados. A nuvem pode ser ampliada ou reduzida para corresponder às especificações exatas do usuário, com a capacidade de computação, armazenamento e escalabilidade de serviços sob demanda em um modelo de faturamento baseado em uso.

## Backup e recuperação

Os clientes de mainframe normalmente mantêm sites de recuperação de desastres ou fazer uso ou um provedor de mainframe independentes para contingências de desastres. Sincronização com um site de recuperação de desastres geralmente é feita por meio de cópias offline de dados. Ambas as opções incorrem em custos altos.

A redundância geográfica automatizada também está disponível por meio do recurso de acoplamento de mainframe. Essa abordagem é cara e normalmente é reservada para sistemas de missão crítica. Em contraste, o Azure tem opções fáceis de implementar e econômicas para [backup](https://docs.microsoft.com/pt-br/azure/backup/backup-overview), [recuperação](https://docs.microsoft.com/pt-br/azure/site-recovery/site-recovery-overview), e [redundância](https://docs.microsoft.com/pt-br/azure/storage/common/storage-redundancy) nos níveis locais ou regionais ou por meio de redundância geográfica.

## Armazenamento

Parte de entendimento sobre como os mainframes funcionam envolve vários termos de sobreposição de decodificação. Por exemplo, armazenamento central, a memória real, o armazenamento real e o armazenamento principal geralmente se refere ao armazenamento anexado diretamente para o processador de mainframe.

O hardware de mainframe inclui processadores e muitos outros dispositivos, como DASDs (dispositivos de armazenamento de acesso direto), unidades de fita magnéticas e vários tipos de consoles do usuário. Fitas e DASDs são usados para funções do sistema e por programas de usuário.

Tipos de armazenamento físico para mainframes incluem:

- **Armazenamento central:** Localizado diretamente no processador de mainframe, isso também é conhecido como processador ou armazenamento real.
- **Armazenamento auxiliar:** Localizado separadamente do mainframe, esse tipo inclui o armazenamento em DASDs e também é conhecido como armazenamento de paginação.

A nuvem oferece uma variedade de opções flexíveis e escalonáveis, e você pagará apenas essas opções que você precisa. O [Armazenamento do Azure](https://docs.microsoft.com/pt-br/azure/storage/common/storage-introduction) oferece um armazenamento de objetos altamente escalonável para objetos de dados, um serviço de sistema de arquivos para a nuvem, armazenamento de mensagens confiáveis e armazenamento de NoSQL. Para VMs, discos gerenciados e discos não gerenciados fornecem armazenamento em disco persistente e seguro.

## Desenvolvimento de mainframe e teste

Dos grandes condutores em projetos de migração de mainframe é a evolução do desenvolvimento de aplicativos. As organizações querem que seu ambiente de desenvolvimento seja mais ágil e responsivo às necessidades de negócios.

Mainframes normalmente têm partições lógicas separadas (LPARs) para desenvolvimento e teste, como controle de qualidade e preparo LPARs. Soluções de desenvolvimento de mainframe incluem compiladores (COBOL, PL / eu Assembler) e editores. O mais comum é a Facilidade de Produtividade do Sistema Interativo (ISPF) para o sistema operacional z/OS que executa os mainframes IBM. Outros incluem a Facilidade de Programação (RPF) ROSCOE e ferramentas de Computer Associates, como Biblioteca CA e Ca-Panvalet.

Compiladores e ambientes de emulação estão disponíveis em plataformas x86, portanto, desenvolvimento e teste podem estar normalmente entre as cargas de trabalho primeiro para migrar de um mainframe no Azure. A disponibilidade e o uso difundido das [ferramentas do DevOps no Azure](https://azure.microsoft.com/solutions/devops/) está acelerando a migração de desenvolvimento e ambientes de teste.

Quando as soluções são desenvolvidas e testadas no Azure e estão prontas para implantação ao mainframe, você precisará copiar o código para o mainframe e compilá-lo ali.