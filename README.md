# Python-Google-Drive

Простой проект для работы с Google Drive API через Python с использованием библиотеки PyDrive.

## Описание

Этот проект позволяет:
- Создавать и загружать текстовые файлы в Google Drive
- Загружать целые директории с файлами в Google Drive
- Автоматически авторизоваться через веб-браузер

## Требования

- Python 3.x
- PyDrive библиотека
- Google Drive API credentials

## Установка

1. Установите необходимые зависимости:
```bash
pip install PyDrive
```

2. Настройте Google Drive API:
   - Перейдите в [Google Cloud Console](https://console.cloud.google.com/)
   - Создайте новый проект или выберите существующий
   - Включите Google Drive API
   - Создайте credentials (OAuth 2.0 Client ID)
   - Скачайте файл конфигурации как `client_secrets.json`

3. Поместите файл `client_secrets.json` в корневую директорию проекта

## Настройка client_secrets.json

Файл `client_secrets.json` должен содержать ваши OAuth 2.0 credentials от Google. Структура файла:

```json
{
  "installed": {
    "client_id": "ваш_client_id.apps.googleusercontent.com",
    "project_id": "ваш_project_id",
    "auth_uri": "https://accounts.google.com/o/oauth2/auth",
    "token_uri": "https://oauth2.googleapis.com/token",
    "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
    "client_secret": "ваш_client_secret",
    "redirect_uris": ["urn:ietf:wg:oauth:2.0:oob", "http://localhost"]
  }
}
```

**Важно:** Никогда не публикуйте файл `client_secrets.json` в публичных репозиториях! Добавьте его в `.gitignore`.

## Использование

1. Запустите скрипт:
```bash
python main.py
```

2. При первом запуске откроется браузер для авторизации Google аккаунта

3. Разрешите доступ к Google Drive

### Основные функции

#### Создание и загрузка текстового файла
```python
create_and_upload_file(file_name='test.txt', file_content='Привет мир!')
```

#### Загрузка всей директории
```python
upload_dir(dir_path='путь/к/директории')
```

## Структура проекта

```
Python-Google-Drive/
├── main.py              # Основной файл с функциями
├── client_secrets.json  # Google API credentials (не включен в репозиторий)
└── README.md           # Документация
```

## Безопасность

- Файл `client_secrets.json` содержит конфиденциальную информацию
- Добавьте `client_secrets.json` в `.gitignore`
- Не делитесь этим файлом с другими пользователями
- При развертывании используйте переменные окружения

## Устранение неполадок

1. **Ошибка авторизации**: Убедитесь, что файл `client_secrets.json` правильно настроен
2. **Нет доступа к интернету**: Проверьте подключение к интернету
3. **Ошибки загрузки файлов**: Проверьте права доступа к локальным файлам

## Лицензия

Этот проект создан в образовательных целях.