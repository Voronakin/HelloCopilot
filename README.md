# HelloCopilot
Описаны варианты как опробовать кодогенерацию с помощью нейросетей.

# Бесплатно

## GitHub Copilot

GitHub Copilot — это инструмент искусственного интеллекта для автоматического дополнения кода, помогающий разработчикам быстрее писать, рефакторить, комментировать и объяснять код на десятках языков программирования прямо в популярных средах разработки (VS Code, Visual Studio, JetBrains и др.). Он анализирует контекст и предлагает релевантные варианты — от строк до целых функций, а также может отвечать на вопросы по коду в чате

### Плагин для JetBrains IDE
https://plugins.jetbrains.com/plugin/17718-github-copilot


### Плагин для Visual Studio Code 
https://marketplace.visualstudio.com/items?itemName=GitHub.copilot

### Опробованная схема
Visual Studio Code + плагин Copilot + Ubuntu

#### Тарифные планы
https://github.com/features/copilot#pricing

## Проблемы
PS IP адреса могут быть заблокированы

## Безопасность
TODO Разобраться с ограничением доступа к чувствителдьным файлам и папкам

# Платно

## Claude Code
Claude Code — это мощный агентный инструмент для программистов от Anthropic, который интегрируется с терминалом и популярными IDE (VS Code, JetBrains), существенно ускоряя работу с кодом и автоматизируя рутинные задачи.

Статья с опытом использования (рекомендуется для первичного ознакомления)
https://habr.com/ru/companies/otus/articles/929624/

### Установка

см. https://docs.claude.com/en/docs/claude-code/overview

1. Установите Node.js версии 18+.

2. Выполните команду установки:

   ```bash
   npm install -g @anthropic-ai/claude-code
   ```

3. Запустите в директории вашего проекта:

    ```bash
    claude
    ```
#### Возможные ошибки
1. При наличие ошибок необходимо перепроверить версию Node.js
    ```bash
    node -v
    ```
Если она меньше 18-й, то необходимо указать нужную.


    nvm use 18


### Интеграция с IDE
При работе с JetBrains IDE есть плагин (https://plugins.jetbrains.com/plugin/27310-claude-code-beta-), при нажатии на него откроется стилизованная консоль.

Подробнее об интеграции см. https://docs.claude.com/en/docs/claude-code/ide-integrations


### Claude Code + API DeepSeek (через Anthropic-совместимый эндпоинт)
С подключением к стандартному API нейросети могут возникнут проблемы.
В качестве альтернативы можно использовать API DeepSeek
см. https://onedollarvps.com/blogs/how-to-use-deepseek-v3-1-in-claude-code.html

Например в консоли проекта запустить следующий скрипт

     sh ../start-claude-deepseek.sh

со следующим содержимым:

    #!/bin/bash
    # DeepSeek V3.1 с Claude Code
    
    export ANTHROPIC_BASE_URL="https://api.deepseek.com/anthropic"
    export ANTHROPIC_AUTH_TOKEN="sk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
    export ANTHROPIC_MODEL="deepseek-chat"
    export ANTHROPIC_SMALL_FAST_MODEL="deepseek-chat"
    
    # Запуск Claude Code
    claude "$@"

### Оплата API DeepSeek
Минимальный платеж порядка 2$.
#### ВНИМАНИЕ. Все последующие действия совершаются исключительно на ваш страх и риск

При затруднении с оплатой на платформе DeepSeek (https://platform.deepseek.com/top_up) можно воспользоваться например 
следующей услугой https://plati.market/itm/deepseek-api-bystroe-popolnenie-api-balansa/5039497?ai=1416461 или аналогичной.
В данном случае, для пополнения необходимо передавать доступы к аккаунту DeepSeek, поэтому НАСТОЯТЕЛЬНО РЕКОМЕНДУЕТСЯ создать отдельный 
аккаунт DeepSeek, доступы к которому уже передавать, а потом менять пароль.

# Рекомендации 
[![Видео на YouTube](https://img.youtube.com/vi/8tVAeYASYT0/0.jpg)](https://youtu.be/8tVAeYASYT0)
