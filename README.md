# @scandicboy/dsh-locale-ru

[![npm version](https://img.shields.io/npm/v/@scandicboy/dsh-locale-ru.svg)](https://www.npmjs.com/package/@scandicboy/dsh-locale-ru)
[![license](https://img.shields.io/npm/l/@scandicboy/dsh-locale-ru.svg)](./LICENSE)
[![GitHub](https://img.shields.io/badge/GitHub-scandicbo7%2Fdsh--locale--ru-181717?logo=github)](https://github.com/scandicbo7/dsh-locale-ru)

**Русская локализация интерфейса [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness).**

Плагин-бандл добавляет язык **«Русский»** и переводит все строки веб-интерфейса: чат, боковую панель, настройки, статусы задач, планирование, цели, расписания, предпросмотр документов, управление плагинами и т.д.

> **Автор:** [scandicboy](https://www.npmjs.com/~scandicboy)
>
> **Сгенерировано с помощью ИИ.** На генерацию полного перевода затрачено **≈ 33 000 000 токенов**.

---

## Возможности

- ✅ Язык **«Русский»** в настройках (Settings → General → Language)
- ✅ **58 пространств имён / 2615 строк** перевода
- ✅ Переключение языка мгновенно, без перезагрузки страницы
- ✅ Английский фолбэк для непереведённых строк
- ✅ Без зависимостей от сторонних пакетов

## Установка

### Через интерфейс (рекомендуется)

1. Откройте боковую панель → **Plugins**.
2. Нажмите **Add plugin**.
3. Введите имя пакета:
   ```
   @scandicboy/dsh-locale-ru
   ```
4. Нажмите **Install**, затем **Enable now**.

### Через `plugin_manager`

```text
install_bundle("@scandicboy/dsh-locale-ru")
```

### Из локального архива (офлайн)

Скачайте `.tgz` со [страницы npm](https://www.npmjs.com/package/@scandicboy/dsh-locale-ru) и укажите путь к нему в поле **Add plugin** вместо имени пакета.

## Использование

1. Откройте **Settings → General → Language**.
2. Выберите **«Русский»**.
3. Интерфейс переключится сразу.

## Совместимость

| Компонент | Версия |
|---|---|
| DeepSeek Harness | `0.2.0-rc.2` |
| Cordis | `~4.0.4` |

## Структура бандла

| Файл | Назначение |
|---|---|
| `cordis.patch.yml` | Вставляет запись `locale-ru` в дерево загрузки (host-половина) |
| `lib/index.js` | Host-заглушка (пустой `apply`) |
| `lib/client.js` | Клиентский бандл: регистрация языка и 58 словарей |

## Как это работает

Плагин использует штатную систему локализации DSH (`@deepseek-ai/dsh-client-locale`):

1. Формат `dsh.bundle.patch` делает пакет **бандлом**, который менеджер плагинов умеет устанавливать.
2. `cordis.patch.yml` добавляет host-запись плагина в дерево загрузки.
3. `lib/client.js` регистрирует язык `ru` через `ctx.locale.addLanguage(...)` и 58 словарей через `ctx.locale.register(...)`.

## Лицензия

[MIT](./LICENSE)
