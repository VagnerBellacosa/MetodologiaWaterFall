# Migração do mainframe DB2 para Oracle e reformulação da plataforma COBOL

 [Clientes ](http://freesoftbr.com/category/customers/)Migração do mainframe DB2 para Oracle e reformulação da plataforma COBOL

![news-image-2](http://freesoftbr.com/wp-content/uploads/2016/06/news-image-2.png)
O cliente é uma cadeia de supermercados, que tem lojas no norte da California, em Nevada e no Novo México, A FreeSoft juntou-se ao projeto de migração de data warehouse do cliente como um parceiro de migração em conjunto com a Oracle, um dos principais fornecedores de RDBMS do mundo.

------

**Visão geral do projeto**

Precisávamos migrar o ambiente construído com tecnologias legadas que estavam enfrentando altos custos de manutenção.

O ambiente de sistema legado, que tinha custo elevado para manutenção, estava operacionalisado com DB2 no ambiente de host IBM OS/390. O banco de dados continha 1 TB de dados armazenados em centenas de tabelas (principalmente particionadas).O processo de ETL foi mapeado para um programa COBOL e o procedimento SQL chamado a partir do JCL.

O objetivo deste projeto era migrar o esquema de banco de dados DB2 para Oracle em um sistema aberto, converter e carregar os dados e, finalmente, reformular o processo de ETL.

------

**Solução**

O projeto de migração foi realizado usando o Framework LiberatorWorkbench da FreeSoft. Foram utilizadas as seguintes ferramentas:

- KnowledgeLiberator para analise de esquemas DB2 e arquivos de controle
- KnowledgeLiberator para analise de procedimentos SQL
- DataLiberator para conversão de esquemas Oracle e procedimentos SQL e geração de scripts para conversão de dados e processamento de carga
- CodeLiberator para nova plataforma COBOL.

------

**Benefícios para o cliente**

- Mainframe DB2 é descontinuado e novo sistema operado em ambientes UNIX apenas em bancos de dados Oracle
- Economia de custos
- Melhora das operações e melhora da produtividade