**Controle de admissão de chamadas (CAC)**

CAC _**(call admission control)**_ protege a largura de banda de uma rede prevendo maiores ocorrências de fluxos de áudio e vídeo que aquela rede possa suportar. Ao fazer isso, não é protegido somente o tráfego de dados, mas também protege a qualidade das chamadas de voz e vídeo que já estão estabelecidas.

Na figura 01, há um exemplo de um sistema de chamada sem CAC. Observe que a terceira chamada provoca uma degradação de qualidade de voz em todas as outras chamadas efetuadas.

**Reordenando e criando uma alternativa para uma chamada**

Como exemplo, uma reordenação da chamada 3, visto na figura 01, pode ser efetuada.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119257/a12i01_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119257/a12i01_quasar80_100.jpg)

Fonte: ODOM, W.; CAVANAUGH, M. J. Cisco QOS exam certification guide, second edition. Cisco Press, Indianápolis, USA, 2012.

Se uma chamada foi rejeitada através do mecanismo CAC por insuficiência da rede, o sujeito ouvirá um sinal de tom ocupado. Na América do Norte isso é conhecido como _**overflow**_ tone ou tom de ocupado. Em outras partes do mundo, pode ser conhecido também como _**"equipment busy"**_ ou equipamento ocupado. Ao reordenar a rede com uma central PSTN (rede pública de telefonia privada), o ouvinte pode escutar uma mensagem como: "todas as linhas estão ocupadas, por favor retorne mais tarde".

Na figura 02 é possível observar como fica essa reordenação. Note que a rede IP suporta no máximo duas chamadas. A terceira é direcionada automaticamente para uma rede PSTN.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119259/a12i02_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119259/a12i02_quasar80_100.jpg)

Fonte: ODOM, W.; CAVANAUGH, M. Cisco QOS Exam Certification Guide (IP Telephony Self-Study), 2 ed. USA: Cisco Press, 2004.

A ferramenta CAC pode decidir entre aceitar ou não novas chamadas de voz e vídeo. Essa permissão pode estar baseada a um número elevado de fatores, mas o principal fator está relacionado ao dimensionamento da largura de banda de forma correta. Por exemplo: um sistema está designado para trabalhar com três chamadas simultâneas. Usando o CAC para uma nova chamada, quando essas três estiverem ocupadas, uma quarta chamada pode ser descartada. Quando a ferramenta CAC rejeita uma chamada, ela pode ser redirecionada para uma voz padrão Voip de um PABX, como também pode ser direcionada a uma mensagem padrão ligada à rede pública de telefonia (PSTN). Sem a ferramenta CAC, simplesmente, a quarta chamada poderia ser descartada sem qualquer aviso ou programação.

A ferramenta CAC provê um importante componente de estratégia em torno da perda de pacotes, diretamente ligados ao sistema de qualidade de voz.

**Controle de admissão em serviços integrados**

Serviços integrados (IntServ) definem um modelo diferente para QoS, como os processos de sinalização através de fluxos individuais que podem ser solicitados em uma reserva de recursos de largura de banda. Para garantir provimentos de banda por fluxo, o IntServ descreve componentes: reserva de recursos e controle de admissão; reserva de recursos: sinaliza para a rede sobre largura de banda e atrasos particulares relacionados a necessidade dos fluxos. Se a sinalização ocorrer com sucesso, vários componentes de redes reservarão a largura de banda necessária. Esses nós IntServ (que normalmente são roteadores) reservam a largura de banda necessária e respondem com mensagens sinalizadoras.

O controle de admissão IntServ decide quando uma solicitação de reserva pode ser rejeitada. Se todas as solicitações forem aceitas, eventualmente muito tráfego poderá ser injetado na rede e nenhum dos fluxos poderá requisitar esse serviço oferecido pelo IntServ.

**Considerações finais**

Caro aluno, como foi colocado aqui nessa aula, CAC é uma ferramenta para admissão e controle de QoS que volta suas atenções principalmente para pacotes de voz e dados.

Já para os serviços de reserva de recursos utilizados pelo método IntServ, o controle de admissão é responsável pelo controle e aprovação das requisições de reservas feitas pelos fluxos. Eventualmente, se o controle de admissão permitir que todos os fluxos entrem na rede, sem nenhuma rejeição, outros que precisariam de reservas acabam ficando sem esse recurso.

Também vale lembrar que o IntServ trabalha com o protocolo RSVP, que é responsável pela sinalização de largura de banda necessária para uma determinada tarefa.

> [!important]  
> É fortemente recomendável a consulta na RFC 1633 que trata os modelos QoS para serviços integrados. Disponível em: <http://tools.ietf.org/html/rfc1633>.