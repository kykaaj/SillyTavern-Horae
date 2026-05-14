# Horae (Localized Fork) — "No More Chinese Bullshit" Edition

**English** | [Русский](README.ru.md)

> *"Why is my AI suddenly writing notes in Chinese?"* — Because the original author hardcoded prompts into the source code. We fixed that.

This is a fork of the [SillyTavern-Horae](https://github.com/SenriYuki/SillyTavern-Horae) extension. We took it, gutted it, and scrubbed away all the hardcoded Chinese strings that were ruining the RP experience for the rest of the world.

### What happened here:
*   **Killed hardcoded Chinese prompts**: Summaries and time tags are now generated in your actual language instead of the author's native tongue.
*   **Fixed crashes**: The original version liked to crash on non-Chinese locales. Now it doesn't.
*   **Vector Memory is clean**: All technical tags in semantic search are now localized.
*   **Backward Compatibility**: If you have a massive chat history with legacy Chinese tags — don't worry, the extension still understands them. It just won't generate new ones.

---

## Installation

1. In SillyTavern, go to Extensions (puzzle icon) -> **Install Extension**.
2. Paste this URL: `https://github.com/kykaaj/SillyTavern-Horae.git`
3. Click Install, refresh the page, and enjoy an English (or Russian) experience.

---

## Developer Note: Localization

If you're going to contribute or mess with the code — **I beg of you**, do not hardcode strings. Use the `L()` function for AI prompts and `t()` for UI elements. Let's not bring the Chinese chaos back.

```js
// ✅ CORRECT (auto-selects language)
const msg = L('中文', 'English', '日本語', '한국어', 'Русский');

// ✅ ALSO CORRECT (for UI/toasts)
showToast(t('common.saveSuccess'), 'success');
```

---
**Original Author:** SenriYuki  
**Fork maintainer:** kykaaj
