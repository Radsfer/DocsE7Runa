# 📄 Arquivo `service-worker.js`

Este arquivo implementa um **Service Worker**, responsável por permitir o funcionamento **offline** do aplicativo através do uso da **Cache API**. Ele intercepta requisições de rede e serve arquivos armazenados localmente quando possível, garantindo que o aplicativo continue acessível mesmo sem conexão com a internet.

---

### Instalação e Pré-Caching

```js
self.addEventListener('install', function(event) {
  event.waitUntil(
    caches.open('my-cache').then(function(cache) {
      return cache.addAll([
        '/',
        '/index.html',
        '/style.css',
        '/script.js',
      ]);
    })
  );
});
```

* O evento `install` é acionado quando o Service Worker é instalado pela primeira vez.
* `caches.open('my-cache')`: Cria (ou abre) um cache nomeado.
* `cache.addAll([...])`: Armazena os arquivos listados para uso offline.
* Arquivos importantes como HTML, CSS e JS são pré-cacheados para garantir que a interface básica do app esteja disponível mesmo sem conexão.

---

### Interceptação de Requisições (`fetch`)

```js
self.addEventListener('fetch', function(event) {
  event.respondWith(
    caches.match(event.request).then(function(response) {
      return response || fetch(event.request);
    })
  );
});
```

* O evento `fetch` é acionado sempre que o app faz uma requisição de rede.
* `caches.match(event.request)`: Verifica se o recurso já está no cache.
* Se sim, retorna o conteúdo em cache.
* Se não, realiza um `fetch()` na rede.
* Esse comportamento implementa uma **estratégia de fallback**: usa primeiro o cache, e recorre à rede apenas se necessário.

---

### Possíveis Melhorias Futuras

* **Versão de cache**: Usar um nome como `'my-cache-v1'` para facilitar atualizações.
* **Cache dinâmico**: Adicionar suporte para armazenar dinamicamente novas páginas acessadas.
* **Atualização de cache**: Implementar lógica de `activate` para remover caches antigos.

---

### Resumo

Este `Service Worker` fornece um **modo offline básico**, garantindo que os arquivos essenciais estejam sempre disponíveis para o usuário. Ele melhora a experiência em redes instáveis e contribui para o desempenho geral do PWA.

---

