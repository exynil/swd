## SWD - Simple Wallpaper Downloader

Скрипт для загрузки рандомных обоев с [wallhaven.cc](https://wallhaven.cc)

### Зависимости

1. [curl](https://curl.se/)
2. [grep](https://www.gnu.org/software/grep/)
3. [jq](https://jqlang.github.io/jq/)
4. [libnotify](https://gitlab.gnome.org/GNOME/libnotify) (необязательно)
5. [fdp](https://github.com/exynil/dotfiles/blob/master/bin/.local/bin/fdp) (необязательно)

### Параметры

`-l`, `--location` - место сохранения обоев

`-c`, `--categories` - категории для загрузки, например, `111` для "`Общие`, `Аниме` и `Люди`", `1` для включения, `0` для исключения

`-p`, `--purity` - фильтр контента на основе оценки чистоты, например, `111` для `SFW`, `скетчи` и `NSFW`, `1` для включения, `0` для исключения

`-o`, `--order` - порядок по возрастанию (asc) или по убыванию (desc)

`-s`, `--sorting` - режим сортировки: `date_added`, `views`, `favorites`, `toplist`, `random`

`-a`, `--atleast` - минимальное разрешение изображения

`-r`, `--ratios` - загружать обои только с заданными соотношениями сторон, разделите несколько соотношений сторон запятой

| Соотношение сторон | Разрешение                                        |
|--------------------|---------------------------------------------------|
| 5:4                | 1280x1024 1600x1280 1920x1536 2560x2048 3840x3072 |
| 4:3                | 1280x960 1600x1200 1920x1440 2560x1920 3840x2880  |
| 16:10              | 1280x800 1600x1000 1920x1200 2560x1600 3840x2400  |
| 16:9               | 1280x720 1600x900 1920x1080 2560x1440 2840x2160   |
| Ultrawide          | 2560x1080 3440x1440 3840x1600                     |
| All                | Не включать для всех                              |


### Настройка

1. Зарегистрируйтесь на [wallhaven.cc](https://wallhaven.cc)
2. Получите бесплатный [api ключ](https://wallhaven.cc/settings/account) для обращения к API
3. Сохраните `api` ключ где нибудь в файле
4. Скопируйте файл `swd.conf` в папку `/home/<user>/.config/swd/swd.conf`
5. В `swd.conf` в параметре `apikey_file` укажите путь до файла с `api` ключом
6. Попробуйте загрузить обои используя одну из ниже приведенных команд

### Примеры

~~~~
./swd -s latest -l "$HOME/Pictures" -a 2560x1080
~~~~

~~~~
./swd -p 011
~~~~

>Вывыдом скрипта будет путь до скачанного изображения, вы можете использовать это для интеграции в свои скрипты

>Интеграция в [рофи](https://github.com/exynil/dotfiles/blob/master/rofi/.config/rofi/scripts/wallpaper)

### Если что-то не работает

1. Проверьте настроена ли у вас переменная окружения `XDG_CONFIG_HOME`
2. Проверьте актуальность вашего `api` ключа
3. Проверьте доступность `api` ключа для скрипта
4. Проверьте все шаги из раздела **`Настройка`**

Если ничего не помогло, напишите мне в [telegram](https://t.me/exynil)