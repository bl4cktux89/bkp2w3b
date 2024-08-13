### **Objetivos**

Neste tópico iremos descrever a implantação de um sistema de rádio enlace digital utilizando equipamentos wireless na frequência de 5GHz. Vamos descrever cada passo que deve ser realizado, bem como todos os cálculos necessários e suas conclusões. Este tópico poderá servir como modelo a qualquer outra implementação em qualquer outra frequência.

### **Introdução**

Para a implementação de um sistema de rádio enlace digital, algumas diretivas de projetos devem ser seguidas igualmente a um relação de _**check list,**_ onde o sucesso do projeto só poderá ser conseguido se todos os itens forem vencidos, passo a passo até o término da instalação e a colocação do sistema em produção.

A sequência de operação poderá ser levemente alterada desde que as premissas básicas sejam vencidas como a obtenção de linha de visada direta, possibilidade da instalação de torres para as antenas e alcance médio para o enlace. Nos tópicos a seguir serão discutidos todos os passos de forma objetiva a implantação de um sistema de rádio enlace com os critérios da boa engenharia.

### _**Wire Survey**_

O _**wire survey**_ é a realização da inspeção técnica nos locais onde serão instalados os equipamentos de rádio frequência da rede sem fio. Este levantamento tem a finalidade de dimensionar a área e identificar o local mais apropriado para a instalação do(s) AP(s), a quantidade de células e de pontos de acesso necessários para que as estações clientes tenham qualidade de sinal aceitável de recepção, acesso à rede e poder utilizar aplicações e recursos de modo compartilhado. Este levantamento deve ser realizado tanto nos ambientes internos (_**indoor**_) como nos ambientes externos (_**outdoor**_).

No caso de rádio enlace, o _**wire survey**_ abrange também o topo dos prédios onde se deseja instalar as antenas ou, um local apropriado para a instalação das torres, sistemas de energia elétrica para alimentação dos rádios que serão instalados nas torres próximas as antenas em caixa hermética adequada e, encaminhamento das torres até a empresa que receberá o sinal do sistema do rádio enlace.

### **Linha de Visada**

Este levantamento tem a intensão de verificar a área mais adequada para a instalação das antenas, observando a existência de uma visada direta entre os pontos de origem e de destino e, de obstáculos como por exemplo, prédios, árvores, morros, e etc.

Binóculos são equipamentos adequados para a realização da inspeção antes de definir as especificações finais do projeto. Deve-se verificar também a desobstrução da primeira zona de Fresnel seguindo todo o trajeto que o sinal fará de uma antena para a outra e observando neste trajeto a existência de prédios, morros, arvores ou qualquer outro obstáculo. Caso sejam verificado obstáculos nesta trajetória, deverão ser anotadas as alturas de todos eles para que entrem nos cálculos de desobstrução. Para tanto, deve-se traçar o perfil do enlace e, se necessário a compensação devido a curvatura da Terra em aumentar a altura das torres de sustentação das antenas a fim de vencer esta condição. A figura 1 ilustra este perfil a ser mensurado. (SANTOS, 2010)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/8/302822/19285.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/8/302822/19285.jpg)

Obstrução na linha de Visada

### _**Check list**_ **operacional para um projeto de rádio enlace**

A partir deste momento será enumerada uma lista de passos necessários para a estruturação de um projeto de rádio enlace de forma coerente e com critérios de boa engenharia. Cada tarefa executada da relação capacita a sua continuidade num processo com início, meio e fim, portanto, não é recomendado ao projetista que pule uma tarefa da relação sem ter resolvido a questão com total segurança dando suporte a próxima tarefa relacionada.

Pode-se dividir em quatorze etapas um projeto de rádio enlace lembrando que cada etapa deve ser executada para dar prosseguimento a continuidade do projeto, portanto, etapa alguma poderá ser suprimida. As etapas estão divididas da seguinte forma:

1. Definição das localidades onde será instalado o sistema de rádio enlace;
2. Realização de um _wire survey_ para definição e levantamento da linha de visada, verificação da altura existente ou da necessidade de torres;
3. Verificação na linha de visada e possíveis interferências, caso elas existindo, levantar suas alturas;
4. Mensurar a distância entre as antenas;
5. Calcular a 1ª zona de Fresnel entre as antenas;
6. Verificar na trajetória da linha de visada à obstrução da 1ª zona de Fresnel para K = 1 e K = 0,7;
7. Mensurar os equipamentos que serão utilizados (rádios, antenas e componentes da linha de transmissão);
8. Calcular a potência efetiva EIRP do sistema envolvendo os equipamentos escolhidos;
9. Calcular a atenuação em espaço livre do trajeto entre as antenas;
10. Calcular a Perda por precipitação pluviométrica no trajeto entre antenas;
11. Calcular a sensibilidade dos receptores por comparação às especificações técnicas;
12. Executar resumo de todos os cálculos para verificação do pleno funcionamento do sistema e demais margens de segurança;
13. Colocar o sistema em produção por testes de exaustão.
14. Entrega do sistema ao cliente.

Para a execução deste projeto utilizaremos o _**software**_ da Google Earth distribuído gratuitamente por download em: [**https://www.google.com.br/earth/download/ge/agree.html**](https://www.google.com.br/earth/download/ge/agree.html)

### **PROJETO DE RÁDIO ENLACE**

Definição das localidades

Esta definição é determinada pelo cliente que contrata os serviços de projeto, portanto, cada cliente é um caso específico e jamais se podem comparar projetos, pois em realidade, não existe dois projetos iguais em sistema de Rádio Enlace. Para colocar em prática o teórico exposto será desenvolvido um projeto de interligação entre três pontos via enlace de rádio do cliente Sr. X em São Paulo – Capital. As informações das localidades contempladas são:

![[Untitled 72.png|Untitled 72.png]]

![[Untitled 1 43.png|Untitled 1 43.png]]

![[Untitled 2 34.png|Untitled 2 34.png]]

As figuras 2 e 3 ilustra a topologia empregada no projeto bem como seu posicionamento em mapa topográfico e as distâncias entre as antenas:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/8/302882/19291.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/8/302882/19291.jpg)

Esquema dos enlaces propostos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/3/2/303285/19292.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/3/2/303285/19292.jpg)

Figura 3 - Localidades do Sr. X pelo Google Earth

### **Realização do** _**Wire Survey**_

Para a realização de um wire survey confiável é necessário a visitação ao local com equipamentos e acessórios pertinentes como bússola, GPS, altímetro ou barómetro e binóculos para o levantamento das altitudes em cada localidade e a definição de algum tipo de interferência na rota dos links. Para tanto, o projetista deve percorrer todo o trajeto ou aquele que for possível verificando prédios, arvores e reservatórios de água por onde seu link passará, registrando todas estas informações para alimentação das informações referente ao projeto.

Todo detalhe deve ser anotado e meticulosamente estudado a fim de se conseguir alternativas técnicas para o projeto e seu pleno funcionamento. No referido cliente X, a visitação mostrou que a localidade não apresenta nenhum prédio de maiores proporções entre as rotas, todas as edificações são em geral térreas ou no máximo com um andar e pequenos comércios de pavimento único.

O declive do solo é pequeno sendo de seis metros da loja 1 – ponto A para a _**loja 2 ponto B**_ e de cinco metros da loja 2 ponto B a loja 3 conto C. As distâncias são curtas para um sistema de rádio enlace, sendo de 2.360 metros do ponto A ao ponto B e de 849 metros do ponto C ao ponto B. De posse destas informações o próximo passo são os cálculos de 1ª zona de Fresnel a fim de decidir a altura das antenas.

### **Cálculos da 1ª zona de Fresnel – Rota 1 – Prédio 1 ao Prédio 2**

Esta rota possui 2.360 metros de comprimento e com declive de 6 metros e será utilizado o canal 36 em 5,180 GHz. Considerando o ponto mais crítico da elipsoide de Fresnel em 1.180 metros porque é justamente a metade dela onde teremos o maior raio de r0:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299567/19297.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299567/19297.jpg)

Cálculo Rota 1

Portanto o raio r0 da 1ª zona de Fresnel da ROTA 1 é = 5,83 metros.

### **Cálculos da 1ª zona de Fresnel – Rota 2 – Prédio 2 ao Prédio 3**

Esta rota possui 849 metros de comprimento e com declive de 5 metros e será utilizado o canal 36 em 5,180 GHz.

Considerando o ponto mais crítico da elipsoide de Fresnel em 424,5 metros porque é justamente a metade dela onde teremos o maior raio de r0:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299568/19298.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299568/19298.jpg)

Cálculo da Rota 2

Portanto o raio r0 da 1ª zona de Fresnel da ROTA 2 é = 3,49 metros.

Todos os prédios do cliente Sr. X são de dois pavimentos estando seu telhado (laje pré-moldada) a uma distância de oito metros do chão acabado, portanto, foi decidida a instalação de torres estaiada de nove metros de comprimento devidamente fixadas em laje, remontando um total de dezessete metros de altura até o cume da torre. Com esta altura linear em todos os prédios obtém-se mais de 100% de área livre na 1ª zona de Fresnel na pior condição do _**link**_ que foi de 5,83 metros de raio do centro do feixe de onda. A figura 3 e 4 ilustram as torres utilizadas no projeto.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318081/19300.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318081/19300.png)

Figura 3 - Torre no prédio Matriz

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318082/19301.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318082/19301.png)

Figura 4 - Torre loja 2

### **Cálculo da Perda no Espaço Livre – Rota 1**

A perda no espaço livre é a atenuação que a onda eletromagnética sofre quando viaja pela atmosfera. Esta perda deve ser calcula a fim da verificação das condições de potência irradiada pelo sistema e se esta potência irradiada é suficiente para sensibilizar os equipamentos e fornecer uma boa performance no enlace. A perda em espaço livre pode ser calcula pela formula:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299570/19303.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299570/19303.jpg)

Formula de Loss - Perda no espaço

Onde:

d = distancia total entre as antenas;

f = frequência de operação do sistema;

92,44 = constante de difração atmosférica.

Utilizando os valores temos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299571/19304.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299571/19304.jpg)

Perda na Rota 1

Temos então o valor de 114,18dB de perda na Rota 1.

### **Cálculo da Perda no Espaço Livre – Rota 2**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299572/19306.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299572/19306.jpg)

Cálculo de perda para Rota 2

Temos então o valor de 105,30dB de perda na Rota 2.

### **Cálculos de Perda por Precipitação Pluviométrica**

O método utilizado para o cálculo se baseia nas recomendações ITU-T 837, 838 e 721,3, onde se define a atenuação especifica (Yr) para uma determinada frequência, sendo dependente da polarização da onda e da taxa de precipitação pluviométrica excedida em mais que 0,01% do tempo do pior mês do ano. A equação que exprime este cálculo é:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/4/297468/19308.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/4/297468/19308.jpg)

Formula de Precipitação Pluviométrica

Onde K o coeficiente de regressão calculado para as gotículas de chuva que é dependente da frequência e da polarização e R é a intensidade de precipitação pluviométrica (mm/hora) excedida em mais de 0,01% do tempo. Na tabela 3 foi escolhida a coluna N por representar São Paulo no mapa). A tabela 1 indica os valores de K e na tabela 2 o mapa para obtenção do valor de R respectivamente. (ITU-R P.838-2), (ITU-R P.837-1)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/2/302245/19311.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/2/302245/19311.png)

Tabela 1 - Valores de K e ∝

Fonte: (ITU-R P.838-2)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318083/19312.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318083/19312.png)

Tabela 2 - Obtenção do valor de R

Fonte: (ITU-R P.837-1)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/2/302256/19314.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/2/302256/19314.png)

Tabela 3 - Valores de R

Fonte: (ITU-R PN.837-1)

**Calculo de** _**Y**__**rh**_ **e** _**Y**__**rv:**_

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/4/297469/19317.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/4/297469/19317.jpg)

Calculo de Yrh e Yrv:

Do prédio 1 ponto A para prédio 2 ponto B – Rota 1 = (comprimento do enlace 2,360km):

- Perda total polarização Horizontal devido à precipitação pluviométrica: 0,717 dB
- Perda total polarização Vertical devido à precipitação pluviométrica: 0,500 dB

Do prédio 2 ponto B para prédio 3 ponto C – Rota 2 = (comprimento do enlace 0,849km):

- Perda total polarização Horizontal devido à precipitação pluviométrica: 0,258 dB
- Perda total polarização Vertical devido à precipitação pluviométrica: 0,179 dB

### **EQUIPAMENTOS E ANTENAS**

### **Rádio**

O Rádio escolhido foi o modelo OBT-58108 do fabricante Orbital que representa a mais avançada tecnologia em comunicação de dados via rádio para aplicações ponto a ponto. O equipamento utiliza a modulação OFDM, onde consegue combinar dois canais de transmissão para entregar uma taxa de transmissão de até 108Mbps, capacidade antes disponível apenas em equipamentos ópticos ou rádios de altíssimo custo. O equipamento apresenta antena integrada e alimentação através do cabo Ethernet, facilitando sua instalação. Todo o gerenciamento é feito através de um servidor web embutido ou através do protocolo SNMP. Devido à sua alta potência de saída o OBT-58108 permite instalar links de mais de 50 quilômetros (variando em função das condições locais).

Especificações do equipamento

![[Untitled 3 22.png|Untitled 3 22.png]]

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/6/5/316555/19319.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/6/5/316555/19319.jpg)

Rádio Orbital - OBT-58108

Fonte: www.orbital.com.br

### **Antena**

Antena parabólica fabricada pela Cisco de altíssimo ganho (28dBi) operando na frequência de 5,8 GHz, especialmente desenhada para sistema de rádio enlace wireless.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/6/7/316734/19320.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/6/7/316734/19320.jpg)

Antena Direcional Cisco - AIR-ANT58G28SDA-N

Fonte: www.cisco.com

**Especificações da Antena**

![[Untitled 4 19.png|Untitled 4 19.png]]

### **Cálculo da Sensibilidade do Sistema**

Para os cálculos da sensibilidade efetiva que um sistema de rádio enlace pode alcançar em primeiro lugar necessita-se da composição dos valores irradiados pelas antenas que fazem este link. Isso significa dizer que a potência EIRP sendo irradiada por cada antena do referido link será somada constituindo o valor real EIRP do enlace e, de posse deste valor executa-se a subtração do valor da atenuação de _**Loss**_ (perda no espaço livre) mais a atenuação pela perda por Precipitação Pluviométrica. A resultante deste cálculo será a sensibilidade requerida pelo sistema e comparam-se as características do rádio receptor a fim de verificar se o equipamento possui a requerida sensibilidade necessária para comunicação entre as antenas do rádio enlace. Portanto, antes dos cálculos de sensibilidade se faz necessário o cálculo da potência efetiva real irradiada EIRP por todas as antenas que compõem o link. O sistema projetado para o cliente Sr. X tem os seguintes valores conforme ilustrado na figura a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318080/19323.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/8/0/318080/19323.png)

Valores dos componentes do projeto de Rádio Enlace

### **Executando os cálculos Rota 1**

Inicialmente vamos calcular uma instalação e como todos os rádios e antenas utilizadas no sistema são iguais, os resultados também satisfazem as demais localidades.

Basicamente temos a soma dos produtos divididos em duas classes, a primeira classe é chamada de equipamentos _**“up”,**_ ou seja, equipamentos geradores de sinal e são eles: os rádios e as antenas.

O segundo grupo são os produtos denominados _**“down”**_ que são usados na linha de transmissão e causam atenuação ao sinal elétrico, neste grupo temos os cabos, conectores, atenuadores, supressores de descarga atmosférica.

### **Calculando os equipamentos** _**up**_ **de uma localidade:**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/4/297470/19325.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/4/297470/19325.png)

Cálculos de UP e DOWN da rota 1

### **Calculando os produtos** _**down**_ **da mesma localidade**

Subtraindo _**Pup**_ de _**Pdown**_ temos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/4/297471/19326.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/4/297471/19326.png)

Sensibilidade da Rota 1

**Nota:** Como a loja 1 esta apontada para a loja 2 formando um link e na loja 2 foi instalado os mesmos equipamentos e produtos podemos repetir o valor de EIRP para loja 2 em 43,28 dBm.

Para determinar o EIRP total deste enlace somam-se os dois EIRP parciais de cada loja conforme demonstrado na equação abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299574/19327.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299574/19327.png)

EIRP total - rota 1

Portanto, temos calculado o EIRP total da Rota 1 que é a soma dos EIRP parciais de cada localidade ficando seu valor em 86,56dBm.

Para verificar a sensibilidade do sistema instalado na Rota 1 deve-se somar as atenuações de Perda no Espaço Livre mais a Perda por Precipitação Pluviométrica e subtrair do valor de EIRP total da Rota 1 conforme demonstrado nos cálculos seguintes:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299575/19298.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299575/19298.jpg)

Atenuação da Rota 1

**Nota:** Foi utilizado o valor de 0,717dB para Perda por Precipitação Pluviométrica na polarização horizontal por ser o pior valor calculado.

Com o valor da atenuação no espaço calculada, pode-se determinar agora o valor da sensibilidade necessária que o enlace precisa ter para “escutar” sua antena par.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299576/19329.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299576/19329.png)

Cálculo da sensibilidade da Rota 1

Pelos cálculos chega-se a sensibilidade necessária para que o equipamento possa funcionar de -28,33, porém, como medida de precaução elevamos em mais 10dB este valor passando agora para uma necessidade de sensibilidade de -38,33dB. Ao defrontarmos com as especificações do rádio utilizado no projeto, verifica-se que sua sensibilidade para uma taxa de sinalização de 108 Mbps é de -73dBm o que satisfaz perfeitamente o projeto com uma segurança de -34,67dBm de sobra até o limite da perda de comunicação.

### **Cálculo Sensibilidade Rota 2**

Para estes cálculos pode-se considerar o mesmo valor de EIRP da rota um para a rota dois, pois, temos os mesmos equipamentos instalados. Portanto, é suficiente apenas a soma dos valores de Perda no Espaço Livre da Rota 2 mais os valores de Perda por Precipitação Pluviométrica da Rota 2.

Novamente o valor a ser considerado em Perda por Precipitação Pluviométrica será o pior valor de 0,258dB conseguido na polarização horizontal.

### **Segue os cálculos:**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299577/19330.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299577/19330.png)

Atenuação da Rota 2

A atenuação total cálculada da rota 2 é de: 105,55dB.

Com o valor da atenuação no espaço calculada para a Rota 2, pode-se determinar agora o valor da sensibilidade necessária que o enlace precisa ter para “escutar” sua antena par.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299578/19331.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299578/19331.png)

Cálculo da sensibilidade da Rota 2

O cálculo apresentado nota-se que a sensibilidade necessária para o enlace é de -18,99dB, porém, como medida de segurança elevamos em mais 10dB este valor passando agora para -28,99dB de sensibilidade. Ao defrontarmos com as especificações do rádio utilizado no projeto, verifica-se que sua sensibilidade para uma taxa de sinalização de 108 Mbps é de – 73dBm o que satisfaz plenamente o projeto com uma segurança de -44,01dBm de sobra até o limite da perda de comunicação.

### **Alinhamento das antenas**

Após a realização da montagem das antenas, devemos alinhá-las para a perfeita comunicação de dados. O alinhamento da antena reduz perdas de pacotes e maximiza a força do sinal.

A figura a seguir mostra a relação trigonométrica do projeto a fim de encontrar o ângulo correto de alinhamento das antenas em diferentes alturas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/6/2/306259/19332.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/6/2/306259/19332.png)

Alinhamento das antenas.

Um _**Global Position System**_ – GPS é uma ferramenta muito útil para determinar as distâncias entre os pontos e um barômetro fornece com bastante precisão a altura dos pontos. Também se podem usar ferramentas eletrônicas como o _**Google Earth**_ que fornece tanto a distância como a altura dos terrenos envolvidos em qualquer projeto.

Todo o projeto do cliente Senhor X foi utilizado o _**Google Earth**_ como ferramenta principal a esta construção.

A diferença de altitude do solo entre loja 1 e loja 2 é de 6 metros e as antenas mais o prédio tem a mesma altura respectivamente de 9 metros para a torre das antenas e 8 metros do prédio de altura.

### **Os cálculos:**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299579/19333.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299579/19333.png)

Cálculo entre prédio 1 e prédio 2

Como a diferença entre prédio 1 e prédio 2 é de 6 metros (794 - 788) podemos considerar que a altura do prédio 1 é igual a 23 metros em relação à altura do prédio 2, portanto,

será igual a 6 metros, pois, as antenas tem a mesma altura.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299580/19335.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299580/19335.png)

Alinhamento Rota 1

### **Cálculo de alinhamento das Antenas para Rota 2**

A diferença de altitude do solo entre loja 2 e loja 3 é de 5 metros e as antenas mais o prédio tem a mesma altura respectivamente de 9 metros para a torre das antenas e 8 metros do prédio de altura.

### **Os cálculos:**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299581/19337.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299581/19337.png)

Ângulos na Rota 2

Sendo que

Como a diferença entre prédio 2 e prédio 3 é de 5 metros (788 - 783) podemos considerar que a altura do prédio 2 é igual a 22 metros em relação à altura do prédio 3, portanto,

será igual a 5 metros, pois, as antenas tem a mesma altura.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299582/19339.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299582/19339.png)

Alinhamento Rota 2

Com os valores já calculados, basta ajustarmos cada antena em seu vetor adequado que teremos uma boa aproximação do apontamento das antenas. Para o ajuste fino deste apontamento, basta utilizar o software respectivo de potência que é encontrado em qualquer sistema de rádio enlace e, conseguir o máximo de ganho com um ajuste fino e delicado nos vetores da antena.

Feito isso, deve-se utilizar uma trava química nos parafusos de fixação (eu normalmente utilizo cola super bond....). Também é aconselhável passar uma boa porção de graça nos parafusos, porcas e demais componentes que ficam em exposição ao tempo.

Com isso é finalizado a instalação física do sistema, bastando agora habilitar os rádio com alimentação elétrica e começar os testes de conectividade. A figura a seguir ilustra a utilização do Google Earth nas vistas horizontal como vertical, bem como a possibilidade da análise do relevo e do solo considerando a altitude entre as localidades da empresa do cliente Sr. X.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/3/2/303293/19340.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/3/2/303293/19340.jpg)

Visão aérea dos links