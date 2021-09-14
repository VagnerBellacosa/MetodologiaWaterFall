# O que é Cross-site Scripting (XSS)?

## Cross-site Scripting (XSS) é um tipo de ataque de injeção de código malicioso em aplicações web, classificado entre as principais vulnerabilidades no [OWASP Top 10 2017](https://www.owasp.org/images/7/72/OWASP_Top_10-2017_(en).pdf.pdf).

Por exemplo, um atacante aproveita uma dada vulnerabilidade em um website considerado confiável pelos seus visitantes para instalar um script que irá executar ações maliciosas como copiar cookies, tokens ou roubar dados de acesso registrados no navegador web do usuário.

Em geral, o ataque acontece em função de falha na validação dos dados de entrada do usuário e a resposta do servidor Web. Dificilmente um usuário será capaz de identificar a falha na comunicação entre a entrada de dados no navegador e a resposta do servidor de destino.

### **Tipos de XSS**

Existem três tipos de ataques de injeção de script:

- **Persistente:** O script injetado pelo atacante fica alojado de forma permanente no servidor de destino. O usuário pode acionar a carga apenas por navegar num website infectado; portanto, qualquer usuário pode executar o código malicioso sem nenhuma ação específica. Esse é um tipo bastante perigoso de ataque, pois o código pode estar alojado em diversos destinos, como campos de comentário, base de dados etc.
- **Não persistente/Refletido:** Neste caso, o script não estará alojado em um servidor de destino e por isso precisará ser entregue para cada vítima. Isso pode acontecer por várias formas de engenharia social, por exemplo uma mensagem de erro ou um resultado de busca. Uma forma frequente será um link distribuído por meio de esquemas de phishing. Ao acionar o servidor, por meio do link, o script será refletido e executado no navegador. Esta técnica é a mais frequente.
- **Baseado em DOM**: O terceiro tipo de ataque XSS explora o Document Object Model (DOM), que é a interface que define a leitura de HTML e XML no navegador. O script é capaz de alterar as propriedades das aplicações que executam estes tipos de extensões diretamente no navegador, portanto sem necessidade de interação com o servidor para performar o ataque. Neste caso, a falha está na validação do código HTML ou XML no navegador.

### **Cross-site request forgery (CSRF)**

Um método de ataque semelhante ao XSS é o CSRF. A diferença mais central é que os ataques de CSFR necessitam de uma sessão autenticada para alcançar o seu objetivo. Portanto, o atacante explora apenas sessões em que o usuário está logado em serviços web. Outra diferença importante é o objetivo do CSFR, que está frequentemente relacionado a solicitações de mudança de estado já que o atacante herda os privilégios de uma sessão autenticada – por exemplo, pode ser usado para modificar as configurações de firewall de rede.

### **Como prevenir ataques XSS**

Ataques XSS ocorrem quando:

1. Uma aplicação web permite a entrada de dados, porém não é capaz de validar os dados de forma eficaz;
2. A entrada de dados é feita por meio de conteúdo ativo (por exemplo HTML, JavaScript, ActiveX, Flash, Silverlight etc).

Portanto, considerar a entrada de dados como não-confiável é uma regra básica para a prevenir esse tipo de ação. No caso de entrada de dados para o contexto HTML, por exemplo, conteúdos ativos devem ser evitados.

As ferramentas de defesa ativa que seguirem estas regras serão fortes aliados contra ataques de XSS. Por exemplo, **[sistema de prevenção contra intrusos (IPS)](http://blockbit.com/produtos/intrusion-prevention-system/)** é crucial para classificar as entradas de usuário por meio de aplicações web a partir de whitelists. Entradas que não correspondem às regras devem ser rejeitadas. Em outras palavras, a regra de ouro para o IPS é negar todas as entradas, e permitir apenas como exceção.

Considerando que os ataque XSS aproveitam brechas em aplicações web, a adoção de uma **ferramenta de gestão de vulnerabilidades** para escanear tais aplicações pode ser relevante, pois permite obter informações recorrentes sobre o status de segurança das aplicações utilizadas pelos seus usuários, seja de forma autenticada ou não-autenticada.

Diversas recomendações para a prevenção de ataques XSS podem ser extraídas do **[Guia de Prevenção de XSS do OWASP](https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet)** (em inglês).

## Sugestões de leitura

[![Internet Segura: Fazer o Simples é a Grande Dica](https://www.blockbit.com/wp-content/uploads/2022/02/Depositphotos_180863630_XL-300x163.jpg)](https://www.blockbit.com/pt/blog/internet-segura-fazer-o-simples-e-a-grande-dica/)

### [Internet Segura: quando fazer o simples é a grande dica para a segurança digital das empresas](https://www.blockbit.com/pt/blog/internet-segura-fazer-o-simples-e-a-grande-dica/)

Você já deve ter ouvido falar que prevenir é o

[LEIA MAIS](https://www.blockbit.com/pt/blog/internet-segura-fazer-o-simples-e-a-grande-dica/)

[![FAKE NEWS: as mentiras que são verdadeiras ameaças para os negócios](https://www.blockbit.com/wp-content/uploads/2022/01/Depositphotos_206853832_XL-300x200.jpg)](https://www.blockbit.com/pt/blog/fake-news-mentiras-que-sao-ameacas-para-os-negocios/)

### [FAKE NEWS: mentiras que são ameaças para os negócios](https://www.blockbit.com/pt/blog/fake-news-mentiras-que-sao-ameacas-para-os-negocios/)

Em uma era cada vez mais conectada e descentralizada, com

[LEIA MAIS](https://www.blockbit.com/pt/blog/fake-news-mentiras-que-sao-ameacas-para-os-negocios/)

[![img](https://www.blockbit.com/wp-content/uploads/2021/12/Depositphotos_111393486_XL-1-300x200.jpg)](https://www.blockbit.com/pt/blog/principais-tendencias-e-ameacas-para-a-ciberseguranca-em-2022/)

### [Principais tendências e ameaças para a Cibersegurança em 2022](https://www.blockbit.com/pt/blog/principais-tendencias-e-ameacas-para-a-ciberseguranca-em-2022/)

Para acompanhar a transformação digital, empresas de todos os segmentos

[LEIA MAIS](https://www.blockbit.com/pt/blog/principais-tendencias-e-ameacas-para-a-ciberseguranca-em-2022/)