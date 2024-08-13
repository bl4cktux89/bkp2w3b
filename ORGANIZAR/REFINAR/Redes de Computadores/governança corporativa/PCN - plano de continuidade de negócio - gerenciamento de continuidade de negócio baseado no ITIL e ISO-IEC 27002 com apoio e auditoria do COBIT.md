**A continuidade de negócios – modelo Cobit**

Algumas legislações nacionais e internacionais obrigam as organizações a possuírem um modelo de continuidade de negócio, para que em qualquer situação de catástrofe a empresa possa continuar suas atividades.

Isso acaba implicando diretamente em TI, ou seja, para se continuar um negócio dentro da organização, as operações de TI também precisam ter contingências, planos de retorno, sites backups, pois somente dessa forma as empresas podem se garantir com a continuidade de seus negócios, em razão da dependência de TI.

Para se conseguir mensurar quais são os serviços cruciais para a sobrevivência dos negócios, é preciso entender quais são os processos-chave da organização e o que faz esses processos executarem (pessoas, processos e tecnologias).

A técnica de mapeamento de processos de negócio é um passo importante e inicial, e o BIA (Business Impact Analisys) também é necessário para então identificar quais são os processos da empresa que devem ser continuados, pois sem eles a empresa morre.

Feito isso, podemos utilizar o modelo Cobit para identificarmos quais são os processos necessários para se obter êxito nessa necessidade de dar continuidade. O Cobit recomenda o seguinte:

Prover a continuidade dos serviços de TI requer o desenvolvimento, manutenção e teste de um plano de continuidade de TI, armazenamento de cópias de segurança (backup) em instalações remotas (offsite) e realizar treinamentos periódicos do plano de continuidade. Um processo eficaz de continuidade de serviços minimiza a probabilidade e o impacto de uma interrupção de um serviço-chave de TI nas funções e processos críticos de negócio.

()

Essas recomendações obtidas no domínio DS – entregar e suportar, no objetivo de controle DS4 – assegurar a continuidade dos serviços podem ser utilizadas como base, e para assegurar esse item de controle devemos consultar as recomendações do conjunto de objetivos:

- **DS4.1 Estrutura de continuidade:** a recomendação desse item é que a empresa se estruture e prepare um modelo de necessidade para ser continuado, em caso de catástrofes. O mapeamento dos processos de negócio com o BIA são o pontapé inicial.
- **DS4.2 Planos de continuidade de TI:** desenvolver planos de continuidade de TI com base na estrutura e projetados para reduzir o impacto de uma grande interrupção de funções e processos de negócio fundamentais. Recomenda-se que todos os processos, papéis e responsabilidades estejam inclusos nos planos.
- **DS4.3 Recursos críticos de TI:** dar atenção especial aos itens mais críticos no plano de continuidade de TI para assegurar a capacidade de restabelecimento e definir prioridades em situações de recuperação. Prevenir o desvio de atenção para os itens de recuperação menos críticos e assegurar resposta e recuperação em alinhamento com as necessidades de negócio de maior importância; ao mesmo tempo, assegurar que os custos sejam mantidos em um nível aceitável e em conformidade com os requisitos contratuais e regulamentares. Considerar a capacidade de restauração e os requisitos de resposta e recuperação em diferentes níveis (por exemplo, de uma a quatro horas, de quatro horas a 24 horas, mais de 24 horas e os períodos operacionais de negócios críticos).
- **DS4.4 Manutenção do plano de continuidade de TI:** encorajar o gerenciamento de TI a definir e executar procedimentos de controle de mudança para assegurar que o plano de continuidade de TI seja mantido atualizado e reflita sempre os requisitos de negócios atuais. É essencial que as mudanças nos procedimentos e responsabilidades sejam comunicadas claramente e de forma oportuna.
- **DS4.5 Teste do plano de continuidade de TI:** testar o plano de continuidade de TI regularmente para assegurar que os sistemas de TI possam ser efetivamente recuperados, que desvios sejam tratados e que o plano se mantenha relevante. Para tanto, são necessários preparação cuidadosa, documentação, registro dos resultados dos testes e implementação de planos de ação de acordo com os resultados. Deve-se considerar estender o teste de recuperação apenas de aplicações isoladas a cenários de testes fim a fim integrados com fornecedores.
- **DS4.6 Treinamento do plano de continuidade de TI:** assegurar que todas as partes envolvidas recebam treinamento regular sobre os procedimentos, papéis e respectivas responsabilidades no caso de um incidente ou desastre. Verificar e intensificar o treinamento de acordo com os resultados dos testes de continuidade.
- **DS4.7 Distribuição do plano de continuidade:** definir e gerenciar uma estratégia de distribuição para assegurar que os planos sejam seguramente distribuídos e que estejam apropriadamente disponíveis às partes interessadas e autorizados quando e onde necessário. Toda atenção deve ser dispensada para tornar o plano acessível em todos os cenários de desastre.
- **DS4.8 Recuperação e retomada dos serviços de TI:** planejar as ações a serem executadas nos momentos de recuperação e retomada dos serviços de TI. Isso pode incluir ativação de _backup sites_, iniciação de processamento alternativo, comunicação para as partes interessadas e os clientes, procedimentos de retorno à produção etc. Assegurar que o negócio entenda o tempo de recuperação de TI e os investimentos tecnológicos necessários para sustentar as necessidades de recuperação e retorno à produção.
- **DS4.9 Armazenamento de cópias de segurança em locais remotos:** Armazenar remotamente todas as mídias de cópias de segurança críticas, documentação e outros recursos de TI necessários para a recuperação da TI e os planos de continuidade de negócio. O conteúdo armazenado nas cópias de segurança precisa ser determinado em colaboração entre os proprietários dos processos de negócio e o pessoal de TI. O gerenciamento das instalações de armazenamento remotas deve atentar para a política de classificação de dados e as práticas de armazenamento de mídias da empresa. O gerenciamento de TI deve assegurar que as condições dos locais de armazenamento remotos sejam periodicamente avaliadas, pelo menos anualmente, nos quesitos conteúdo, proteção ambiental e segurança. Assegurar a compatibilidade de _hardware_ e _software_ para restaurar os dados arquivados e testar e atualizar periodicamente os dados arquivados.
- **DS4.10 Revisão pós-retomada dos serviços:** após a retomada bem-sucedida da função de TI depois de um desastre, determinar se o gerenciamento de TI tem procedimentos para avaliar a adequação do plano atual e realizar sua atualização, se necessário.

**O Framework ITIL apoiando no desenvolvimento do processo de continuidade**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/5/5/3/155365/a16i01_gti80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/5/5/3/155365/a16i01_gti80_100.jpg)

O ITIL irá entender basicamente os objetivos de controle citados pelo Cobit, e então analisar dentro da organização quais são as recomendações que já existem e as que ainda são necessárias. É necessário analisar se as recomendações que existem seguem rigorosamente o Cobit e quais motivos de não seguirem.

No framework ITIL, o processo que irá contribuir para a continuidade de serviços de TI é o processo gerenciamento de continuidade, que está no livro de desenho de serviço.

Os planos de recuperação citados pelo ITIL para cumprir a continuidade são:

- **Nenhuma contingência:** o nome mesmo já diz.
- **Procedimentos administrativos:** sem estrutura de TI, pode se utilizar, por exemplo, formulários de papel na falta de um sistema.
- **Arranjos recíprocos:** em que empresas disponibilizam um espaço umas para as outras.
- **Recuperação gradual:** nessa estratégia a própria organização tem um espaço disponível com uma infraestrutura que contenha eletricidade, conexões com telefone, ar-condicionado, em que as aplicações possam ser migradas e os níveis de serviços restaurados.
- **Recuperação intermediária:** neste cenário existe um local de evacuação alugado ou disponível.
- **Recuperação imediata:** é o que chamamos de site backup, em que há uma estrutura igual ou semelhante de servidores, serviços e aplicações disponíveis.

Alguns indicadores de performance utilizados para medir a eficiência e eficácia do processo são:

- Custos.
- Resultados do plano de testes.
- Perdas em consequência de desastres.
- Número de incidentes identificados na auditoria que não estão inseridos no plano de GCSTI.

Mesmo empresas que hospedam seu parque de servidores em data centers ou na "nuvem" precisam do GCSTI, e quem sabe incluir itens, tais como: saber os planos de contingência que a empresa contratada tem, criação de SLAs, multas para não cumprimento de contratos, entre outros.

Esse assunto certamente não é algo barato para as organizações, por isso muitas vezes é deixado de lado, porém, dentro em um custo viável devemos pensar em soluções para amenizar riscos de eventos como os "apagões".

**Controles recomendados pela ISO/IEC 27002**

O principal objetivo do processo de continuidade de negócio é garantir que, em caso de uma catástrofe, os negócios da empresa não sofram interrupção ou tenham o mínimo de continuidade dentro da organização dos processos mais críticos e vitais.

A ISO/IEC 27002 possui um capítulo específico para tratar esse assunto em termos de controles, que apoiam a organização em manter o equilíbrio do PCN (Plano de Continuidade de Negócio), o capítulo 11 – Gestão da Continuidade do Negócio.

Nesse contexto, é preciso entender como a TI está tratando as falhas, incidentes e desastres que afetam a operação do negócio corporativo. Como a TI está preparada para reagir ou preferencialmente prever eventos que comprometam a operação da organização? Qual o impacto (financeiro, institucional e comercial) de uma parada na operação? Para tratar desse assunto é extremamente relevante observar a importância de um Plano de Continuidade de Negócios.

O Plano de Continuidade de Negócios, mais conhecido como PCN, tem por objetivo principal ser um documento que auxilia a organização no tratamento de desastres, tentando diminuir perdas, oferecendo mais disponibilidade, segurança e confiabilidade na TI para que suporte com valor e qualidade o negócio da organização.

Muitas organizações se dizem preparadas, pois possuem contingência, mas e a continuidade (são duas coisas bem diferentes uma da outra). A contingência pode ser entendida como backup. Você faz backup todo dia? Então você tem uma contingência. Mas em caso de ter que recuperar um backup, quanto tempo a organização vai esperar para voltar a operar? Quanto menor este tempo, mais continuidade está sendo oferecida.

Os principais controles da ISO/IEC 27002 são:

- 11.1 Aspectos da gestão da continuidade do negócio.
- 11.1.1 Processo de gestão da continuidade do negócio.
- 11.1.2 Continuidade do negócio e análise de impacto.
- 11.1.3 Documentando e implementando planos de continuidade.
- 11.1.4 Estrutura do plano de continuidade do negócio.
- 11.1.5 Testes, manutenção e reavaliação dos planos de continuidade do negócio.
- 11.1.5.1 Teste dos planos.