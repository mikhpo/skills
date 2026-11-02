# История изменений

## 2026-11-02

- Репозиторий создан: шесть общих скиллов агентов - github-workflow, sourcecraft-workflow, yc-postgresql, postgresql-dump, postgresql-restore, browser-screenshots
- Настроена синхронизация зеркал GitHub и SourceCraft: main и теги выравниваются обертками CI обеих платформ скриптом tools/sync_mirrors.py
- Подключен линтинг Markdown: pre-commit хуки (включая типографику и развертывание переносов), CI-проверки на обеих платформах, команда task markdownlint
- Механика синхронизации и настройка ключей описаны в CONTRIBUTING.md
