
# 📄 Arquivo `script.js`

## 1. Visão Geral
  O arquivo 'script.js' é responsável por implementar scripts necessários em outras partes do projeto.
  
## 2. Dependências e Importações

```js
import { auth } from './auth.js';
import { db, carregarMeuSimpleID, listarAmigosAceitos } from './firebase-config.js';
import { getAuth, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.0/firebase-auth.js";
import { doc, collection, addDoc, getDocs, Timestamp, deleteDoc, serverTimestamp, setDoc, getDoc, increment } from 'https://www.gstatic.com/firebasejs/11.6.0/firebase-firestore.js';
import { carregarTarefas,mostrarPopup,carregarInventario, calcularDefesa } from './tarefas.js';
```
* **`auth`**: objeto de autenticação do Firebase.
* **`imports from firebase-config`**: instância configurada do Firestore e funcionalidades referentes a interações sociais do software.
* **`imports from firebase-auth.js`**: métodos do Firebase para gerenciar autenticação
* **`imports from firebase-firestore`**: étodos do Firebase para gerenciar documentos
**`imports from tarefas.js`**: auxílio na criação de tarefas, popups, sistema de inventário e PVE.

---

## 3. Funções utilizadas

### 3.1. Mensagens
```js
function mostrarMensagem(mensagem)
```
- Recebe uma mensagem como parâmetro
- Exibe a mensagem ao usuário através do modal
- Utiliza do blur quando há um plano de fundo
- Garante que uma mensagem não sobreponha outra
  <br><br><br>
```js
function exibirProximaMensagem()
```
- Utiliza elementos HTML
- Verifica se há mensagens na fila
- Obtém a primeira mensagem da fila, a exibe e retira da fila
- Se certifica se há mais mensagens a serem exibidas depois do usuário fechar o diálogo
- Exibe a próxima mensagem da fila, caso haja
  <br><br><br>

### 3.2. Blur

```js
function exibirBlurBackground()
```
- Aplica blur em segundo plano
  <br><br><br>

```js
function esconderBlurBackground()
```
- Remove blur
  <br><br><br>

### 3.3. Pop Up
```js
function mostrarPopup(mensagem, duracao = 2000)
```
- Recebe uma mensagem e uma duração (em ms) como parâmetro
- Exibe a janela com a mensagem pela duração escolhida
  <br><br><br>

### 3.4. Verificação de sistema operacional
```js
function isIOSDevice()
```
- Identifica o navegador e o sistema operacional do usuário
- Retorna 'true' se é um dispositivo IOS
  <br><br><br>

### 3.5. Anexação de arquivos
```js
function fileToBase64(file)
```
- Converte arquivos para base64
- Auxilia no upload de anexos
<br><br><br>

### 3.6. Adicionar tarefas

```js
async function adicionarTarefa(descricao, dataLimite)
function ajustarWrappers()
````
- Verifica se o usuário já é autenticado
- Valida a estrutura de dados da tarefa
- Cria uma tarefa e age conforme o seu tipo
- Armazena a tarefa no banco de dados
- Recarrega a lista de tarefas
  <br><br><br>

### 3.7. Função de Swipe

```js
function atualizarVisibilidadeAppBody()
function handleSwipe()
```
Configura a função de swipe:
- Verifica a intensidade do gesto
- Coleta elementos como botões de navegação
- Determina a direção do deslizamento
- Aplica CSS para adicionar uma transição animada
- Atualiza estado da aba ativa
- Configura a visibilidade de elementos
  <br><br><br>

## 4. Manipulação do DOM

### 4.1. Criação de Tarefas
```js
document.getElementById('botao-criar-tarefa').addEventListener('click', handleCreateTask)
```
- Preenche campos obrigatórios
- Chama a função 'adicionarTarefa()' com os dados preenchidos
- Por fim, cria uma tarefa
<br><br><br>

### 4.2. Exclusão de todas as tarefas
```js
document.getElementById('delete-all-tasks-button').addEventListener('click', handleDeleteAllTasks)
```
- Confirmação e validação de usuário antes de excluir
- Remove todas as tarefas do banco de dados
- Recarrega a página após conclusão
  <br><br><br>

### 4.3. Atualização de Interface
```js
document.querySelectorAll('.bottom-nav .nav-button').forEach(btn => {
  btn.addEventListener('click', handleTabChange)
})
```
- Gerencia a transição entre abas
- Atualiza a estilização a partir de classes CSS
- Carrega conteúdo específico
<br><br><br>

### 4.4. Gestos Touch
```js
document.addEventListener('touchstart', handleTouchStart)
document.addEventListener('touchend', handleTouchEnd)
```
- Implemente a função de swipe
- Delimita a sensibilidade do gesto
- Anima as transições entre abas

