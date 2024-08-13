### **Meios físicos de comunicação**

Os meios de comunicações constituem um dos elementos fundamentais para qualquer sistema de comunicação. Os meios mais comuns utilizados em comunicação de dados são o cabo coaxial, o cabo par-trançado, a fibra óptica e o sem fio. A aplicação desses meios de comunicação depende de várias características, dentre elas, do local, da largura de banda requerida, do alcance, etc. Tais características serão discutidas a seguir, levando em consideração as propriedades físicas, mecânicas, elétricas e ópticas dos meios de comunicação.

### Cabo Coaxial

**Constituição do cabo coaxial**

O cabo coaxial é assim chamado devido a formação de camadas de isolantes e condutores em formato concêntrico em volta de um eixo (axis). O principal conector utilizado para cabos coaxiais, conhecidos como BNC (Bayonet Neill-Concelman), Figura 1. Os elementos de construtivos desse cabo são mostrados na Figura 2 e descritos abaixo:

(1) Núcleo condutor de cobre;

(2) Isolador dielétrico interno

(3) Blindagem eletromagnética;

(4) Revestimento de plástico.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/4/345461/26694.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/4/345461/26694.jpg)

Figura 1 - Conector BNC de 50 ohms para cabo coaxial.

Fonte: https://upload.wikimedia.org/wikipedia/commons/thumb/b/b9/BNC_connector_50_ohm_male.jpg/800px-BNC_connector_50_ohm_male.jpg

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/6/267698/12791.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/6/267698/12791.jpg)

Figura 2 - Elementos de um cabo coaxial

**Aplicação**

No passado, os cabos coaxiais foram extensivamente utilizados em redes locais do tipo 10BASE-2, utilizando cabo coaxial fino (Thinnet, de 50 ohms), mais flexível e com alcance de até 185 m. Outro cabo coaxial, chamado de Thicknet (grosso, de 75 ohms), é menos flexível e são empregados em redes do tipo 10BASE-5, com alcance de até 500 m, de integração com rede de serviço de dados, voz e imagem. Atualmente, são empregados principalmente em sistemas de TVs por assinatura e banda larga, além de circuitos fechados de TV (CFTV). A sua restrição para tais aplicações é devida, principalmente, ao maior alcance em relação aos cabos par-trançados e maior imunidade a interferências externas. Entretanto, os cabos coaxiais apresentam as seguintes desvantagens em relação aos demais meios de comunicação:

Dificuldade de montagem;

Distância limitada a 500 m;

Baixo índice de segurança;

Dificuldade em fazer alteração na topologia da rede.

### Fibras ópticas

As fibras ópticas são meios de transmissão guiado por um dielétrico, feito de vidro ou polímero. O seu funcionamento se baseia no fenômeno de reflexão interna total que ocorre no núcleo da fibra, que explicado a partir da Figura 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/6/347640/26695.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/6/347640/26695.png)

Reflexão internal total.

Fonte:

Para que haja a reflexão interna total é necessário que exista uma condição que permita que a luz que adentra a fibra encontre uma interface núcleo/casca com índices de refração do núcleo maior do que o da casca (n1 > n2). O ângulo de incidência (ângulo entre a normal e a interface de entrada - ) também influência na reflexão interna total, já que, dependendo do ângulo de incidência, a luz pode propagar para fora da fibra óptica (raio refratado), não ocorrendo assim, o guiamento óptico. Existe um ângulo crítico que permite o guiamento entre a interface da fibra óptica e a casca (clading), entretanto, essa situação não é a ideal, pois provoca muita perda de potência óptica para fora da fibra. O ideal é que ocorra o processo de reflexão interna total (WIRTH, Almir, 2002).

Outra importante característica das fibras ópticas está associada com a fonte emissora de luz. Por convenção, tudo o que é luz corresponde ao espectro eletromagnético que vai do violeta (λ= ~ 400 nm) ao vermelho (λ= ~ 750 nm), abaixo de 400 nm encontra-se o ultravioleta e acima do 750 nm encontra-se o infravermelho. A radiação utilizada para iluminar a fibra óptica está situado em algumas regiões do espectro eletromagnético, que chamamos de janelas de telecomunicações. Na Figura 4 são mostradas essas janelas de telecomunicações.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/6/347696/26696.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/6/347696/26696.png)

Janelas de telecomunicações ópticas.

Fonte:

Salvo as fibras ópticas do tipo poliméricas, utilizamos as janelas de telecomunicações da tabela x para transmissão de dados em fibras ópticas. Isso se deve a menor atenuação em fibras ópticas de silício nessas regiões, conforme mostrado na Tabela 1.

Tabela 1 - Atenuação para as diferentes janelas de telecomunicações.

|Janela de transmissão|Comprimento de onda (nm)|Atenuação (dB/Km)|
|---|---|---|
|[[Primeira]]|~850|3,0|
|[[Segunda]]|~1310|0,5|
|[[Terceira]]|~1530|0,2|

  
  

Fonte: Wirth, Almir, 2002.

Normalmente, utilizamos LED para transmissão na primeira janela de telecomunicações e LASER na segunda e terceira. Uma outra opção de fonte que podemos utilizar na segunda janela é o VCCEL, um tipo de laser de baixo custo.

**Classificação das fibras ópticas**

As fibras ópticas podem ser classificadas de acordo com suas características construtivas, tais como, diâmetro e perfil de índice de refração do núcleo, conforme mostrado na Figura 5 e explicado abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/7/347782/26697.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/7/7/347782/26697.png)

Diferentes tipos de fibras ópticas.

Fonte:

- **Fibra multimodo de índice degrau (FMD):** As fibras do tipo FMD são as fibras com maior espessura de núcleo, de aproximadamente 72,5 um, e o núcleo possui um único índice de refração, por isso o perfil de índice é um degrau, conforme mostrado na Figura x (a). Normalmente, as FMD são utilizadas em curtas distância, de no máximo 2 Km, em virtude um fenômeno conhecido como dispersão, que provoca o alargamento do sinal conforme a luz se propaga ao longo do núcleo da fibra. Como pode ser observado na Figura 5, os modos percorrem diferentes caminhos ao longo do núcleo da fibra óptico, fazendo com que alguns modos cheguem mais rápido do que outros no receptor. 
- **Fibra multimodo de índice gradual (FMG):** Diferentemente das FMDs, as FMG possuem uma variação no perfil de índice de refração do núcleo, maior no eixo do núcleo e caindo gradativamente em direção a casca, conforme mostrado na Figura x(b). Isso é feito para reduzir o problema de dispersão presente nas do tipo FMD, fazendo com que os modos guiados cheguem praticamente ao mesmo tempo. Além disso, o diâmetro do núcleo é reduzido para 50um. Tais melhorias proporcionam um alcance melhor para esse tipo de fibra óptica, chegando, em alguns casos, a 10 km.
- **Fibra monomodo (FM):** As fibras ópticas monomodo (FM) conseguem acoplar apenas um modo, por isso são chamadas de monomodo. Para que ocorra esse fenômeno é necessário reduzir o diâmetro do núcleo (~ 10 um) e utilizar longos comprimentos de onda (normalmente 1310 e 1530 nm), dessa forma, o fenômeno de dispersão do sinal desaparece e o alcance dessas fibras pode chegar a facilmente a 50 Km.

**Conectores**

Existe uma gama enorme de conectores de fibra. A sua utilização depende do tipo de polimento, encaixe e quantidade de fibra por conector. Os mais comuns são mostrados na Figura 6.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/9/345921/26698.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/9/345921/26698.jpg)

Figura 7 - Diferentes tipos de conectores para fibras ópticas.

Fonte:

### **Cabo Par-trançado**

O cabo par-trançado é formado por 4 pares de fios entrelaçado aos pares e classificados em: Cabo par-trançado não blindado (UTP - Unshielded Twisted Pair) e cabo par-trançado blindado. Entretanto, o cabo par-trançado blindado pode ser classificado em:

- FTP (Foiled Twisted Pair): Utiliza blindagem mais simples, possuindo apenas uma blindagem de folha de alumínio ou aço envolvendo todos os pares, com a finalidade de impedir apenas a interferência externa.
- STP (Shielded Twisted Pair): Neste caso, a blindagem é um pouco mais robusta do que o FTP, envolvendo cada par individualmente, reduzido dessa forma, a interferência entre os pares.
- SSTP (Screened Shielded Twisted Pair): Possui a blindagem mais robusta entre os blindados, construído com uma blindagem envolvendo cada par e outra blindagem externa envolvendo todos os cabos, adequado para ambientes com forte interferência eletromagnética.

O cabo par-trançado (Twister pair) é o mais utilizado atualmente em virtude do seu baixo custo relativo e facilidade de instalação e manutenção. O Cabo par-trançado é fabricado unindo dois fios de cobre trançados entre si com o objetivo de reduzir a interferência entre pares (Diafonia) e a interferência eletromagnética externa por meio do efeito de cancelamento. Aliado ao cancelamento de pares, uma outra técnica é adotada pela placa de rede para reduzir ainda mais a interferência, essa técnica é conhecida como balanceamento de pares, e consiste em polarizar os fios de um mesmo par com polaridades diferentes, como mostrado na Figura 7.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/9/345932/26699.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/9/345932/26699.png)

Figura 7 - Processo de balanceamento de um cabo par trançado.

Fonte: http://e.cdn-hardware.com.br/static/books/redes/cap1-8_html_7bd5ad9e.png

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/8/260846/14970.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/8/260846/14970.jpg)

Figura 8 - Constituição do cabo par-trançado

**Categorias de cabos par-trançado**

As categorias de cabos par-trançados são mostradas na Tabela 2. Em todas as categorias, o comprimento máximo é de 100 m, com exceção do cabo categoria 6, com alcance máximo de 55 m. Como pode ser observado na tabela, o que diferencia um cabo de outro é sua frequência de operação e, consequentemente, a máxima taxa de transferência de dados.

Tabela 2 - Categoria de cabo par trançado e suas características.

|Nome|Padrão|Largura de banda(em MHz)|Principais Aplicações|Observações|
|---|---|---|---|---|
|[[Cat.1]]||0,4|Telefonia e linhas de modem|Obsoleto|
|[[Cat.2]]||4|Sistemas legados, IBM 3270|Obsoleto.|
|[[Cat.3]]|UTP|16|10BASE-T e 100BASE-T4 Ethernet|Descrito na EIA/TIA-568. Não recomendado para taxas maiores que 16 Mbit/s. Cabos de telefonia.|
|[[Cat.4]]|UTP|20|16 Mbit/s Token Ring|Obsoleto.|
|[[Cat.5]]|UTP|100|100BASE-TX & 1000BASE-T Ethernet|Muito usados nas redes LAN|
|[[Cat.5e]]|UTP|125|100BASE-TX & 1000BASE-T Ethernet|Melhoria da Cat5.|
|[[Cat.6]]|UTP|250|10GBASE-T Ethernet||
|[[Cat.6a]]||500|10GBASE-T Ethernet|Adiciona blindagem. ISO/IEC 11801:2002.|
|[[Cat.7]]||600|Telefonia, CCTV, 1000BASE-TX no mesmo cabo.10GBASE-T Ethernet.|Cabo blindado. ISO/IEC 11801 2nd Ed.|
|[[Cat.7a]]||1000|Telefonia, CATV, 1000BASE-TX no mesmo cabo.10GBASE-T Ethernet.|Usa os 4 pares. ISO/IEC 11801 2nd Ed. Am. 2.|
|[[Cat.8.1]]||1600-2000|Telefonia, CATV, 1000BASE-TX no mesmo cabo.40GBASE-T Ethernet.|Em desenvolvimento.|
|[[Cat.8.2]]||1600-2000|Telefonia, CATV, 1000BASE-TX no mesmo cabo.40GBASE-T Ethernet.|Em desenvolvimento.|

  
  

Fonte: Marin, Paulo Sergio - 2013.

**Conectores para cabo par-trançado**

Os cabos par-trançado utilizam os conectores RJ-45 blindado e não blindado, dependo da aplicação. Também há possibilidade de se utilizar o conector TERA, desenvolvido pela empresa SIEMON, para categorias superiores a 6a.

A crimpagem dos cabos no conector deve seguir a ordem especificada pela norma TIA/EIA-568-B. Essa norma especifica dois tipos de montagem, a 568-A e a 568-B. As duas montagens apresentam as mesmas características em termos de desempenho e podem ser executadas de acordo com a ordem apresentada na tabela abaixo.

Dependendo do equipamento no qual os cabos devem ser conectados, é necessário confecciona-los de maneira diferente, como mostrado abaixo:

- Cabo direto: Normalmente utilizado para conectar dispositivos diferentes como, por exemplo, switch-computador. Nesse caso, ambas as extremidades devem ser crimpadas ou com 568-A ou com 568-B.
- Cabo cruzado (crossover): caso s dispositivos sejam semelhantes, por exemplo, PC-PC, deve-se crimpar as pontas de forma diferente, uma ponta 568-A, e a outra, 568-B. Entretanto, atualmente, existem placas de rede que detectam automaticamente como o cabo foi crimpado, permitindo utilizar tanto cruzado, como direto.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/4/345465/26700.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/4/345465/26700.jpg)

Figura 9 - Conector RJ-45 para cabos par trançado

Fonte: https://pt.wikipedia.org/wiki/Cabo_de_par_tran%C3%A7ado#/media/File:Rj-45_uncripped.jpg

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/9/345935/26702.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/5/9/345935/26702.jpg)