### Introdução

Espera-se que a rede de computadores e os sistemas que fazem uso dela, sejam capazes de atender as funções e serviços ofertados, dentro de um limite de qualidade. Quando pensamos em desempenho de uma rede, automaticamente associamos a qualidade do serviço da rede, está correlação não é por acaso, visto as exigências, os problemas e dificuldades.

A instalação de serviços na web segundo Kurose (2006),  tem se tornado rotina e, muitas vezes, realiza-se em tempo abaixo do necessário. A grande demanda por novos serviços podem acarretar projetos sem os cuidados e testes necessários, levando a vulnerabilidades no desempenho, segurança e disponibilidade do site.

Nosso objetivo é descrever de maneira clara e sucinta as noções de disponibilidade e confiabilidade em redes de computadores, conforme apresenta Menascé (2002), como sendo fatores essenciais para avaliação do desempenho.

### Disponibilidade

Pode-se definir disponibilidade como sendo a parcela de tempo em que se espera que um sistema ou serviço esteja disponível para utilização ABNT (1994), ou seja, esteja funcional. Disponibilidade é expressada em termos percentuais, levando em consideração apenas o tempo em que os serviços estão disponíveis, devendo para os calculos de disponibilidade, excluir os períodos de paradas agendadas para manutenção dos serviços.

Durante a execução de um serviço na web, algumas falhas podem acontecer. Essas falhas afetam os serviços comprometendo sua disponibilidade sendo assim, torna-se necessário e importante gerenciar essas falhas para minimizar os problemas de indisponibilidade. Segundo Gildo (2007), os pontos para se manter a disponibilidade dos serviços web ou a infraestrutura de redes e servidores são importantes para gestão de projetos.

Conforme foi apresentado, o modelo FCAPS mostra um modelo de gerenciamento de falhas, que nada mais é do que um conjunto de facilidades que habilitam a detecção, isolamento e correção de operações anormais no ambiente de rede gerenciado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/4/0/324056/19570.gif)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/4/0/324056/19570.gif)

Recuperação de falhas

### Por que os sistemas falham?

Existem muitos motivos para um sistema de computador falhar, é importante categorizar os diferentes tipos de falhas. Citamos abaixo alguns possíveis fatores:

- Falha de Hardware;
- Problemas de conectividade;
- Problemas relacionados com a segurança;
- Falhas nas rotinas dos aplicativos;
- Etc...

Abaixo são descritas de maneira sistemática as causas e os tipos de falhas, abordadas em 3 dimensões:

1. **Duração da Falha;**
2. **Efeito da Falha;**
3. **Escopo da Falha.**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/9/8/7/198782/i02_51501.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/9/8/7/198782/i02_51501.jpg)

### Duração da Falha

A duração de uma falha pode afetar muito na disponibilidade do serviço e trazer prejuízos enormes a uma organização. Esta dimensão pode ser dividida em 3 classes conforme mostra a ABNT (1994):

1. **Falhas permanentes:** acontece quando um sistema ou serviço deixa de funcionar com nenhuma possibilidade de retornar à funcionalidade sem a devida correção ou substituição do item com falha. Por exemplo, problemas no disco do servidor, enquanto o mesmo não for substituído, os sistemas permaneceram parados.
2. **Falhas recuperáveis:** é quando o sistema fica inacessível por uma falha localizada. Por exemplo, quando um servidor de web por falta de conexão da internet, deixa as páginas inacessíveis.
3. **Falhas transientes:** as falhas transientes têm duração muito curta e às vezes não são perceptíveis pelos usuários de um serviço.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267905/15423.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/9/267905/15423.jpg)

### Efeito da Falha.

A dimensão do efeito da falha, praticamente informa o que foi afetado no sistema ou serviço. Esta dimensão pode ser dividida em 2 classes conforme mostra a ABNT (1994):

1. **Falhas funcionais:** quando sistema não apresenta alguma funcionalidade conforme a sua especificação. Por exemplo: Não mostrar a ficha completa de um livro em uma livraria online. O sistema está em funcionamento, porém algum item não funciona.
2. **Falhas de desempenho:** quando o sistema apresenta aparentemente todas as funcionalidades previstas, mas não de forma adequada. Todos os itens estão funcionando, mas não de maneira correta.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/7/293772/17454.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/7/293772/17454.jpg)

### Escopo da falha.

A terceira dimensão das falhas,  compreende a abrangência da falha e também o retorno que é passado ao usuário do sistema ou serviço, e pode ser dividida em duas classes:

1. **Parcial:** é quando alguns dos serviços fornecidos pelo sistema se tornam indisponível e outros estão em funcionamento.
2. **Total:** essas falhas são caracterizadas por uma interrupção completa de todos os serviços oferecidos pelo sistema. Por exemplo, uma falta de energia deixando todo um serviço fora do ar.

### Medições de disponibilidade

As medições de disponibilidade são definidas como a fração de tempo em que um componente está operacional ABNT (1994).

Partindo do estado em que um sistema está operacional, ele levará certo tempo para falhar novamente. O tempo médio para que o sistema falhe é chamado de **MTTF**.

Quando um sistema falhar, ele levará certo tempo para se recuperar da falha e retornar a um estado operacional. O tempo médio para que o sistema se recupere é chamado de **MTTR**.

O tempo médio entre falhas é chamado de **MTBF** e pode ser conhecido pela seguinte relação:

**MTBF = MTTF + MTTR**

**MTTF:** _**Mean Time To Failure**_ – Tempo Médio Para Falha.

**MTTR:** _**Mean Time to Recover**_ – Tempo Médio Para Recuperação.

**MTBF:** _**Mean Time Between Failures**_ – Tempo Médio Entre Falhas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/4/6/354679/25832.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/4/6/354679/25832.png)

Medições de disponibilidade

**FORTALECENDO CONCEITOS !**

### Confiabilidade X Disponibilidade

**Confiabilidade:** é a probabilidade de que um sistema esteja funcionando correta e constantemente por um período determinado de tempo.

**Disponibilidade:** noção de que um sistema alterne, entre os períodos ativos e não ativos. A fração do tempo que um sistema está operacional.

### Classes de disponibilidade.

A tabela abaixo demostra a disponibilidade dos sistemas, mostrando os níveis de disponibilidade como base nos minutos de um ano.

![[Screenshot_from_2022-03-20_21-42-18.png]]

Na sequência mostramos como calcular a disponibilidade de forma simplificada. Sabe-se que a disponibilidade de um sistema é a relação entre o tempo de vida útil (tempo ativo) deste sistema e seu tempo total de vida (ativo + inativo).  Isto pode ser representado pela seguinte relação, onde _**Downtime**_ é o período de tempo que o sistema ficou inoperante.

**Disponibilidade = (TUT ?** _**Downtime**_**) / TUT**

Considerando como TUT (Total de Unidade de Tempo) um período fechado de 8 760 horas por ano, ou seja, 365 dias x 24 horas.

Vamos nos basear neste valor para o exemplo que segue e verificar o resultado da porcentagem na tabela anterior para classificarmos o sistema.

Exemplo: Em um serviço de web, em seu ambiente de rede, o Administrador precisa fazer uma atualização do sistema que ficará _**offline**_ por 2 horas. Calculando a disponibilidade, podemos afirmar que este sistema é:

### Calculando:

**Disponibilidade** = (TUT – _**Downtime**_) / TUT

**Disponibilidade** = (8760 – 2) / 8760

**Disponibilidade** = 99,9%

Verificando na tabela já ilustrada, podemos afirmar que este sistema é **bem controlado**.

### Cuidados nos projetos.

O bom uso e controle dos links de dados e dos equipamentos definidos na estrutura da rede, possibilitarão a diminuição das falhas e o aumento da disponibilidade, (COELHO, 2003).

Para um bom projeto é indispensável, um correto dimensionamento dos niveis de disponibilidade da rede, segundo Kerzner (2008), esses cuidados fazem parte das boas práticas (HELDMAN, 2006).