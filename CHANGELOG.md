# История изменений

## 2026-11-02

- Репозиторий создан: шесть общих скиллов агентов - github-workflow, sourcecraft-workflow, yc-postgresql, postgresql-dump, postgresql-restore, browser-screenshots
- Настроена синхронизация зеркал GitHub и SourceCraft: main и теги выравниваются обертками CI обеих платформ скриптом tools/sync_mirrors.py
- Подключен линтинг Markdown: pre-commit хуки, CI-проверки на обеих платформах, команда task markdownlint
- Типографские утилиты оформлены скиллами fix-typography и unwrap-markdown со вложенными скриптами; собственные хуки репозитория переведены на скрипты из скиллов
- Конфигурация markdownlint сокращена до отключения MD013 и MD041, обоснование отключений - в CONTRIBUTING.md
- Механика синхронизации и настройка ключей описаны в CONTRIBUTING.md
