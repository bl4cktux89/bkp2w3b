[![](https://ampli-images.s3.amazonaws.com/production/966bcadb-525f-4c7b-822d-9465d580f479/original)](https://ampli-images.s3.amazonaws.com/production/966bcadb-525f-4c7b-822d-9465d580f479/original)

### **Qual é o foco da aula?**

Nesta aula, trabalharemos conceitos e definições de sistemas distribuídos e veremos as diferenças entre _clusters_ e _grids_, além de exemplos de sistemas distribuídos e de sincronização de relógios no sistema operacional Windows.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- interpretar o conceito e exemplos de sistemas distribuídos;
- examinar as diferenças entre _cluster_ e _grid_;
- analisar o papel da virtualização em sistemas distribuídos.

**Introdução da aula**

Você sabia que, para o funcionamento correto de uma aplicação distribuída, os relógios de todas as máquinas devem estar sincronizados? Além disso, já ouviu falar em um servidor NTP, o qual serve como base para sincronizar os relógios das máquinas?

Imagine que você foi contratado por uma startup de desenvolvimento de sistemas bem-sucedida nos negócios, a qual iniciou projetos de sistemas para grandes empresas. Em seu primeiro dia, você recebeu um e-mail para uma reunião on-line de boas-vindas, mas percebeu que, ao responder e confirmar a reunião, ocorreu a indicação de horário equivocada, ou seja, o horário de recebimento do e-mail original apareceu como posterior ao horário do e-mail de resposta, conforme mostrado na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/44d5bb6a-e5ad-48b3-a604-2bb53913fbde/original)](https://ampli-images.s3.amazonaws.com/production/44d5bb6a-e5ad-48b3-a604-2bb53913fbde/original)

Exemplo de problema em uma caixa de e-mails. Fonte: captura de tela do Microsoft Outlook.

Essa figura ilustra um problema de sincronização de relógios nos sistemas computacionais que se comunicam em rede.

Sua primeira missão como analista na startup é reportar um erro de sincronização de aplicações que rodam em diferentes máquinas de um cliente de lojas de varejo. Assim que começou sua análise, você percebeu que os relógios das máquinas que rodam a aplicação não estão sincronizados, então, para resolver isso, você deverá preparar um relatório mencionando o problema e como resolver esse ajuste de horas, para que um técnico de campo seja enviado até o local.

Após seus relatórios e apresentações entregues ao dono das lojas, este percebe que você sabe do que está falando e confessa que não entende como os computadores podem conversar entre si. Entre outras coisas, você fala da importância do sincronismo entre as máquinas e decide mostrar que sistemas em rede não são tão complicados assim.

Você já parou para pensar quais são as configurações e os comandos necessários para que essa sincronização funcione adequadamente? Qualquer computador pode ser usado para realizar a configuração ou é necessário um servidor específico para essa tarefa? Se for necessário um servidor, qual é o mais utilizado?

Para esclarecer essas dúvidas, você decide exemplificar o funcionamento de um sistema em rede de maneira simples e prática, acessando remotamente e sincronizando o relógio local dos computadores das três lojas com a internet, por meio do seu notebook, fazendo, assim, um acesso remoto, utilizando comandos específicos, relacionados aos servidores NTP. Para que o proprietário consiga fazer o procedimento quando a sua loja adquirir uma nova máquina, crie um relatório técnico com os comandos necessários, passo a passo, para que ele mesmo sincronize a nova máquina com as demais.

Para completar esse desafio, nesta aula, você verá em detalhes o funcionamento desse processo de sincronização de relógios, incluindo comandos específicos a serem utilizados tanto para a configuração como para a constatação de que o serviço de sincronização está funcionando de maneira adequada. Ficou curioso? Espero que você se sinta motivado a dedicar seu tempo e seus esforços a um estudo que lhe proporcionará chances reais de assimilar os conceitos e as práticas que você utilizará na sua vida profissional.