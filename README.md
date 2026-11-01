# skills

Общие скиллы агентов для установки через [npx skills](https://skills.sh). Основной репозиторий - GitHub, зеркало - SourceCraft (синхронизация main и тегов обертками CI).

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

Установленные скиллы попадают в `.agents/skills/` проекта (общий каталог, OpenCode читает его напрямую) и связываются с каталогами выбранных агентов.

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

## Синхронизация зеркал

Основная разработка ведется на GitHub (ветки и PR), зеркало - SourceCraft. Скрипт `tools/sync_mirrors.py` выравнивает main и теги fast-forward push-ами: GitHub Actions (`trunk.yml`) пушит в SourceCraft по деплой-ключу из секрета `SYNC_SOURCECRAFT_SSH_KEY`, SourceCraft CI (`trunk-workflow` в `.sourcecraft/ci.yaml`) - в GitHub по секрету `SYNC_GITHUB_SSH_KEY`. Повторный запуск безопасен: при синхронных зеркалах скрипт не выполняет действий.
