[![](https://ampli-images.s3.amazonaws.com/production/31116631-031a-433d-b0ab-ce1dfe755108/original)](https://ampli-images.s3.amazonaws.com/production/31116631-031a-433d-b0ab-ce1dfe755108/original)

### **Qual é o foco da aula?**

Nesta aula, veremos detalhes específicos para utilização do Docker, abordando questões de configuração e uso do Apache.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- examinar o conceito e aplicação do Docker;
- analisar o modo de instalação do Docker;
- interpretar uma série de comandos no Docker.

**Introdução da aula**

Você já pensou de que maneira são orquestrados os serviços quando acessamos um website? Uma das principais plataformas de conteinerização utilizadas atualmente é o Docker, principal assunto desta aula. Aqui vamos trabalhar com a instalação do Docker no sistema operacional GNU/Linux Ubuntu e aprender alguns dos principais comandos que podem ser utilizados na plataforma Docker. Você já parou para pensar em quais comandos devem ser usados para que essa orquestração de serviços funcione adequadamente?

Quando falamos de sistemas distribuídos, é inevitável falar sobre virtualização e conteinerização. Na prática, essas tecnologias são frequentemente utilizadas por grandes empresas. Você concluiu seu curso e está participando de um processo seletivo para uma oportunidade como trainee na área de DevOps da maior empresa nacional de portal de notícias, cujos clientes que consomem o conteúdo disponibilizado por essa empresa são bancos, em sua maioria. Você está se saindo muito bem no processo seletivo e agora será submetido ao teste final, uma atividade prática com Docker.

O coordenador está gostando de seu desempenho nos testes e diz que, caso você consiga orquestrar o servidor web Apache em um _cluster_ simples, a vaga será sua. Desta forma:

1. Crie um _cluster_ com cinco réplicas do servidor web Apache utilizando o Docker Swarm;
2. Verifique em quais nós do _cluster_ esse serviço está rodando;
3. Acesse a página de boas-vindas desse servidor Apache através do(s) endereço(s) IPv4 de cada nó onde esse serviço web estiver rodando.

Para completar o desafio, nessa aula você verá, em detalhes, como se utiliza o Docker, incluindo comandos específicos a serem utilizados, tanto para configuração, quanto para constatação de que o serviço de Apache está funcionando de maneira adequada. Ficou curioso? Vamos lá!