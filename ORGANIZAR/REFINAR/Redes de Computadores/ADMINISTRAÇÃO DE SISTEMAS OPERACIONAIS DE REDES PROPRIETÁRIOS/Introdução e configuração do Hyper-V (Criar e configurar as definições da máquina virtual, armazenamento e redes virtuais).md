### **Introdução**

Hyper-V é uma tecnologia de virtualização da Microsoft que permite vários sistemas operacionais convidados executarem simultaneamente máquinas virtuais em um computador e consequentemente fornecer acesso a aplicações e serviços separados para computador cliente. Ao implementar o Hyper-V, o hipervisor do Windows atua como o motor de máquina virtual, fornecendo a camada de software necessária para a instalação de sistemas operacionais convidados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/1/259159/form_obj_0.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/1/259159/form_obj_0.png)

Figura 1: Gerenciador do Hyper-V

### **Compreendendo Hyper-V**

O Hyper-V pode ser instalado apenas em computadores com processadores de 64 bits que implementam a virtualização assistida por hardware e proteção de execução de dados imposta por hardware. Especificamente, deve-se ativar o suporte a virtualização no firmware, especificamente, Intel Virtualization Technology (Intel VT) ou AMD Virtualization (AMD-V) e também definir a permissão de uso para qualquer Intel XD bit (Execute Disable bit) ou AMD NX bit (no execute bit).

A virtualização pode oferecer melhorias de desempenho, reduzir o número de servidores e reduzir o custo total de propriedade. Embora seja possível utilizar tanto o Windows 8 como o Windows Server 2012 para implantar computadores virtualizados, o Hyper-V para Windows Server é muito diferente do cliente Hyper-V para Windows 8.

Windows Server 2012 suporta muitos recursos de virtualização, incluindo a migração ao vivo e armazenamento de máquina virtual dinâmico. É possível utilizar a migração ao vivo para mover de forma transparente máquinas virtuais em execução, quer de um nó de um cluster para outro ou de um servidor sem cluster para outro. Com o armazenamento de máquina virtual dinâmico, é possível adicionar ou remover discos rígidos virtuais e discos físicos, enquanto a máquina virtual está em execução.

### **Instalando o Hyper-V**

As máquinas virtuais exigem redes virtuais para se comunicar com outros computadores e ao instalar o Hyper-V, pode-se criar uma rede virtual para cada adaptador disponível. Após concluir a instalação do Hyper-V, pode-se criar e gerenciar redes virtuais usando Gerenciador de Rede Virtual, porém a Microsoft recomenda reservar um adaptador de rede para acesso remoto ao servidor. Lembre-se de que antes de instalar o Hyper-V é preciso habilitado o processador para virtualização e posteriormente completar as seguintes etapas:

**Para habilitar o Hyper-V no Windows 8.1**

1. No Painel de Controle, clique em Programas e, a seguir, em Programas e Recursos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/5/9/1805959/11660.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/5/9/1805959/11660.png)

Figura 2: Painel de Controle

2. Clique em Ativar ou desativar recursos do Windows.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/5/9/1805965/11661.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/5/9/1805965/11661.png)

Figura 3: Ativar ou desativar recursos do Windows

3. Selecione Hyper-V, clique em OK e em Fechar.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/5/9/1805973/11662.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/5/9/1805973/11662.png)

Figura 4: Recursos do Windows

4. Reinicie o computado para concluir as alterações.

**Definições do Hyper-V e criação de Máquina Virtual**

A Figura 5 faz parte do processo de criação de uma nova máquina virtual, onde é possível decidir o nome da máquina virtual e a localização dos arquivos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/5/9/1805980/11666.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/5/9/1805980/11666.png)

Figura 5: Definições da Máquina Virtual