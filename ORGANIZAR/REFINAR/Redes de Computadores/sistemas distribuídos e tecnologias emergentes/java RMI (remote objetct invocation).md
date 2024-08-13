O JAVA RMI (Remote Method Invocation) é uma interface de programação que permite a execução de chamadas remotas no estilo RPC para um ambiente de desenvolvimento de aplicações distribuídas, que residem em Máquinas Virtuais Java (JVM). O JVM é um mecanismo de chamada de procedimento remoto orientada a objetos.

Através da utilização da arquitetura RMI, é possível que um objeto ativo em uma JVM, possa interagir com objetos de outras máquinas virtuais Java, independentemente da localização dessas máquinas virtuais.

Assim como em outras soluções, o RMI também é uma solução Cliente/Servidor.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/0/314021/19232.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/0/314021/19232.jpg)

Arquitetura Cliente/Servidor e a IDL

Fonte: Fonte: ROQUE, Vitor. Arquitecturas Distribuídas Cliente/Servidor: CORBA, DCOM e Java RMI. Universidade de Aveiro, Portugal, 1999.

A dependência do RMI está na sua linguagem que a concebeu, pois deve ser escrita, obrigatoriamente, em JAVA. Mas como a linguagem JAVA é portável, ou seja, não é limitada a um único Sistema Operacional, a mesma pode ser executada em computadores com MS-Windows, MAC-OSX, UNIX e GNU/LINUX.

Assim, os objetos podem estar em computadores diferentes, com Sistemas Operacionais diferentes, que a JVM trará portabilidade na solução.

A Figura abaixo mostra a estrutura dos componentes da arquitetura RMI.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/3/8/313815/19235.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/3/8/313815/19235.jpg)

Estrutura dos componentes da arquitetura JAVA Remote Method Invocation - RMI

Fonte: Fonte: ROQUE, Vitor. Arquitecturas Distribuídas Cliente/Servidor: CORBA, DCOM e Java RMI. Universidade de Aveiro, Portugal, 1999.

Analisando a estrutura do JAVA RMI, veremos quatro camadas, sendo que a primeira camada (vista de cima para baixo) representa os componentes de interface do Cliente e do Servidor.

As demais próximas três camadas são referentes ao ambiente RMI.

Na segunda camada, temos os **Stub** e **Skeleton** que são responsáveis pelo gerenciamento das interfaces dos objetos remotos que respondem ao cliente e ao servidor.

Os **Stubs** são classes usadas do lado da aplicação cliente e funcionam como Proxies entre a aplicação cliente e o objeto remoto (servidor). Os Stubs recebem os parâmetros dos métodos exportados pelo objeto remoto, (definidos pela interface da classe remota) e os reencaminha para o lado do servidor onde serão interpretados por uma instância de uma classe **Skeleton**.

O **Skeleton** recebe os parâmetros enviados pelo Stub e executa as respectivas chamadas no objeto remoto (servidor). Em sentido inverso, os Skeletons são também responsáveis por receber o valor de retorno do método remoto e direcioná-los para os Stubs dos clientes correspondentes.

Na terceira camada, encontramos o RRL (Remote Reference Layer) que é a camada responsável pelo gerenciamento de atividades, bem como, da comunicação entre os objetos remotos e as Máquinas Virtuais (JVMs).

Finalmente na última, temos a camada de transporte que é responsável pela comunicação entre as várias JVM's, cliente e servidor, usando TCP/IP. É importante saber que mesmo que as JVM's sejam executadas no mesmo computador, o RMI recorre _**sempre**_ à comunicação TCP/IP. Isto significa que é necessário possuir uma interface de rede funcional para se poder utilizar RMI, mesmo tendo a aplicação cliente e a aplicação servidora executando no mesmo computador.

**TRANSFERÊNCIA DE PARÂMETROS**

Como a maioria dos sistemas RMI suportam referências de objeto no âmbito do sistema, a transferência de parâmetros em invocações de método é menos restrita do que no caso de RPC’s, considerando a situação em que há somente objetos distribuídos.

Assim, todos os objetos no sistema podem ser acessados por máquinas remotas, quando podemos usar referências de objeto como parâmetros em invocações de método. Essas referências são passadas por valor e copiadas de uma máquina para outra. Dessa forma, quando um processo recebe uma referência de objeto como resultado de um método de invocação, ele pode simplesmente se vincular ao objeto referenciado quando for necessário mais tarde.

Quando um método é invocado com uma referência de objeto como parâmetro, essa referência é copiada e transferida como parâmetro somente quando referencia um objeto remoto. Contudo, quando a referência está no mesmo espaço de endereço do cliente, o objeto referenciado é copiado como um todo e passado junto com a invocação, ou seja, o objeto é passado como valor.

Vejamos como isso funciona:

- Um programa cliente executa na máquina **A** e um programa servidor na máquina **C**.
- O cliente tem uma referência a um objeto **O1** que usa um parâmetro quando chama o programa servidor na máquina **C**, e também, ele contém uma referência a um objeto remoto **O2** que reside na máquina **B**, que também é usada como parâmetro.
- Ao chamar o servidor, uma cópia de **O1** é passada para o servido na máquina **C**, junto com apenas uma cópia da referência a **O2**.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/3/8/313865/19239.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/3/8/313865/19239.jpg)

Transferência de Parâmetros entre objetos utilizando sistema RMI.

Fonte: Figura 10.8 - pag.278 - do Livro Sistemas Distribuídos - Princípios e Paradigmas

Observe que tratar uma referência a um objeto local ou uma referência a um objeto remoto pode ser muito transparente em Java, onde a distinção é visível só porque objetos locais são essencialmente de um tipo de dados diferente dos objetos remotos. Entretanto, ambas as referência são tratadas praticamente do mesmo jeito.

Em Java, objetos distribuídos foram integrados à linguagem, com o objetivo de manter o máximo possível da semântica de objetos não distribuídos. Assim, os desenvolvedores da linguagem Java visaram o alto grau de transparência de distribuição.

**EXEMPLO DE UM PROGRAMA JAVA RMI**

Vamos escrever um aplicação RMI simples usando a IDE NetBeans (versão 6.9.1). A aplicação RMI que escreveremos se trata de uma calculadora que recebe dois inteiros e devolve sua soma. A aplicação cliente se conectará a aplicação servidor, enviará dois valores inteiros e o servidor devolverá a soma dos valores informados. Vejamos como será:

- O primeiro passo para escrever a aplicação cliente é abrir o NetBeans.
- Em seguida vá até a opção Arquivo -> Novo Projeto.
- Na janela de novo projeto escolha Java de um lado e Aplicativo Java do outro.
- Clique no botão Próximo.
- Dê o nome "CalculadoraServidor" ao projeto e salve-o no diretório "C:\estudos_rmi" de forma que a pasta do projeto seja C:\estudos_rmi\CalculadoraServidor".
- Clique no botão Finalizar.

Vamos começar criando a interface remota, que será compartilhada tanto pela aplicação servidor quanto pela aplicação cliente.

- Na opção Arquivo -> Novo Arquivo.
- Na janela Novo arquivo escolha Java de um lado e Interface Java do outro.
- Clique no botão Próximo.
- Dê o nome "CalculadoraServerInterface" à interface e selecione o pacote "calculadoraservidor".
- Clique no botão Finalizar.

Altere o código do arquivo CalculadoraServerInterface.java para a versão como segue:

_**package calculadoraservidor;**_

_**import java.rmi.*;**_

_**public interface CalculadoraServerInterface extends Remote{**_

_**// método público que recebe dois valores inteiros e**_

_**// retorna sua soma**_

_**public int somar(int a, int b) throws RemoteException;**_

_**}**_

Agora temos um método somar() que recebe dois inteiros e retorna sua soma. Vamos agora escrever uma classe que implementa esta interface.

- Na opção Arquivo -> Novo Arquivo.
- Na janela Novo arquivo escolha Java de um lado e Classe Java do outro.
- Clique no botão Próximo.
- Dê o nome "CalculadoraServerInterfaceImpl" à classe e selecione o pacote "calculadoraservidor".
- Clique no botão Finalizar.Altere o código do arquivo CalculadoraServerInterfaceImpl.java para a versão mostrada abaixo:

_**package calculadoraservidor;**_

_**import java.rmi.*;**_

_**import java.rmi.server.*;**_

_**public class CalculadoraServerInterfaceImpl extends UnicastRemoteObject**_

_**implements CalculadoraServerInterface{**_

_**public CalculadoraServerInterfaceImpl() throws RemoteException{**_

_**// construtor padrão**_

_**}**_

  _**// método público que recebe dois valores inteiros e**_

_**// retorna sua soma**_

_**public int somar(int a, int b) throws RemoteException{**_

_**return a + b;**_

_**}**_

_**}**_

Agora vamos implementar o servidor e registrá-lo com o RMI server. Altere o código do arquivo Main.java para a seguinte versão:

_**package calculadoraservidor;**_

_**import java.rmi.registry.*;**_

_**public class Main {**_

_**public static void main(String[] args) {**_

_**try {**_

_**CalculadoraServerInterface csi = new CalculadoraServerInterfaceImpl();**_

_**Registry registry = LocateRegistry.getRegistry();**_

_**registry.rebind("CalculadoraServerInterfaceImpl", csi);**_

_**System.out.println("Servidor Calculadora " + csi +**_

_**" registrado e pronto para aceitar solicitações.");**_

_**}**_

_**catch (Exception ex) {**_

_**System.out.println("Houve um erro: " + ex.getMessage());**_

_**}**_

_**}**_

_**}**_

A aplicação servidor já está concluída. Pressione F6 para executá-la. Teremos o seguinte erro de tempo de execução:

Houve um erro: Connection refused to host: 192.168.1.64; nested exception is:

java.net.ConnectException: Connection refused: connect

Isso aconteceu porque não iniciamos o RMI Registry. Para isso, abra uma janela de comando e dispare:

_**start rmiregistry**_

Isso fará com que uma nova janela de comando seja aberta. Não a feche. O RMI Registry está sendo executado nela. Volte à aplicação e pressione F6 novamente. Agora o erro de tempo de execução é:

Houve um erro: RemoteException occurred in server thread;

nested exception is: java.rmi.UnmarshalException:

error unmarshalling arguments;

nested exception is:

java.lang.ClassNotFoundException: calculadoraservidor.CalculadoraServerInterface

Este erro ocorreu porque o RMI Registry não conseguiu encontrar nenhuma informação a respeito da interface CalculadoraServerInterface.

Para contornarmos este problema, vamos apenas construir a aplicação (pressionando F11 ou acessando Executar -> Construir projeto principal) e executá-la a partir do **jar** gerado (CalculadoraServidor.jar).

Assim, abra uma janela de terminal e vá até o diretório de sua localização:cd C:\estudos_rmi\CalculadoraServidor\dist

Agora dispare:

_**java -jar CalculadoraServidor.jar**_

Novo erro ... Agora pare o RMI (Ctrl + C), feche todas as janelas de

comando e adicione o valor:

"C:\estudos_rmi\CalculadoraServidor\dist\CalculadoraServidor.jar;" à sua variável de CLASSPATH.

Inicie o RMI novamente, abra uma nova janela de terminal, vá até o diretório "C:\estudos_rmi\CalculadoraServidor\dist" e execute o JAR novamente.

Se tudo correu bem você terá o seguinte resultado:

Servidor Calculadora CalculadoraServerInterfaceImpl[UnicastServerRef [liveRef: [

endpoint:[192.168.1.64:4634](local),objID:[4124a53a:12e63b2ebea:-7fff, 383998976

7738511284]]]] registrado e pronto para aceitar solicitações.

Esta mensagem indica que o servidor RMI está 100% funcionando e pronto para atender às requisições do cliente.

Hora de passarmos ao desenvolvimento do cliente, vamos escrever a aplicação RMI Cliente:

Na aplicação cliente nós precisaremos referenciar a interface CalculadoraServerInterface, que é parte da aplicação servidor:

- Clique com o botão direito em Bibliotecas.
- Escolha a opção Adicionar JAR/Pasta.
- Localize o diretório "C:\estudos_rmi\CalculadoraServidor\dist".
- Selecione o JAR CalculadoraServidor.jar
- Clique no botão Open.

- Modifique o Main.java para a seguinte versão:

_**package calculadoracliente;**_

_**import java.rmi.registry.*;**_

_**import calculadoraservidor.*;**_

_**public class Main {**_

_**public static void main(String[] args) {**_

_**try {**_

_**Registry registry = LocateRegistry.getRegistry("localhost");**_

_**CalculadoraServerInterface c = (CalculadoraServerInterface)**_

_**registry.lookup("CalculadoraServerInterfaceImpl");**_

_**System.out.println("O objeto servidor " + c + " foi encontrado com sucesso.\n");**_

_**// vamos efetuar uma soma?**_

_**System.out.println("A soma de 2 + 5 é: " + c.somar(2, 5));**_

_**}**_

_**catch(Exception ex){**_

_**System.out.println(ex);**_

_**}**_

_**}**_

_**}**_

Agora a aplicação cliente pode ser executada a partir do NetBeans (com o RMI Registry ativo e a aplicação Servidor em execução).

Basta pressionar F6 e teremos o seguinte resultado:

O objeto servidor Proxy[CalculadoraServerInterface,

RemoteObjectInvocationHandler[UnicastRef [liveRef:

[endpoint:[192.168.1.64:4649](remote),objID:[4d4c1a57:12e63bb67ba:-7fff,

3392955188099866234]]]]] foi encontrado com sucesso.

A soma de 2 + 5 é: 7