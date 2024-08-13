### **Introdução**

O Microsoft Windows Server 2012 suporta apenas arquitetura de 64 bits e as opções disponíveis para instalação são: nova instalação, atualização de um sistema operacional Microsoft Windows existente ou uma nova instalação em um ambiente de inicialização múltipla. Nesta aula, discutiremos sobre como preparar e executar instalações e a maneira de como implantar servidores Windows de acordo com os objetivos e requisitos necessários.

### **Inicializando a instalação**

A instalação do Windows Server 2012 pode ser inicializada a partir da mídia de distribuição do Windows ou executada a partir do sistema operacional Windows atual. Ao executar a instalação, há duas abordagens básicas: interativa ou automatizada. Durante o processo de instalação interativa, o administrador de sistemas acompanha e insere as informações até concluir o processo de instalação. Na forma mais básica de instalação automatizada, a instalação utiliza somente arquivos de resposta, o qual contém na totalidade ou parte da informação de configuração normalmente solicitada durante um processo de instalação interativa.

### **Preparando para uma instalação do Windows Server 2012**

A instalação de um sistema operacional de servidor exige uma avaliação e preparação antes de iniciar o trabalho, é importante observar e rever os detalhes de instalação e hardware para o servidor, verificar as últimas notas técnicas, verificar backups. A maioria das edições de 2012 tem como requisitos base um processador de 1,4 gigahertz (GHz) de 64 bits, 512 megabytes (MB) de memória RAM e 32 gigabytes (GBs) de espaço em disco rígido.

### **Instalação do Windows Server 2012**

Para iniciar o processo de instalação de um sistema operacional Windows Server de forma interativa o administrador de sistemas deve realizar a implantação tomando as decisões de acordo com cada momento. Para uma instalação de forma típica do Windows Server 2012, em uma máquina virtual, é necessário a realização das seguintes etapas:

1. Conecte-se à origem de instalação. As opções de conexão incluem:

- Um DVD-ROM contendo os arquivos de instalação do Windows Server 2012 ou,
- Um arquivo .iso contendo os arquivos de instalação do Windows Server 2012.

2. Na primeira página do Assistente de Instalação do Windows, selecione o seguinte:

- Idioma a instalar
- Formato de hora e moeda
- Teclado ou método de entrada

3. Na segunda página do Assistente de Instalação do Windows, clique em **Instalar agora**. Essa página também pode ser usada para escolher a opção **Reparar o Computador**. Use essa opção no caso de uma instalação ficar corrompida e você não conseguir mais inicializar no Windows Server 2012.

4. No Assistente de Instalação do Windows, na página **Selecione o Sistema Operacional que deseja Instalar**, escolha uma das opções de instalação disponíveis para o sistema operacional. A opção padrão é Instalação Server Core.

5. Na página **Termos de Licenciamento**, examine os termos da licença do sistema operacional. Você deve optar por aceitar os termos de licença para poder continuar com o processo de instalação.

6. Na página **Que tipo de instalação você deseja**, existem as seguintes opções:

- **Atualização**. Selecione essa opção se você tiver uma instalação existente do Windows Server que deseja atualizar para o Windows Server 2012. Convém iniciar atualizações a partir da versão anterior do Windows Server em vez de inicializar a partir da origem de instalação.
- **Customizada**. Selecione essa opção se quiser fazer uma nova instalação.

7. Na página **Onde você deseja instalar o Windows?**, escolha um disco disponível no qual instalar o Windows Server 2012. Também existe a opção de reparticionar e reformatar discos nessa página. Ao clicar em **Próximo**, o processo de instalação copiará arquivos e reinicializará o computador várias vezes.

8. Na página **Configurações**, forneça uma senha para a conta de administrador local.

### **Instalação do Windows Server 2012 na Hyper-V**