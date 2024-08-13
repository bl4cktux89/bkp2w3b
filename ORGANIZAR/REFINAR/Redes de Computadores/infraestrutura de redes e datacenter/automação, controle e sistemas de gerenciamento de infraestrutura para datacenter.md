Uma vez que um Data Center é um centro de atividades multi disciplinares como energia, redes, telecomunicações, climatização, combate a incêndio, segurança e serviços em geral de dados, internet, armazenamento, etc., é de se esperar que necessitamos de sistemas que controle, automatizem e gerenciem todo o Data Center.

A maioria dos sistemas de gerenciamento também automatizam alguns processos, mecanismos e configurações do Data Center. De uma central de controle é possível controlar as temperatura das salas, algumas vezes a temperatura e umidade de corredores de racks, controlar a carga das baterias do UPS, ativar portas de routers e switches, bloquear ou liberar portas, desligar servidores, redirecionar tráfego de rede, etc.

Outros controles são locais. Por exemplo, um CRACs (_**computer room air conditioner**_) pode ter sua automação regulada no próprio equipamento, como temperatura de retorno e umidade exigidas. Uma UPS age com parâmetros próprios para garantir continuidade de energia.

**DCIM:** _**Data Center Information Management**_

É correto afirmar que muitos profissionais de TI estão familiarizados com os métodos tradicionais de monitorar infraestrutura tal como alertas de equipamentos desligados, verificação de recursos disponíveis nos servidores e verificação da latência da rede. Alguns conhecidos produtos como o _**WhatsUpGold**_, _**Nagios**_, Dell IT Assist ou o HP Open View são padrões seguros para manter uma guarda sobre a “saúde” dos sistemas físicos, software e o ambiente.  O DCIM é tudo isto e muito mais.

O monitoramento tradicional da infraestrutura permite controlar e saber se seu servidor está ok, mas não informará, por exemplo, quantos servidores ainda podem ser colocados nos espaços livres de uma fileira de racks, sem que o sistema de climatização se sobrecarregue. O DCIM encaixa-se nestas falhas dos sistemas tradicionais. Não é que os sistemas tradicionais falham, mas é o crescimento das opções tecnológicas somado às alterações possíveis de projeto de um Data Center.

O DCIM incrementa o monitoramento com as seguintes características:

- Rastreamento de Ativos.
- Gerenciamento de Mudanças
- Análise do comportamento dos sistemas virtuais x físicos.
- Gerenciamento das operações de utilidades (_utilities_) como: energia, refrigeração, perspectivas de economia e eficiência.
- Maximização da utilização do sistema para melhor eficiência.
- Consolidação dos recursos tecnológicos.
- Otimização da infraestrutura física (incluindo o gerenciamento de espaço) para disponibilizar alta capacidade.
- Monitoramento multi camadas (Multi-layered – Será explicado mais adiante).
- Planejamento futuro baseado na modelagem de cenários.
- Controle de posicionamento de equipamentos e cabos.

Co**mo poderíamos utilizar um DCIM?**

Fora o óbvio que seria ser alertado por incidentes, podemos usar muito melhor um DCIM.

Um exemplo seria observar um ativo qualquer (talvez um storage). Poderíamos querer fazer isto porque se trata de um storage antigo e estou interessado em observá-lo. O DCIM permite uma análise completa deste recurso enquanto ele está em pleno uso. Taxas de transferência, temperatura dos processadores, espaço ocupado e livre, etc.. Isto seria apenas uma pequena parte que um DCIM pode fazer. Ele vai mais longe ainda, fornecendo detalhes da influência da infraestrutura e nos recursos do Data Center. Poderia, por exemplo, fornecer detalhes de como o storage está gastando/consumindo energia. Também quanto este dispositivo influencia na temperatura do corredor quente do sistema de climatização.

Outro cenário seria a manutenção, para acertos ou, mesmo, melhoria, assistida pelo DCIM. Onde os técnicos podem observar, em gráficos, os efeitos de sua manutenção, algumas vezes reajustando as configurações, outras vezes decidindo cancelar a manutenção devido a efeitos muito maléficos à operação do Data Center.

Talvez o uso mais importante de um DCIM esteja na capacidade de prever situações de consumo e produtividade, relacionando energia, fluxo de ar, temperaturas de vários pontos dos espaços do Data Center, transferência de dados, processamento em servidores físicos, storages, hypervisors de máquinas virtuais e tráfego da internet, tudo isto avaliado por processos internos do DCIM com requintes de inteligência artificial e processos de reconhecimento de padrões.

As características ou as vantagens chave de um DCIM podem ser refletidas nas seguintes situações:

- Monitorar e reportar sobre todos os equipamentos.
- Visualizar as perdas e os ganhos de eficiência de energia.
- Saber exatamente quanto é usado da capacidade instalada e quanto não é.
- Modelar vários cenários de provisionamento.
- Eliminar as causas de _downtime._ (o tempo parado de um equipamento, um rack, um sistema de climatização, etc.).
- Incrementar a eficácia do uso de energia, capital e recursos humanos.

Melhorar as eficiências, reduzir custos e manter a disponibilidade são as prioridades top para a administração dos Data Centers hoje. No passado, a ideia de conservar os recursos enquanto melhora-se a performance foi quase impossível mesmo para os mais experientes profissionais de TI das organizações. Em função do modelo de funcionamento de um Data Center, as possibilidades de usar tudo que é possível da tecnologia, mudou isto para melhor.

No gráfico 1 podemos ver uma possível saída de uma consulta feita para o DCIM, onde, facilmente, poderíamos calcular a eficiência de energia.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/3/260350/15039.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/3/260350/15039.png)

Gráfico 1. Consumo de energia em espaços diferentes do Data Center.

Fonte: Autoria própria

Na figura 1 podemos ver uma sala típica de monitoramento de um Data Center. Observe que se trata de um local seguro, isolado e de alta concentração. As informações podem refletir um possível incidente e ações devem ser tomadas para garantir o SLA (Service Level Agreement) com seus clientes.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/6/2/266272/15038.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/6/2/266272/15038.jpg)

Figura 1. Sala de monitoramento suprida pelo DCIM.

Na figura 2 podemos observar uma cena típica, como comentado no texto. Ao fazer manutenção, os técnicos precisam consultar as condições e localização correta dos equipamentos onde haverá intervenção. O DCIM é muito usado pelo seu aspecto de rastreabilidade dos ativos, como equipamentos e cabos, assim como o fornecimento dos dados de funcionamento daqueles equipamentos (se estão em uso) e ainda , quais as consequências sobre outros ativos enquanto a manutenção está sendo feita.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/6/2/266273/15040.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/6/2/266273/15040.jpg)

Figura 2: Acesso físico para manutenção auxiliado pelo DCIM

Resumindo, o gerenciamento do Data Center é a base para a manutenção saudável do negócio do Data Center e este é o motivo necessário e suficiente para justificar o investimento em um bom sistema de gerenciamento.