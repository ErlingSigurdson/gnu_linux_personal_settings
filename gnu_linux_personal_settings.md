# Персональные настройки GNU/Linux

Здесь приведён список некоторых настроек и программ, большую часть которых я обычно предпочитаю иметь выполненными и установленными на каждой своей системе (компьютере или виртуальной машине) под управлением операционной системы GNU/Linux.

Что касается среды рабочего стола, обычно я использую KDE Plasma или Cinnamon, поэтому многие настройки описаны исходя из этого варианта.

### Общие настройки
- настройка автоматического подключения к сети Wi-Fi / Ethernet;
- настройка интерпретации операционной системой времени UEFI/BIOS как местного, а не как UTC (актуально, если GNU/Linux установлен в дуалбут с Windows, чтобы две разные ОС не рассчитывали системное время по-разному);
- настройка аудиоустройств.

### Настройки среды (окружения) рабочего стола
- установка региональных и языковых настроек (если при установке ОС не были установлены подходящие);
- добавление русской раскладки клавиатуры;
- настройка переключения раскладок клавиатуры (языка ввода) по сочетанию Alt+Shift;
- настройка вида индикации текущей раскладки клавиатуры (значок государственного флага, а не буквенное обозначение) на таскбаре;
- настройка расположения, высоты, прозрачности и режима отображения таскбара;
- настройка размера и расположения значка кнопки стартового меню (кнопки "пуск", кнопки запуска меню приложений / лончера приложений), значков программ и виджетов на таскбаре;
- настройка режима отображения виджетов (какие всегда будут видны на таскбаре, какие всегда будут в трэе, какие будут выводиться на таскбар в зависимости от контекста);
- закрепление на таскбаре нужных значков программ;
- настройка стартового меню: добавление программ в избранное, настройка отображения кнопок завершения работы;
- добавление кнопки сворачивания всех окон в самом углу экрана, справа внизу;
- настройка отображения стандартных значков на рабочем столе (чтобы были видны ссылки на директории Home и Trash или заменяющие их виджеты). В KDE Plasma виджет "Trash" расположить внизу справа.
- настройка размера и расположения значков на рабочем столе;
- настройка тёмной темы оформления рабочего стола;
- установка любимых обоев;
- установка кастомного значка кнопки стартового меню;
- установка формата отображения даты и времени;
- настройка яркости и контраста;
- настройка гаммы (RGB);
- отключение бесенячих виджетов, таких как Sticky Note (убирается в настройках mouse action рабочего стола, в опции эффекта нажатия средней клавиши мыши/тачпада);
- (для Cinnamon) замена стандартного стартового меню на Cinnamenu;
- (для KDE Plasma и других сред рабочего стола, где это поддерживается) настройка лимита вместимости корзины (trash) и поведения при её переполнении.

### Бутлоудер
- настройка опций загрузки в grub (перечня, очерёдности, варианта по умолчанию, времени на выбор);
- установка кастомной темы grub.

### Терминал
- установка bash в качестве моей пользовательской оболочки. В KDE Plasma проще всего изменить оболочку в настройках Konsole. Вообще же для этого могут использоваться следующие команды:
```
usermod -s /bin/bash <my_username>
или
chsh -s /bin/bash
```
- установка/настройка автодополнения при наборе команд оболочки (да, не везде оно есть по умолчанию, особенно если пользователь использует не ту оболочку, которая предполагалась создателями дистрибутива по умолчанию);
- настройка в эмуляторе терминала цветовой схемы, размера шрифта по умолчанию, размера окна по умолчанию и т. д.;
- установка/настройка языковых опций (locale). Как правило, достаточно выполнить и заодно добавить в пользовательский файл настройки оболочки (например .bashrc или .bash_profile в случае с bash) следующую команду:
```
export LC_ALL=C.UTF-8
```
- установка tmux;
- установка tree.

### Текстовые редакторы
1) Графические
- обычно в любом дистрибутиве GNU/Linux уже имеется приличный текстовый редактор, например, Kate и KWrite в комплекте с KDE Plasma. Поэтому остаётся установка текстовых редакторов, обычно используемых для разработки ПО (см. раздел "Программирование").

2) Текстовые
- установка micro (https://micro-editor.github.io/);
- настройка micro:
    - перенос исполняемого файла micro в /bin;
    - добавление в пользовательский файл настройки оболочки строки "export EDITOR=micro";
    - настройка переноса строк (вызов меню Ctrl+E, команды "set wordwrap on" и "set softwrap on";
    - выбор цветовой схемы (обычно выбираю railscast).

### Файловые менеджеры
1) Графические
- настройка отображения домашней папки текущего пользователя при запуске файлового менеджера;
- (для KDE Plasma) из-за бага с невозможностью загрузить в браузер множество файлов одним drag-and-drop'ом требуется установка параллельно с Dolphin дополнительного графического файлового менеджера, например, Thunar;
- если есть желание попрактиковаться с keyboard-only, установить Double Commander. Можно настроить ему внешний вид и цветовую схему (тему).

2) Текстовые
- установка Midnight Commander (mc);
- настройка mc:
    - выбрать цветовую схему (обычно выбор зависит от свойств дисплея, подбираю наиболее удобную и приятную для глаз);
    - добавить наиболее часто используемые директории в избранное (Ctrl + \);
    - если mc запускает не ту оболочку, которая мне нужна, можно присвоить переменной среды SHELL значение "/bin/bash":
    ```
    alias mc="export SHELL=/bin/bash; mc"
    ```

### Управление дисковыми пространствами и восстановление данных
- установка parted;
- установка Gparted;
- установка TestDisk (TestDisk + PhotoRec).

### Дистрибуция ПО и "магазины" приложений
- установка Flatpak;
- добавление в графический интерфейс обычно используемого мной "магазина" приложений поддержки Flatpak (Flathub), если она не добавлена по умолчанию.

### Браузеры
1) Графические
- установка Mozilla Firefox, Google Chrome;
- настройка графических браузеров:
    - настройка применяемого по умолчанию масштаба страниц (zoom);
    - настройка восстановления ранее открытых вкладок при запуске браузера;
    - настройка темы оформления;
    - настройка скачивания файлов (изменение папки для сохранения по умолчанию и включение опции "при загрузке всегда спрашивать, куда сохранить файл");
    - настройка домашней страницы;
    - вход в учётные записи в Яндексе и Google с сохранением аутентификационных данных браузерами;
    - импорт моей коллекции закладок, упорядочивание закладок;
    - установка плагина для создания полностраничных скриншотов.
2) Текстовые
- установка elinks, links2, w3m.

### Мессенджеры
- установка Telegram Desktop (на Debian-like лучше flatpak с FlatHub, там более новая версия);
- настройка WhatsApp Web (привязка устройства и авторизация через графический браузер).

### Медиа
- установка VLC media player.

### Офис
- установка LibreOffice Writer;
- установка LibreOffice Calc;
- установка Okular или аналогичной программы для работы с PDF.

### Работа с изображениями
- установка GIMP.

### Программирование
- установка git;
- настройка git:
    - установка/настройка автодополнения при наборе команд для git (да, не везде оно есть по умолчанию);
    - заполнение данных о пользователе в git;
    - добавление в пользовательский файл настройки оболочки моих alias'ов, переменных и команд для git (https://aufhebung.ru/git_shenanigans/);
    - установка Arduino IDE 2.x и "ядер" для различных линеек микроконтроллеров:
        1. для AVR (MiniCore): https://mcudude.github.io/MiniCore/package_MCUdude_MiniCore_index.json
        2. для ESP32: https://espressif.github.io/arduino-esp32/package_esp32_index.json
        3. для ESP8266: https://arduino.esp8266.com/stable/package_esp8266com_index.json
        4. для STM32 (stm32duino): https://github.com/stm32duino/BoardManagerFiles/raw/main/package_stmicroelectronics_index.json
        5. для LGT8F328P: https://raw.githubusercontent.com/dbuezas/lgt8fx/master/package_lgt8fx_index.json
- установка Arduino CLI;
- установка esptool.py (устанавливается с помощью pip);
- установка Visual Studio Code (VS Code) / VSCodium;
- установка gcc, g++;
- установка make;
- установка npm;
- установка Node.js (nodejs).

### ssh
- установка sshd;
- импорт моих ssh-ключей, выставление для них ограниченного доступа с помощью chmod;
- импорт моих настроек для ~/.ssh/config.

### Диагностика системы
- установка htop;
- установка fastfetch / neofetch;
- установка Psensor.

### Сети
- установка клиента OpenVPN, импорт настроечного файла, импорт десктоповой кнопки запуска клиента OpenVPN с использованием настроечного файла;
- установка curl;
- установка netcat (nc), предпочтительно вариант ncat (от создателей nmap), на втором месте — netcat-traditional (nc.traditional);
- установка socat;
- установка ss;
- установка пакета net-tools (ifconfig и т. д.);
- установка iptables;
- установка nmap;
- установка ufw;
- установка wget.

### СУБД и инструменты для работы с базами данных
- установка MySQL / MariaDB;
- установка DBeaver.

### UART
- установка moserial (для GUI);
- установка tio (для терминала);
- добавление текущего пользователя в группу, имеющую доступ к последовательным портам (обычно она называется dialout);
- удаление brltty (в некоторых системах может препятствовать работе последовательного порта).

### Отладка программ
- установка gdb;
- установка valgrind;
- установка strace.

### Ради прикола
- установка sl;
- установка cowsay;
- установка asciiquarium;
- установка ninvaders;
- установка какого-нибудь клона или продолжателя Tetris, например, Quadrapassel. Только не Bastet!

### Разное
- либо установка KDE Spectacle и его настройка таким образом, чтобы по нажатию на клавишу PrintScreen включался режим захвата прямоугольной области на экране, либо аналогичная настройка иного (уже имеющегося) приложения для создания скриншотов;
- установка qBittorrent;
- установка Zoom;
- установка FileZilla, настройка SFTP и подключений к моим VPS;
- установка KiCad;
- установка openssl;
- установка dos2unix;
- установка jp2a;
- установка Wine;
- установка tidy;
- установка Remmina;
- установка xrdp и xorgxrdp;
- установка xdotool;
- установка wmctrl;
- установка iconv;
- установка enca;
- установка ffmpeg.
