# [Guia completo] Como lidar com software legado?

- julho 5, 2019

Trabalhar com um software novo, utilizando tecnologias que estão no topo no mercado hoje em dia, como **[React, Angular](https://geekblogti.wpengine.com/react-vs-vue-vs-angular-qual-escolher/)**, Elixir, Rust, Kotlin, [**Svelte** ](https://geekblogti.wpengine.com/svelte-o-framework-javascript-que-nao-e-um-framework/)costuma fazer os olhos de muitos desenvolvedores brilharem.

O que acontece é que nem sempre trabalhamos com tecnologia de ponta. Temos momentos — ou até **100% do tempo** — em que precisamos colocar as mãos no projeto antigo da empresa e fazer manutenção em um software legado. A má notícia é que, às vezes, o código tem mais de 15 anos de mercado.

Alguns softwares legados tem módulos tão mal escritos, que lembram um buraco negro. Só pronunciando o seu nome, o desânimo toma conta da equipe.

Brincadeiras à parte, código complexo, milhares de linhas de bagunça, sem testes automatizados, documentação inexistente, com inúmeras responsabilidades, gera muito desconforto.

É sobre esse desconforto e sobre técnicas para você melhorar o código legado que nós vamos falar.

Me acompanhe!

[![img](https://geekblogti.wpengine.com/wp-content/uploads/2019/10/CTA-Emprego-dos-sonhos-4-1024x209.jpg)](https://www.geekhunter.com.br/criar-perfil-gratis?utm_source=Blog&utm_medium=cta&utm_campaign=cadastro-de-candidato)

**Conteúdo** [ocultar](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#) 

[1 Encarando o software legado de frente](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#Encarando_o_software_legado_de_frente)

[2 1. Qual o objetivo com a refatoração?](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#1_Qual_o_objetivo_com_a_refatoracao)

[2.1 Quanto tempo a refatoração tomará?](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#Quanto_tempo_a_refatoracao_tomara)

[3 2. Vale a pena refatorar na validação de produto?](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#2_Vale_a_pena_refatorar_na_validacao_de_produto)

[4 3. O código está muito ruim. Vale a pena começar de novo?](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#3_O_codigo_esta_muito_ruim_Vale_a_pena_comecar_de_novo)

[5 4. Código legado sem manutenção, mas bem escrito](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#4_Codigo_legado_sem_manutencao_mas_bem_escrito)

[6 Start na refatoração: planejamento](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#Start_na_refatoracao_planejamento)

[6.1 1. Esteira de etapas automatizada](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#1_Esteira_de_etapas_automatizada)

[6.2 2. Análise estática de código](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#2_Analise_estatica_de_codigo)

[6.3 3. IDE](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#3_IDE)

[7 Colocando as mãos no código](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#Colocando_as_maos_no_codigo)

[7.1 Testes de unidade](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#Testes_de_unidade)

[7.2 Testes de integração](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#Testes_de_integracao)

[7.3 Testes de aceitação](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#Testes_de_aceitacao)

[7.4 Documentação Técnica](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#Documentacao_Tecnica)

[7.5 Documentação não-técnica](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#Documentacao_nao-tecnica)

[8 Como evitar que o projeto volte a apresentar problemas estruturais?](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#Como_evitar_que_o_projeto_volte_a_apresentar_problemas_estruturais)

[8.1 1.Clean Code.](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#1Clean_Code)

[8.2 2. Continuous Delivery: Reliable Software Releases Through Build, Test, and Deployment Automation.](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#2_Continuous_Delivery_Reliable_Software_Releases_Through_Build_Test_and_Deployment_Automation)

[8.3 3. Refactoring improving the design of existing code (1a/2a edição)](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#3_Refactoring_improving_the_design_of_existing_code_1a2a_edicao)

[9 Afinal, como lidar com software legado?](https://blog.geekhunter.com.br/lidando-com-codigo-legado/#Afinal_como_lidar_com_software_legado)

## Encarando o software legado de frente

![img](https://geekblogti.wpengine.com/wp-content/uploads/2019/04/8-Homem-computador-1-1.jpg)

Uma estratégia de encarar o problema é o colocando debaixo do tapete e fingir que ele não existe. Até chegar o momento de dar manutenção, cada um na equipe pensa: “*Espero que não seja o infeliz que tem que a missão de mexer naquele troço*”.

Como podemos evitar que aquele simpático trecho de algoritmo vire um Frankstein que coloque medo em qualquer pessoa?

Podemos começar colocando uma luz sobre a escuridão do código e expor os problemas que a bagunça causou.

Mas como medir a qualidade? Testando o código legado?

Identificar as falhas nos dá conhecimento para enfrentá-las. As consequências mais comuns do software legado, são:

-   Baixa velocidade de desenvolvimento;
-   Inseguranças (ou de alterar o código e estragar algo importante, ou de colocar em produção e aí sim estragar tudo);
-   Alta complexidade;
-   Baixa coesão;
-   Alto acoplamento.

Cada dia que o problema que se mantém vivo no código por falta de interesse ou medo, estamos carregando um fardo cada vez mais pesado.

A decisão de não mantê-lo mais daquela maneira, faz com seja reescrito e colocado no eixo. É preciso coragem para transformar, mas, mais do que é isso, é preciso olhar para o problema.

> *“Diga não para bugs tenebrosos de difícil inspeção!”*
>
> **PERITO, Jeferson. 2019.**

Caso caiamos em algum código mal escrito e decidimos refatorá-lo, precisamos avaliar a necessidade e 4 pré-requisitos podem ser respeitados:

## 1. Qual o objetivo com a refatoração?

![programacao usando o computador](https://geekblogti.wpengine.com/wp-content/uploads/2019/04/aplicacao-serverless-com-AWS-como-desenvolver-uma-do-0-min1-1024x683-1-1024x683.jpg)

Nesse momento de validação o objetivo não é criar um código perfeito e dedicar muito tempo nisso. A refatoração pode servir muito para validar idéias que estão sendo propostas e definidas entre os *stakeholders.*

Nunca é a solução final. A ideia pode não ir para frente ou sofrer uma grande alteração de escopo, onde o grande esforço colocado pode ter servido para nada.

**Mas lembre-se:** a qualidade também não deve ser descartada totalmente, principalmente em projetos-protótipos, que tem alguma chance — mesmo que pequena — de serem lançados.

Esses projetos podem ser utilizados como esqueleto em um projeto a ser iniciado, mas vale lembrar que o objetivo principal é a validação de ideias.

*>****>Leitura Recomendada:\****
Leia nosso artigo sobre a* [***importância da documentação de software\***](https://geekblogti.wpengine.com/qual-e-a-importancia-da-documentacao-de-software/)

### Quanto tempo a refatoração tomará?

Caso você opte pela refatoração, tempo x qualidade são essenciais.

Por experiência própria, creio que só com a senioridade para conseguir equilíbrio entre qualidade e tempo de desenvolvimento, pois como disse anteriormente, o seu projeto pré-protótipo pode virar efetivo no futuro.

Você não quer ter que pagar os juros gerados por um débito técnico, certo? Em resumo: a qualidade não deve ser a métrica principal, mas não pode ser esquecida.

***>> Leitura Recomendada:***
*Leia nosso artigo sobre* [***As principais fontes de informação de um programador\***](https://geekblogti.wpengine.com/as-principais-fontes-de-informacao-que-um-programador-deve-conhecer/)

## 2. Vale a pena refatorar na validação de produto?

![img](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201024%20683'%3E%3C/svg%3E)

Em oposição ao caso anterior, aqui estamos falando de um projeto real.

A qualquer momento, módulos inteiros podem virar pó, do dia para a noite. Imagine que o sistema possui poucos clientes ou nenhum.

Em um projeto nesse nível de maturidade, uma estratégia é manter o tronco (*core*) do sistema com uma engenharia razoável e com alta cobertura de testes, pois aqui a chance de grandes mudanças costuma ser menor que nas suas periferias.

Então caso caia em uma periferia, lembre-se que aquilo pode não estar ali amanhã e aquele esforço de refatorar não valha a pena.

*>****>Sugerido:\****
****[Boas práticas técnica para um código limp](https://pt.slideshare.net/rodrigokono/boas-prticas-tcnica-para-um-cdigo-limpo-clean-code)\***[***o\***](https://pt.slideshare.net/rodrigokono/boas-prticas-tcnica-para-um-cdigo-limpo-clean-code)

## **3. O código está muito ruim. Vale a pena começar de novo?**

![img](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201024%20683'%3E%3C/svg%3E)

Imagine que o código está muito ruim. Mesmo assim, eu considero extremismo reconstruir tudo do zero.

Na grande maioria dos casos que presenciei o código era recuperável. O processo pode ser muito doloroso, mas recuperável.

Em minha avaliação era: construir algo do zero poderia levar mais tempo e um congelamento da evolução do quadro de novas tarefas.

Eu pensava que era mais fácil continuar com aquele pedaço de código “*sangrando*” e ir aplicando regra do escoteiro para refatorar os pontos mais acessados enquanto não conseguisse liberar janela de tempo para corrigir os defeitos mais graves.

## **4. Código legado sem manutenção, mas bem escrito**

![img](https://geekblogti.wpengine.com/wp-content/uploads/2019/04/como-funcionam-microservices-1024x683.jpg)

Esse caso é algo que particularmente nunca presenciei, mas achei interessante trazer devido ao fato de ter já estudado como atuar nesse tipo de ocasião.

Caso se depare com esse tipo de projeto — deve ter chego nele por alguma alteração de escopo — o nível de refatoração é baixo.

Os maiores encargos seriam, basicamente, atualização da versão de linguagem e suas bibliotecas visando maior estabilidade, velocidade e correção de bugs.

Outra preocupação são *trade-offs,* que já foi algo válido, mas hoje não faz mais sentido.

[![img](https://geekblogti.wpengine.com/wp-content/uploads/2019/07/CTA-Rodap%C3%A9-Front-end-e-Back-end-58-1024x134.jpg)](https://bit.ly/2JS9hZn)

## Start na refatoração: planejamento

![img](https://geekblogti.wpengine.com/wp-content/uploads/2019/04/comunicacao-desenvolvedores-1024x683.jpg)

Ok, foi decidido dar o pontapé inicial em uma refatoração e você irá se aventurar no código legado. Mas como escrever um código legível?

Para iniciar a nossa aventura precisamos de apoio, ferramentas que nos auxiliem no caminho certo para atingir o objetivo e técnicas comprovadas que garantam a estabilidade do artefato para *deploy.*

Vejamos algumas delas:

### **1. Esteira de etapas automatizada**

Etapas ou *jobs* são processos onde podemos executar *scripts* para realizar alguma tarefa específica.

Então a dica é colocarmos em uma ordem estilo “esteira de montagem”, podendo executar cada etapa em sequência seguindo pré requisitos de execução.

Esses *jobs* ou etapas também podem ser paralelizados de acordo com a necessidade, são disparados por algum gatilho ou manualmente.

**Vamos definir alguns jobs para uma aplicação web:**

- Build;
- Testes de integração;
- Testes de aceitação;
- Execução de scripts de banco de dados;
- Deploy em ambiente de teste;
- Deploy em ambiente de produção.

Com os jobs definidos vamos colocar em uma esteira.

Existem diversas ferramentas que gerenciam jobs de integração contínua (*Integração contínua é uma prática de entregar software de maneira confiável, automatizada com tolerância a falhas. Sugiro estudar fortemente*).

O primeiro job que queremos executar é o **Build.** A sua responsabilidade será de rodar os testes de unidade e empacotar em um arquivo que será a versão candidata para o *deploy* em produção.

É importante colocarmos um gatilho que executará toda vez que houver uma alteração na árvore de arquivos no nosso repositório de código fonte.

O segundo job deve ser executar os *scripts* de banco de dados. A ordem é rodar os testes de integração, após o *build* terminar a execução **com sucesso.**

Caso falhe o *build*, essa etapa não será executada até o job anterior ser corrigido.

O terceiro job, deve ser realizar o *deploy* para o ambiente de teste, caso o job anterior passe com sucesso.

O quarto job é executar os testes de aceitação em ambiente de testes — caso o job anterior passe sem problemas.

O quinto job deve ser deploy em ambiente de produção. **Lembre-se:** você só executará se todos os anteriores passarem, mas o gatilho será manual, pois nem sempre iremos querer um *deploy* em produção.

Com o fim da execução da esteira, temos a garantia de que tudo passou por bateria de scripts, testes e de que tudo correrá bem.

### **2. Análise estática de código**

Adicionamos um passo a mais: a análise estática de código. Essa etapa analisará o código fonte e nos informará o débito técnico.

Até é possível configurar pontos como métodos muito complexos, nomenclatura fora do padrão, números mágicos, entre outros.

Isso garante a qualidade em nível de legibilidade e facilidade de manutenção.

Essa etapa pode ou não causar erro na esteira caso o novo *commit* infrinja essas regras.

### **3. IDE**

Uma IDE ajuda muito hoje em dia por possuir ferramentas de *refactoring.* Essas ferramentas vão desde extração de função, alteração de nome de função/classe (também alterando o código que o chama), entre outras funcionalidades.

Eu particularmente não executo os testes de unidade quando é uma refatoração executada pela IDE, por ter extrema confiança nela.

## **Colocando as mãos no código**

![img](data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%201024%20683'%3E%3C/svg%3E)

Complexidade pequena, pipeline de *build* e *deploy* automatizado, grande e boa cobertura de testes automatizados, código bem estruturado e implantação definida e automatizada, documentação técnica boa e stakeholders acessíveis. O melhor dos mundos para *refactoring*

Nas condições acima, o trabalho é tranquilo. O tipo de trabalho de que falo pode ser remover algum ruído no código, atualização de biblioteca ou até mesmo alguma evolução de código.

Faça refatoração em *baby steps.* A indicação é fazer o *build* e acompanhar o pipeline — *com um bom café quente* — e rodar toda a bateria de testes. 🙂

Ok, vimos um pouco do mundo perto da perfeição. Na vida real isso não vai acontecer com frequência (infelizmente).

É comum vermos projetos em código legado que vem se arrastando por anos.

Isso porque, provavelmente, durante o seu desenvolvimento, não surfaram na vibe dos princípios *clean code.*

O **[livro Clean Code do Uncle Bob](https://www.amazon.com.br/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)** — juntamente com outras pessoas influentes — ajudou a democratizar as práticas que hoje são difundidas amplamente na Engenharia de Software.

Ao pegar softwares legados com muitos anos de existência, a chance de possuir um nível elevado de boas práticas, nos padrões *clean cod*e, é menor do que em softwares escritos hoje em dia.

Vamos ver como proceder em alguns casos que falte ou não seja suficiente alguma prática:

### **Testes de unidade**

Refatorar sem testes de unidade e garantir qualidade é praticamente impossível.

Precisamos de estabilidade e garantia. Fazer isso de maneira manual é muito penoso por causa do tempo para testar.

Enquanto um ser humano levaria dezenas de horas, a máquina leva poucos segundos. Mas, caso não tenha testes de unidade, mãos à obra.

Não comece sem antes ver o comportamento mapeado pelos testes. Claro, quando for executado pela esteira com sucesso.

A partir disso então podemos partir para alterar o código caso não precise de…

### **Testes de integração**

Pode ser um passo opcional, o trecho de código pode não interagir com outros recursos externos como banco de dados, arquivos de sistemas, *API* e etc.

Vale lembrar da pirâmide de testes, pois testes de integração costuma ter um custo de tempo e/ou recursos da máquina, e o ciclo da pipeline tem que ser o mais rápido possível. a

Aqui vale a senioridade mapear o peso de ter esse teste de integração.

Eu particularmente acho essencial ter testes de integração no core do sistema para blindar de bugs.

Outras partes eu coloco na balança é a complexidade ou alta sensibilidade a falha, caso não possuir esses detalhes, um mock de testes resolve bem simulando o comportamento da interação entre os componentes.

***>> Leitura Recomendada:***
*Leia nosso artigo sobre as diferenças entre* **[\*UX e UI\*](https://geekblogti.wpengine.com/front-end-descomplicado-ux-ui/)**

### **Testes de aceitação**

O grande porém é que o tempo de execução, que é alto. Algumas dezenas de testes pode levar + de 10 minutos para executar, gerando grande atraso.

É possível simular o comportamento do usuário por meio de testes automatizados, também conhecidos como testes de aceitação.

Novamente aqui vale avaliar se tudo o que será refatorado merece testes.

No caso Landing Pages, login no sistema e o core são bons candidatos a ter testes de aceitação. Vale uma avaliação criteriosa quanto às Landing Pages e Login, pois são as portas de entrada dos usuários do sistema.

### **Documentação Técnica**

Esse tópico pode incomodar algumas pessoas, principalmente aquelas pessoas usam[ **metodologias ágeis**](https://geekblogti.wpengine.com/tudo-que-voce-precisa-saber-sobre-agile-scrum-e-kanban/).

Quem trabalha com metodologia ágil defende comunicação sobre documentação. Isto é, a coloca em segundo plano, mas não elimina a utilização.

Documentação técnica pode ser utilizada para clarificar idéias em alto nível.

Ela tem que ser visível a todos e não escondida em um local que ninguém veja. Deve ser simples, leve para todos da equipe conseguirem entender e identificar as nuances.

Existem alguns tipos de documentação de alto nível que pode ser úteis como diagrama de contexto, atividade e máquina de estado.

Processos que rodam em *background,* que sofrem pouca manutenção, definição de arquitetura em alto nível ou código em baixo nível são candidatos de implementação de documentação técnica.

### **Documentação não-técnica**

Documentação não-técnica são geralmente escritas por profissionais de negócio, com acompanhamento da equipe de desenvolvimento.

Aqui são usados documento de visão, users stories, ou outra forma de padronização de definição, não necessariamente é um requisito para um software de sucesso.

Mas, em muitos casos é de grande importância estratégica. Esses documentos servem como pedra fundamental e, estruturar de maneira textual as funcionalidades do sistema e como o software se comporta, mantendo um histórico e o contrato que o código-fonte se espelha, ajuda muito.

A escrita de documentação não técnica costuma ser um trabalho das pessoas de negócio, não do setor de TI.

Mas, se identificarmos uma falha que afeta o *business* nosso dever como profissional é ajudar na escrita.

Vale a pena a implementação em uma refatoração apenas em caso seja da cultura implementar.

Se não possui, apenas ignore. No entanto, se sentir a real necessidade da documentação não-técnica, reúna os interessados e faça uma mesa redonda explicando a necessidade.

***>> Leitura Recomendada:**
Leia nosso artigo sobre a*[ ***história do mercado front-end\***](https://geekblogti.wpengine.com/mercado-front-end-da-origem-ate-o-futuro/)

## Como evitar que o projeto volte a apresentar problemas estruturais?

![img](https://geekblogti.wpengine.com/wp-content/uploads/2019/04/mercado-de-ti-no-brasil-min-1-1024x683.jpg)

Uma prática que muitos gurus da tecnologia defendem é a regra do escoteiro: “*Deixar o local de acampamento melhor do que você encontrou*”.

“Melhor do que você encontrou” não significa o melhor possível.

O importante é resolver alguns dos problemas ponderando com o tempo que tem disponível para *refactoring*.

Você tinha 10 problemas em uma classe e eliminou 3? Ótimo, ficou melhor do que antes. Com o tempo os módulos que sofrem mais alterações tendem ser os melhores escritos.

Refatorar de maneira passiva ajuda a manter a boa qualidade, cria a cultura de boas práticas e evita ter que alocar tempo para se dedicar a grandes refatorações de sistema.

Caso queira se aprofundar os estudos, segue a sugestão de 3 livros:

### 1.[Clean Code.](https://www.amazon.com.br/Clean-Code-Handbook-Software-Craftsmanship-ebook/dp/B001GSTOAM/ref=sr_1_1?__mk_pt_BR=ÅMÅŽÕÑ&keywords=clean+code&qid=1555527962&s=digital-text&sr=1-1)

Livro clássico que reuniu diversas práticas de código limpo.

### *2. [Continuous Delivery: Reliable Software Releases Through Build, Test, and Deployment Automation.](https://www.amazon.com.br/Continuous-Delivery-Deployment-Automation-Addison-Wesley-ebook/dp/B003YMNVC0)*

Ensina passo-a-passo a como automatizar o processo de entrega de software em produção.

### *3. [Refactoring improving the design of existing code](https://www.amazon.com.br/Refactoring-Improving-Existing-Addison-Wesley-Signature-ebook/dp/B07LCM8RG2/ref=sr_1_1?__mk_pt_BR=ÅMÅŽÕÑ&keywords=Refactoring+improving+the+design+of+existing+code&qid=1555527999&s=digital-text&sr=1-1)*[ ](https://www.amazon.com.br/Refactoring-Improving-Existing-Addison-Wesley-Signature-ebook/dp/B07LCM8RG2/ref=sr_1_1?__mk_pt_BR=ÅMÅŽÕÑ&keywords=Refactoring+improving+the+design+of+existing+code&qid=1555527999&s=digital-text&sr=1-1)*[(1a/2a edição)](https://www.amazon.com.br/Refactoring-Improving-Existing-Addison-Wesley-Signature-ebook/dp/B07LCM8RG2/ref=sr_1_1?__mk_pt_BR=ÅMÅŽÕÑ&keywords=Refactoring+improving+the+design+of+existing+code&qid=1555527999&s=digital-text&sr=1-1)*

Livro do Martin Fowler sobre refatoração de código legado o tornando atual, mapeando diversas técnicas e processos.

[![img](https://geekblogti.wpengine.com/wp-content/uploads/2019/07/CTA-Rodap%C3%A9-Front-end-e-Back-end-24-1024x134.jpg)](https://bit.ly/2JS9hZn)

## Afinal, como lidar com software legado?

Software é desenvolvido por uma empresa e ela possui cultura, se ela não tem no sangue testes automatizados e clean code, pode ser um grande desafio trazer boas práticas porque mudança de cultura é complexo e demorado.

Organizar *workshops* para os desenvolvedores e apresentação formal para a gerência sobre as vantagens práticas de clean code, agiliza mudanças, diminui stress e pode ser um início de mudança de paradigma no local onde você trabalha.

Lembre-se de não ficar desapontado(a) ou indignado(a) com a pessoa que escreveu daquela maneira.

Faça um exercício de empatia e imagine qual era o clima da empresa, o nível técnico, a cultura e a exigência da época. Outro lembrete é que a pipeline e refatoração caminham de mãos dadas!

Boa sorte!

![img](http://s3.amazonaws.com/blog-geek-midia/wp-content/uploads/2019/01/21164829/perfil.jpeg)

[Jeferson Perito](https://blog.geekhunter.com.br/author/jeferson-perito/)