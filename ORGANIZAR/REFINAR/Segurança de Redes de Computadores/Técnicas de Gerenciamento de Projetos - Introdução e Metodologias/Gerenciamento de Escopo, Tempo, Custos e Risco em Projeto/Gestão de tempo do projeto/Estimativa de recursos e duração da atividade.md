[![](https://ampli-images.s3.amazonaws.com/production/995e1fcc-9c89-42bf-a67d-c2bfa7054256/original)](https://ampli-images.s3.amazonaws.com/production/995e1fcc-9c89-42bf-a67d-c2bfa7054256/original)

fonte: Shutterstock.

Depois que sequenciamos as atividades, podemos fazer uma **estimativa de recursos da atividade**. Estimar recursos para atividades é o processo de quantificar o material, as pessoas, os equipamentos e/ou suprimentos que deverão ser utilizados para realizar cada atividade. Nessa estimativa, pode até aparecer o nome da pessoa responsável pelas tarefas, conforme exemplo da figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/0dabce6d-9657-4cb4-815b-b185a119aa00/original)](https://ampli-images.s3.amazonaws.com/production/0dabce6d-9657-4cb4-815b-b185a119aa00/original)

Estimativas de recursos por atividade. Fonte: Barbosa (2012).

Repare que neste exemplo da figura acima, temos a estimativa de tempo otimista (To), realista (Tm) e pessimista (Tp), e também o tipo de recurso necessário e a quantidade dele. Lembre-se de que podemos também inserir nas estimativas equipamentos, salas, telefones etc. O importante é identificar os recursos, as especialidades e o tempo necessário para cada um em cada atividade.

Por esse exemplo da figura acima, podemos entrar no próximo passo da elaboração do cronograma, que é fazermos uma **estimativa de duração de atividade**. Esse é um processo no qual calculamos a duração das atividades que estarão no cronograma. As estimativas de duração são fornecidas por pessoas ou grupos do time do projeto que possuem mais experiência com a atividade específica. A estimativa, normalmente, é elaborada progressivamente. Nesse processo, a qualidade dos dados fornecidos é muito importante. Uma das técnicas mais utilizadas de estimativa de duração das atividades é conhecida como PERT (_Program Evaluation and Review Technique_), que se baseia em três estimativas: uma mais otimista (ou mais curta) para a realização de uma atividade do projeto (to), uma de duração mais provável para ele (tm) e uma mais pessimista (mais longa) para cada tarefa (tp). A partir delas, é utilizado o seguinte cálculo para estimarmos o tempo (te) que levará cada tarefa:

[![](https://ampli-images.s3.amazonaws.com/production/a2079ef4-3feb-46eb-80c3-5f4a126139e6/original)](https://ampli-images.s3.amazonaws.com/production/a2079ef4-3feb-46eb-80c3-5f4a126139e6/original)

Quando conseguimos estimar o tempo que levará cada tarefa, podemos incluir isso no nosso diagrama de rede, conforme figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/61e4cee0-e0b7-40f4-b8fc-097ea3257c72/original)](https://ampli-images.s3.amazonaws.com/production/61e4cee0-e0b7-40f4-b8fc-097ea3257c72/original)

Diagrama de setas com tempo estimado para preparar o café da manhã. Fonte: Jkolb, 2016.

Um desdobramento complementar do diagrama de rede é um diagrama baseado no CPM (_Critical Path Method_, ou **Método do Caminho Crítico**). No CPM, não temos apenas informações sobre a duração de cada atividade, mas também sobre as datas mais cedo e mais tarde nas quais esta atividade pode acontecer. A data mais cedo da atividade (Tc) é a menor data em que a atividade deve acontecer, desde que as anteriores ocorram nas durações previstas, conforme figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/b1937dc1-3350-4bc8-bc99-527553182b4a/original)](https://ampli-images.s3.amazonaws.com/production/b1937dc1-3350-4bc8-bc99-527553182b4a/original)

Data mais cedo. Fonte: Stonner (2013).

Vejam que a atividade “Carregar catalisador na torre” depende das três atividades predecessoras: “instalar dispositivos de carregamento”, que termina na hora 10, “limpar e reparar internos da torre”, que termina na hora 20, e “regenerar catalisador gasto”, que termina na hora 18. Como é necessário que todas as atividades predecessoras terminem para que a próxima atividade inicie, isso nos mostra que o momento mais cedo em que a atividade “carregar catalisador na torre” pode iniciar é na hora 20.

Para calcular as datas mais cedo de um diagrama de precedências, seguimos da esquerda para a direita, ou seja, do início ao fim, somando as durações das atividades e, quando houver duas ou mais atividades convergindo para uma sucessora, a data mais cedo de início desta sucessora é a maior dentre as datas que nela convergem (STONNER, 2013).

A data mais tarde do evento (Tt) é a maior data em que o evento pode ocorrer sem atrasar a conclusão do empreendimento, conforme figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/74b9e114-a9f4-4f64-8b46-039b9e7b756b/original)](https://ampli-images.s3.amazonaws.com/production/74b9e114-a9f4-4f64-8b46-039b9e7b756b/original)

Data mais tarde. Fonte: Stonner (2013).

Neste exemplo, a atividade “montar andaime interno” é a predecessora das atividades "iniciar quebra do refratário”, que inicia na hora 12, “medir espessura dos tubos da radiação”, que inicia na hora 14, e “remover _skinpoints_”, que inicia na hora 16. Como é necessário concluir a atividade “montar andaime interno” antes do início de todas as outras atividades, isso nos leva a ver que o momento mais tarde que a atividade “montar andaime interno” pode terminar é 12.

Para calcular as datas mais tarde de um diagrama de precedências, siga da direita para a esquerda, subtraindo as durações das atividades e, quando houver duas ou mais atividades partindo de uma mesma predecessora, a data mais tarde de finalização desta predecessora é a menor dentre as datas que dela divergem (STONNER, 2013).

O **diagrama do caminho crítico** é oriundo do diagrama de precedência, e combina as técnicas de PERT e CPM. O caminho crítico de um projeto é aquele cuja sequência não contém folgas, ou seja, é o caminho mais longo do projeto. Por isso, caso alguma atividade que faz parte do caminho crítico atrase, o projeto como um todo atrasa também.

______

**📝 Exemplificando**

Para calcular o caminho crítico, temos que somar as durações de todas as atividades em todos os caminhos. O caminho que tiver a maior duração é o caminho crítico.

[![](https://ampli-images.s3.amazonaws.com/production/498ec604-0469-4f02-bba7-aad9bf5a2dae/original)](https://ampli-images.s3.amazonaws.com/production/498ec604-0469-4f02-bba7-aad9bf5a2dae/original)

Caminho crítico. Fonte: Rodrigues (2012).

No exemplo, os cálculos ficam assim:

O primeiro caminho possível do projeto A, B, E, G soma um total de 14 horas (A, B, E, G = 3 + 1 + 4 + 6 = **14**). O segundo caminho possível, A, C, E, G, soma 15 horas (A, C, E, G = 3 + 2 + 4 + 6 = **15**). Já, o terceiro caminho possível, A, D, F, G, soma 17 horas (A, D, F, G = 3 + 3 + 5 + 6 = **17**). Assim, após este cálculo, podemos ver que o **caminho crítico** **é A, D, F, G**. Os outros dois caminhos possuem folga.

______

As folgas são períodos de tempo que as atividades de um projeto podem atrasar sem afetar o prazo final do projeto planejado no cronograma. Vamos calcular a folga dos caminhos que encontramos no exemplo? Acompanhe:

**A, B, E, G = 3 + 1 + 4 + 6 = 14 – 17 (dias do caminho crítico) = 3 dias.**

**A, C, E, G = 3 + 2 + 4 + 6 = 15 – 17 (dias do caminho crítico) = 2 dias.**

Com isso, conclui-se que nesses caminhos podemos atrasar tarefas em até três e dois dias que não haveria um atraso na finalização do projeto. Uma observação importante é que apenas atividades que não participam do caminho crítico possuem folga.

Em caso de emergências, quando o projeto está atrasado, o gerente de projetos pode usar duas técnicas para tentar entregá-lo em dia: a **compressão** (que é a diminuição do atraso do projeto pela inclusão de mais pessoas para fazer uma mesma atividade crítica em menos tempo) e o **paralelismo** (que é a execução de uma atividade do projeto ao mesmo tempo em que outra, mesmo que uma seja a sua predecessora). Ambas as técnicas aumentam o risco e comprometem os custos do projeto: a primeira, pelo fato de se ter de colocar mais pessoas fazendo a mesma coisa; e a segunda (ainda mais arriscada) porque aumenta a possibilidade de retrabalho.