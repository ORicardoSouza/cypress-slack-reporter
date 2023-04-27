# Cypress Slack Reporter

![Cypress Logo](https://docs.cypress.io/img/logo/cypress-io-bg.png)

Este é um guia para configurar o [Cypress](https://www.cypress.io/) para enviar relatórios para o [Slack](https://slack.com/).

## Instalação

Instale o pacote `cypress-slack-reporter` como uma dependência de desenvolvimento do seu projeto:

```
npm install cypress-slack-reporter --save-dev
```

## Configuração

1. Adicione o seguinte código no arquivo `cypress/support/index.js` para configurar o `cypress-slack-reporter`:

   ```
   const slackReporter = require('cypress-slack-reporter');

   module.exports = (on, config) => {
     slackReporter(config) (on, config);
   };
   ```

2. Crie um webhook no Slack seguindo as instruções descritas na [documentação oficial](https://api.slack.com/messaging/webhooks).

3. Adicione as seguintes variáveis de ambiente no arquivo `.env` do seu projeto, substituindo `<SLACK_WEBHOOK_URL>` pelo URL do webhook do Slack que você criou e `<SLACK_CHANNEL>` pelo nome do canal no Slack para onde deseja enviar as notificações:

   ```
   SLACK_WEBHOOK_URL=<SLACK_WEBHOOK_URL>
   SLACK_CHANNEL=<SLACK_CHANNEL>
   ```

4. Execute os testes do Cypress com o seguinte comando:

   ```
   npm run cypress:run --env reporter=cypress-slack-reporter
   ```

## Documentação oficial

- [Cypress Slack Integration](https://docs.cypress.io/guides/cloud/slack-integration)
- [Cypress Slack Reporter](https://www.npmjs.com/package/cypress-slack-reporter)
