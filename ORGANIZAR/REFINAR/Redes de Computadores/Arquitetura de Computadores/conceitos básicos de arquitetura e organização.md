**Arquitetura x organização de computadores**

Na literatura, ao se descrever um sistema de computação, é feita uma distinção entre os termos: arquitetura e organização do computador. O termo arquitetura de um computador refere-se aos atributos de um sistema que são visíveis para o programador ou, em outras palavras, aos atributos que têm impacto direto sobre a execução lógica de um programa.

Já o termo organização de um computador diz respeito às unidades operacionais e suas interconexões que efetivam as especificações de sua arquitetura, ou seja, como as características da arquitetura são implementadas.

Por atributos de arquitetura, podemos entender: o conjunto de instruções, o número de bits usados para representar os tipos de dados, os mecanismos de E/S etc., enquanto os atributos da organização são transparentes aos usuários e incluem detalhes de hardware, por exemplo: sinais de controle, tecnologia de memória utilizada etc.

Especificar se um computador deve ou não ter uma instrução de multiplicação constitui uma decisão de projeto da arquitetura.

Por outro lado, definir se essa instrução será implementada por uma unidade específica de multiplicação ou por um mecanismo que utiliza repetidamente sua unidade de soma é uma decisão de projeto de sua organização.

Exemplo: todo INTEL da família x86 compartilha a mesma arquitetura básica => compatibilidade. No entanto, a organização difere de uma versão para a outra.

Conclusão: uma organização deve ser projetada para implementar uma especificação particular de arquitetura.

**Estrutura x função**

Tanto a estrutura quanto as funções de um computador são muito simples. Basicamente, podemos definir estrutura e função como segue:

Estrutura: é a forma como os componentes se relacionam uns com os outros.

Função: a operação que cada componente individual realiza dentro da organização.

**Funções**

As funções básicas que um computador pode desempenhar são: processamento de dados, armazenamento de dados, transferência de dados e controle.

**Estrutura**

1. Unidade central de processamento: controla a operação do computador e desempenha funções de processamento de dados (processador).  
2.  
Memória principal: armazena dados e instruções.  
3.  
E/S: transfere dados entre o computador e o ambiente externo.  
4.  
Sistema de interconexão: mecanismos que estabelecem a comunicação entre a CPU, memória principal e os dispositivos de E/S.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108761/a11i01_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108761/a11i01_arco80_100.jpg)

Dentre os componentes de um computador, a CPU é o que apresenta uma estrutura mais complexa, sendo seus principais itens:

1. Unidade de controle (UC): controla a operação da CPU e, portanto, do computador.
2. Unidade lógica aritmética (ULA): realiza todo o processamento de dados, por operações lógicas aritméticas.
3. Registradores: oferecem um tipo de armazenamento interno de dados para a CPU.
4. Interconexão da CPU: mecanismo que possibilita a comunicação entre as unidades de controle, a ULA e os registradores.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108764/a11i02_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108764/a11i02_arco80_100.jpg)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108762/a11i03_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108762/a11i03_arco80_100.jpg)