  

A arquitetura Cliente/Servidor trata de um método de distribuição de aplicações computacionais por meio de plataformas, utilizando aplicações distribuídas entre provedores de serviço e centrais de dados com numerosos clientes contendo uma interface gráfica para os usuários acessarem e manipular os dados.

Cliente/Servidor geralmente refere-se a um modelo onde dois ou mais computadores interagem de modo que um oferece os serviços aos outros. Este modelo permite aos usuários acessarem informações e serviços de qualquer ponto da rede. É uma arquitetura computacional que envolve requisições de serviços de clientes para servidores.

De uma forma resumida, um sistema Cliente/Servidor poderia ser, então, entendido como a interação entre Software e Hardware em diferentes níveis, implicando na composição de diferentes computadores e aplicações.

Para melhor se entender o paradigma Cliente/Servidor é necessário observar que o conceito chave está na ligação lógica e não física. O Cliente e o Servidor podem coexistir ou não na mesma máquina. Porém um ponto importante para uma real abordagem Cliente/Servidor é a necessidade de que a arquitetura definida represente uma computação distribuída.

Algumas das características do Cliente e do Servidor são descritas a seguir:

**Cliente**

- É a estação de trabalho que roda um processo que interage com o usuário por meio de uma interface gráfica ou não, permitindo consultas ou comandos para recuperação de dados e análise;
- É o processo ativo na relação Cliente/Servidor.
- Inicia e termina as conversações com os Servidores, solicitando serviços distribuídos.
- Não se comunica com outros Clientes.
- Torna a rede transparente ao usuário.

**Servidor**

- É responsável pelo serviço que responde as requisições do cliente que fica disponível todo o tempo.
- É o processo que devolve as informações solicitadas na relação Cliente/Servidor.
- Responde às solicitações dos Clientes.
- Não se comunica com outros Servidores enquanto estiver fazendo o papel de Servidor.
- Presta serviços distribuídos.
- Atende a diversos Clientes simultaneamente.

Alguns tipos de serviços que um Servidor pode proporcionar são:

- de Arquivos
- de Impressora
- de Banco de Dados
- de Redes
- de Processamento e Imagens
- de Comunicação, entre outros.

O estilo de interação entre o usuário e o Cliente utiliza interfaces gráficas - GUI (Graphical User Interface), para melhor conexão entre os processos rodando na máquina cliente e na máquina servidora.

Dentre as muitas vantagens da arquitetura Cliente/Servidor, pode-se citar:

2.1 - Vantagens

- **Confiabilidade**

Se uma máquina apresenta algum problema, ainda que seja um dos Servidores, parte do Sistema continua ativo.

- **Matriz de Computadores agregando capacidade de processamento**

A arquitetura Cliente / Servidor provê meios para que as tarefas sejam feitas sem a monopolização dos recursos. Usuários finais podem trabalhar localmente.

- **O Sistema cresce facilmente**

Torna-se fácil modernizar o Sistema quando necessário.

- **O Cliente e o Servidor possuem ambientes operacionais individuais /**

**Sistemas Abertos**

Pode-se misturar várias plataformas para melhor atender às necessidades individuais de diversos setores e usuários.

Outro ponto importante trata-se da interoperabilidade entre as estações Clientes e Servidoras e principalmente entre as redes de computadores, garantindo escalabilidade e possibilitando o crescimento, com a possibilidade de inclusão de diversas novas tecnologias desenvolvidas.

Embora o avanço da arquitetura Cliente/Servidor tenha trazido uma variada gama de facilidades para o desenvolvimento de aplicações distribuídas, também possui algumas desvantagens:

2.2 - Desvantagens

- **Manutenção**

As diversas partes envolvidas nem sempre funcionam bem juntas. Quando algum erro ocorre, existe uma extensa lista de itens a serem investigados.

- **Ferramentas**

A escassez de ferramentas de suporte, não raras vezes obriga o desenvolvimento de ferramentas próprias. Em função do grande poderio das novas linguagens de programação, esta dificuldade está se tornando cada vez menor.

- **Gerenciamento**

Aumento da complexidade do ambiente e a escassez de ferramentas de auxílio tornam difícil o gerenciamento da rede.

Modelos da Arquitetura Cliente / Servidor

Existem cinco tipos de modelos para a implantação da arquitetura Cliente/Servidor em processamentos distribuídos:

Arquitetura C/S Simples

O primeiro tipo de sistema distribuído é a arquitetura Cliente/Servidor Simples. Nesta arquitetura, o Servidor não pode iniciar nada. O Servidor somente executa as requisições do Cliente. Existe uma clara função de diferenciação: Pode-se estabelecer que o Cliente é o mestre e o Servidor é o escravo, como mostra a figura 1.

![[pic1 2.jpg|pic1 2.jpg]]

  

Arquitetura C/S em Dois Níveis

A configuração usual Cliente/Servidor encontrada na maioria das empresas, é aquela em que existem vários Clientes requisitando serviços a um único Servidor. Esta arquitetura se caracteriza como sendo c_**entrada no Servidor**_ (figura 2a). Porém na visão do usuário, ele imagina que existem vários Servidores conectados a somente um Cliente, ou seja, c_**entrado no Cliente**_ (figura 2b). Entretanto, com as várias ligações de comunicação possíveis, existe na realidade uma mistura de Clientes e Servidores (figura 2c).

![[PIC2.jpg]]

  

Arquitetura C/S Multinível

Nesta arquitetura (figura 3), permite-se que uma aplicação possa assumir tanto o perfil do Cliente como o do Servidor, em vários graus. Em outras palavras, uma aplicação em alguma plataforma será um Servidor para alguns Clientes e, concorrentemente, um Cliente para alguns Servidores.

![[PIC3.jpg]]

Esta arquitetura pode ser vista como o caso mais geral da arquitetura Cliente/Servidor, ilustrado na figura 4. Cada um dos nodos desta arquitetura assume tanto o papel de Cliente quanto de Servidor. Na verdade, torna-se pouco funcional lidar com quem é o Cliente ou o Servidor. É o caso onde o processo interage com outros processos em uma base pareada, não existindo nenhum Mestre ou Escravo: qualquer estação de trabalho pode iniciar um processamento, caso possua uma interface de comunicação entre o usuário e o processo Cliente.

![[pic4.jpg]]