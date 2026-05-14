# Horae (Localized Fork) - Memory Engine for SillyTavern

**Русский** | [English](#english)

Это форк расширения [SillyTavern-Horae](https://github.com/SenriYuki/SillyTavern-Horae), полностью очищенный от захардкоженных китайских промптов и строк.

### Почему этот форк существует?
В оригинальной версии Horae многие системные промпты (для саммари, временных меток и логики) были жёстко прописаны на китайском языке внутри кода. Из-за этого даже при смене языка в настройках, в конспектах и логах постоянно всплывала «китайщина», которая сбивала ИИ с толку.

**Что исправлено:**
- Все скрытые китайские промпты вынесены в систему локализации (`i18n`).
- Исправлены ошибки в коде, приводившие к крашу расширения на не-китайских локалях.
- Полностью переведены на русский/английский технические теги векторной памяти (даты, статусы, события).
- Сохранена полная совместимость со старыми чатами (расширение всё еще понимает старые китайские теги в истории, но само пишет уже на человеческом языке).

---

## English <a name="english"></a>

This is a fork of the [SillyTavern-Horae](https://github.com/SenriYuki/SillyTavern-Horae) extension, fully cleaned of hardcoded Chinese prompts and logic.

### Why does this fork exist?
In the original version of Horae, many system prompts (for summaries, timestamps, and core logic) were hardcoded in Chinese directly within the code. Consequently, even when changing the language in the settings, "Chinese leftovers" would constantly appear in notes and logs, often confusing the AI.

**What has been fixed:**
- All hidden Chinese prompts have been migrated to the localization system (`i18n`).
- Code syntax errors that caused the extension to crash on non-Chinese locales have been resolved.
- Technical tags for vector memory (dates, statuses, events) are now fully localized.
- Full backward compatibility with old chat logs is maintained (the extension still understands legacy Chinese tags in history but generates new data in your preferred language).

---

## Installation / Установка

1. Откройте SillyTavern → Панель расширений (иконка пазла) → **Install Extension**.
2. Вставьте URL этого репозитория: `https://github.com/kykaaj/SillyTavern-Horae.git`
3. Нажмите Install и обновите страницу.

---

## Developer Note: Localization / Заметка для разработчиков

Если вы планируете вносить изменения в код этого форка, пожалуйста, **не используйте захардкоженные строки** (особенно китайские) ни в `index.js`, ни в HTML. 

Используйте встроенную функцию `L()` для динамических строк или `t()` для интерфейса:

```js
// ✅ Правильно (автоматический выбор языка для ИИ)
const text = L('Китайский', 'English', 'Japanese', 'Korean', 'Русский');

// ✅ Правильно (для UI элементов)
showToast(t('common.saveSuccess'), 'success');
```

---
**Original Author:** SenriYuki  
**Fork maintainer:** kykaaj
