**Arquitetura de computadores**

O estudo da arquitetura de computadores efetua-se com recurso à abstração. Podemos ver um computador de várias formas.

- Para um utilizador normalmente o computador é a aplicação
- Para nós (na disciplina) tem a ver com a arquitetura

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/6/8/6/168638/a19i06_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/6/8/6/168638/a19i06_arco80_100.jpg)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108879/a19i01_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108879/a19i01_arco80_100.jpg)

**ISA – Instruction set architecture**

ISA descreve o funcionamento do processador de um ponto de vista lógico. Especifica como um processador funciona, que instruções executa, quais os modos de endereçamento que são suportados e que tipos de dados são suportados.

- Por exemplo, IA-32 (Arquitectura Intel de 32 bits) tem várias implementações, incluindo os processadores Pentium, Celeron e os processadores de alto desempenho Xeon.

Alguns exemplos de especificações ISA:

- MIPS
- SPARC
- JVM (Java Virtual Machine)
- Plataforma .Net Microprocessador virtual

Na JVM e na plataforma .NET, as especificações ISA referem-se a uma camada de software. Do ponto de vista funcional, é como um processador virtual que implementa um processador JAVA ou .NET.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108880/a19i02_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108880/a19i02_arco80_100.jpg)

Como podem os dados ser acedidos? Ao modo como se especificam os operandos, chamam-se modos de endereçamento:

- Registro, quando o operando é armazenado num registro
- Imediato (ou literal), se o operando é parte da instrução
- Direto (ou absoluto)
- Registro indireto
- Autoincremento
- Autodecremento
- Autodecremento
- Deslocamento
- Indexado
- Indexado escalado indireto
- Indexado escalado indireto com deslocamento
- PC relativo

**Quais as instruções que podem ser executadas?**

**Instruções de transferência de dados** efetuam a transferência de dados de uma posição para outra. Quando existe um espaço separado de I/O, essas instruções também se referem a instruções I/O. Igualmente as instruções de acesso à pilha se incluem nessa categoria

- **Instruções aritméticas e lógicas inteiras** – operações aritméticas e lógicas
- I**nstruções de vírgula flutuante**
- **Instruções de deslocamento e rotação** – efetuam deslocamento e rotações à esquerda e à direita
- **Instruções de manipulação de bits** – operam especificamente em determinados bits dos operandos. As instruções normalmente incluem condições de teste (que afetam determinadas flags)
- I**nstruções de controle do fluxo do programa** – saltos condicionais/incondicionais
- **Instruções de controle do sistema** – chamadas de rotinas, interrupções, exceções
- **Instruções de unidades de funções especiais** – instruções proprietárias de unidades funcionais
- **Instruções configuráveis** – específicas de processadores que permitem a customização de instruções.

Ao nível ISA, podemos definir dois tipos:

- **CISC** – Complex Instruction Set Computer
- **RISC** – Reduced Instruction Set Computer

**Linguagem Assembly e linguagem máquina**

- Linguagem de baixo nível especificada por meio de mnemônicas
- Linguagem é nativa do processador, por este fato não existe portabilidade
- A linguagem assembly está na relação de 1:1 com a linguagem máquina
- Como consequência da linguagem assembly, um programa tende a ser grande, mas bastante eficiente

**Linguagens de alto nível**

- São fortemente estruturadas
- Definem estruturas de controle de fluxo de programa
- Portabilidade

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108881/a19i05_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108881/a19i05_arco80_100.jpg)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108882/a19i03_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108882/a19i03_arco80_100.jpg)

A linguagem CLI (Common Language Infrastructure) permite que aplicações escritas em múltiplas linguagens de alto nível possam ser executadas em diferentes ambientes sem ser necessário reescrever o código.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108883/a19i04_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108883/a19i04_arco80_100.jpg)