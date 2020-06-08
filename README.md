# openwrt-telegram-bot
Как задеплоить на OpenWRT своей телеграмм бот написаный на питоне

**1. Вам нужно установить пакеты python3, python3-setuptool, python3-pip (можно через браузер, а можно через терминал).**

*opkg update*

*opkg install python3*

*opkg install python3-setuptool*

*opkg install python3-pip*

**2. Далее обновим pip.**

*pip3 install --upgrade pip*

**3. Потом через командную строку установить pyTelegramBotAPI и все библиотеки которые вы используете в боте.**

*pip3 install pyTelegramBotAPI*

*Если будет MemoryError значит примонтируйте swap флешку (мне помогло 256 Мб свапа).

**4. Далее через WinSCP подключаемся к роутеру и загружаем файлы (drag&drop) на роутер:**

**4.1 Скрипт который будет запускать бот по пути /etc/init.d/...  (он лежит в этом репозитории)**

*Не забудьте поменять в этом скрипте "your_bot_name" на название вашого файла который вы зальёте в следующем шаге.

**Название скрипта запуска (service) может быть любое

4.2 Телеграмм бот написаный на python заливаем по пути /usr/lib/telebot/your_bot_name.py

**5. Далее пишем в командной строке роутера (через PuTTY):**

*chmod +x -R /usr/lib/telebot/**

*chmod +x /etc/init.d/your_service_name*

*service your_service_name enable*

**Бот размещён на вашем роутере и запущен.**
