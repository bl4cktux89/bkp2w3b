**Definição**

Analisadores de tráfego são programas de computadores (também chamados de utilitários ou ferramentas) que auxiliam administradores de rede a capturar e, interativamente, analisar os pacotes de dados que estão trafegando em uma rede de computadores.

**Aplicação**

Em geral, esse tipo de análise é realizada a fim de detectar alguma anomalia na rede como, por exemplo, para identificar o motivo de um _**smartphone**_ ou _**laptop**_ não conseguir acessar a internet. A ação de analisar os pacotes na identificação de uma solução a uma anomalia na rede é frequentemente associada ao termo, em inglês, _**troubleshooting**_ (KUROSE; ROSS, 2014).

Outro aspecto muito importante é que esses programas auxiliam, e muito, na compreensão de conceitos diversos em disciplinas relacionadas a redes de computadores e, portanto, é fortemente recomendado aos alunos que utilizem tais ferramentas para um melhor aproveitamento da disciplina.

Além disso, como tais ferramentas são muito utilizadas no dia a dia de diversos profissionais da área de infraestrutura, como analistas, engenheiros e administradores de redes, se familiarizar e adquirir proficiência em tais ferramentas pode ser um diferencial para que você se destaque frente as demais candidatos em uma entrevista de emprego ou, caso já esteja empregado ou trabalhe como autônomo em uma consultoria, que se destaque em um projeto de grande complexo e de grande importância para seu cliente.

**Principais analisadores**

Sem sombra de dúvidas, quando estamos falando de analisadores de tráfego, o mais famoso entre eles é o Wireshark®, embora existam outras ferramentas relativamente similares como, por exemplo, o Capsa Suite, da Colasoft ([**https://www.colasoft.com/capsa-free/**](https://www.colasoft.com/capsa-free/)), específico para plataformas MS-Windows© e o TCPDump ([**https://www.tcpdump.org/**](https://www.tcpdump.org/)), disponível para plataformas Unix e GNU/Linux.

Existem ainda analisadores específicos para redes sem fio (_**wireless**_), como o NetSpot© ([**https://www.netspotapp.com/**](https://www.netspotapp.com/)), o inSSIDer© ([**https://www.metageek.com/products/inssider/**](https://www.metageek.com/products/inssider/)) e o WiPry© ([**https://www.oscium.com/spectrum-analyzers/wipry-5x**](https://www.oscium.com/spectrum-analyzers/wipry-5x)).

**Wireshark**

O Wireshark é um analisador de tráfego _**open-source,**_ originalmente desenvolvido por Gerald Combs, em 1998; à época, um aluno graduado cinco anos atrás, em Ciência da Computação, na Universidade do Missouri, no Estado de Kansas (EUA). Atualmente conta com centenas de contribuidores ao redor do mundo, tendo instaladores para MS-Windows© (incluindo uma versão _**portable**_), Unix, GNU/Linux e OSX©: [**https://www.wireshark.org/download.html**](https://www.wireshark.org/download.html). Na página do projeto é possível encontrar a documentação atualizada, incluindo os procedimentos para instalação nos diferentes sistemas operacionais: [**https://www.wireshark.org/docs/**](https://www.wireshark.org/docs/).

Após instalação (WIRESHARK, 2018), deve-se indicar qual a interface de rede que se deseja analisar com um duplo clique do mouse sobre o nome da interface como, por exemplo, a interface de rede _**eno1**_, de uma máquina com sistema operacional GNU/Linux, conforme Figura 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/5/9/6/2359684/40655.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/5/9/6/2359684/40655.png)

Screenshot de programa free e open-source, instalado no meu PC.

Após essa etapa, o Wireshark inicia automaticamente a captura dos pacotes sendo transmitidos e recebidos por essa interface de rede, e a análise dos mesmos já pode ser realizada, incluindo os tipos de protocolos, endereços IP e portas de comunicação, conforme ilustra a Figura 2:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/7/3/8/2373870/40656.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/7/3/8/2373870/40656.png)

Screenshot de programa free e open-source, instalado no meu PC.

O Wireshark possibilita uma análise detalhada, baseada no modelo de referência ISO/OSI, camadas 1 (física) a 4 (transporte), que são as camadas referentes aos dispositivos de rede, lembrando que as demais camadas – 5 (sessão) a 7 (aplicação) – são inerentes aos programas que utilizam os pacotes das camadas inferiores.

Existe um manual completo, disponível na internet, para você poder dominar o uso do Wireshark: [**https://www.wireshark.org/docs/wsug_html_chunked/**](https://www.wireshark.org/docs/wsug_html_chunked/)

Assim, é recomendável a leitura da documentação acima mas, principalmente, que você continue seus estudos, tire suas dúvidas e participe das discussões com o analisador da disciplina e os colegas da turma!

**Certificação**

O Wireshark tem se tornado tão popular como ferramenta de _**troubleshooting**_ dos profissionais de redes que inclusive possui uma certificação própria, intitulada _**Wireshark Certified Network Analyst**_ (WCNA), promovida por uma empresa da Laura Chappell (notória especialista sênior de análise de redes); a Wireshark University.

Detalhes da certificação, incluindo materiais de estudo, podem ser encontrados em: [**http://www.wiresharktraining.com/certification.html**](http://www.wiresharktraining.com/certification.html).

**Conclusão**

Neste capítulo apresentamos a definição dos analisadores de tráfego, sua importância e utilidade; mencionamos alguns exemplos de analisadores disponíveis no mercado, com maior detalhamento referente ao Wireshark, que é o mais utilizado entre eles pelos profissionais que trabalham com redes de computadores.