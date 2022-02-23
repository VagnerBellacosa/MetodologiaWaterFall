# Segurança: cuidado com o envenenamento do DNS

**08/06/2009** às 20:02

**4 min** de leitura

![Imagem de: Segurança: cuidado com o envenenamento do DNS](https://tm.ibxk.com.br/tecmundo-padrao.jpg?ims=1120x420)

[![Avatar do autor](https://www.tecmundo.com.br/desktop/assets/static/avatar-editor.svg)](https://www.tecmundo.com.br/autor/79-wikerson-landim)

[Wikerson Landim](https://www.tecmundo.com.br/autor/79-wikerson-landim)

3 Compartilharam

0 Comentários

Você já deve ter visto ou ouvido em diversos lugares matérias ou comentários sobre pessoas que caíram em algum tipo de golpe pela internet. A eficiência dos golpistas tem sido tão grande que, muitas vezes, perceber que você está em site falso acaba se tornando uma tarefa para especialistas.

Mas você sabe como atuam os bandidos da rede? Nesse artigo vamos explicar como funciona a praga do envenenamento do cache DNS - técnica também conhecida como *pharming* - e o que fazer para minimizar os riscos com esse problema, que vem vitimando sites e usuários de grandes corporações, como bancos e empresas de telefonia.

**A falsa identidade**

Quando você está online na internet seu computador passa a ser um número, conhecido como endereço de IP (*Internet Protocol*). Assim como os usuários têm o seu número, o mesmo acontece com os sites.

Na rede cada endereço possui um DNS (*Domain Name System*). Esse número de DNS é o responsável por transformar a URL que você conhece (por exemplo, www.baixaki.com.br) em um código, mais simples e de fácil localização para as máquinas dos usuários.

![Golpistas atacam diretamente no DNS, redirecionando os usuários](https://img.ibxk.com.br/materias/630903503.jpg?ims=328x)


Quando o usuário faz essa requisição, em formato URL, o DNS redireciona esse endereço para um código. O código então é enviado para o seu IP, de maneira a traduzir para o seu navegador as informações para que elas sejam apresentadas da maneira que você conhece.

É justamente aí que atuam os bandidos. No processo de envenenamento do DNS o criminoso consegue colocar um código malicioso dentro do DNS do site. Quando o usuário faz uma requisição para o site acaba sendo interceptado e redirecionado para onde quem implantou o código bem entender.

**Sua memória temporária entra em campo. E contra você.**

Quem o está redirecionando para outro lugar pode optar por levar você para uma página completamente diferente (o que provavelmente causaria estranhamento no usuário) ou ainda para uma página absolutamente igual ao seu destino inicial. Mas com uma diferença: sob controle total do golpista.

Sem perceber você pode acabar digitando ali informações confidenciais como número dos seus documentos, cartões de crédito, logins e senha. De posse dessas informações, á claro, os bandidos farão a festa.

![Cuidado ao digitar senhas e números de cartões ou documentos](https://img.ibxk.com.br/materias/106971713.jpg?ims=328x)Se você já acessou anteriormente o endereço em questão é possível que todas as informações sobre ele estejam no seu *cache*, que nada mais é do que a sua memória temporária. Ela existe para tornar a sua navegação mais rápida.

O *cache* guarda essa informação por alguns dias – às vezes até algumas semanas – para que, caso você acesse novamente a página, não seja preciso repetir alguns processos comuns.

Um exemplo simples: se você acessa o site do seu banco, todas as informações estruturais da página serão sempre as mesmas. O que muda são as atualizações de conteúdo e imagem. Tendo essa estrutura da página no seu *cache*, seu computador acessará mais rápido a página, já que precisará carregar somente as novas informações.

Este é um dos tipos de golpes mais simples. Existem outros, que se desenvolvem em meio a sistemas mais complexos, mas a estrutura do seu funcionamento permanece sendo a mesma.

**Soluções e prevenções**

Em tese, não existe uma solução eficiente para evitar que o *pharming* seja banido por completo. O que os servidores DNS dos sites mais seguros fazem é minimizar as possibilidades de ataques como esse.

Alguns bancos já estão adotando um sistema chamado *DNSSEC*. Com ele, na teoria, os servidores passam a ser à prova de envenenamento, já que o criminoso não conseguiria plantar um IP falso no DNS.

![Neste quesito o usuário tem pouco o que fazer](https://img.ibxk.com.br/materias/121450201.jpg?ims=328x)Para saber se o seu banco já possui o sistema, basta observar o endereço URL de páginas seguras. Se a extensão delas for do tipo “*B.BR*” ao invés dos tradicionais “*.COM*” ou “*.COM.BR*” tenha certeza que você conta com uma proteção a mais.

Outra medida preventiva, já tradicional nos sistemas de *e-commerce* são as páginas com *SSL*, o famoso “cadeado de segurança”. Esse sistema impede que sites falsos consigam exibir no navegador do usuário um cadeado válido. Nesse caso quem deve prestar atenção na hora de disponibilizar os seus dados é o usuário.

**Infelizmente, poucas alternativas**

Além de prestar atenção a esses detalhes, como a terminação da URL e o cadeado de segurança nas páginas seguras do site, não há muito que o usuário possa fazer. Como o processo de envenenamento do DNS não ocorre diretamente na máquina do usuário e, sim, no servidor do site, as medidas mais importantes de segurança devem ser adotadas diretamente na fonte.

No entanto, abaixo listamos algumas medidas que você pode adotar para minimizar seus riscos não só em virtude desse problema, mas de outros que possam ocorrer:

- Quando sair das páginas onde estiver logado, saia usando logout ao invés de apenas fechar a página;

  

- Mude sua senha periodicamente (recomenda-se a cada três meses);

  

- Evite sites suspeitos. Se precisar usá-los, acesse com um navegador alternativo e não com o seu navegador padrão;

  

- Cuidado com emails falsos. Bancos e órgãos do governo não farão nenhum contato com você solicitando números de documentos, senhas ou mesmo que você clique em um determinado link. Fuja imediatamente.

  

- Mantenha *antivírus* e *antispyware* atualizados. Na dúvida sobre qual usar, [clique e confira algumas dicas do Baixaki](https://www.baixaki.com.br/info/635-aprenda-a-usar-um-dos-antivirus-gratuitos-mais-populares-do-mercado-o-avast-.htm).

  

- Cuidado com os seus dados. Se um site pede pra você números que não fazem o menor sentido – por exemplo o do seu cartão de crédito se você não está fazendo nenhuma compra – fuja pois a chance de ser um golpe é grande.