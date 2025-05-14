# Home

Bem vindo ao R.U.N.A!

## Integrantes

- Henrique de Freitas Araújo (ricosgames.henrique@gmail.com)
- Jader Oliveira Silva (jaderoliveira28@gmail.com)
- João Pedro Rodrigues Silva (jprs1308@gmail.com)
- Pedro Augusto Gontijo Moura (pedroaugustomoura70927@gmail.com)
- Rafael Adolfo Silva Ferreira (rafael.ferreira11.98@gmail.com)
- Rafael Ferreira da Rocha (rafaelrocha241003@gmail.com)
- Samuel Silva Gomes (silvagomes881@gmail.com)

## Histórico de Versões

Essa seção ficará responsável por descrever as atualizações feitas durante as semanas com o _Sprint_ relativo ao projeto R.U.N.A. Os registros específicos feitos pelos contribuidores do Projeto podem ser verificados no GitHub: [https://github.com/Ak4ai/TasksApp](Github R.U.N.A).

---

### Protótipo Inicial (28/04/25 - 05/05/25)


O protótipo inicial foi concebido com o objetivo de demonstrar a estruturação básica necessária para a criação, organização e gerenciamento de tarefas personalizadas por parte do usuário. Esta etapa visa apresentar ao orientador e demais avaliadores a proposta inicial da interface gráfica, bem como validar a separação modular dos arquivos responsáveis pelas funcionalidades do sistema.

A seguir, descreve-se a estrutura modular adotada, com os arquivos principais e suas respectivas responsabilidades no projeto:

* **`index.html`**: Arquivo principal da interface gráfica. Responsável por estruturar os elementos HTML visíveis ao usuário, como campos de entrada de dados, botões, layout das tarefas e containers para exibição de mensagens e feedbacks.

* **`style.css`**: Define o estilo visual da aplicação, organizando cores, espaçamentos, tipografia, transições e responsividade. Sua modularização permite separar completamente o design do funcionamento lógico do sistema.

* **`auth.js`**: Módulo responsável pela autenticação do usuário via Firebase Authentication. Implementa funcionalidades como login com conta Google, logout e persistência da sessão do usuário.

* **`firebase-config.js`**: Arquivo de configuração do Firebase. Centraliza as credenciais e inicializa os serviços de banco de dados (Firestore), autenticação e demais recursos necessários da plataforma.

* **`script.js`**: Controla funcionalidades de interface gerais, como manipulação de eventos de botões, interações com o DOM e chamadas de funções utilitárias para o comportamento geral do aplicativo.

* **`tarefas.js`**: É o núcleo da lógica de tarefas. Este módulo gerencia a criação, visualização, marcação como concluída, edição e exclusão de tarefas, além de implementar a lógica de recorrência (tarefas periódicas) e atualização em tempo real da interface com base nos dados armazenados no Firestore.

* **`service-worker.js`**: Responsável por implementar o comportamento offline e o cache da aplicação. Este arquivo é parte fundamental da conversão do projeto em uma Progressive Web App (PWA), garantindo que o aplicativo funcione mesmo na ausência de conexão com a internet.

A modularização proposta permite melhor organização do código, facilita manutenções futuras e oferece flexibilidade para expansão das funcionalidades do sistema. Além disso, cada módulo possui uma responsabilidade única e bem definida, respeitando o princípio de *separação de preocupações*, amplamente adotado no desenvolvimento de aplicações modernas baseadas na arquitetura Web.

---


### Segunda Release (05/05/25 - 12/05/25)

**Responsáveis pelo desenvolvimento desta versão:** 
- Henrique de Freitas, Jader Oliveira, João Pedro Rodrigues e Samuel Silva
**Responsáveis pela documentação desta versão:** 
- Pedro Augusto, Rafael Adolfo e Rafael Ferreira

Durante a reunião inicial que precedeu esta semana de desenvolvimento da segunda versão do R.U.N.A, muito foi-se discutido acerca da disposição do software, principalmente sobre as necessidades que deveriam ser atendidas de imediato para um melhor arranjo dos módulos do programa em si. Criou-se um diagrama de usuário como "guia" para os desenvolvedores ao longo do projeto. Assim, para essa primeira semana de desenvolvimento após o protótipo, tinha-se como objetivo:
> Implementar a tipagem de tarefas (Importantes Periódicas, Importantes Não-Periódicas, Personalizadas) visando futuramente integrar-se com o sistema de 'tags' para tarefas.
> Ajustar a frequência selecionada pelo usuário para a recorrência de tarefas periódicas e personalizadas suprindo as necessidades impostas pelo mesmo.
> 

