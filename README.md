# skills

Общие скиллы агентов для установки через [npx skills](https://skills.sh). Репозиторий доступен на GitHub и SourceCraft, main и теги синхронизируются автоматически (см. [CONTRIBUTING.md](CONTRIBUTING.md)).

## Установка

Из корня проекта:

```bash
npx skills add mikhpo/skills
```

CLI предложит выбрать скиллы и агентов. Выборочные установки:

```bash
npx skills add mikhpo/skills --skill sourcecraft-workflow --skill github-workflow
npx skills add mikhpo/skills -g          # глобально, для всех проектов
```

Установленные скиллы попадают в общий каталог `.agents/skills/` проекта и связываются с каталогами выбранных агентов.

## Обновление

```bash
npx skills check     # проверить наличие обновлений
npx skills update    # обновить установленные скиллы
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

## Разработка репозитория

Скиллы редактируются в `skills/<имя>/SKILL.md`. Правки вносятся обычным циклом ветка-PR на любой из платформ; требования к текстам - тот же стиль, что в самих скиллах: русский язык, дефис вместо длинного тире, прямые кавычки. Хуки pre-commit проверяют тексты при каждом коммите; разовая проверка - `task markdownlint`. Механика синхронизации зеркал - в [CONTRIBUTING.md](CONTRIBUTING.md).
