
# MDC Editor - Защищенный текстовый редактор с шифрованием

Безопасный редактор для Markdown файлов с встроенным шифрованием (формат `.mdc`). Файлы защищены паролем с использованием AES-256 шифрования.

## Возможности

- 🔒 Защита файлов паролем
- 📝 Редактирование Markdown
- 🚀 Открытие файлов двойным кликом (ассоциация файлов)
- 🔑 PBKDF2 для надежной защиты паролем
- 🖥️ Кроссплатформенность (Windows, Linux, macOS)

## Установка

1. Установите необходимые пакеты:
```bash
pip install PySide6 cryptography
```

2. Скачайте программу:
```bash
git clone https://github.com/neeroteam/MDC-Editor.git
cd MDC-Editor
```

## Использование

### Основное использование
```bash
python editor.py
```

### Ассоциация файлов
Настройте открытие `.mdc` файлов двойным кликом:

**Windows:**
1. Кликните правой кнопкой на файл `.mdc`
2. Выберите "Открыть с помощью" → "Выбрать другое приложение"
3. Выберите Python и отметьте "Всегда использовать это приложение"

**Linux:**
```bash
sudo cp mdc-editor.desktop /usr/share/applications/
sudo update-desktop-database
```

**macOS:**
1. Кликните правой кнопкой на файл
2. "Свойства" → "Открывать с помощью"
3. Выберите MDC Editor и нажмите "Изменить все"

## Как это работает

1. При сохранении:
   - Генерируется случайная "соль"
   - Пароль преобразуется в ключ (PBKDF2)
   - Содержимое шифруется (Fernet/AES-256)
   - В файл записывается соль и зашифрованные данные

2. При открытии:
   - Читается соль из файла
   - Пароль преобразуется в ключ
   - Данные расшифровываются

## Лицензия

MIT License.

---

> **Примечание:** Не забывайте свои пароли! Без пароля восстановить файлы невозможно.
``` 
