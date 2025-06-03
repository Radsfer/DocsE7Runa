# 📄 Arquivo `notifications.js`

## 1. Visão Geral

O módulo **`notifications.js`** implementa a lógica de notificações do aplicativo, permitindo com que o usuário agende as notificações das tarefas que ele desejar. Isso é feito através da integração com o Firebase Firestore para armazenar as notificações que são agendadas.

## 2. Dependências e Importações

```js
import { messaging } from './firebase-config.js';
import { getToken, onMessage } from "https://www.gstatic.com/firebasejs/11.6.0/firebase-messaging.js";
import { getFirestore, doc, setDoc, collection, addDoc, serverTimestamp } from "https://www.gstatic.com/firebasejs/11.6.0/firebase-firestore.js";
import { getAuth, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.0/firebase-auth.js";
```

* `messaging`: biblioteca de envio de mensagens do Firebase
* `getToken`: pega tokens do Firebase
* `onMessage`: gerencia notificações em segundo plano
* `getFirestore`: acessa a database do Firestore
* `doc`: biblioteca de documentos
* `setDoc`: cria e/ou sobrescreve documentos
* `collection`: contém os documentos
* `addDoc`: adiciona novos documentos
* `serverTimestamp`: biblioteca de fuso horário do Firestore
* `getAuth`: acessa a autenticação do Firebase 
* `onAuthStateChanged`: monitora mudanças no estado de autenticação do usuário

## 3. Estado Global
```js
let pendingFcmToken = null;
let _isIOS = null;
```

## 4. Funções Utilizadas

```js
async function solicitarPermissaoNotificacao()
```

* Solicita ao usuário a permissão para usar notificações
*  Salva o token FCM no Firestore, vinculado ao UID do usuário em uma subcoleção
*  Guarda o token para salvar depois da autenticação

```js
function isIOS()
```

* Verifica se o dispostivo utilizado é um iOS


```js
function mostrarModalNotificacaoIOS()
```

* Mostra o modal após login se o dispositivo for um iOS
* Não mostra se o usuário aceitou a permissão de notificações
* Não mostra se o usuário marcou a opção "nunca mostrar"

```js
async function buscarTokenFCM()
```

* Função dedicada à buscar o token FCM e salvá-lo no Firestore de forma semelhante à função `solicitarPermissãoNotificacao()`. 

