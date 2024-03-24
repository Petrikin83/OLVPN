# Бот для покупки ключей к приложению Outline

Бот для покупки ключей к приложению Outline! 
Этот бот предлагает вам возможность приобрести ключи доступа к приложению Outline.
Outline - удобный инструмент для безопасного и анонимного интернет-серфинга.

## Описание

Outline - приложение, которое помогает обеспечить вашу онлайн-приватность и безопасность. 
С помощью него вы можете легко обходить цензуру и ограничения в интернете, 
сохраняя свою анонимность и защищая свои данные от нежелательного доступа.

Бот предоставляет Вам простой и удобный способ приобрести ключи доступа к приложению Outline. 
Вы можете выбрать ключи с различными сроками активности: от 1 дня до 30 дней, 
чтобы выбрать подходящий вариант для вашей потребности.

После окончания срока, ключ будет удален.
Вы так же можете его удалить самостоятельно из бота.

---
---

Бот сделан в минималистичном стиле - ничего лишнего.

Запускается по команде /start, далее все на inline-клавиатуре
Есть команда для администратора - /findpay <id> 
для поиска успешных оплат у пользователя, в случае возникновения трудностей.

Бот работает  на aiogram 3+, используется SQLAlchemy 2+ для управления БД. 
БД в данном боте реализована на SQLite, так как ее хватает сполна.
В каталоге /core/templates/ даны шаблоны для ответов. Они используются в связке с Jinja2
Шаблоны дают возможность редактировать/дополнять ответы не перезагружая бота.
Для управления outline, как менеджер используется модуль написанный другим разработчиком,
в pip этого модуля не было, потому он скачан и работает внутри проекта, находясь в каталоге outline_vpn/
Там же есть файл readme где указаны ссылки на автора.


## Требования

Для запуска проекта вам потребуется следующее:

- Python 3.9 или выше
- aiogram для работы с Telegram API
- SQLAlchemy для работы с базой данных
- asyncpg для асинхронного взаимодействия с PostgreSQL
- Jinja2 для шаблонизации сообщений
- urllib3 для выполнения HTTP-запросов
- python-dotenv для управления переменными окружения
- var-dump для отладки
- yookassa для обработки платежей через YooKassa

## Установка и Использование

0. Будем считать, что токен TLG, Outline сервер а так же данные данные для платежей в ЮКасса у Вас уже есть.
1. Клонируйте репозиторий на свой компьютер/сервер.
2. Создайте виртуальное окружение и активируйте его.
3. Установите зависимости с помощью команды `pip install -r requirements.txt`.
4. При запуске введите запрашиваемые данные или отредактируйте файл .env, чтобы настроить бота под свои нужды.
5. Запустите бота с помощью команды `python main.py`.
---
### Вы можете автоматизировать запуск и работу бота, например если у вас Ubuntu.
Все действия из консоли, поменяйте данные на свои по необходимости

```
nano /etc/systemd/system/olvpnbot.service
```

```
[Unit]
Description=Opnbot
After=network.target

[Service]
Type=simple
User=root
Group=root
Restart=on-failure
WorkingDirectory=/root/tlg/bots/olvpnbot
ExecStart=/root/tlg/bots/olvpnbot/venv/bin/python3 /root/tlg/bots/olvpnbot/main.py

[Install]
WantedBy=multi-user.target
```

```
systemctl daemon-reload
systemctl start olvpnbot
systemctl status olvpnbot
systemctl enable olvpnbot
```



Рабочий экземпляр бота: [@olvpnbot](https://t.me/olvpnbot). 
