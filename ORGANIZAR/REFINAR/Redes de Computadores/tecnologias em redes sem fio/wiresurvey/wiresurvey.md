### Objetivo:

Neste tópico vamos aprender a executar um projeto de instalação de uma rede wireless – LAN, na topologia BSS, descobrindo todos os aspectos necessários para o seu perfeito funcionamento. Vamos entender também todos os aspectos de um _**“wire survey”**_ que em realidade é o levantamento técnico das condições do local onde a rede deve ser implementada.

### Introdução

De uma forma bem simples, a definição de um “wire survey” consiste no processo da obtenção de informações físicas, elétricas e de irradiação para se determinar o número de equipamentos _**Access Point**_ a serem instalados e suas respectivas localizações. O objetivo deste levantamento é determinar que a rede vai alcançar toda a área de cobertura com um sinal relativamente adequado para o acesso de usuários fixos e móveis.

Quando um projetista de rede cabeada inicia seu trabalho, ele faz um levantamento conhecido como _**“site survey”,**_ o que em outras palavras é uma planta baixa que irá determinar todos os locais que serão atendidos pela rede, conhecido como _**work áreas.**_ Após este levantamento prévio, o projetista começa a desenhar todos os encaminhamentos, utilizando os materiais que a normativa EIA/TIA 569A determina e posterior a isso, a passagem dos cabos e a instalação dos TR _**(Telecommunications Room)**_ e a sala de ER _**(Equipament Room).**_

O grande diferencial numa rede wireless é que esta não utiliza cabos, portanto, as estações não estão presas ao local antes conhecido como área de trabalho (WA), então cabe ao projetista desta nova modalidade prover a melhor condição de sinal wireless a toda edificação do projeto.

A preocupação principal nesta modalidade está no fato de que as ondas eletromagnéticas emitida pelos APs viaja no espaço e não se comporta como um sinal elétrico confinado em um cabo. Durante a viagem pelo ar, ela sofre uma série de interferências, a começar pelo próprio local, as paredes, os objetos físicos e as pessoas que podem deteriorar de tal forma um frame wireless até que ele seja totalmente incompreensível pela estação receptora. Além disso, existem as interferências causadas por fornos de micro-ondas, telefones sem fio, brinquedos de rádio controle, motores elétricos e reatores, danificando ainda mais as informações que viajam pelo espaço.

Portanto, determinar as características físicas de uma rede wireless é um trabalho bastante criterioso, que deve ser realizado com o máximo de cuidado e, deve ser repetido periodicamente, com a finalidade de ajustar novamente as posições dos rádios, ou muitas vezes até instalar mais equipamentos, porque as condições físicas dentro de uma empresa estão sempre se alterando.

Para assegurar o perfeito funcionamento de todas as estações conectadas na rede wireless, uma pesquisa do comportamento da radiofrequência deve ser feita em toda a empresa, medindo o sinal que chega aos equipamentos e verificando a velocidade de conexão. Vamos ver como isso funciona?

### Classificação de Taxa de Sinalização x _Throughput_ em Mbps

A velocidade informada nos equipamentos de redes wireless sempre faz menção à taxa de transferência de informação sinalizada, porém, esta taxa de sinalização não é o _**throughput**_ real de transmissão.

Segundo Santos Junior (2005), o _**throughput**_ real diz respeito à capacidade de dados reais transmitidos e, esta diferença se dá por diversos fatores, como carregamento de bits para sincronização, encapsulamento, utilização do _**chip code**_ e até variações do meio físico encontradas no interior das empresas, portanto, a quantidade de bits transmitidos de informação real é muito menor que as taxas informadas pelos equipamentos de transmissão. Para produtos IEEE 802.11g onde há uma taxa de sinalização de 54Mbits, na realidade a taxa efetiva de dados transferida (_**throughput)**_ será de aproximadamente 28,2Mbits na melhor das condições de propagação do sinal. Quanto mais afastada está a estação do rádio AP, menor é sua taxa de transferência, portanto, no levantamento de _**wire survey**_ é necessário garantir uma boa taxa de transmissão em qualquer local da companhia, sem que este sinal exceda os limites físicos da mesma para que não comprometa ainda mais as questões de segurança. A tabela1 ilustra as diferenças entre taxa de sinalização e _**throughput**_ real para os padrões IEEE 802.11g e b.

**Tabela 1 – Sinalização x** _**Throughput**_

![[Untitled 77.png|Untitled 77.png]]

Um _**wire survey**_ completo é a chave para o sucesso de uma instalação. Cabe aos projetistas equacionar a melhor qualidade do sinal em todos os departamentos de uma empresa, visando a sobreposição dos fatores de degradação da rede e das interferências. Alguns fatores para o sucesso do projeto que devem ser seguidos são:

- Melhor desempenho – Conseguido através de testes por toda a empresa, levando em consideração o número de usuários que a rede deverá suportar e em qual área haverá maior concentração dos mesmos.
- Determinar o melhor local para a instalação dos APs – O _Access Point_ deve ser localizado no ponto a partir do qual se obtenha o melhor nível de sinal a todas as estações.
- Rede otimizada – Desenvolver uma rede que possa atender as diversas aplicações, como voz e dados para todas as estações, dentro da célula de abrangência das referidas áreas.
- Rede livre de interferências – Procurar minimizar os efeitos nocivos dos equipamentos que provocam deterioração da rede wireless como: fornos de micro ondas, equipamentos _Bluetooth_, câmeras wireless, telefones sem fio e outras redes wireless operando na mesma frequência (no mesmo canal).
- Distância – Quanto maior a distância entre o rádio e as estações, menor será a qualidade do sinal e consequentemente a diminuição da velocidade nominal de conexão. Lembre-se que a força do sinal de radiofrequência é inversamente proporcional ao quadrado da distância.
- Comportamento da radiofrequência nos obstáculos – Os objetos de um ambiente terão forte impacto no desempenho da rede em virtude dos fenômenos de difração, reflexão, refração e absorção do sinal de RF. Estes problemas podem ser minimizados pelo posicionamento dos Access Points, procurando sempre deixar livre a área entre o AP e a estação.
- Área de cobertura – Para o perfeito atendimento das estações dentro de uma área de cobertura de um AP, devemos considerar sempre numa escala de 100 posições, que o sinal recebido tenha de estar pelo menos a 80% desta escala, e também uma sobreposição entre as células de pelo menos 30% para suporte aos equipamentos móveis dentro do processo de roaming.

Para a execução de um projeto de rede wireless são necessários alguns passos. São eles:

- Obter junto à empresa uma planta baixa, contendo todas as localidades que deverão ser atendidas pela rede wireless. Caso não exista tal planta, o projetista deverá executar um rascunho que apresente todas as características físicas do local, como paredes e demais interferências. Este rascunho ou a planta devem estar numa escala métrica real.
- Levar para o _wire survey_ pelo menos dois Access Points devidamente equipados com cabos de extensão elétrica para o reposicionamento dos APs.
- Equipamento notebook com placas de rede wireless.
- Equipamento ou utilitário para determinar a taxa de transferência e a força e qualidade do sinal.
- Trena, lápis e fitas adesivas coloridas para marcação das posições.

De posse do ferramental acima, iniciaremos o _**wire survey**_, utilizando a própria ferramenta do Windows situada na sua placa de conexão wireless para mensurar a qualidade e a força do sinal transmitido pelo _**Access Point**_. Para habilitar a ferramenta do _**Windows**_ temos de entrar no _**status**_ de conexão de rede sem fio, conforme segue a sequência no sistema operacional Windows 7:

- Painel de controle

- Redes e Internet

- Central de Redes e Compartilhamento

Aplicar dois clicks em “Conexão de Redes sem Fio”, surgindo à tela:

- Status de Conexão de Rede Sem Fio

Após o surgimento da tela de status, devemos posicionar o primeiro _**Access Point**_ em um lugar alto, por exemplo, em cima de algum armário e de forma centralizada, observando sempre a planta. Devemos ligar o AP e conectarmos a ele com o notebook utilizado para o _**wire survey.**_

Deve-se agora. Já conectados ao AP, caminhar com o notebook afastando do mesmo e observando a tela de status da conexão wireless, percebendo assim a qualidade do sinal na escala e a velocidade. Devemos afastar no máximo onde a escala diminua um ponto e a velocidade caia para 48Mbps, conforme ilustrado na figura 1; nesta posição especifica, deve-se marcar o solo com a fita adesiva colorida. Este será o nosso limite de abrangência da célula do AP-1 e devemos circular em volta do AP-1 para perceber se é mantido os 80% na escala de qualidade do sinal e a mesma velocidade de 48Mbps.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295050/18651.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295050/18651.jpg)

Figura 1 - Status de sinal e potência.

Após esta confirmação, deve-se medir com a trena a distância, partindo do AP-1 até a devida marca feita com a fita adesiva. Subtrai-se 30% desta medida e novamente marca-se no chão com a fita. Imaginemos que foi medida uma distância de 60 metros até a primeira marca (com valores de 48Mbps), subtraindo os 30% (60 * 0,3 = 18), teremos uma distância de 42 metros onde colocaremos a segunda marca com fita adesiva.

Desta segunda marca, mediremos novamente uma distância de 60 metros e instalaremos o segundo _**Access Point**_. Teremos agora dois APs instalados (AP-1 e AP-2), onde, as células estarão interconectadas em aproximadamente 30%, permitindo assim o perfeito funcionamento num sistema de _**roaming.**_ A figura 2 ilustra o processo de _**wire survey**_.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295098/18652.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295098/18652.jpg)

Figura 2 - Medição de um Wire Survey

Neste levantamento, cada _**Access Point**_ terá uma área de cobertura de aproximadamente 60 metros de raio, o que é um excelente alcance e na pior condição, as estações mais afastadas terão uma conexão de 48Mbps com uma qualidade de sinal de 80%. Lembre-se que este alcance e velocidade devem ser conseguidos em toda a extensão da célula.

Se a edificação do projeto for maior onde dois APs não consigam alcançar todas as localidades, mais APs podem ser utilizados executando o mesmo procedimento. Um fator que não deve ser esquecido é colocar somente os canais que não sofrem interpolação, ou seja, os canais 1, 6 e 11 sucessivamente nesta sequência até alcançar todas as localidades da companhia.

### Revisão:

- O projeto de instalação de uma rede wireless é conhecido como wire survey.
- O wire survey consiste em demarcar numa planta, de forma aproximada, a abrangência de uma célula conseguida por um Access Point, levando em consideração todas as dificuldades do local.
- Cada célula deve sobrepor em 30% para que se consiga o roaming com equipamentos móveis.