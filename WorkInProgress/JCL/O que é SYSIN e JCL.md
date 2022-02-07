| O que é SYSIN e JCL |
| ------------------- |
|                     |



? A Linguagem de Controle de Job, ou JCL , para mainframes da IBM permite que os usuários de computador apresentar conjuntos de comandos para executar relatórios , tarefas de manutenção e outros processos como pacotes chamados empregos. A tarefa é executada de forma independente no computador, que exigem geralmente pouca atenção por parte do usuário ou operador. Dentro de um trabalho, vários nomes de arquivo padrão, incluindo SYSIN , atuam como fontes e destinos de dados utilizados e produzidos por programas. JCL

JCL é composto por vários tipos de comandos chamados declarações , e um trabalho pode conter algumas declarações ou milhares deles . Todos os trabalhos começam com uma declaração de emprego ou cartão de trabalho , o que dá um nome ao trabalho e fornece informações utilizadas para acompanhar o trabalho. Demonstrações começam com duas barras , seguido por um nome e um tipo de declaração , tal como a seguinte declaração de trabalho :

//YRENDRPT JOB 100 , Ano GERAL Relatório Final

Este JCL dá ao trabalho o nome de " YRENDRPT ", a palavra " tRABALHO " o identifica como uma declaração de trabalho ", 100, GERAL " diz ao computador como contabilizar o tempo de computação e recursos o trabalho utiliza e "Relatório de Fim de Ano " é um breve comentário descrevendo o trabalho. Instruções JCL subseqüentes executar programas, atribuir nomes de arquivos ou adicionar documentação para o trabalho

programas e arquivos padrão

Programas que são executados em seu computador são principalmente interativo ; . Eles ficam informações de seus comandos digitados e cliques do mouse . Programas em postos de trabalho, no entanto, não são interativos , mas eles ainda precisam de obter informações de algum lugar e colocar os dados processados em outro lugar. Arquivos Standard agir como as fontes de entrada e de saída para destinos programas em execução em empregos. JCL da IBM usa os nomes de arquivos genéricos SYSIN , SYSOUT e SYSPRINT como estas fontes e destinos. Quando um programa solicita dados , o programa obtém os dados a partir de SYSIN . Quando se produz dados , os dados vão para sysout e relatórios impressos ir para SYSPRINT . Um técnico de computador atribui esses nomes para dispositivos reais - . Por exemplo, SYSPRINT para uma impressora a laser de alta capacidade
arquivo de atribuição

Para fornecer flexibilidade , uma declaração de atribuição arquivo JCL permite um redirecionamento de dados programador a partir dos nomes de arquivo padrão para arquivos de disco ou dispositivos. Por exemplo, como as informações saídas do programa, por padrão, os dados vão para SYSOUT . A instrução DD no JCL atribui SYSOUT para um arquivo de disco, para que o programa acaba de gravar os dados para o arquivo , como no seguinte JCL :

//SYSOUT DD DSN = YEAREND.ACCOUNTS.REPORT

a declaração DD envia dados a partir do arquivo SYSOUT genérico para um arquivo de disco especial chamado " YEAREND.ACCOUNTS.REPORT ".

SYSIN

Programas ler dados do arquivo padrão SYSIN . Tal como acontece com outros arquivos padrão , você pode usar instruções DD para redirecionar dados de arquivos de disco ou o trabalho em si para fornecer um programa com dados. No exemplo a seguir , um programa lê um número de cliente do trabalho. O número de cliente segue o programa :

//RUNRPT EXEC PGM = YTDRPT //SYSIN DD * 601445 /*

O YTDRPT programa lê cada linha após a "//SYSIN " declaração JCL ; a linha " /*" diz ao programa que o trabalho não tem mais dados de entrada a serem processados.