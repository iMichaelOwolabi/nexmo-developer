---
title: Node
language: node
---

```js
const Vonage = require('@vonage/server-sdk');

const options = {
  apiHost: 'api-sg-1.nexmo.com',
  restHost: 'rest-sg-1.nexmo.com'
}

const vonage = new Vonage({
    apiKey: API_KEY,
    apiSecret: API_SECRET,
    applicationId: APP_ID,
    privateKey: PRIVATE_KEY_PATH,
    signatureSecret: SIGNATURE_SECRET,
    signatureMethod: SIGNATURE_METHOD
  }, options);
```
