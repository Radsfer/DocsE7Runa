# Introdução ao R.U.N.A

##  Sobre o Projeto R.U.N.A

###  **Objetivo do Projeto**

Criar um aplicativo mobile que ajude os usuários a organizarem melhor sua rotina, compromissos e tarefas do dia a dia, permitindo mais produtividade e controle do tempo.

## 🌟 Ideia Central do Projeto (Resumo)

> Criar um app de agenda que seja simples de usar, com visual moderno e que permita ao usuário **criar, organizar e acompanhar tarefas e compromissos** de forma eficiente. O app busca ser um “assistente pessoal leve”, voltado para estudantes e profissionais que precisam de mais organização, mas sem complicações. Além de elementos gameficados para um maior apelo com o público jovem.


###  **Principais Funcionalidades Planejadas**

- Cadastro/Login.
    
- Adicionar tarefas e manipular as mesmas para uma integração coerente com o usuário.
    
- Visualizar a agenda (organização das tarefas) em diferentes formatos.
    
- Auxiliar na criação rotinas e checklists.
    
- Receber lembretes e notificações acerca das tarefas criadas de acordo com a personalização do usuário.
    
- (Extras futuramente: integração com calendário do dispositivo e com os documentos do mesmo, modo foco, estatísticas)
    
##  Ferramentas Utilizadas no Projeto

###  **Desenvolvimento**

- **Visual Studio Code:** Ambiente de desenvolvimento, com
extensões para auxiliar na criação de software.

- **Java Script:** Linguagem de programação moderna e segura,
utilizada no desenvolvimento web e mobile.

- **HTML & CSS:** Como linguagens de marcação para estilização
front end do aplicativo.

###  **Controle de Versão**

- **Git + GitHub**: Controle de versões e colaboração no código-fonte.    

###  **Gerenciamento Ágil**

- **Mattermost**: Organização do backlog e tarefas das sprints.
        
- **Google Drive/Docs**: Armazenamento de arquivos e documentação compartilhada.
    

###  **Comunicação**

- **WhatsApp**: Comunicação rápida entre os membros da equipe.
    
- **Discord**: Reuniões do time, Sprint Reviews e Planning.
    

---


###  Como Priorizar?

Usou-se a técnica **MoSCoW** para organizar:

- **Must have** (essenciais): login, adicionar tarefas, visualização
    
- **Should have** (importantes, mas não essenciais agora): categorias, notificações
    
- **Could have** (desejáveis): pomodoro, estatísticas
    
- **Won’t have (por agora)**: integração com Google Calendar

### Possíveis Gastos Computacionais

A construção de um aplicativo de tarefas baseado em tecnologias Web, como HTML, CSS e JavaScript, implica na criação e manipulação dinâmica de múltiplos elementos de interface, especialmente estruturas _div_ . Essa prática, embora usual, exige atenção ao desempenho, uma vez que a renderização e reatividade desses elementos no navegador têm impacto direto na performance da aplicação, especialmente em dispositivos com recursos limitados, como smartphones mais antigos.

Com o crescimento funcional esperado — incluindo manipulação de tarefas, estilização visual, anexação de arquivos, integração com calendário e agenda, além de aspectos de gamificação — torna-se evidente a necessidade de uma arquitetura eficiente. A densidade de tarefas que um usuário pode acumular, aliada às interações dinâmicas (como marcar tarefas como concluídas, reorganizar prioridades e visualizar estatísticas) demanda uma abordagem otimizada tanto no front-end quanto no back-end, especialmente no gerenciamento e atualização do DOM.

Para oferecer um sistema de autenticação robusto e confiável, optou-se pela utilização do serviço de gerenciamento de identidade do Google Firebase. Essa escolha introduz camadas adicionais de complexidade relacionadas à segurança, modularidade e privacidade dos dados. O sistema precisa lidar com múltiplas sessões, permissões granulares e sincronizações em tempo real, o que exige um planejamento cuidadoso para evitar sobrecarga computacional, especialmente quando usuários estiverem simultaneamente ativos em dispositivos distintos.

A interface gamificada — composta por barras de progresso, níveis de experiência, recompensas visuais e outros elementos de motivação — traz uma camada adicional de complexidade visual e lógica. Tais elementos não apenas aumentam o consumo de recursos gráficos no navegador, mas também exigem ciclos de atualização constantes e armazenamentos intermediários (cache e sincronização com banco de dados), elevando o custo computacional e o número de requisições à nuvem.

Dessa forma, o desenvolvimento do aplicativo exige decisões arquitetônicas que equilibrem responsividade, eficiência de renderização, modularidade de código e escalabilidade. Técnicas como virtual DOM, debouncing em interações frequentes, lazy loading de componentes e compressão de assets tornam-se estratégias fundamentais para manter a fluidez e a experiência do usuário em alto nível.

### Possíveis Riscos e Soluções

Durante o desenvolvimento e a execução do aplicativo, diversos riscos técnicos podem comprometer sua eficiência e confiabilidade. Um dos principais desafios está relacionado à alta densidade de dados que o sistema pode acumular com o tempo, especialmente considerando tarefas periódicas. Esse crescimento pode acarretar em um aumento significativo no custo computacional, impactando diretamente no desempenho da aplicação, tanto no lado do cliente quanto no servidor.

Uma estratégia eficaz de mitigação consiste na personalização consciente e funcional das tarefas, bem como na implementação criteriosa da recriação automatizada de tarefas recorrentes. A lógica por trás dessa funcionalidade deve garantir que tarefas sejam recriadas apenas quando necessário, conforme a frequência previamente selecionada pelo usuário (diária, semanal, etc.), evitando execuções desnecessárias ou duplicações em massa. Dessa forma, o sistema tende a favorecer a criação de um conjunto reduzido de tarefas críticas para o dia a dia, ao mesmo tempo em que mantém flexibilidade para tarefas mais distantes no tempo.

A má implementação da lógica de recorrência representa um risco técnico elevado. Um algoritmo ineficiente, por exemplo, poderia gerar tarefas em cascata de forma exponencial, levando a problemas como estouro de memória ou lentidão sistêmica. Para mitigar tal cenário, o projeto adota uma estrutura modular, com código desacoplado e foco em otimizações de uso de memória e controle de chamadas assíncronas.

Além disso, a integridade dos dados do usuário é considerada prioridade crítica. A perda de dados comprometeria não apenas a confiança na aplicação, mas também sua utilidade prática. Por isso, o sistema se apoia em estratégias de sincronização com o Firebase, backup automático e autenticação segura para garantir a preservação das tarefas registradas, mesmo diante de falhas pontuais.

Embora ações de má-fé por parte de usuários estejam fora do escopo de controle direto, o game design adotado atua como ferramenta preventiva e motivacional. A proposta de recompensas simbólicas, acúmulo de experiência e metas internas visa transformar o cumprimento de tarefas em um desafio pessoal, promovendo o engajamento sem recorrer a práticas competitivas externas.

Dessa forma, os riscos foram mapeados e tratados com soluções específicas que visam garantir a escalabilidade, segurança e fluidez do software em contextos reais de uso.

## Modelo utilizado durante o Projeto

A metodologia organizacional utilizada durante o projeto foi o **Scrum**. Esta é uma metodologia ágil de desenvolvimento de software que ajuda equipes a trabalharem de forma colaborativa, adaptável e eficiente. É ideal para projetos com requisitos que podem mudar com o tempo — como é o caso de aplicativos voltados ao público final. O modelo **Scrum** surgiu no início dos anos 1990 como uma resposta às limitações dos métodos tradicionais de desenvolvimento de software (como o modelo cascata), que muitas vezes resultavam em projetos longos, inflexíveis e com entregas de baixo valor ao cliente. 

Esta metodologia foi escolhida visando empregar as vantagens da mesma (como as reuniões periódicas entre toda equipe para o levantamento de pontos cruciais dentro do projeto) para assim tornar o projeto organicamente bem estruturado.

📚 **Referência recomendada**

> Sutherland, J., & Schwaber, K. (2020). _The Scrum Guide™ – The Definitive Guide to Scrum: The Rules of the Game_. [https://scrumguides.org](https://scrumguides.org/)

Esse é o guia oficial mantido pelos criadores do Scrum. Ele explica os fundamentos, papéis, eventos e artefatos da metodologia, sendo a principal fonte de consulta para equipes ágeis no mundo todo.

### **Elementos principais do Scrum:**

#### 1. **Papéis**

- **Product Owner (PO)**: Responsável por representar os interesses do cliente/usuário. Ele define e prioriza as funcionalidades no _Product Backlog_.
    
- **Scrum Master**: Garante que o time siga os princípios do Scrum, remove impedimentos, facilita reuniões e ajuda todos a colaborarem melhor.
    
- **Time de Desenvolvimento**: Conjunto de programadores, designers e outros membros que constroem o produto.
    

#### 2. **Artefatos**

- **Product Backlog**: Lista priorizada de funcionalidades (histórias de usuário) que o produto precisa ter.
    
- **Sprint Backlog**: Subconjunto do _product backlog_ com as tarefas que serão feitas na sprint atual.
    
- **Incremento**: É o produto parcialmente desenvolvido no final de cada sprint, com uma ou mais funcionalidades já implementadas e testadas.
    

#### 3. **Eventos**

- **Sprint**: Período de tempo fixo (geralmente 1 a 4 semanas) em que o time desenvolve parte do produto.
    
- **Sprint Planning**: Reunião para planejar o que será feito na sprint.
    
- **Daily Scrum (Daily Stand-up)**: Reunião diária de no máximo 15 minutos para alinhamento rápido.
    
- **Sprint Review**: Apresentação do que foi desenvolvido na sprint.
    
- **Sprint Retrospective**: Discussão sobre o que funcionou e o que pode melhorar para a próxima sprint.

    

# Diagrama de uso

aqui vai a documentação

# Interface de usuário
