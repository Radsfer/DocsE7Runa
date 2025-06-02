
# 📄 Arquivo `script.js`

## Módulos Importados

```js
import { auth } from './auth.js';
```
- Gerencia a autênticação do usuário via Firebase
  <br><br><br>

```js
import { db } from './firebase-config.js';
```
- Representa a instância configurada do Firestore (banco de dados do Firebase)
  <br><br><br>

```js
import { collection, addDoc, getDocs, Timestamp, deleteDoc } from 'https://www.gstatic.com/firebasejs/11.6.0/firebase-firestore.js';
```
Importa algumas funções como:
- `collection`: referencia uma coleção no Firestore
- `addDoc`: adiciona novos documentos
- `getDocs`: busca documentos existentes
- `Timestamp`: manipula datas no formato Firebase
- `deleteDoc`: usado para excluir tarefas
  <br><br><br>

```js
import { carregarTarefas,mostrarPopup,carregarInventario } from './tarefas.js';

```

Importa funções do arquivo 'tarefas.js':
- `carregarTarefas()`
- `mostrarPopup()`
- `carregarInventario()`
---

## Funções utilizadas

### Mensagens
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

### Blur

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

### Pop Up
```js
function mostrarPopup(mensagem, duracao = 2000)
```
- Recebe uma mensagem e uma duração (em ms) como parâmetro
- Exibe a janela com a mensagem pela duração escolhida
  <br><br><br>

### Verificação de sistema operacional
```js
function isIOSDevice()
```
- Identifica o navegador e o sistema operacional do usuário
- Retorna 'true' se é um dispositivo IOS
  <br><br><br>

### Anexação de arquivos
```js
function fileToBase64(file)
```
- Converte arquivos para base64
- Auxilia no upload de anexos
<br><br><br>

### Adicionar tarefas

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

### Função de Swipe

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

## Manipulação do DOM

### Criação de Tarefas
```js
document.getElementById('botao-criar-tarefa').addEventListener('click', handleCreateTask)
```
- Preenche campos obrigatórios
- Chama a função 'adicionarTarefa()' com os dados preenchidos
- Por fim, cria uma tarefa
<br><br><br>

### Exclusão de todas as tarefas
```js
document.getElementById('delete-all-tasks-button').addEventListener('click', handleDeleteAllTasks)
```
- Confirmação e validação de usuário antes de excluir
- Remove todas as tarefas do banco de dados
- Recarrega a página após conclusão
  <br><br><br>

### Atualização de Interface
```js
document.querySelectorAll('.bottom-nav .nav-button').forEach(btn => {
  btn.addEventListener('click', handleTabChange)
})
```
- Gerencia a transição entre abas
- Atualiza a estilização a partir de classes CSS
- Carrega conteúdo específico
<br><br><br>

### Gestos Touch
```js
document.addEventListener('touchstart', handleTouchStart)
document.addEventListener('touchend', handleTouchEnd)
```
- Implemente a função de swipe
- Delimita a sensibilidade do gesto
- Anima as transições entre abas

