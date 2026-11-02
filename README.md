# skills

Общие скиллы агентов для установки через [npx skills](https://skills.sh). Репозиторий доступен на [GitHub](https://github.com/mikhpo/skills) и [SourceCraft](https://sourcecraft.dev/mikhpo/skills), main и теги синхронизируются автоматически (см. [CONTRIBUTING.md](CONTRIBUTING.md)).

## Установка

Глобально - скиллы доступны во всех проектах машины:

```bash
npx skills add mikhpo/skills -g
```

В проект - альтернативный вариант: скиллы размещаются в каталоге проекта (`.agents/skills/`) и версионируются вместе с ним:

```bash
npx skills add mikhpo/skills
```

CLI предложит выбрать скиллы и агентов. Выборочные установки:

```bash
npx skills add mikhpo/skills -g --skill sourcecraft-workflow --skill github-workflow
```

## Обновление

```bash
npx skills check         # проверить наличие обновлений
npx skills update -g     # обновить глобальные скиллы
npx skills update -p     # обновить скиллы проекта
```

## Скиллы

| Скилл | Назначение |
| --- | --- |
| sourcecraft-workflow | Работа с SourceCraft через CLI src: задачи, PR, CI, логи кубов |
| github-workflow | Работа с GitHub через CLI gh: задачи, PR, вложения, CI |
| yc-postgresql | Управление кластером Managed PostgreSQL в Yandex Cloud через yc |
| postgresql-dump | Логический дамп PostgreSQL утилитой pg_dump |
| postgresql-restore | Восстановление PostgreSQL из дампа утилитой pg_restore |
| browser-screenshots | Скриншоты страниц сайта: headless Chrome, playwright, PIL |
| fix-typography | Автозамена запрещенных символов типографики в текстовых файлах |
| unwrap-markdown | Развертывание жестких переносов строк в Markdown: абзац - одна строка |

## Разработка репозитория

Скиллы редактируются в `skills/<имя>/SKILL.md`. Правки вносятся обычным циклом ветка-PR на любой из платформ. Хуки pre-commit проверяют тексты при каждом коммите; разовая проверка - `task markdownlint`. Механика синхронизации зеркал - в [CONTRIBUTING.md](CONTRIBUTING.md).
