
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

```js
function mostrarPopup(mensagem, duracao = 2000)
```
- Recebe uma mensagem e uma duração (em ms) como parâmetro
- Exibe a janela com a mensagem pela duração escolhida
  <br><br><br>

```js
function isIOSDevice()
```
- Identifica o navegador e o sistema operacional do usuário
- Retorna 'true' se é um dispositivo IOS
  <br><br><br>

```js
async function adicionarTarefa(descricao, dataLimite)
````
- Verifica se o usuário já é autenticado
- Verifica o tipo da tarefa (periódico, personalizado...)
- Cria uma tarefa e age conforme o seu tipo
- Armazena a tarefa no banco de dados
- Recarrega a lista de tarefas
  <br><br><br>

```js
function handleSwipe()
```
Configura a função de swipe:
- Verifica a intensidade do gesto
- Coleta elementos como botões de navegação
- Determina a direção do deslizamento
- Aplica CSS para adicioanr uma transição animada
- Atualiza estado da aba ativa
  <br><br><br>

```js
function fileToBase64(file) {...}
```
- Permite a anexação de arquivos
  <br><br><br>
---
## Manipulação do DOM

```js
document.addEventListener('DOMContentLoaded', () => { ... })
```
- Define o comportamento inicial da página ao ser carregada
  <br><br><br>

```js
document.getElementById('criar-button').addEventListener('click', () => { ... }) 
```
- Abre modal
  <br><br><br>

```js
document.getElementById('fechar-modal').addEventListener('click', () => { ... })
```
- Fecha modal
  <br><br><br>

```js
import { atualizarDataAtual } from './tarefas.js';
  
  document.addEventListener('DOMContentLoaded', () => { ... })
```
- Atualiza a data
- Configura o sistema de tabs
  <br><br><br>

```js
document.querySelectorAll('.bottom-nav .nav-button').forEach(btn => 
```
- Ativa aba correspondente
- Atualiza o estado dos botões
- Carrega tarefa se for a aba de tasks
  <br><br><br>


```js
document.getElementById('delete-all-tasks-button').addEventListener('click', ...)
```
- Deleta todas as tarefas após uma confirmação e verificação<br><br><br>

