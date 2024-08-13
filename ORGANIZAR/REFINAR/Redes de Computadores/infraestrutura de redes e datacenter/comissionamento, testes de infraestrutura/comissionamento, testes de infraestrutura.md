Ao final da entrega do projeto do Data Center executado, inicia-se um processo cujo o objetivo é verificar se todas as características esperadas do projeto foram executadas de acordo, o que significa que o Data Center pode entrar em operação com seus respectivos clientes. O nome deste processo é comissionamento (Esta palavra tem mais sentido na cultura norte americana, o correto seria Verificação de Escopo se utilizar a metodologia do PMI -_**Project Management Institute**_).

Quando se constrói um Data Center, é difícil saber se todos os sistemas físicos da infraestrutura como, climatização, geração de energia, alimentação e distribuição elétrica, detecção e supressão de incêndio, gerenciamento e segurança estão operando corretamente e corretamente interconectados. Esta verificação nada mais é que rever e testar o projeto da infraestrutura do Data Center, através de um sistema holístico com o objetivo de garantir um alto nível de confiabilidade.

O comissionamento é uma tarefa árdua e exige despesas consideráveis, além de um time de profissionais multidisciplinares. Por tal razão, tem sido associado a grandes Data Centers. No entanto, tentar fazer pequenos testes e lançar oficialmente um Data Center, pode representar um grande risco para o negócio, manchando a imagem do Data Center e, se nada for feito para mitigar os efeitos do desastre comercial, levar o negócio a falência.

Quando os fornecedores instalam seus equipamentos no Data Center, produzem pequenos testes para garantir uma aceitação e, em seguida, poderem gerar a fatura para cobrança. Nenhum destes fornecedores está comprometido para verificar o funcionamento de seus equipamentos em conjuntos com todos os outros sistemas instalados. É aí que entra uma estrutura de controle da equipe designada para o comissionamento e inicia testes gerais onde observa-se o funcionamento do todo e, somente assim, produzir uma aceitação real para o funcionamento do Data Center.

A norma ASHRAE tem um capítulo para este momento, o _**Guideline 0-2005 The commissioning Process**_ que pode ser fartamente utilizado como um guia para este trabalho, descrevendo uma visão geral do comissionamento, descrição de cada fase, requisitos para a aceitação de cada fase, requisitos para a documentação de cada fase e, finalmente os requisitos para o treinamentos das pessoas que trabalharão no Data Center.

No trabalho de comissionamento ocorre um momento rico em aquisição de experiência sobre o Data Center. Os testes produzem documentação que acrescenta muito no conhecimento de cada participante do comissionamento. Por exemplo, introduzindo um novo CRAC (_**computer room air conditioning**_), observa-se o aumento da corrente de alimentação na PDU (_**power distribution unit**_), este aumento pode apresentar algo a mais do que previa-se pela documentação do fabricante. Neste caso, estuda-se se houve algum erro de projeto incluindo posicionamento, ângulo no qual foi instalado, bitolas dos cabos de alimentação, calibragem do equipamento, vazamentos nos dutos de retorno, impedimentos nos ventiladores, etc. Se nenhum erro foi encontrado, a equipe acabou de aprender que deve-se esperar mais de consumo para aquele equipamento. Como foi falado, esta experiência é fartamente rica para a equipe do Data Center.

O documento mais importante gerado no comissionamento é o “_**AS BUILT**_”, todos os outros documentos são retratos da produção dos subsistemas. O _**AS BUILT**_ é o guia básico e também é o documento que o proprietário quer ver. Em todo o mundo, o pagamento de serviços de instalações deste porte é liberado apenas com a apresentação e aceitação do “_**AS BUILT**_”.

Os elementos do “_**As Built**_” são:

- Descrição do Data Center
    - Tamanho em m.
        
        2
        
    - Componentes chave da infraestrutura.
    - Níveis de redundância de componentes
    - Nível do Data Center
- Características de projeto do Data Center
    - Planta de localização de equipamentos e a demonstração física, incluindo racks.
    - Planta e demonstração da distribuição de energia.
    - Planta demonstrando o sistema de tubulação de refrigeração, sistema de água resfriada e supressão de incêndio.
    - Planta com os padrões do fluxo de ar esperado/planejado.
- Verificações de Componentes
    - Modelo especificado (Fabricante, nome do modelo, número do modelo)
    - Modelo entregue (Fabricante, nome do modelo, número do modelo)
    - Modelo instalado (Fabricante, nome do modelo, número do modelo)
    - Capacidade do modelo (kW, volts, amperes)
    - Condição geral do equipamento.
- Dados de Desempenho
    - Procedimentos de testes
    - Resposta esperada
    - Resposta Real
    - Aprovação: Aprovado ou Reprovado.

O documento resumo do resultado do comissionamento apresenta o seguinte formato:

- Sumário Executivo
    - Visão Geral do Data Center
    - Resumo das condições esperadas do Data Center
    - Resumos do escopo do comissionamento
- Visão Geral da Metodologia do Comissionamento
    - Procedimentos testados
    - Sequenciamento dos testes.
- Comissionamento do Desempenho e tendências do sistema do Data Center.
    - Infraestrutura física de energia de entrada e retirada de calor.
    - Análise dos sistemas de climatização e energia em termos de capacidade e custos.
    - Análise dos erros enfatizando as causas raiz.
- Conclusão
    - Possíveis impactos
    - Expansão futura.

**Uma lista de verificações e testes para conduzir o comissionamento.**

A tabela 1 mostra um bom guia para a equipe de comissionamento.

![[Untitled 69.png|Untitled 69.png]]

![[Untitled 1 42.png|Untitled 1 42.png]]

![[Untitled 2 33.png|Untitled 2 33.png]]

![[Untitled 3 21.png|Untitled 3 21.png]]

**Qual o resultado de trabalho de comissionamento?**

A figura 1 mostra uma simplificação, mas bastante esclarecedora, de o que ocorre ao aplicar-se um trabalho bem feito de comissionamento.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/3/1/273142/14427.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/3/1/273142/14427.jpg)

Figura 1: Fluxo de trabalho e resultados da equipe de comissionamento

Fonte: Autoria própria

O comissionamento é uma tarefa muito complexa e longa. O importante é que o leitor tenha percebido os resultados esperados e as vantagens de se fazer este trabalho que leva a um nível excelente de conhecimento da capacidade de seu Data Center.

Para terminar, fica para o leitor uma pequena lista de falhas típicas no processo de comissionamento:

- Demora para designar e acionar o agente do comissionamento. Um planejamento rigoroso e completo deve ser feito e será um contrasenso começar os trabalhos só após o final do projeto. É de boa prática que o agente de comissionamento já esteja trabalhando no plano de avaliação enquanto o Data Center está em construção.
- Falta de alinhamento com a tecnologia atualizada. Conceitos antigos ou defasados podem causar total inversão da expectativa de cada componente ou sistema causando stress e enganos prejudiciais.
- Falha na identificação clara do papel de cada integrante da equipe. Muito trabalho pode ser desperdiçado no caso de má definição dos papéis.
- Falha em validar o plano de ação da equipe. Isto pode criar falhas do caminho a ser seguido e atrasar as atividades e/ou até invalida-las.
- Falha para evitar o corte de orçamento. A equipe de comissionamento é a maior interessada em manter o processo sob controle e dentro das expectativas de tempo e orçamento. Deixar que a pressão dos negócios crie cortes pode prejudicar de sobremaneira o processo além de introduzir desânimo e maior risco de erros humanos.
- Falha na simulação de cargas de calor. Como o data center não está carregado com os servidores reais, simula-se o calor com simuladores especializados. Erros neste ponto podem causar erros nas medidas e produzir um “OK” onde deveria estar “não OK” e vice-versa.
- Falha na identificação de elos fracos. Todo um subsistema pode ser colocado em risco se não houver completa atenção em pequenas fragilidades que são subestimadas.
- Falha na indicação e comunicação de procedimentos de emergência. Diferenças de conhecimento da operação do Data Center e o pessoal do comissionamento, podem produzir paradas inesperadas.
- Falha humana por fadiga. A pressão e o desejo de que o comissionamento termine pode causar excesso de fadiga e consequentemente introduzir falhas de julgamento, análise e, até, risco pessoal.
- Falha de atualização da documentação: A base de conhecimento adquirida deve ser imediatamente atualizada na documentação de operação do Data Center, permitindo que o novo conhecimento auxilie na operação e traga vantagens. O contrário pode causar mal funcionamento e perda ou gerar _downtime_.

Este material não pretende completar todo o conhecimento sobre comissionamento. O nível de multi disciplinas que está envolvido é muito grande. Existem muitos exemplos de livros especificamente sobre o assunto. Caso o leitor estiver envolvido numa avaliação como esta, certamente deverá estudar profundamente o processo em literatura especializada.