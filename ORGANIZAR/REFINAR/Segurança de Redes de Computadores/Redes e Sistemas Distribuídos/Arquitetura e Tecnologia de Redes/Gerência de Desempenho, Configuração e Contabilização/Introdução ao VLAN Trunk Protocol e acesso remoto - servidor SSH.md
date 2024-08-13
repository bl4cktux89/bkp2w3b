[![](https://ampli-images.s3.amazonaws.com/production/5e7056d4-8153-434e-9d82-34beaa148bd9/original)](https://ampli-images.s3.amazonaws.com/production/5e7056d4-8153-434e-9d82-34beaa148bd9/original)

O VLAN _Trunk Protocol_ (VTP) é um protocolo de camada 2 (inter-rede), desenvolvido pela Cisco e utilizado para configuração de _Virtual Local Area Network_ (VLAN), com o objetivo de facilitar a administração dos sistemas. Este protocolo define uma estrutura do tipo cliente-servidor, na qual as alterações são feitas necessariamente no servidor e replicadas aos clientes da rede. Importante apontar que esta técnica é utilizada por administradores de redes para melhorar o controle do sistema.

______

**🔁****Assimile**

Uma VLAN é uma forma de criar sub-redes virtuais em uma estrutura de rede local implementada em switches, onde cada interface de rede (_host_) pode se comportar como uma VLAN e definir seu próprio domínio de _broadcast_.

______

Com a utilização do VLAN _Trunk Protocol_, o trabalho de configuração de redes locais virtuais é reduzido, pois o gestor da rede configurará apenas um _switch_, que será o responsável pela função de distribuir e sincronizar as informações para os outros _switches_ da rede. Esta tecnologia oferece redução de atividades de configuração e reconfiguração e minimização de erros através da centralização das configurações em um switch chamado de VLAN _Trunk Protocol_ Server. Na VLAN, nos switches que fazem parte de uma rede com VLAN, as tabelas de roteamento são atualizadas, isso porque as VLANs são criadas na interface de rede do _switch_. A estrutura de uma rede configurada com o VLAN _Trunk Protocol_ é:

- _**Server**_ **VTP**: dispositivo responsável por criar, deletar, renomear e definir o domínio e as configuração das VLANs.
- _**Client**_ **VTP**: dispositivos que compõem a VLAN, porém não podem configurá-la.
- _**Transparent**_ **VPT**: _switch_ com VLANs configuradas manualmente, que não participa do VTP.

[![](https://ampli-images.s3.amazonaws.com/production/6b1a5dd2-5850-48eb-a2ee-df665361c517/original)](https://ampli-images.s3.amazonaws.com/production/6b1a5dd2-5850-48eb-a2ee-df665361c517/original)

Estrutura formada pelo VLAN Trunk Protocol (VTP). Fonte: elaborada pelo autor.

______

**💭Reflita**

Caso um administrador de redes tenha desejo de implementar redes locais virtuais, ele deverá fazer a configuração manualmente em cada _switch_ da rede. Isto é simples em uma rede com dois ou três _switches_, porém se torna inviável em uma rede maior, com uma estrutura mais complexa e suscetível a erros de configuração.

O VTP pode ser a tecnologia adequada para gestão de redes com múltiplos switches?

______

**Acesso remoto - servidor SSH**

O protocolo de rede SSH (_Secure Socket Shell ou Secure Shell_) permite que se faça comunicação com segurança (criptografada) entre um _host_ cliente e um servidor de rede, permitindo fazer o gerenciamento de dados e informações deste servidor de forma remota (em local físico diferente de sua localização). Através do SSH, um usuário ou gestor da rede pode fazer _login_ em outro computador da rede e executar comandos como se estivesse diretamente operando um sistema servidor local. A interface é realizada através de um Shell remoto, que executa os comandos digitados e faz a ponte entre a máquina do usuário e o servidor remoto

Os comandos de interação são realizados através de um terminal, chamado de _Shell_, responsável pela interpretação dos comandos do usuário junto ao sistema operacional de rede. Trata-se de um serviço que possui um protocolo que estabelece a administração remota de um servidor. É baseado em interação via texto, porém sua utilização é simples, através de um conjunto de recursos que permitem desde a transferência de arquivos entre cliente e servidor até a instalação e configuração de serviços de gerenciamento de redes de forma remota.

O SSH é originalmente desenvolvido para sistemas operacionais, UNIX, adaptados em distribuições baseadas em Linux. No entanto, também é possível utilizá-lo em sistemas operacionais baseados em plataforma Windows com aplicativos adicionais e a partir da sua versão 10 sem utilização de aplicações complementares.

O comando SSH segue a seguinte estrutura:

**ssh** _**user@host**_

- **ssh**: indica o uso do comando para abertura de conexão remota criptografada.
- _**user**_: exemplificado como a conta à qual se deseja conectar remotamente (necessário ter direitos de administrador (Windows) e _root_ (Linux).
- _**host**_: indica o computador que se deseja acessar, identificado através do endereço IP ou nome de domínio.

Após a digitação do comando para inicialização dos serviços de SSH, será necessário informar nome de usuário e senha de acesso à conta, definidos no servidor SSH em um sistema operacional de rede. A figura a seguir apresenta um exemplo de conexão de SSH realizada pelo _Laptop-1 SSH Client_ com um _SSH Server_ em uma localização física diferente.

[![](https://ampli-images.s3.amazonaws.com/production/800b07a7-10b3-43c9-aeb1-d9bae14f817c/original)](https://ampli-images.s3.amazonaws.com/production/800b07a7-10b3-43c9-aeb1-d9bae14f817c/original)

SSH Conexão remota com SSH. Fonte: elaborada pelo autor.

A seguir, a figura apresenta um exemplo de utilização de cliente SSH para acesso remoto a um servidor determinado.

[![](https://ampli-images.s3.amazonaws.com/production/d215aa12-042c-4520-a5a8-33def8717535/original)](https://ampli-images.s3.amazonaws.com/production/d215aa12-042c-4520-a5a8-33def8717535/original)

SSH Cliente no Windows 10. Fonte: Hostmidia.

______

**📝****Exemplificando**

Para habilitar a ferramenta SSH no Windows, siga os seguintes passos:

1. Abra as configurações do Windows.
2. Acesse Aplicativos.
3. Clique em “Aplicativos e Recursos”.
4. Clique em “Recursos Opcionais”.
5. Selecione o OpenSSH, caso não apareça.
6. Clique em “Adicionar um recurso”; Localize “Cliente OpenSSH”, caso deseje instalar o cliente ou “Servidor OpenSSH” para o servidor e clique em Instalar.

Para utilizar o SSH, é necessário que se tenha acesso à internet e privilégios de administrador. Se for distribuição Linux, deverá ter acesso como _root_ (administrador). Os dados de acesso como conta do usuário, senha e porta do servidor também são necessários para que se realize uma conexão SSH.

Para melhor compreender a instalação e execução do Open SSH no Windows 10, você pode visitar o site da Microsoft com as devidas orientações e a página _OpenSSH_.

Outras ferramentas para implementação de SSH:

- PuTTy: cliente SSH para a plataforma Windows e Unix (Linux).
- SmarTTY: um cliente SSH.
- XShell: clientes SSH versátil.