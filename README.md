# Ansible

## Какие данные нужно задать

- Пользователь для авторизации на ВМ (по умолчанию `ansible`)
- Пользователь для запуска beckend'а (по умолчанию `jarservice`)
- Пользователь для запуска frontend'а (по умолчанию `www-data`)
- Версии сборок front и back
- Рабочие каталоги приложения на виртуалках
- IP адрес новой виртуальной машины для backend'а
- IP адрес новой виртуальной машины для frontend'а
- Серый IP адрес виртуальной машины backend'а в unit-файле frontend'а
- Имя пользователя для Nexus-репозитория
- Пароль учетной записи Nexus-репозитория
- URL'ы Nexus-репозитория

## Примечания

- При первом соединении с новой ВМ по ssh отпечаток принимается автоматически
- Таймаут перед подключением 30 секунд - даем время виртуалке ожить
- Чувствительные параметры шифруем

## Команды для выполнения

### Логин Nexus

```bash
ansible-vault encrypt_string 'username' --name nexus_user
```

### Пароль Nexus

```bash
ansible-vault encrypt_string 's0mePassword' --name nexus_password
```

### URL Nexus

```bash
ansible-vault encrypt_string 'https://somedomain.com/addr/to/repourl' --name nexus_url
```

### Основные команды

```bash
ansible-playbook playbook.yaml
```
