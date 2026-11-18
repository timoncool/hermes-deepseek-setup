# Настройка Hermes Agent с DeepSeek

Скилл запускает русскоязычный мастер настройки в уже работающем Hermes. Он выясняет, для чего вам нужен агент, проверяет текущую модель и рабочую папку, ищет нужные расширения и устанавливает выбранные. В конце вы вместе выполняете первую задачу.

## Для начала

1. [Установите Hermes Desktop](https://hermes-agent.nousresearch.com/desktop).
2. Откройте [кабинет DeepSeek](https://platform.deepseek.com/), пополните API-баланс через **Top up** и создайте ключ в **API keys**.
3. В Hermes нажмите шестерёнку справа сверху. В **Провайдеры → API-ключи → DeepSeek** вставьте ключ и нажмите **Сохранить**. В **Модель → Основная модель** выберите **DeepSeek → deepseek-flash**, нажмите **Применить**, откройте новый сеанс и дождитесь ответа на «Привет!».

## Как запустить

Как только DeepSeek ответит в Hermes, отправьте туда **одну ссылку на этот репозиторий**.

https://github.com/timoncool/hermes-deepseek-setup

Hermes установит скилл и начнёт настройку в этом же чате.

<details>
<summary>Инструкция для Hermes Agent</summary>

Если пользователь прислал ссылку на этот репозиторий без текста, это вход в мастер настройки. Если он явно задал другой вопрос о репозитории, ответь на вопрос.

1. Проверь, доступен ли скилл `hermes-deepseek-setup`. Если его нет, используй штатный установщик Hermes. Вызови из инструмента терминала `hermes skills install https://raw.githubusercontent.com/timoncool/hermes-deepseek-setup/main/SKILL.md` для профиля, в котором идёт этот чат. Сохрани штатную проверку скилла. Если Hermes покажет запрос подтверждения, дождись подтверждения в интерфейсе.
2. Загрузи `skill_view("hermes-deepseek-setup")` в текущем сеансе. Если после установки индекс ещё не обновился, прочитай установленный `SKILL.md` прямо с диска. Если инструмент установки недоступен, прочитай [исходный SKILL.md](https://raw.githubusercontent.com/timoncool/hermes-deepseek-setup/main/SKILL.md) и проведи настройку здесь, указав, что скилл не сохранён на диск.
3. Сразу выполни первый шаг скилла в этом же разговоре. Начни с первого вопроса по-русски. Не проси пользователя открыть терминал, вызвать слэш-команду или начать новый сеанс.

</details>

## Что произойдёт после запуска

Hermes задаст несколько простых вопросов. Назовите одну реальную задачу, например «Хочу расшифровывать интервью» или «Хочу подключить Speech Studio и озвучивать сценарии». Скилл предложит план, найдёт актуальные инструкции и проверит, хватает ли встроенных возможностей. После вашего согласия Hermes установит выбранные скиллы, плагины или MCP-подключения. Он покажет ручные шаги, если потребуется войти в сервис или дать разрешение.

Можно принести правила из предыдущего агента. Скилл покажет, что предлагает перенести, и выполнит выбранный перенос. Провайдер, ключи и настройки других профилей без вашего решения остаются прежними.

[Документация Hermes о скиллах](https://hermes-agent.nousresearch.com/docs/guides/work-with-skills/) · [Команды Hermes](https://hermes-agent.nousresearch.com/docs/reference/cli-commands/) · [Подключение DeepSeek](https://api-docs.deepseek.com/quick_start/agent_integrations/hermes/)

## Как устроен скилл

- У [онбординга OpenClaw](https://github.com/openclaw/openclaw/blob/main/docs/start/onboarding-overview.md) взял порядок: сначала рабочая модель, потом персонализация.
- У [NVIDIA NemoClaw User Guide](https://github.com/nvidia/skills/blob/main/skills/nemoclaw-user-guide/SKILL.md) взял один вопрос за раз и запуск согласованных команд самим агентом. Шаги, требующие действий человека, показаны отдельно, как в [Hermes Setup Wizard Generator](https://github.com/NousResearch/hermes-agent/blob/main/website/docs/user-guide/skills/optional/devops/devops-setup-wizard-generator.md).
- По примеру [Research Paper Writing для Hermes](https://github.com/NousResearch/hermes-agent/blob/main/optional-skills/research/research-paper-writing/SKILL.md) подключения подбираются под этап и задачу. Здесь это один небольшой набор под первую рабочую пробу.
