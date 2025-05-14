# 📄 Arquivo `firebase-config.js`

Este arquivo é responsável pela **configuração e inicialização do Firebase** no projeto. Ele garante o acesso aos serviços essenciais da plataforma, como o Firestore e Analytics, e exporta as instâncias necessárias para uso em outros módulos do sistema.

---

### Importações

```js
import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.0/firebase-app.js";
import { getAnalytics } from "https://www.gstatic.com/firebasejs/11.6.0/firebase-analytics.js";
import { getFirestore } from "https://www.gstatic.com/firebasejs/11.6.0/firebase-firestore.js";
```

* `initializeApp`: Responsável por inicializar o app Firebase com a configuração fornecida.
* `getAnalytics`: Permite coleta e análise de métricas de uso do aplicativo.
* `getFirestore`: Ativa o banco de dados NoSQL Firestore, usado para persistência de dados no projeto.

---

### Configuração do Firebase

```js
const firebaseConfig = {
  apiKey: "...",
  authDomain: "...",
  ...
};
```

* Objeto contendo as chaves de configuração do projeto no console do Firebase.
* Cada campo corresponde a um recurso essencial (como domínio de autenticação, identificador do projeto, etc).
* **Importante**: Essas chaves públicas são seguras para projetos client-side e não expõem dados sensíveis.

---

### Inicialização dos Serviços

```js
const app = initializeApp(firebaseConfig);
const analytics = getAnalytics(app);
const db = getFirestore(app);
```

* `app`: Contém a instância principal do Firebase, a ser compartilhada entre os módulos.
* `analytics`: Ativa o monitoramento de uso e performance.
* `db`: Instância do banco Firestore, usada para leitura e escrita de dados (ex: tarefas, usuários).

---

### Exportação

```js
export { app, db };
```

* Permite que `app` e `db` sejam utilizados em outros arquivos do sistema, como por exemplo:

  * `auth.js` para autenticação de usuários.
  * `tarefas.js` para manipulação dos dados de tarefas no Firestore.

---

### Resumo Técnico

O arquivo `firebase-config.js` representa o ponto central de **integração entre o aplicativo e os serviços Firebase**, garantindo modularidade e organização do código. A separação clara da configuração favorece a manutenção, o reuso e facilita o processo de atualização de credenciais no futuro.
