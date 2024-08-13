### Introdução

Um dos grandes desafios da Tecnologia da Informação é manter a disponibilidade dos sistemas computacionais, para garantir o funcionamento dos sistemas, são aplicados processos, que tem como finalidade a recuperação de uma interrupção do sistema que pode afetar as operações comerciais. Um processo integrado de recuperação de serviços, inclui um conjunto de atividades para garantir a “disponibilidade de informações” BC envolve medidas proativas e reativas para manter a continuidade dos negócios, essas medidas, também são conhecidas pelo termo BC (Business Continuity).

### O que é Business Continuity?

Business Continuity trata da capacidade de garantir que informações estarão disponíveis, mesmo se houver algum problema, independentemente de onde, o quê ou quem causou a indisponibilidade das informações, estas informações devem ser recuperadas, isso significa criar medidas proativas (antes de algo acontecer) e reativas(após algum incidente ocorrer). Portanto é muito importante automatizar ao máximo essas medidas, de maneira que o tempo de resposta seja mais rápido.

Business Continuity, significa Continuidade de negócios, refere-se à disponibilidade de informações, mas você deve se perguntar, “por que tanta preocupação assim? ”Pois essas informações valem muito para algumas empresas, pois são informações financeiras muitas vezes, ou elas perdem dinheiro por seu site/aplicativo estar fora do ar, a reputação da sua empresa é ameaçada, e muitas vezes se perde produtividade sem o sistema. Todos esses impactos negativos podem ser tratados com Business Continuity.

### Gerenciamento de falha e indisponibilidade de serviços

Ainda quando falamos sobre informações, também estamos fazendo referência a disponibilidade da mesma para a empresa, bem como a inteligência utilizada para validar o ciclo de vida que esta informação tem para a empresa, assim como a geração de lucros em estudos e utilização da informação no momento adequado. Não devemos nos esquecer também do efeito inverso, que seria a indisponibilidade das informações, isso poderia gerar prejuízos sem dimensões para a empresa dependendo do seu negócio.

O gerenciamento de falhas ou indisponibilidade não se limita à prevenção. Não importa quão bem as ameaças sejam gerenciadas, as vulnerabilidades controladas e os controles de acesso implementados: alguma coisa sempre pode dar errado. Um gerenciamento de segurança prudente determina que é preciso assumir sempre que, em algum momento, uma falha irá ocorrer na infraestrutura de Tecnologia da Informação.

As falhas, no entanto, não se limitam às quebras de segurança; desastres naturais, falta de energia, defeitos de hardware e falhas de software; são ocorrências que podem afetar a capacidade de operação de qualquer organização. A continuidade de serviços é a prática de se preparar para tais ocorrências e criar estratégias de recuperação com impacto mínimo sobre as operações de negócios. Esta aula concentra-se em alguns aspectos principais das práticas de continuidade de serviços:

- Identificação de requisitos empresariais para a continuidade de serviços.
- Formulação de planos de backup e recuperação.
- Exploração das melhores práticas para se manter a continuidade de serviços.

Como em outras áreas do gerenciamento de segurança, há um grau significativo de sobreposição entre a continuidade de serviços e outras operações de TI. No caso da continuidade de serviços, muito do que está descrito nesta aula corresponde à área de gerenciamento de armazenagem.

É claro que o gerenciamento de armazenagem aborda mais do que apenas a continuidade de serviços, assim como o gerenciamento de segurança abrange mais do que a continuidade de serviços. Ambos estão estreitamente ligados, porém, e as técnicas desenvolvidas nas duas áreas complementam-se mutuamente, oferecendo uma abordagem abrangente sobre o planejamento da continuidade de serviços.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/1/345177/25307.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/1/345177/25307.jpg)

Falha de Software

### Tipos de Falhas e disponibilidade de dados

Primeiro, precisamos entender os principais tipos de falhas para entender como solucionarmos, eles são:

- Falha do aplicativo: Por exemplo um bug no sistema, ou uma falha de segurança.
- Falha a nível computacional: No servidor, por exemplo, pode ser física ou de software.
- Falha a nível de rede: Algum dispositivo apresenta problemas ou sobrecarga na rede, como switches, fabrics, etc.
- Falha no armazenamento: Problemas com discos, ou falta de espaço por exemplo
- Falha no Data Center: Problemas elétricos, meteorológicos, etc

Agora que entendemos as principais falhas, vamos entender o que significa ter disponibilidade das informações, para isso precisamos ter três quesitos:

- Acessibilidade: As informações sempre podem ser acessadas
- Confiabilidade: As informações devem ser íntegras
- Agilidade: A agilidade na qual as informações são acessadas

Garantindo esses três pontos nos asseguramos a disponibilidade de informações, esse desafio pode parecer difícil, e de certa forma é, porém temos técnicas que quando bem aplicadas, funcionam muito bem para que se tenha uma integridade total de suas informações e elas sejam totalmente acessíveis sempre! A recuperação de desastres como serviço (DRaaS) aparece como uma solução para desastres baseada em nuvem.

**MODELOS DE DOCUMENTOS GESTÃO DE CONTINUIDADE DOS NEGÓCIOS E DE TECNOLOGIA DA INFORMAÇÃO**

A adoção de documentos que norteiam as boas práticas para gestão de continuidades dos negócios é imprescindível nos dias de hoje, para todas as organizações, veja abaixo um exemplo desses documentos norteadores.

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/1/267125/15497.pdf)

### Requisitos empresariais para a continuidade de serviços

O primeiro ponto para se compreender a abrangência dos requisitos da continuidade de serviços consiste em entender os dados e ativos necessários para manter as operações de uma organização. O planejamento da continuidade de serviços não é apenas uma questão de fazer backup de todos os dados, armazenagem de mídia de backup em outro local e restaurar dados conforme o necessário. Embora tal abordagem possa funcionar em pequenas empresas, a infraestrutura de TI de grande parte das empresas já evoluiu para ambientes mais complexos, que exigem uma série de soluções.

Nesse caso, é necessário entender três conceitos básicos a fim de partir para o mapeamento do PCN (Plano de Continuidade de Negócio), que são:

- Nível básico - o nível básico de funcionalidade inclui os serviços necessários para se prover as operações essenciais (sistemas operacionais e hardware básicos também estão incluídos nesse ponto de recuperação), assim como aqueles vinculados a fluxos de receita ou exigidos por normas. Se tais sistemas caírem, a empresa não poderá fazer negócios. Formulação de planos de _backup_ e recuperação.
- Nível secundário - uma vez garantidas as operações e funções de nível básico, o nível seguinte envolve as funções secundárias. Elas dependem de sistemas que prestam serviços adicionais, mas podem ficar indisponíveis por curtos períodos sem grande impacto sobre a receita ou a conformidade normativa.
- Nível terciário - o grupo final de funções de alto nível abrange os serviços que podem ficar indisponíveis durante períodos prolongados (um dia ou mais), sem impactos negativos sobre os negócios. Embora os executivos e gerentes possam estar habituados às atualizações diárias de produção e operações, se um painel executivo ou um _Data Warehouse_ permanecer inoperante por um ou dois dias, a organização consegue continuar cumprindo as metas de produção e atendendo às expectativas dos clientes.

Uma vez encontrados esses níveis dentro da organização, o plano de continuidade de negócio está pronto para ser produzido e documentado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/8/363816/29083.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/8/363816/29083.png)

Exemplo de plano de recuperação de desastres

### _SLA´s (Service-Level Agreement´s)-Níveis de acordo de Serviço_

Como alternativa à continuidade dos negócios, as empresas contratam serviços que podem oferecer um outro local físico para manter a custódia dos dados e serviços das organizações. Esses serviços podem ser classificados em três modalidades que são:

### Sites de continuidade operacional – cold site

É um local que contém os suprimentos necessários para a instalação de um sistema de computador. Caso uma situação emergencial tome lugar, a empresa pode obter do prestador de serviços a instalação de computadores de backup nesse ambiente. Por se tratar apenas de um espaço físico, a empresa poderá ficar um grande período sem seus serviços, até que seja novamente recuperado.

### Sites de continuidade operacional – warm site

O warm site contém equipamentos similares ao site original de trabalho e os principais serviços para a empresa trabalhar. Porém, nesse modelo, é necessário fazer a restauração de alguns backups para tudo ficar no estado de trabalho próximo ao último anterior. O warm site contém os equipamentos necessários para manter o site backup em funcionamento por um longo tempo.

### Sites de continuidade operacional – hot site

Todos os equipamentos e dados permanecem em um local à disposição da empresa para ser utilizado quando a contingência acontecer, sendo somente necessário levar os colaboradores para o local físico do hot site. Suas principais vantagens são a possibilidade de ser testado periodicamente e a velocidade de retomada de funcionamento em caso de desastre.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/3/7/353768/29084.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/3/7/353768/29084.jpg)

Recuperação de desastres

**CARTILHA DE SEGURANÇA PARA INTERNET**

Para saber mais sobre Segurança e recuperação de desastres acesse a Cartilha  feita pelo Centro de Estudos, Resposta e Tratamento de Incidentes de Segurança no Brasil (CERT.br), que é um dos serviços prestados para a comunidade Internet do Brasil pelo Núcleo de Informação e Coordenação do Ponto BR (NIC.br), o braço executivo do Comitê Gestor da Internet no Brasil (CGI.br).

Acesse: https://cartilha.cert.br/

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/1/345177/25307.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/1/345177/25307.jpg)

Gerenciamento de falhas

**SAIBA MAIS SOBRE SLA´S (SERVICE-LEVEL AGREEMENT´S)-NÍVEIS DE ACORDO DE SERVIÇO**

Para saber mais sobre disponibilidade e indisponibilidade, bem como o tempo de recuperação de falhas, consulte o site Uptime.is

Disponível em:https://uptime.is/

### Resumo

O DRP (Disaster Recovery Plan) ou Plano de Recuperação de Desastres é uma forma de garantir que, em caso de uma catástrofe que possa causar a indisponibilidade de todos os serviços de uma empresa, nesse momento se mantenha os principais deles ativos.

Os principais níveis de um Plano de Recuperação de Desastres são:

- **Nível básico** - identificar quais são os recursos de infraestrutura e sistemas que obrigatoriamente devem ficar em alta disponibilidade ou disponibilidade contínua.
- **Nível secundário** identificar quais sistemas e funções dos sistemas serão fundamentais para a empresa não deixar de operar normalmente.
- **Nível terciário -** Identificar os impactos causados por sistemas que apesar de importantes para a organização, podem ser recuperados sem causar grandes perdas, como a indisponibilidade de um servidor de correios.

A última coisa para analisar, seria o tempo de inatividade de um sistema, que consiste em o tempo de uma falha para outra e sua recuperação. Depois disso, o administrador do sistema deve analisar quais são os pontos mais importantes que não podem ter falha, pois se tiverem vão afetar o sistema de maneira geral. Após fazer isso, a solução para esses pontos críticos é criar uma redundância. Essa redundância pode ser de rede, sistema computacional ou de armazenamento e até mesmo a nível de Data Center. E claro, sempre mantendo várias cópias de todas informações (backup), essa replicação pode ser feita no mesmo local, ou remotamente, conforme a contratação e níveis de serviço: Hot site, Warm site, Cold site.

Como foi visto neste tópico, a continuidade dos negócios é muito importante para as organizações, precisamos seguir esses conceitos básicos para manter as informações sempre disponíveis e íntegras.