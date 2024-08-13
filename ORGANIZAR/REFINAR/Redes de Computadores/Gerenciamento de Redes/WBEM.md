**Introdução**

Olá! Seja bem-vindo à décima sétima aula! O Web-Based Enterprise Management (WBEM) é um conjunto de sistemas de gestão desenvolvido para unificar a gestão de ambientes de computação distribuída. Trata-se de um modelo, e não uma ferramenta com interface particular.

**Arquitetura**

Para entender a arquitetura WBEM, devemos ter em mente que não é um software nem um hardware ou, tampouco, qualquer outro dispositivo. Através de uma interface, seja gráfica (GUI), de navegação (BUI) ou de linha de comando (CLI), podemos ter acesso a um conjunto de APIs para encontrar um servidor WBEM e construir uma mensagem XML. A grande vantagem é que as interfaces podem ser alteradas sem que o resto do sistema precise estar ciente das mudanças.

Na maioria das operações, o servidor WBEM determina, a partir do modelo, que necessita se comunicar com hardware real ou software. Este é tratado pelos chamados "provedores": pequenos pedaços de código de interface entre o servidor WBEM (usando uma interface normalizada, conhecida como CMPI) e hardware real ou software. Como a interface é bem-definida e o número de tipos de chamada é pequeno, normalmente é fácil escrever provedores. Em particular, o provedor não sabe nada de GUI, BUI ou CLI, sendo usado pelo operador.

Tipos de mapeamentos WBEM:

- URI (WBEM Especificação Mapeamento URI 1,0).
- XML (Representação do CIM usando XML 1.2; CIM DTD 1.2).
- XML Schema.

Protocolos suportados:

- CIM-XML.
- WS-Management.
- CIM-RS.
- SM-CLP (Command Line Protocol 1.0).
- SLP (WBEM descoberta usando SLP; Template SLP).

Linguagens:

- CQL (CIM Query Language 1.0).
- FQL (Filtro Query Language 1.0).