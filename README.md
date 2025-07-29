# Ansible Playbook for Lighthouse

Устанавливает и настраивает Lighthouse на Ubuntu-хосте.

## Параметры
- Использует Nginx как веб-сервер
- Клонирует репозиторий Lighthouse из GitHub
- Работает на порту 80

## Теги
- `--tags install` - установка компонентов
- `--tags config` - настройка конфигурации
- `--tags deploy` - деплой приложения

## Использование
Запуск на prod окружении:
```bash
ansible-playbook -i inventory/prod.yml site.yml
