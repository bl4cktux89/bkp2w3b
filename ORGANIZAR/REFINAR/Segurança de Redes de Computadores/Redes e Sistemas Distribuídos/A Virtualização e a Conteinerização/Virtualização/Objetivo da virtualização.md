[![](https://ampli-images.s3.amazonaws.com/production/6ef63cc4-c59e-421c-910f-53e4b3357225/original)](https://ampli-images.s3.amazonaws.com/production/6ef63cc4-c59e-421c-910f-53e4b3357225/original)

A virtualização se torna cada vez mais popular com o passar dos anos e é amplamente utilizada nos ambientes corporativos e, em alguns casos, até domesticamente. O grande objetivo da virtualização é fornecer uma versão virtual de tecnologias essenciais em computação, por exemplo, redes, armazenamento, hardware, entre outros. Além disso podemos também, virtualizar aplicações. Segundo Dawson e Wolf (2011, [s.p.]), a “virtualização desacopla as tarefas e a parte funcional das aplicações da infraestrutura física necessária para seu funcionamento, permitindo uma flexibilidade e agilidade sem precedentes em termos de armazenamento, servidores e desktops”.

______

**🔁Assimile**

Atualmente, é possível fornecer uma versão virtual de tecnologias essenciais em computação. Por exemplo, para um site permanecer no ar por 24 horas, não precisamos ter um servidor web/aplicação físico mantendo seu funcionamento, podemos ter um servidor virtual ou máquina virtual, como são chamadas, tipo de servidor que substitui ou emula o funcionamento de um servidor físico.

______

Quando virtualizamos recurso de hardware, como memória RAM, processador, placas de vídeo, placa de rede, entre outros, temos uma máquina virtual que funciona com os recursos de hardware em formato virtual. Sabendo disso, podemos instalar um sistema operacional sobre outro sistema, ou seja, sobre nossa máquina física podemos ter várias máquinas virtuais. Esses recursos de hardware são representados por softwares na virtualização. A mesma coisa também pode ser feita com a rede: é possível criar uma infraestrutura lógica de rede sobre uma rede física. Nela podemos personalizar e configurar de formas diferentes da rede física, conforme nossas necessidades. Também é possível ter em nossa residência uma rede física “A” composta pelas redes lógicas “B” e “C”.

Quando utilizamos virtualização, representamos os dispositivos físicos por meio de entidades de software, assim, nossos servidores e _workstations_ se tornam o que chamamos de máquinas virtuais, ou VMs. A parte de armazenamento de dados é conhecida como _Software Defined Storage_ (SDS), ou armazenamento definido por software. Já a parte de rede é chamada de _Software Defined Networking_ (SDN), ou rede definida por software. Unindo todos esses elementos com um conjunto de máquinas virtuais, temos um _Software Defined Data Center_ (SDDC), ou data center definido por software.

Portanto, as máquinas virtuais são abstrações de hardware de computadores que permitem que uma única máquina física aja como se fosse várias máquinas diferentes. Assim, podemos ter vários sistemas operacionais distintos rodando em uma só máquina.

A virtualização contém três componentes principais, conforme o Portal Redhat (2018):

- **Hospedeiro**: como chamamos a máquina física em que existem máquinas virtuais.
- **Convidado**: como são chamadas as máquinas virtuais ou computadores virtualizados.
- **Camada de virtualização**: o software que permite criar sistemas convidados sobre sistemas hospedeiros.

Podemos observar na figura abaixo a interação dos três componentes principais da virtualização e exemplos de como são compostos:

[![](https://ampli-images.s3.amazonaws.com/production/f55e50c0-c57c-40d9-8e04-a589bd050506/original)](https://ampli-images.s3.amazonaws.com/production/f55e50c0-c57c-40d9-8e04-a589bd050506/original)

Elementos de máquinas virtuais. Fonte: elaborada pelo autor.

Para o usuário final, não faz diferença se a máquina acessada é física ou virtual, pois as duas funcionam da mesma forma, o que acaba sendo imperceptível. Nesse cenário de virtualização podemos ter em um mesmo servidor uma máquina virtual com o sistema operacional Windows Server, uma máquina virtual com Linux e uma máquina com FreeBSD, por exemplo. Os principais fatores que levam à utilização de virtualização são:

- **Diminuição de espaço físico**: muitas vezes, o ambiente corporativo não tem espaço físico para suportar servidores, com todos requisitos necessários, como a refrigeração adequada para eles.
- Rapidez na implantação: máquinas virtuais são implantadas mais rapidamente do que máquinas físicas.
- **Redução de custos administrativos**: os custos administrativos para se manter uma máquina física são bem maiores do que os custos referentes às máquinas virtuais.
- **Economia de energia elétrica**: como podemos ter várias máquinas virtuais funcionando sobre apenas uma máquina física, consequentemente, economizaremos energia, tendo menos máquinas alimentadas.
- **Aproveitamento da capacidade de computação e performance**: é possível aproveitar melhor os recursos de um servidor físico dividindo-os em várias máquinas virtuais.