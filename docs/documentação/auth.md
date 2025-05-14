# 📄 Arquivo `auth.js`

Este módulo é responsável pela **autenticação de usuários via Google** utilizando o **Firebase Authentication** e garantindo a persistência de login entre sessões. Além disso, inicia o carregamento das tarefas e atualização da data no sistema após o login.

---

### Importações

```js
import {
  getAuth,
  signInWithPopup,
  GoogleAuthProvider,
  onAuthStateChanged,
  setPersistence,
  browserLocalPersistence
} from "https://www.gstatic.com/firebasejs/11.6.0/firebase-auth.js";
```

* Importa os métodos necessários para autenticação via Firebase, incluindo controle de estado do usuário e configuração de persistência local.
* Importa o módulo Firebase App (`app`) e as funções `carregarTarefas` e `atualizarDataAtual` do módulo de tarefas.

---

### Inicialização de Autenticação

```js
const auth = getAuth(app);
const provider = new GoogleAuthProvider();
let jaCarregouTarefas = false;
```

* Inicializa o provedor de autenticação com Google.
* Define um controle para evitar carregamento repetido de tarefas em múltiplos eventos de login.

---

### Persistência Local

```js
setPersistence(auth, browserLocalPersistence).then(() => {
```

* Define que a sessão do usuário será armazenada localmente no navegador.
* Garante que o login seja mantido mesmo após o fechamento ou atualização da aba.

---

### Monitoramento de Autenticação

```js
onAuthStateChanged(auth, (user) => {
  ...
});
```

* Quando o usuário autentica ou sai, o estado é atualizado automaticamente.
* Caso logado:

  * O container de login é ocultado.
  * O nome do usuário é exibido na interface.
  * As tarefas são carregadas e a data é atualizada (apenas uma vez).
* Caso deslogado:

  * O botão de login com Google é exibido.
  * O evento de clique é configurado para iniciar o processo de autenticação.

---

### Login com Google

```js
function loginComGoogle() {
  signInWithPopup(auth, provider)
    .then(...)
    .catch(...);
}
```

* Realiza login via janela popup do Google.
* Em caso de sucesso:

  * Esconde o login.
  * Exibe o nome do usuário autenticado.
* Em caso de erro:

  * Mostra um alerta para o usuário.
  * Registra o erro no console para depuração.

---

### Atualização de Data em Intervalo

```js
setInterval(atualizarDataAtual, 60 * 60 * 1000);
```

* Atualiza a data exibida a cada 1 hora para garantir que a exibição permaneça sincronizada com o tempo real.

---

### Exportação

```js
export { auth };
```

* Exporta a instância do objeto `auth` para que outros módulos (como `tarefas.js`) possam consultar o usuário logado.

---

## Resumo Técnico

Este módulo centraliza toda a lógica de autenticação baseada no Firebase com Google como provedor. Ele também garante persistência entre sessões, integra com a interface e inicia os módulos essenciais do aplicativo. A separação em módulos permite um design limpo, reutilizável e fácil de manter.

