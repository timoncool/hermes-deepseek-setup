# Настройка Hermes Agent с DeepSeek

Скилл запускает русскоязычный мастер настройки в уже работающем Hermes. Он выясняет, для чего вам нужен агент, проверяет текущую модель и рабочую папку, ищет нужные расширения и устанавливает выбранные. В конце вы вместе выполняете первую задачу.

## Для начала

1. [Установите Hermes Desktop](https://hermes-agent.nousresearch.com/desktop).
2. Откройте [кабинет DeepSeek](https://platform.deepseek.com/), пополните API-баланс через **Top up** и создайте ключ в **API keys**.
3. В Hermes нажмите шестерёнку справа сверху. В **Провайдеры → API-ключи → DeepSeek** вставьте ключ и нажмите **Сохранить**. В **Модель → Основная модель** выберите **DeepSeek → deepseek-flash**, нажмите **Применить**, откройте новый сеанс и дождитесь ответа на «Привет!».

## Установка скилла

В терминале на компьютере, где работает Hermes, выполните:

```text
hermes skills install https://raw.githubusercontent.com/timoncool/hermes-deepseek-setup/main/SKILL.md
```

Откройте новый сеанс Hermes и отправьте:

```text
/hermes-deepseek-setup
```

Если терминал неудобен, [скачайте ZIP репозитория](https://github.com/timoncool/hermes-deepseek-setup/archive/refs/heads/main.zip), распакуйте и переместите папку со `SKILL.md` в `%LOCALAPPDATA%\hermes\skills` на Windows или в `~/.hermes/skills` на macOS, Linux и WSL. Назовите папку `hermes-deepseek-setup`. Если у вас свой `HERMES_HOME`, используйте его папку `skills`. Если команда ещё не появилась, введите `/reload-skills` и откройте новый сеанс.

## Что произойдёт после запуска

Hermes задаст несколько простых вопросов. Назовите одну реальную задачу, например «Хочу расшифровывать интервью» или «Хочу подключить Speech Studio и озвучивать сценарии». Скилл предложит план, найдёт актуальные инструкции и проверит, хватает ли встроенных возможностей. После вашего согласия Hermes установит выбранные скиллы, плагины или MCP-подключения. Он покажет ручные шаги, если потребуется войти в сервис или дать разрешение.

Можно принести правила из предыдущего агента. Скилл покажет, что предлагает перенести, и выполнит выбранный перенос. Провайдер, ключи и настройки других профилей без вашего решения остаются прежними.

[Документация Hermes о скиллах](https://hermes-agent.nousresearch.com/docs/guides/work-with-skills/) · [Команды Hermes](https://hermes-agent.nousresearch.com/docs/reference/cli-commands/) · [Подключение DeepSeek](https://api-docs.deepseek.com/quick_start/agent_integrations/hermes/)

## Как устроен скилл

- У [онбординга OpenClaw](https://github.com/openclaw/openclaw/blob/main/docs/start/onboarding-overview.md) взял порядок: сначала рабочая модель, потом персонализация.
- У [NVIDIA NemoClaw User Guide](https://github.com/nvidia/skills/blob/main/skills/nemoclaw-user-guide/SKILL.md) взял один вопрос за раз и запуск согласованных команд самим агентом. Шаги, требующие действий человека, показаны отдельно, как в [Hermes Setup Wizard Generator](https://github.com/NousResearch/hermes-agent/blob/main/website/docs/user-guide/skills/optional/devops/devops-setup-wizard-generator.md).
- По примеру [Research Paper Writing для Hermes](https://github.com/NousResearch/hermes-agent/blob/main/optional-skills/research/research-paper-writing/SKILL.md) подключения подбираются под этап и задачу. Здесь это один небольшой набор под первую рабочую пробу.
