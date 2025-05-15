## Análise do Diagrama de Usuário Inicial — Projeto R.U.N.A.

![Diagrama de Usuário do R.U.N.A.](../img/diagrama-usuario-runa.png)

O diagrama apresentado é uma representação clara e funcional da estrutura lógica inicial do aplicativo **R.U.N.A.**, dividida entre duas camadas principais: o que é **visível para o usuário** e o que é **não visível para o usuário**.

### Camada Visível para o Usuário

Esta camada reflete as interações diretas que o usuário terá com a interface do sistema, contemplando:

- **Cadastro/Login**: Entrada inicial no sistema, integrando autenticação com o backend (como citado abaixo).
- **Tela de Entrada**: Interface principal de acesso às tarefas e funcionalidades. Apresenta a categorização das tarefas em:
  - **Importante Periódico**: Tarefas recorrentes (ex: aniversários).
  - **Importante Não Periódico**: Tarefas pontuais (ex: prova).
  - **Personalizado**: Tarefas definidas livremente pelo usuário (ex: jogar futebol com amigos).
- **Configurações**: Permite personalização, ativação/desativação de notificações, definição de tags e ajuste visual.
- **Gatilhos**: Interface para ajuste de gatilhos relacionados a tempo ou localização.

### Camada Não Visível para o Usuário

Esta camada compreende a lógica de funcionamento do sistema, não acessada diretamente, mas fundamental para a operação correta da aplicação:

- **Request para o servidor AWS**: Responsável por armazenar e validar login dos usuários.
- **Classificação Padrão das Tarefas**: Estabelece uma ordem de prioridade e exibição, com:
  - Tarefas não periódicas importantes aparecendo primeiro.
  - Tarefas periódicas importantes em segundo.
  - Tarefas personalizadas sendo tratadas conforme decisão do usuário.
- **Gatilhos de Tarefa**: Todo tipo de tarefa está atrelado a um gatilho por tempo ou localização.
- **Funcionalidades Internas**: Inclui o controle de tabs, lógica de botões e gerenciamento de tags, crucial para a fluidez e funcionalidade da interface.

### Considerações

O diagrama está bem estruturado e evidencia preocupações essenciais no desenvolvimento da aplicação, como modularidade, usabilidade e lógica de funcionamento. Ele também ajuda a manter a visão clara da separação entre front-end e lógica de negócios (back-end), o que é essencial para a escalabilidade futura do R.U.N.A.

> Este mapeamento inicial fornece uma base sólida para futuras decisões de arquitetura e implementação, além de facilitar a comunicação entre desenvolvedores, designers e stakeholders.


