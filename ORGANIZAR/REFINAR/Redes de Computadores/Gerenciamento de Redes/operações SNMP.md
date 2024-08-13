  

**Introdução**

Olá! Seja bem-vindo à nona aula! Nela, veremos como o protocolo SNMP transporta informações da MIB entre as entidades agentes e gerentes.

**Operações SNMP**

A utilização mais comum é em um modo comando–resposta, no qual a entidade gerenciadora envia uma requisição ao agente que recebe e realiza alguma ação, feito isso, o agente envia uma resposta à requisição do gerente. A requisição do gerente pode ser uma solicitação de informação (consulta) ou uma modificação de valores de objetos para atualizar seu estado de alguma forma. A resposta do agente se baseia no envio das informações consultadas ou na confirmação de que atualizou seu estado.

Um segundo uso comum é para um agente enviar uma mensagem não solicitada, conhecida como **Mensagem TRAP**, à entidade gerente. Essas mensagens são usadas para notificar um gerente de uma situação excepcional que resultou em mudança nos valores dos objetos MIB. É possível, por exemplo: quando uma interface "cai" ou quando atinge determinado nível de congestionamento ou outro evento notável, que seja enviado ao administrador de rede uma mensagem TRAP.

É importante ressaltar que o protocolo SNMP é um protocolo da camada de aplicação e utiliza o protocolo UDP como transporte de seus dados.

**Tipos de mensagens**

O SNMP define sete tipos de mensagens PDU (Protocol Data Unit):

- GetRequest: Mensagem gerente-agente; captura o valor de uma ou mais instâncias de objetos MIB.
- GetNextRequest: Mensagem gerente-agente; captura o valor da próxima instância de objeto MIB na lista ou tabela.
- GetBulkRequest: Mensagem gerente-agente; captura valores em grandes blocos de dados, por exemplo, valores em uma grande tabela.
- InformRequest: Mensagem gerente-gerente; informa à entidade gerente remota valores da MIB que são remotos para seu acesso.
- SetRequest: Mensagem gerente-agente; define valores de uma ou mais instâncias de objetos MIB.
- Response: Mensagem agente-gerente ou gerente-gerente; gerada em resposta a: GetRequest, GetNextRequest, GetBulkRequest, SetRequest PDU ou InformRequest.
- SNMPv2-Trap: Mensagem agente-gerente; informa ao gerente um evento excepcional.