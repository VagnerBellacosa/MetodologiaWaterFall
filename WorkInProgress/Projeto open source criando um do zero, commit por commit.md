# Projeto open source: criando um do zero, commit por commit

- [Open Source](https://www.zup.com.br/categorias/open-source) -  21 out 2021

#### Neste artigo você vai ver:

- [Software público x Software Open Source: o que muda?](https://www.zup.com.br/blog/projeto-open-source#texto-blog)
- [O que é DCO e como ele ajuda na gestão de um projeto Open Source?](https://www.zup.com.br/blog/projeto-open-source#texto-blog)
  - [Como eu assino commits dentro do DCO?](https://www.zup.com.br/blog/projeto-open-source#texto-blog)
    - [Algumas maneiras de assinar o commit](https://www.zup.com.br/blog/projeto-open-source#texto-blog)
  - [Assinatura de commits com chave GPG](https://www.zup.com.br/blog/projeto-open-source#texto-blog)
  - [Diferença entre DCO e Signed Commit](https://www.zup.com.br/blog/projeto-open-source#texto-blog)
- [Como o DCO é usado na prática dentro dos projetos Open Source da Zup](https://www.zup.com.br/blog/projeto-open-source#texto-blog)
- [Projeto Open Source, de fato.](https://www.zup.com.br/blog/projeto-open-source#texto-blog)

Um projeto **Open Source** é considerado, pela maior parte de profissionais da tecnologia, como uma porta de entrada, seja para adquirir mais segurança ao praticar suas habilidades técnicas, seja pelo desejo de **inovar** e **colaborar com as comunidades**, garantindo que todas as pessoas possam participar com seus [quatro direitos](https://opensource.org/)**.**

No entanto, existe uma confusão muito comum entre projetos públicos e Open Source. Isso, na prática, gera a falsa impressão de que construir um projeto de código aberto fique apenas em um âmbito mais filosófico, quando na verdade envolve um processo minucioso e detalhado, inclusive nos commits. 

Neste artigo, você vai entender melhor as diferenças entre os tipos de projetos e aprender como, na prática, é planejar e garantir que um projeto que seja Open Source de verdade.

Autores: [Hector Augusto Custodio](https://www.linkedin.com/in/hector-augusto-custódio-0b6aa1136/) e [Otávio Santana](https://www.linkedin.com/in/otaviojava/).

## **Software público x Software Open Source: o que muda?**

Embora sejam semelhantes, um software público não necessariamente segue todos os princípios que devem estar presentes em um projeto [Open Source](https://www.zup.com.br/blog/open-source-no-brasil), uma vez que existem diversos contextos que precisam ser verificados. Por exemplo:

- [Selecionar a licença do seu software](https://www.amazon.com/Understanding-Open-Source-Software-Licensing-ebook/dp/B00BQN40II/).
- Verificar se as suas dependências ou as dependências das suas dependências são compatíveis. Com isso, não corre o risco de quebrar a compatibilidade com o seu software.
- Confirmar se o nome do seu projeto quebra algum *trademarks*.
- Garantir que todas as contribuições sejam, de fato, Open Source.

Isso quer dizer até os commits precisam seguir um padrão? 

Sim! No geral, a maioria dos nossos projetos trabalham com **versionamento de controle**, sendo o [Git](https://www.zup.com.br/blog/git-github-e-gitlab) o principal meio, e o commit é entendido como a menor unidade para a contribuição dos projetos. 

É importante garantir que todas as contribuições devem ser “doadas”, uma vez que tanto elas quanto o próprio software são vistos como propriedades intelectuais, ou seja, pertencentes a alguém. Se a contribuição não estiver alinhada a alguns mecanismos de contribuição da comunidade (como o caso do [Eclipse](https://www.eclipse.org/legal/ECA.php) e da [Apache](https://www.apache.org/licenses/contributor-agreements.html) Foundation) , **o projeto não poderá ser considerado Open Source.**

![Na imagem temos o exemplo de uma contribuição em um projeto Eclipse com a mensagem em inglês “Author(s) covered by necessary legal agreements”, ou “Autor (es) coberto (s) pelos acordos legais necessários”em português.](https://secureservercdn.net/198.71.233.31/36q.76e.myftpupload.com/wp-content/uploads/2021/10/Projeto-open-source-1-1024x416.png)

Por causa disso, muitas dessas fundações possuem mecanismos em seus CI (*Continuous Integration*) que também validam a parte legal. Afinal de contas, o Open Source é a principal motivação destas organizações existirem. 

![Na imagem temos o exemplo de uma contribuição em um projeto Eclipse que mostra a etapa de verificação de acordos legais efetuada com sucesso.](https://secureservercdn.net/198.71.233.31/36q.76e.myftpupload.com/wp-content/uploads/2021/10/Projeto-open-source-2.png)

Contudo, nem todos os projetos possuem uma infraestrutura tão complexa como essas fundações. Como, então, garantir essa governança? A resposta está no **DCO**.

## **O que é DCO e como ele ajuda na gestão de um projeto Open Source?**

A checagem de **DCO (*****Developer Certificate of Origin\*****, ou Certificado de Origem do Desenvolvedor)** é uma camada a mais de segurança para o projeto e também para as pessoas que contribuem para ele. Ela é feita através da assinatura de “commits”, na qual cada alteração realizada no código fonte é “assinada”. 

O certificado de Origem surgiu em 2004, quando foi adotado pela [Linux Foundation](https://www.linuxfoundation.org/) para melhorar o processo de submissão de contribuições utilizando o Kernel Linux. 

A assinatura se tornou parte do registro das alterações e serve, até hoje, para garantir quem fez cada uma delas, e que a pessoa aceita os [termos de responsabilidade](https://developercertificate.org/) sobre as mudanças feitas, mesmo no caso de várias pessoas estarem trabalhando em conjunto em uma mesma “branch”. Dessa forma, o projeto pode usar e distribuir as contribuições que foram feitas sob sua licença.

Em resumo: enquanto a licença de software rege a distribuição e licenciamento de propriedade intelectual de um projeto Open Source, o **DCO rege o direito autoral das contribuições** que são feitas.

### **Como eu assino commits dentro do DCO?**

Antes de você assinar seus commits, é preciso que seu nome e e-mail estejam configurados corretamente no Git com os comandos abaixo. Além disso, esse e-mail tem de ser o mesmo usado no seu cadastro no GitHub.

```bash
git config --global user.name “Nome”
git config --global user.email “email@dominio.com.br”
```

O processo de assinatura de commits é simples: nada mais é do que uma linha no final da mensagem de commit com o nome e e-mail do autor no modelo, como no exemplo: 

```bash
Signed-off-by: Author <email@dominio.com.br>
```

#### **Algumas maneiras de assinar o commit**

1. Adicionando a flag **-s** ou **–signoff** ao comando de commit:

```bash
git commit -m “Meu commit assinado” -s
```

1. Diretamente na caixa de commit do GitHub Web. Atualmente, **esta opção deve ser feita manualmente**, pois a interface do GitHub não fornece uma maneira automatizada de assinar o commit.


Para esta opção, o seu e-mail e nome de usuário devem estar configurados de maneira igual aos da assinatura no painel do GitHub.

![Imagem de uma tela do GitHub em que aparece uma caixa aberta com título "Commit Suggestion", ou Sugestão de Commit. Nele, está escrito "Meu Commit Assinado Signed-off-by: Author <email@dominio.com.br>"](https://secureservercdn.net/198.71.233.31/36q.76e.myftpupload.com/wp-content/uploads/2021/10/Projeto-open-source-3.png)

### **Assinatura de commits com chave GPG**

Outra maneira de você fazer a assinatura de seus commits é por meio do [GPG](https://gnupg.org/) , uma ferramenta que permite o uso de criptografia para garantir ainda mais segurança nas suas contribuições.

Na prática, o GPG trabalha com criptografia assimétrica, em que são criadas duas chaves, uma pública e outra privada, que servem para criptografar e descriptografar uma mensagem, respectivamente.

O GPG ainda possibilita a assinatura de mensagens ou arquivos usando este mesmo método. O Git faz uso disso, então, para que sejam geradas chaves para assinar cada “commit” e, ao adicionar essa chave em suas configurações do GitHub, cada alteração feita será verificada e receberá uma “badge” com tal indicação.

![Imagem do site do GitHub em que aparece uma janela de confirmação de que o commit foi assinado e a chave de GPG gerada para criptografar a mensagem. ](https://secureservercdn.net/198.71.233.31/36q.76e.myftpupload.com/wp-content/uploads/2021/10/Projeto-open-source-4.png)

É importante notar aqui que os commits feitos pelo GitHub Web como “merges” e aceites de *pull request* (PR) são assinados automaticamente pela própria plataforma.

![Imagem do site do GitHub em que aparece uma janela de confirmação de que o commit foi criado e assinado automaticamente pela versão web do GitHub.](https://secureservercdn.net/198.71.233.31/36q.76e.myftpupload.com/wp-content/uploads/2021/10/Projeto-open-source-5.png)

Essa configuração deve ser feita apenas uma vez por máquina e todo commit assinado com o uso dessa chave já é automaticamente verificado pelo GitHub. O uso desta técnica melhora a segurança ainda mais, já que garante exatamente quem fez a alteração e evita modificações maliciosas no commit ou na branch.

Vale esclarecer que este método de assinatura não é reconhecido pelas checagens de DCO, mas apenas por proteção de branches nas configurações do repositório. Por esse motivo, é recomendado que a assinatura com **signed off** seja feita em conjunto.

Você pode aprender mais sobre chaves GPG consultando a [documentação oficial do GitHub](https://docs.github.com/pt/github/authenticating-to-github/managing-commit-signature-verification/generating-a-new-gpg-key). 

### **Diferença entre DCO e Signed Commit**

A diferença entre DCO e *Signed Commit* está, principalmente, na forma como é feita a segurança e verificação dos “commits”. 

Veja na imagem a seguir como você pode alterar o nome usado no signed-off (que faz o DCO passar com sucesso), e o quanto isso é dificultado pelas camadas de segurança do GPG que apontam a alteração como “unverified”.

![Imagem do site do GitHub que mostra um comentário de signed-off e, na sequência, um comentário automático informando que é preciso fazer algumas verificações para o commit estar completo. ](https://secureservercdn.net/198.71.233.31/36q.76e.myftpupload.com/wp-content/uploads/2021/10/Projeto-open-source-6.png)

## **Como o DCO é usado na prática dentro dos projetos Open Source da Zup**

Atualmente dentro dos projetos [Open Source da Zup](https://opensource.zup.com.br/), usamos o [nosso próprio validador](https://github.com/ZupIT/zup-dco-validator) que foi criado a partir da necessidade de ter um maior controle e diferenciação das assinaturas DCO e GPG.

Para que uma contribuição seja aceita dentro dos nossos projetos, é necessário que o commit seja validado com o DCO. A assinatura com o GPG é incentivada e aconselhada, porém não é obrigatória.

A assinatura de commits é, para nós, uma solução viável e vantajosa para aumentar a segurança e controle de repositórios com um volume alto de alterações. Além de apresentar uma segurança mais robusta, o uso das chaves facilita a adesão para quem desenvolve, pois evita problemas e transtornos para assinar cada alteração. Uma vez configurada, não é preciso se preocupar com mais nada e o único ponto de atenção é o de orientar as pessoas a fazer essa configuração antes de colocar o bloqueio nas branches.

Além da validação do DCO, nós também adicionamos mais uma camada de segurança, que é a verificação do cabeçalho do código fonte, o que nos permite verificar as licenças dos arquivos que foram submetidos ao projeto. Para garantir este fluxo, temos um [Github Action que garante que, caso o arquivo não tenha a licença, quebre a build](https://github.com/ZupIT/header-license-checker).

## **Projeto Open Source, de fato.**

Como você deve ter percebido, trabalhar com Open Source é um grande desafio, principalmente porque vai muito além de uma validação técnica, mas também de uma integração para garantir que o software seja Open Source, o direito autoral seja cedido com esse propósito.

Neste sentido, o DCO é uma ferramenta que nos ajuda a certificar que projetos fora de uma fundação ultrapassem a filosofia e demonstram ser Open Source também na prática.

E aí, você sabia que tinha tanta coisa envolvida para declarar que um projeto é realmente open source? Tem outras dúvidas sobre o mundo open source? Conta para a gente nos comentários. 

**Referências:**

- [Gerar uma nova chave GPG](https://docs.github.com/pt/github/authenticating-to-github/managing-commit-signature-verification/generating-a-new-gpg-key)
- [How (and why) to sign Git commits](https://withblue.ink/2020/05/17/how-and-why-to-sign-git-commits.html)
- [probot/dco: GitHub App that enforces the Developer Certificate of Origin (DCO) on Pull Requests](https://github.com/probot/dco)