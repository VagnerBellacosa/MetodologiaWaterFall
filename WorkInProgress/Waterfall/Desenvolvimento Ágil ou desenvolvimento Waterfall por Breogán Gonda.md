# Desenvolvimento Ágil ou desenvolvimento Waterfall? por Breogán Gonda*

Outubro 05, 2020

Desenvolvimento Ágil ou desenvolvimento Waterfall? É uma velha questão, cuja resposta eu tenho dedicado os últimos 35 anos. Os fatos nos dizem que o paradigma Waterfall dominava totalmente o mundo e que, pouco a pouco, foi substituído pelo paradigma Ágil em muitas empresas, mas que seguem existindo outras, especialmente as grandes corporações, que permanecem prisioneiras do velho paradigma.

![Breogán Gonda*](https://www.genexus.com/media/images/bgv-2016.jpg?timestamp=20171211192735)

Desenvolvimento Ágil ou desenvolvimento Waterfall? É uma velha questão, cuja resposta eu tenho dedicado os últimos 35 anos. Os fatos nos dizem que o paradigma Waterfall dominava totalmente o mundo e que, pouco a pouco, foi substituído pelo paradigma Ágil em muitas empresas, mas que seguem existindo outras, especialmente as grandes corporações, que permanecem prisioneiras do velho paradigma.

Por que quero falar agora sobre isso? Porque baixei da Amazon e li o livro: "Why Agile is Falling at Large Companies”, de Ms. Geri Schneider Winters. Meu primeiro pensamento: "outro livro que tenta provar que as coisas não pode ser feitas, que as mudanças não são possíveis". Com todo o cuidado e respeito, eu disse: ler aqueles que pensam como a mim pode ser agradável, embora provavelmente inútil, ler aqueles que pensam de forma diferente é sempre útil.

A leitura foi gratificante: o livro explora profunda e seriamente a questão. Em vez de colocar a ênfase na impossibilidade (como eu suponha ao ler o título), que nos impele a aplicar o paradigma Ágil de forma responsável, sólida, medida, tendo em conta todos os elementos necessários para o sucesso. Mas eu não vou falar mais sobre isso aqui: Sinceramente, recomendo a leitura do livro!

**Paradigma Waterfall**

O paradigma Waterfall implica uma análise monolítica, muito profunda e detalhada do problema a ser resolvido e a resolução total do mesmo ao nível do projeto, para passar em seguida para a implementação. Será que funciona? Enfatiza a previsibilidade (custo em tempo e dinheiro) e, idealizada, tudo funciona bem, desde que o projeto inicial se ajuste a realidade, não contenha erros significativos e que essa realidade não mude muito durante o projeto.

Este paradigma foi pensado para outras circunstâncias, em que o tamanho dos sistemas e, acima de tudo, a velocidade de mudança eram muito menores do que hoje.

No início dos anos 80 começamos a ser procurados para a implementação de grandes sistemas corporativos e imediatamente enfrentamos grandes dificuldades, fomos superando com esforço, mas cada vez mais convencidos de que o paradigma que estávamos usando não era adequado.

No meu caso, em 1984, apareceu uma grande empresa brasileira que precisava de um sistema corporativo baseado em um único grande banco de dados central em torno do qual tudo precisava ser construído. Após a primeira análise se percebeu que se trataria de um banco de dados de pelo menos 500 entidades e ficou claro que enfrentá-lo com o tradicional paradigma Waterfall nos levaria ao fracasso. Também ficou claro que nós não tínhamos um paradigma alternativo, de modo que começamos a investigar, procurando novas soluções.

**Paradigma Ágil**

Muitas pessoas tiveram, mais cedo ou mais tarde, problemas semelhantes. Todos nós fizemos, provavelmente, a mesma pergunta: Com o Waterfall priorizamos a previsibilidade de custos, mas o que ocorre com a qualidade do produto?; Como os sistemas obtidos atendemos às necessidades reais?; Como continuamos a mantê-los válidos e atualizados através do tempo? É razoável pensar que os custos (dinheiro e tempo) serão menores que em Ágil? Na prática tendem a ser muito maiores!

O paradigma Ágil tende a ser um desenvolvimento incremental. Como o caracterizamos? Por uma permanente interação, envolvimento dos usuários, prototipagem oportuna e com o nível adequado de abstração, tudo isso pode ser resumido conceitualmente em: "*feedback*".

Quais os problemas fundamentais que encontramos no Paradigma Ágil? À medida que se avança, são encontradas situações que não estavam previstas. Quando devemos modificar ou adicionar processos para tratar os mesmos dados isto é feito com facilidade. Mas tudo é muito diferente quando as mudanças estruturais são necessárias no banco de dados: o nível de independência entre os dados e os programas que nos fornecem os DBMS é rudimentar e, portanto, quando há mudanças significativas nas estruturas dos dados, você precisa executar um conjunto de operações complexas, tais como, por exemplo, determinar quais os programas permanecerão corretos e quais deverão ser modificados, o que tem custos significativos no tempo, dinheiro e no risco de erros.

Não é assim no paradigma Waterfall? É também, mas Waterfall é destinada a situações de estabilidade, onde há pouca ou nenhuma alteração.

**A necessidade de mudanças estruturais no banco de dados**

Fatalmente devemos cair neste problema?, Não há nenhuma maneira de resolvê-lo automaticamente?

Foram feitas muitas tentativas: por exemplo, no final dos anos 70, ANSI-SPARC emitiu uma recomendação destinada a independência viável entre dados e programas. Então Cincom Sistemas lançou um DBMS (SUPRA), que obedecia razoavelmente a essa recomendação. Mais tarde Microsoft em sua Framework.net incluiu um mecanismo (Datasets/Dataviews) com o mesmo objetivo. Por diferentes razões, estas iniciativas não prosperaram.

Em 1985, com o resultado de investigações próprias, podemos concluir que a melhor maneira de resolver o problema foi a de aumentar o nível de abstração e passar a trabalhar com o conhecimento puro.

Ao longo do tempo temos conseguido uma boa gestão automática do conhecimento dos sistemas de negócios que nos permitem, como subprodutos, a automação de:

\- Projeto, geração, manutenção e reorganização do banco de dados.
\- Geração de projeto e manutenção de programas.

Tudo isso nós temos concretizado em nosso produto GeneXus, amplamente utilizado em mais de 45 países, principalmente em sistemas de missão crítica em empresas de todos os tipos.

**RESUMO:**

O paradigma Waterfall é obsoleto, mas continua existindo porque quase todos os sistemas legados utilizam.
Não é razoável enfrentar hoje sistemas novos com o paradigma Waterfall.

O paradigma Ágil oferece vantagens claras para novas aplicações.

Usando a tecnologia que permite que uma boa independência entre os dados e os programas, de modo a viabilizar um verdadeiro desenvolvimento incremental, ajuda muito.

 ***\* Breogán Gonda\***