

# Diagrama de caso de uso

## O correto uso da linguagem de notação (ou ainda chamada diagramação) UML e o diagrama de casos de uso durante o levantamento de requisitos de um sistema auxilia no entendimento da lógica do sistema e do negócio envolvido.

[![Foto de Chico Alff](https://analisederequisitos.com.br/wp-content/uploads/2018/02/chico-alff-analise-requisitos-e1519081966448-140x140.jpg)](https://analisederequisitos.com.br/author/chicoalff/) [Chico Alff](https://analisederequisitos.com.br/author/chicoalff/)Última Atualização 24 de dezembro de 2021

![Como fazer diagrama de casos de uso uml de forma simples](https://analisederequisitos.com.br/wp-content/uploads/2018/02/como-fazer-diagrama-de-casos-de-uso-uml-simples.jpg) Como fazer diagrama de casos de uso uml de forma simples

O **diagrama de caso de uso** é um artefato visual da linguagem de modelagem padrão de software, a UML (Unified Modeling Language), um framework muito conhecido e utilizado pelas melhores empresas de desenvolvimento de software.

Este diagrama juntamente com os demais artefatos fornecidos por esta linguagem de e notação de software possibilitam que a execução e o [gerenciamento de um projeto](https://analisederequisitos.com.br/6-segredos-gerenciamento-de-projetos/) de desenvolvimento de software seja padronizado e detalhadamente [documentado](https://analisederequisitos.com.br/documento-de-requisitos-modelo-gratis/).



CONTEÚDO DO ARTIGO



[Pra que serve o diagrama de casos de uso?](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Pra_que_serve_o_diagrama_de_casos_de_uso)[A importância do uso dos diagramas UML](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#A_importancia_do_uso_dos_diagramas_UML)[Utilizando UML e Padrões de Craig Larman](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Utilizando_UML_e_Padroes_de_Craig_Larman)[Componentes do diagrama de caso de uso](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Componentes_do_diagrama_de_caso_de_uso)[Atores do caso de uso](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Atores_do_caso_de_uso)[Requisitos no caso de uso](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Requisitos_no_caso_de_uso)[Indicadores de relacionamento:](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Indicadores_de_relacionamento)[Include ou Inclusão](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Include_ou_Inclusao)[Exemplo de caso de uso include](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Exemplo_de_caso_de_uso_include)[Extend ou Extensão](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Extend_ou_Extensao)[Exemplo de caso de uso extend](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Exemplo_de_caso_de_uso_extend)[Herança e generalização](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Heranca_e_generalizacao)[Exemplos de casos de uso](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Exemplos_de_casos_de_uso)[Exemplo de relacionamento de herança (pattern)](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Exemplo_de_relacionamento_de_heranca_pattern)[Exemplo de relacionamento de execução](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Exemplo_de_relacionamento_de_execucao)[Exemplo de relacionamento include e extend](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#Exemplo_de_relacionamento_include_e_extend)

## Pra que serve o **diagrama de casos de uso**?

Através da modelagem de um diagrama de caso de uso, é possível representar os requisitos de um sistema, sejam estes [**requisitos funcionais**](https://analisederequisitos.com.br/requisitos-funcionais-e-requisitos-nao-funcionais-o-que-sao/) ou [**não funcionais**](https://analisederequisitos.com.br/requisitos-funcionais-e-requisitos-nao-funcionais-o-que-sao/).

O correto uso da linguagem de notação (ou ainda chamada diagramação) UML e o diagrama de casos de uso durante o [levantamento de requisitos ](https://analisederequisitos.com.br/5-tecnicas-para-levantar-requisitos-de-software/)de um sistema auxilia no entendimento da lógica do sistema e do negócio envolvido.

[quote style=”default” cite=”Wikipédia.org” url=”https://pt.wikipedia.org/wiki/Diagrama_de_caso_de_uso”]O diagrama de caso de uso descreve a funcionalidade proposta para um novo sistema que será projetado, é uma excelente ferramenta para o levantamento dos requisitos funcionais do sistema.[/quote]

Em projetos que utilizam notações visuais em seu processo de desenvolvimento, a **incidência de refluxos** durante as[ fases de arquitetura, desenvolvimento e testes](https://analisederequisitos.com.br/infografico-engenharia-de-software-as-5-fases-do-desenvolvimento-de-software/) tendem a serem menores.

Artigos relacionados

- [![Como fazer diagrama de casos de uso uml de forma simples](data:image/gif;base64,R0lGODdhAQABAPAAAP///wAAACwAAAAAAQABAEACAkQBADs=)](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/)

  [Diagrama de caso de uso](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/)

- [![curso uml online gratis com certificado - UML, Cursos](data:image/gif;base64,R0lGODdhAQABAPAAAP///wAAACwAAAAAAQABAEACAkQBADs=)](https://analisederequisitos.com.br/curso-de-uml-gratis-online/)

  [Curso Linguagem de Modelagem Unificada (UML)](https://analisederequisitos.com.br/curso-de-uml-gratis-online/)

[![A UML é uma linguagem-padrão para a elaboração da estrutura de projetos de software. (LOGO UML)](data:image/gif;base64,R0lGODdhAQABAPAAAP///wAAACwAAAAAAQABAEACAkQBADs=)](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/uml-unified-modeling-language-logo/)A UML é uma linguagem-padrão para a elaboração da estrutura de projetos de software. (LOGO UML)

Mesmo que a [diagramação](https://alff.medium.com/o-que-são-os-diagramas-de-caso-de-uso-4432a726b2f8) dos casos de uso seja uma tarefa mais comum do [analista de requisitos](https://analisederequisitos.com.br/engenharia-e-analise-de-requisitos/), é possível também que sua elaboração seja feita pelo[ analista de negócios](https://analisederequisitos.com.br/grupo-analise-de-requisitos-no-telegram/) da equipe.

## A importância do uso dos diagramas UML

Quando elaborados por analistas que dominam a linguagem de notação UML, os casos de uso tornam-se uma importante ferramenta de documentação e validação de requisitos.

A utilização de **diagramas de caso** **de uso** pode (deve) ser combinada com o documento de especificação de requisitos utilizado pela equipe, sendo fundamental para a [engenharia de requisitos](https://www.analisederequisitos.com.br/) atual.



O entendimento de diagramas UML não apresenta maiores dificuldades, já que seus elementos e simbologia são altamente lúdicos.

Entretanto, mesmo considerando a facilidade de entendimento é necessário que os envolvidos tenham domínio da notação **UML**. Caso contrário a utilização de tais diagramas pode impor riscos graves para o projeto.

## Utilizando UML e Padrões de Craig Larman

Um literatura recomenda a todos os profissionais que desejam compreender melhor e utilizar de forma mais eficiente os diagramas UML é o livro “Utilizando UML e Padrões” do autor Craig Larman.

Você pode fazer o download gratuito do livro em: [Livro/PDF: Utilizando UML e Padrões de Craig Larman](https://analisederequisitos.com.br/utilizando-uml-e-padroes-craig-larman/)

[![Livro para download grátis em PDF: Livro - Utilizando UML e Padrões: uma Introdução à Análise e ao Projeto Orientados a Objetos e ao Desenvolvimento Iterativo.](data:image/gif;base64,R0lGODdhAQABAPAAAP///wAAACwAAAAAAQABAEACAkQBADs=)](https://analisederequisitos.com.br/utilizando-uml-e-padroes-craig-larman/utilizando-uml-e-padroes-craig-larman-livro-pdf-download/)Livro para download grátis em PDF: Livro – Utilizando UML e Padrões: uma Introdução à Análise e ao Projeto Orientados a Objetos e ao Desenvolvimento Iterativo.|

## Componentes do diagrama de caso de uso

Todo diagrama de caso de uso é composto por elementos que indicam entidades, requisitos, processos, restrições e atuadores. Graficamente existe a representação por:

- Atores
- Casos de Uso (requisitos de sistema ou negócio)
- Relacionamento de inclusão (*include*)
- Relacionamento de extensão *(extend)*
- Relacionamento de herança *(pattern)*



Através destes três tipos de representação é possível elaborar modelagens complexas e detalhadas da execução de determinada **rotina**, **função** ou **condição** em um software.

![Diagrama de casos de uso UML, aprenda como funcionam.](data:image/gif;base64,R0lGODdhAQABAPAAAP///wAAACwAAAAAAQABAEACAkQBADs=)Diagrama de casos de uso UML, aprenda como funcionam.

### Atores do caso de uso

É toda e qualquer entidade que, durante a execução de determinada tarefa, rotina ou função interage com sistema ou algum artefato de saída por ele produzido.

Essa definição do **ator de um caso** aplica-se para sistemas de software ou sistemas de negócios. A representação gráfica do ator é feita por um boneco de linhas retas e um círculo representando sua cabeça, no estilo “boneco palito”.

- ![Representação dae um “ator” em um diagrama de casos de uso UML.](data:image/gif;base64,R0lGODdhAQABAPAAAP///wAAACwAAAAAAQABAEACAkQBADs=)Representação de um “ator” em um diagrama de casos de uso UML.

### Requisitos no caso de uso

É a representação de **toda e qualquer interação com o sistema** (seja ele um software ou não). Um caso de uso pode representar uma interação com **um ou mais atores**, uma interação com um ou mais casos de uso adicionais.

Ainda é correto afirmar que um caso de uso pode contem um requisito de sistema, seja ele um [requisito funcional ou não funcional](https://analisederequisitos.com.br/requisitos-funcionais-e-requisitos-nao-funcionais-o-que-sao/).

Um caso de uso pode também representar uma **interação com outros casos de uso** e com um ou vários atores simultaneamente. A representação padrão é um círculo contendo em seu interior o título do caso de uso.

- ![Representação de um “caso de uso” em um diagrama de casos de uso UML.](data:image/gif;base64,R0lGODdhAQABAPAAAP///wAAACwAAAAAAQABAEACAkQBADs=)Representação de um “caso de uso” em um diagrama de caso de uso UML.

### Indicadores de relacionamento:

Em um diagrama de caso de uso elaborado na [linguagem UML](https://pt.wikipedia.org/wiki/UML) existem três tipos de relacionamentos possíveis, *include, extend* e herança.

Os relacionamentos entre casos de uso do tipo include e *extend* são representados por uma linha pontilhada com seta, já os **relacionamentos de herança** são representados por uma linha sólida com seta.

### *Include* ou Inclusão

Indica que o tipo de relacionamento entre dois casos de uso implica na **obrigatoriedade da execução** do caso de uso que está sendo incluído no caso de uso base.

### Exemplo de caso de uso *include*

De forma simples e genérica podemos dizer que: quando um caso de uso “A” possui relacionamento do tipo *include* com o caso de uso “B”, sua execução deverá também executar o caso de uso “B”.

- ![Representação de um relacionamento “include” em um diagrama de caso de uso UML.](data:image/gif;base64,R0lGODdhAQABAPAAAP///wAAACwAAAAAAQABAEACAkQBADs=)Representação de um relacionamento “include” em um diagrama de caso de uso UML.

### *Extend* ou Extensão

Este tipo de relacionamento indica que dois ou mais casos de uso relacionados **podem** **ou não** executar o caso de uso que recebe o relacionamento do tipo *extend.*

### Exemplo de caso de uso e*xtend*

O caso de uso “H” possui relacionamento do tipo *extend* com o caso de uso “P”, tal relacionamento significa que ao executar o caso de uso “H” pode-se ou não requisitar a execução do caso de uso “P”.

De forma objetiva, podemos afirmar que um relacionamento *extend* indica que a execução do caso de uso relacionado é opcional, **não implicando no sucesso** da execução do caso de uso base.

- ![Representação de um relacionamento “extend” em um diagrama de caso de uso UML.](data:image/gif;base64,R0lGODdhAQABAPAAAP///wAAACwAAAAAAQABAEACAkQBADs=)Representação de um relacionamento “extend” em um diagrama de caso de uso UML.

### Herança e generalização

O relacionamento do tipo herança ou ainda chamado de *patern*, é um relacionamento possível entre dois ou mais atores de um caso de uso.

A linguagem **[UML](http://www.dsc.ufcg.edu.br/~jacques/cursos/map/html/uml/uml.htm) não permite** entretanto, o relacionamento de **herança entre casos de uso**. É muito comum encontrar diagramas de caso de uso onde o analista realizou essa ligação não permitida, dessa forma é necessário atenção durante a criação dos relacionamentos do caso de uso.

Quando dois ou mais atores de um diagrama de caso de uso estão relacionados através da representação gráfica de herança, indica que o ator que solicita a herança de outro ator, **deve herdar todas as permissões e características do ator que** recebe o relacionamento.

Este tipo de ligação entre atores é extremamente útil para o **reaproveitamento de características** em diagramas que representam sistemas complexos ou grandes cenários de interação.

- [![Representação de um relacionamento “herança” em um diagrama de caso de uso UML.](data:image/gif;base64,R0lGODdhAQABAPAAAP///wAAACwAAAAAAQABAEACAkQBADs=)](https://www.analisederequisitos.com.br/wp-content/uploads/2018/02/diagrama-casos-de-uso-uml-herança-4-573x365.png)Representação de um relacionamento “herança” em um diagrama de caso de uso UML.

## Exemplos de casos de uso

Uma vez que tenhamos bem claro quais são os componentes de um diagrama de caso de uso vamos entender como ele é elaborado.

Abaixo mostraremos um exemplo de diagrama de caso de uso extremamente simples, apenas para representar seu uso.

Não se preocupe, mesmo que pareça ter pouco sentido, o diagrama é muito fácil de entender e útil.

### Exemplo de relacionamento de herança *(pattern)*

O diagrama acima é composto por dois atores diferentes e cinco casos de uso distintos. Logo de início, podemos observar que entre o ator “Cliente” e o ator “Usuário” existe um relacionamento de herança, indicando que o “Cliente” herdará todas as atribuições e permissões do ator “Usuário”.

### Exemplo de relacionamento de execução

O caso de uso “Realizar cadastro” possui um relacionamento de execução com o ator “Usuário”, indicando que tal ator pode solicitar o caso de uso.

### Exemplo de relacionamento *include* e *extend*

O caso de uso “Consultar Cardápio” também é acionado pelo ator “Usuário”. Diferente do caso de uso anterior, este possui um relacionamento do tipo *include* com o caso de uso “Efetuar login”.

Ele indica que para a execução do “Consultar cardápio” obrigatoriamente o caso de uso “Efetuar login” deve ser executado.

Este caso de uso possui ainda um relacionamento do tipo *extend* com o caso de uso “Realizar pedido”. O *extend* entre os dois casos de uso citados, indica que o caso de uso “Realizar pedido” pode ou não ser executado em decorrência do seu extensor (“Consultar cardápio”).

Por último existe o caso de uso “Efetuar pagamento”, que é incluído (relacionamento tipo *include)* pelo caso de uso “Realizar pedido”.

Este relacionamento está definindo a obrigatoriedade da execução do incluído para a finalização do caso de uso base.

------

Conheça e aprenda mais sobre o processo de gerenciamento de projetos e análise de requisitos de software. Recomendamos a leitura dos seguintes artigos:

- [O que são Requisitos Funcionais e Não Funcionais?](https://analisederequisitos.com.br/requisitos-funcionais-e-nao-funcionais/)
- [34 técnicas de Análise de Negócios do BABOK®](https://analisederequisitos.com.br/lista-34-tecnicas-de-analise-de-negocios-babok-v2-0/)
- [Técnicas de levantamento de requisitos](https://analisederequisitos.com.br/tecnicas-de-levantamento-de-requisitos/)
- [Protótipos de interface usando Pencil](https://analisederequisitos.com.br/prototipos-de-interface-pencil/)
- [Livro/PDF: Guia do Scrum – Ken Schwaber](https://analisederequisitos.com.br/guia-do-scrum/)



[análise de requisitos](https://analisederequisitos.com.br/tag/analise-de-requisitos/) [caso de uso](https://analisederequisitos.com.br/tag/caso-de-uso/) [diagrama de caso de uso](https://analisederequisitos.com.br/tag/diagrama-de-caso-de-uso/) [levantamento de requisitos\]](https://analisederequisitos.com.br/tag/levantamento-de-requisitos/) [uml](https://analisederequisitos.com.br/tag/uml/)

[![Foto de Chico Alff](https://analisederequisitos.com.br/wp-content/uploads/2018/02/chico-alff-analise-requisitos-e1519081966448-180x180.jpg)](https://analisederequisitos.com.br/author/chicoalff/)

### [Chico Alff](https://analisederequisitos.com.br/author/chicoalff/)

Paranaense com alma paulistana e coração italiano. Bacharel em Engenharia de da Computação (Laurea magistrale in Ingegneria e Scienze Informatiche) pela Università degli Studi di Verona, Técnologo em Sistemas para Internet. Iniciou também uma licenciatura em História Italiana e Letras Clássicas pela Università di Bologna, aventura que infelizmente não foi concluída. Atualmente é acadêmico do curso de Engenharia Civil na Faculdade Mater Dei.Trabalha com desenvolvimento de software desde 2010, especializou-sem em Engenharia de Requisitos, Análise de Negócios e Gerenciamento de Projetos.Ao longo de sua carreira autou em projetos para a administração pública, sistemas de ERP, processamento distruibuído e inteligência artificial.

- [Website](https://analisederequisitos.com.br/)
- [Facebook](https://www.facebook.com/chicoalff)
- [Twitter](https://twitter.com/whereisalff)
- [Linkedin](https://www.linkedin.com/in/alff/)
- [Pinterest](https://br.pinterest.com/analisederequisitos/)
- [Instagram](https://www.instagram.com/whereisalff/)

### Deixe um comentário

Você precisa fazer o [login](https://analisederequisitos.com.br/wp-login.php?redirect_to=https%3A%2F%2Fanalisederequisitos.com.br%2Fdiagrama-de-caso-de-uso%2F) para publicar um comentário.

Últimas postagens

- [![Criando fluxos de processo BPMN e diagramas UML grátis direto no Google Drive](https://analisederequisitos.com.br/wp-content/uploads/2022/02/curso-projetos-de-sistemas-de-ti-390x220.png)](https://analisederequisitos.com.br/crie-processos-fluxos-diagramas-visual-paradigm/)

  [Crie processos BPMN e diagramas UML com Visual Paradigm](https://analisederequisitos.com.br/crie-processos-fluxos-diagramas-visual-paradigm/)

- [![Gerenciamento de Projetos: urso online, gratuito e com certificado.](https://analisederequisitos.com.br/wp-content/uploads/2020/03/gerencialmento-de-projetos-curso-gratis-de-ti-gratis-fgv.png)](https://analisederequisitos.com.br/curso-de-gerenciamento-de-projetos-fgv/)

  [Curso de gerenciamento de projetos grátis, com certificado](https://analisederequisitos.com.br/curso-de-gerenciamento-de-projetos-fgv/)

- [![O que é um requisito de software? Como podemos realizar a identificação dos requisitos do sistema?](https://analisederequisitos.com.br/wp-content/uploads/2018/03/o-que-sao-requisitos-de-software.jpg)](https://analisederequisitos.com.br/requisitos-funcionais-e-nao-funcionais/)

  [O que são Requisitos Funcionais e Não Funcionais?](https://analisederequisitos.com.br/requisitos-funcionais-e-nao-funcionais/)

- [![Análise de negócios: as 34 técnicas do BABok V3](https://analisederequisitos.com.br/wp-content/uploads/2019/01/img_1871-1.jpg)](https://analisederequisitos.com.br/lista-34-tecnicas-de-analise-de-negocios-babok-v2-0/)

  [34 técnicas de Análise de Negócios do BABOK®](https://analisederequisitos.com.br/lista-34-tecnicas-de-analise-de-negocios-babok-v2-0/)

Mais lidos

- [Protótipos de interface com Balsamiq Mockups](https://analisederequisitos.com.br/prototipos-de-interface-balsamiq/)
- [O que são Requisitos Funcionais e Não Funcionais?](https://analisederequisitos.com.br/requisitos-funcionais-e-nao-funcionais/)
- [Documento de requisitos de software](https://analisederequisitos.com.br/documento-de-requisitos-de-software/)
- [Diagrama de caso de uso](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/)
- [Técnicas de levantamento de requisitos](https://analisederequisitos.com.br/tecnicas-de-levantamento-de-requisitos/)

[Análise de Requisitos | analisederequisitos.com.br](https://analisederequisitos.com.br/) | 2011 - 2021 - Primeiro portal em língua portuguesa dedicado exclusivamente à Análise de Requisitos, Desenvolvimento Ágil, Análise de Negócio, Gerenciamento de Projetos e Engenharia de Software

Todo conteúdo publicado é de propriedade de Análise de Requisitos. O uso e reprodução de qualquer material é permitida, desde que observada e indicada a fonte.

[Botão Voltar ao topo](https://analisederequisitos.com.br/diagrama-de-caso-de-uso/#go-to-tie-body)