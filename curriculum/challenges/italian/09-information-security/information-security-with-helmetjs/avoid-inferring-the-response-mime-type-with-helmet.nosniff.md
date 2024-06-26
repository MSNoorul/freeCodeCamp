---
id: 587d8248367417b2b2512c3a
title: Evitare di dedurre il tipo MIME della risposta con helmet.noSniff()
challengeType: 2
forumTopicId: 301574
dashedName: avoid-inferring-the-response-mime-type-with-helmet-nosniff
---

# --description--

As a reminder, this project is being built upon the following starter project on <a href="https://gitpod.io/?autostart=true#https://github.com/freeCodeCamp/boilerplate-infosec/" target="_blank" rel="noopener noreferrer nofollow">Gitpod</a>, or cloned from <a href="https://github.com/freeCodeCamp/boilerplate-infosec/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>. I browser possono svolgere lo sniffing del contenuto o del MIME per sovrascrivere l'intestazione `Content-Type` di una risposta per indovinare ed elaborare i dati utilizzando un tipo di contenuto implicito. Anche se questo può essere conveniente in alcuni scenari, può anche portare ad alcuni attacchi pericolosi. Questo middleware imposta l'intestazione `X-Content-Type-Options` su `nosniff`, istruendo il browser a non bypassare il `Content-Type` fornito.

# --instructions--

Usa il metodo `helmet.noSniff()` sul tuo server.

# --hints--

Il middleware helmet.noSniff() deve essere montato correttamente

```js
(getUserInput) =>
  $.get(getUserInput('url') + '/_api/app-info').then(
    (data) => {
      assert.include(data.appStack, 'nosniff');
      assert.equal(data.headers['x-content-type-options'], 'nosniff');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

