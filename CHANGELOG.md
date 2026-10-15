# История выпусков

## v0.5.0-alpha.4 — Background Work, Recovery & Diagnostics Preview

Крупный публичный alpha-срез после цикла работ над фоновой Session Memory, восстановлением, ошибками и диагностикой.

### Главное

- фоновые BASE / CHECKPOINT итоги длинных сессий;
- durable background tasks;
- восстановление после части ошибок модели / runtime / API;
- Manual Retry;
- Attention Center для фоновых проблем;
- развитие общего Error Protocol;
- журнал ошибок и диагностики;
- настройки фоновых итогов в Диспетчере мозга;
- отдельное разрешение API для background Summary;
- настройка timeout;
- светофор реального состояния мозга и фоновой работы;
- улучшенная защита cursor / chunk / summary;
- bounded recovery вместо бесконечных повторов;
- Split/Merge, Compact Repair, Generation Headroom, Reasoning Headroom, Adaptive Baseline;
- release hygiene: runtime logs и prompt dumps не входят в публичную сборку.

### Проверка

- 3280 автоматических тестов — PASS;
- один 70K сценарий / 116 сообщений полностью обработан 8 локальными профилями и 1 API-профилем;
- во всех прогонах достигнуто 116/116 и `pending=False`;
- portable ZIP проверен на чистой распаковке;
- встроенный llama.cpp Runtime Pack работает;
- публичный ZIP не содержит исходники, тесты, `.venv`, guard logs, prompt dumps и GGUF-модели.

### Release candidate

- внутренний Git commit: `261e5c18c6f17e300ca5d21abe495879891c39d5`;
- Windows x64;
- portable ZIP;
- SHA256: `47A46DC678088D7FC3D37AAEA3EEA032972A1A035B15AA23D4E98DCDAD9EE078`.

### Важно

Summary Quality ещё не финальна. См. `KNOWN_ISSUES.md`.

---

## v0.5.0-alpha.3 — Portable Fix

Исправлена portable-сборка: в архив включён `llama.cpp Runtime Pack`.

Дополнительно улучшены:

- ошибки внешних API;
- диагностика OpenRouter;
- повторное добавление сообщения после неудачного API-запроса;
- лимит обычного API-ответа;
- восстановление Project Brief;
- автоматический сборщик portable-релиза.

---

## v0.5.0-alpha.2 — Windows x64

Крупное обновление Диспетчера мозга и API-контура.

Добавлены / улучшены:

- дерево провайдеров и моделей;
- OpenRouter;
- Gemini;
- основа OpenAI Responses API;
- новый светофор состояния;
- Planning Intake;
- Structured Outputs;
- Error Protocol / диагностика;
- обработка длинных ответов;
- portable Windows x64.

---

## v0.5.0-alpha.1

Первая публичная тестовая сборка LocalModAI для Windows.

### Добавлено

- создание и открытие проектов;
- несколько связанных чатов внутри проекта;
- базовая Project Memory;
- подключение локальных GGUF-моделей;
- краткое понимание проекта перед планированием;
- Planning Intake;
- Plan Candidate;
- несколько независимых вариантов плана;
- проверка языка проекта;
- повторная попытка после пустого ответа модели;
- сохранение старых вариантов для сравнения.
