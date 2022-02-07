- [Definição - O que significa Job Control Language (JCL)?](https://pt.theastrologypage.com/job-control-language#menu-1)
- 
- [Techopedia explica Job Control Language (JCL)](https://pt.theastrologypage.com/job-control-language#menu-3)



## Definição - O que significa Job Control Language (JCL)?

A Job Control Language (JCL) é uma linguagem de script executada em um sistema operacional de mainframe IBM. Consiste em instruções de controle que designam um trabalho específico para o sistema operacional.

A JCL fornece um meio de comunicação entre o programa de aplicativo, o sistema operacional e o hardware do sistema.



## 



## Techopedia explica Job Control Language (JCL)

A JCL é considerada uma das linguagens de script rudes executadas nos sistemas em lote IBM OS / 360. Ele pode definir nomes de conjuntos de dados, parâmetros e dispositivos de saída do sistema. Um recurso comum na JCL do DOS e do OS é a unidade de trabalho, chamada de tarefa. Um trabalho consiste em várias pequenas etapas para executar um programa específico e é identificado por cartões chamados cartões de trabalho, que indicam o início do trabalho e definem exatamente como o trabalho deve ser executado.

Os sistemas operacionais DOS e OS usam 71 caracteres por linha. No entanto, o comprimento máximo é de 80 caracteres. Os caracteres 73 a 80 são usados para localizar as áreas de erro relatadas pelo sistema operacional.

Quando uma instrução JCL fica muito longa e excede o limite de 71 caracteres, ela pode ser estendida usando um cartão de continuação. Uma instrução pode continuar com o número de cartões necessário, finalizando todos os cartões JCL, excluindo o último cartão em uma instância em que uma vírgula é usada ou usando (//) no início do cartão de continuação na coluna um e usando em pelo menos um caractere de um espaço.