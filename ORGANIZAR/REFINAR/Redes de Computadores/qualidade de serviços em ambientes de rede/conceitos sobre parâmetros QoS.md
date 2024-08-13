**Conceito geral**

Antes de tudo, vamos dar uma pequena definição do que realmente é uma QoS, em linhas gerais. Existe uma vasta literatura que define o que é uma QoS. Podemos dizer que uma QoS é um requisito das aplicações para a qual se exige que determinados parâmetros estejam dentro de limites bem definidos, considerando aí um valor mínimo e um valor máximo. Normalmente, uma QoS é garantida pela rede, seus componentes e equipamentos.

Em linhas gerais sobre um aspecto mais administrativo, podemos dizer que "qualidade" é entendida como bem-estar, adequação ao uso e satisfação. Um produto ou serviço de qualidade é aquele que atende perfeitamente, de forma confiável, de forma acessível, de forma segura e no tempo certo às necessidades do cliente.

Por exemplo, podemos analisar um determinado projeto da seguinte maneira:

1. ... que atende perfeitamente ... → Projeto perfeito
2. ... de forma confiável ... → Sem defeitos
3. ... de forma acessível ... → Baixo custo
4. ... de forma segura ... → Segurança do cliente
5. ... no tempo certo ... → Entrega no prazo certo, no local certo e na quantidade certa

**Atrasos**

Trata de um parâmetro importante na utilização de QoS. Em geral, um atraso em rede pode ser definido como a somatória de todos os atrasos impostos pela rede e equipamentos utilizados na comunicação. Em vista da aplicação, o atraso resulta em um tempo de resposta (tempo de entrega da informação, pacotes etc.) para a aplicação. Alguns dos principais fatores que geram um atraso na rede: atraso de propagação (Propagation Delay), velocidade de transmissão e tempo de processamento nos equipamentos.

Vale ainda salientar, que possivelmente você irá escutar dois termos que são referenciados em QoS: latência e atraso. Ambos têm o mesmo significado, mas convencionalmente "latência" é utilizado para atrasos em equipamentos e "atraso" está associado com transmissões de dados.

**Jitter (flutuação)**

Jitter é definido como uma variação de atraso de entrega de pacotes.

Para aplicações como a transmissão de áudio e vídeo, não importa muito se os pacotes demoram 20 ms ou 30 ms para serem entregues, desde que o tempo em trânsito seja constante. A variação (isto é, o desvio-padrão) nos tempos de chegada de pacotes é chamada Jitter. Por exemplo, uma flutuação elevada, na qual alguns pacotes demoram 20 ms e outros demoram 30 ms para chegar, resultará em uma qualidade irregular do som ou do filme. Em contraste, um acordo em que 99% dos pacotes fossem entregues com um retardo no intervalo de 24,5 ms a 25,5 ms poderia ser aceitável.

O valor escolhido deve levar em conta o tempo de trânsito na velocidade da luz e o retardo mínimo na passagem pelos roteadores, e talvez deixar uma pequena folga para alguns retardos inevitáveis.

Por exemplo, a faixa de frequência (Dial) de um rádio FM, em que encontramos diversas informações diferentes pelas estações, que estão localizadas em frequências diferentes (portadoras: 88,1, 89,1, 90,5, 96,1, 100,9, 101,7 MHz etc.), todas as estações chegam juntas ou estão disponíveis na antena do aparelho, mas o ouvinte escolhe apenas um canal que deseja ouvir.

No sistema de voz, para tornar realidade essa interconectividade, foi necessário o uso extensivo da multiplexação desses canais de voz. No primeiro nível de multiplexação FDM, 12 canais de voz são multiplexados, formando o chamado canal de grupo. Cinco canais de Grupo, por sua vez, são multiplexados em um canal de supergrupo, que contém 60 canais de voz. No terceiro nível, cinco canais de supergrupo são multiplexados em um canal de grupo mestre, que carrega 300 canais de voz, e, em seguida, o supergrupo mestre, com 900 canais (ITU-T).

**Perdas de pacotes**

De acordo com a definição dada por (ODOM, 2012), a perda de pacotes pode ser definida como um pacote, que se adentrou à rede e não foi entregue até seu fim, ou seja, se perdeu no trânsito dessa rede. Roteadores e switches podem ser as razões por esses bloqueios. Entretanto, ferramentas de QoS podem influenciar no comportamento dessa perda quando pacotes estiverem para ser perdidos em filas muito extensas. Quando a fila estiver cheia e outro pacote precisar ser endereçado, o descarte ocorrerá automaticamente pelos equipamentos da rede.

Em geral, roteadores perdem, bloqueiam ou descartam pacotes por várias razões, em que a maioria das ferramentas QoS ficam sem opção de ação a respeito. Entretanto, outras ferramentas de QoS podem ser utilizadas para minimizar o impacto desses pacotes perdidos.

Duas características sobre perdas de pacotes que valem a pena ressaltar:

- As perdas ocorrem por fatores como erros e congestionamentos.
- As perdas ocorrem por causa de erros ocorridos durante a transmissão.

Por isso, o que deve ser feito para minimizar essas perdas, do ponto de vista da QoS, é especificar e garantir limites razoáveis (taxas de perdas) que permitam uma operação adequada da aplicação.

**Filas**

As filas têm um papel importantíssimo quando se trata de uma qualidade de serviços em redes de computadores. O comprimento das filas (também conhecido como Buffer) atua diretamente na boa qualidade do serviço.

Podemos conceituar uma fila com um exemplo: quando um roteador possui, em sua entrada, mais dados (ou pacotes) do que ele é capaz de liberar, automaticamente precisa criar um processo para a liberação desses pacotes. Esse processo de liberação é o que pode ser definido como "fila". Fazendo uma analogia, uma fila que ocorre numa rede é como uma fila que ocorre em um caixa de supermercado, por exemplo. A vazão, ou seja, a quantidade de pessoas que precisa passar pelo caixa encontra a barreira de ter apenas um atendente, que irá proporcionar o atendimento de apenas uma pessoa por vez. Logo, se o tempo de passagem dessa pessoa pela fila foi inferior ao tempo que outras pessoas chegaram para passar nesse mesmo caixa, automaticamente se formará uma fila. É assim também que ocorre com os equipamentos (roteadores) que precisam liberar o trafégo dos pacotes de dados na rede.

É por isso que atualmente existem diversas ferramentas de QoS que tratam especificamente desse processo de gerenciamento de filas, como "fila do tipo tail (FIFO)", "fila do tipo SQF", "fila do tipo red", "fila do tipo WFQ", o qual será visto em uma oportunidade futura, nas próximas aulas.

**Tempos de transmissão e propagação**

Traduzindo de um dicionário puro, o termo "transmissão" pode ser entendido como:

Ação ou efeito de transmitir: transmissão de um direito. Comunicação do movimento de um órgão mecânico a outro por meio de engrenagens, polias, correias etc.; instrumento próprio para transmitir movimento. Corpo ou serviço encarregado da construção e manutenção dos meios de comunicação entre as forças armadas (telefone, rádio etc.).

((Fonte: Dicionário online de Português, 2013))

Já para o termo "propagação", diretamente pode ser definido como:

Ação ou efeito de propagar, de multiplicar por meio de reprodução: a propagação do gênero humano. Fig. Extensão, difusão, desenvolvimento: a propagação das idéias. Física. Modo de transmissão das ondas sonoras ou luminosas.

((Fonte: Dicionário online de Português, 2013))

Desse modo, em redes de computadores, podemos entender transmissão como a transmissão de sinais, sob a forma de ondas eletromagnéticas, sendo suportada em meios de transmissão, que podem ser:

- Guiados (par de cobre entrançado, cabo coaxial, fibra óptica)
- Não guiados (ar, vácuo)

Assim, transmissão é o meio físico e a propagação é como será o comportamento desses dados no meio físico disponibilizado, sempre tendo em mente que essa propagação está diretamente ligada ao tempo que vai levar para que um determinado dado (ou pacote) percorra um caminho específico até chegar ao seu destino.

Em um exemplo simples: numa transmissão por rádio a velocidade de propagação é próxima da velocidade da luz (300.000 Km/s). Usando cabos, as velocidades de propagação são inferiores. A fibra óptica monomodo permite atingir 70% da velocidade da luz, ou seja, cerca de 210.000 Km/s. A velocidade de propagação nos cabos de cobre situa-se entre 40% e 60% da velocidade da luz, ou seja, 120.000 Km/s a 180.000 Km/s.