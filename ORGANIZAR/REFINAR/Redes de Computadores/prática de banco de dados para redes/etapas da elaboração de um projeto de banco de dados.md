**Introdução**

Os modelos de dados especificam a estrutura lógica dos dados. Os formatos mais conhecidos são:

- Hierárquico.
- Rede.
- Relacional.
- Orientado a objetos.

**Modelo hierárquico**

Surgiu na década de 1960 com a primeira linguagem de banco de dados: a DL/I desenvolvida pela IBM e a North American Aviation.

Organiza os dados de cima para baixo, como uma árvore. Cada registro é dividido em partes denominadas segmentos. O banco de dados se assemelha a um organograma com um segmento raiz e um número qualquer de segmentos subordinados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121598/a02i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121598/a02i01_md80_100.jpg)

**Modelo em rede**

Definido pelo DBTG (Data Base Task Group) do comitê do CODASYL (Conference on Data Systems Language) a partir de 1971. Esse modelo é uma extensão do modelo hierárquico.

Nos modelos baseados em rede, os dados são agrupados em forma de registros em que um aponta para outro por meio de ponteiros (links), exemplo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121597/a02i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121597/a02i02_md80_100.jpg)

**Modelo relacional**

O modelo relacional é um conjunto de tabelas relacionadas entre si por meio dos próprios dados, não utilizando ponteiros para ligar os registros. Veja o mesmo exemplo usando o modelo relacional:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121599/a02i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/5/121599/a02i03_md80_100.jpg)

**Modelo orientado a objetos**

Um objeto que representa algo no mundo real possui dados que o identificam e funções que ele pode executar. As funções são escritas com uma linguagem de programação. Os dados são chamados de atributos e as funções de métodos. As classes são definições de como os objetos deverão ser. Cada objeto é uma instância de uma determinada classe, um exemplo análogo: "A receita de um bolo é uma classe e o bolo é o objeto dessa classe. A partir de uma única receita podemos gerar vários bolos."

**Etapas de elaboração de um projeto de banco de dados**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121600/a02i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121600/a02i04_md80_100.jpg)

Um projeto de banco de dados é constituído por **três níveis** de abstração:

1. Modelo conceitual.
2. Modelo lógico.
3. Modelo físico.

O **modelo lógico,** que será estudado em detalhes nas próximas aulas, refere-se especificamente ao **modelo relacional**, pois ainda é o mais usado atualmente.

**Análise de requisitos**

O primeiro passo para modelar os dados é fazer a análise de requisitos, ou seja, descrever todas as informações necessárias para extrair os dados que deverão compor o banco de dados. A descrição a seguir é um roteiro de necessidades que devem ser levantadas.

- Quais os problemas que o banco de dados poderá solucionar.
- Qual o objetivo de criar um banco de dados para aquela realidade específica, ou seja, os resultados esperados.
- Quais as informações que desejamos saber do banco de dados.
- Quais as regras de negócio.
- Quem está participando diretamente e indiretamente no negócio.
- Verificar documentos que formalizam a negociação: notas, contratos, pedidos etc.
- Dados relevantes, casos de sucesso ou fracasso, pertinentes à problemática.
- Datas críticas.
- Restrições de dados.

Roger Pressman, em seu livro _**Engenharia de Software**_, descreve algumas características que um analista deve ter para fazer uma análise de requisitos com sucesso, uma vez que o usuário geralmente é leigo em informática:

- A capacidade de compreender conceitos abstratos, reorganizá-los em divisões lógicas e sintetizar "soluções" baseadas em cada divisão.
- A capacidade de absorver fatos pertinentes de fontes conflitantes.
- A capacidade de entender os ambientes do usuário/cliente.
- A capacidade de aplicar elementos do sistema de hardware e/ou software aos elementos do usuário/cliente.
- A capacidade de se comunicar bem nas formas escrita e verbal.

**Modelo conceitual**

Para representar o modelo conceitual de dados usaremos o Modelo Entidade-Relacionamento (MER) criado por Peter Chen, em 1976, baseado na teoria relacional desenvolvida por E. F. Codd em 1970. O MER surgiu para padronizar a modelagem de dados por meio de diagramas, assim, qualquer profissional poderia ler e compreender toda a sua estrutura, sem mesmo conhecer a realidade a que se referia.

A padronização facilita a criação de ferramentas CASE (Computer Aided Software Engineering), programas usados na engenharia de software para auxiliar no desenvolvimento de sistemas.

O MER (Modelo Entidade-Relacionamento) tem como princípio a representação do mundo real em forma de objetos dos quais queremos obter informações. Estes objetos recebem o nome de entidades. Para desenhar o modelo conceitual, usamos um diagrama com símbolos para representar as entidades, os atributos e descrever os relacionamentos.

Simbologia do Diagrama Entidade Relacionamento (DER)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121601/a02i05_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/6/121601/a02i05_md80_100.jpg)