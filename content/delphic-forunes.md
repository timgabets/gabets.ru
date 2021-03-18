+++
title = "Delphic Fortunes"
date = 2021-03-18
+++

Как-то так получилось, что я дожил до седых волос и впервые услышал о [Дельфийских Максимах](https://ru.wikipedia.org/wiki/%D0%94%D0%B5%D0%BB%D1%8C%D1%84%D0%B8%D0%B9%D1%81%D0%BA%D0%B8%D0%B5_%D0%BC%D0%B0%D0%BA%D1%81%D0%B8%D0%BC%D1%8B) только сейчас, ближе к четвёртому десятку. Этот набор афоризмов настолько мне зашёл, что я решил добавить его в [fortune](https://en.wikipedia.org/wiki/Fortune_(Unix)) в терминалах на своих рабочих и домашних машинах.

Специально для зумеров напомню, что fortune - это древняя юниксовая программа, которая показывает некие афоризмы/цитаты/анекдоты при логине в юниксовом/линуксовом терминале. Например, так:
![Fortune example](/img/fortune.png)
Ну такое, местами прям надо вкуривать и неплохо знать английский. Вариант с дельфийскими максимами мне нравится  больше:
> 015. Φίλοις βοήθει       Help your friends       Помогай друзьям
> 016. Θυμοῦ κράτει       Control anger       Сдерживай гнев

Вдобавок ко всему, цитаты на греческом и русском помогают сразу при логине оценить насколько хорошо твой терминал и шрифты умеют в юникод.

Итак, копипастим список афоризмов с [wiki](https://ru.wikipedia.org/wiki/%D0%94%D0%B5%D0%BB%D1%8C%D1%84%D0%B8%D0%B9%D1%81%D0%BA%D0%B8%D0%B5_%D0%BC%D0%B0%D0%BA%D1%81%D0%B8%D0%BC%D1%8B), вставляем в текстовый файл, в котором каждый афоризм разделяем символом % - это формат, который использует fortune. Получаем что-то вроде [вот этого](/delphic). Дальше всё просто:

## Gentoo Linux

Ставим fortune:
```bash
USE="offensive" emerge fortune-mod
```

Смотрим, где находятся файлы для fortune:
```bash
fortune -f
100.00% /usr/share/fortune
...
```
Кладём туда наш [delpic файл](/delphic), генерим .dat с помощью strfile (так надо):
```bash
mv delphic /usr/share/fortune
strfile /usr/share/fortune/delphic
fortune delphic
```

Добавляем в свой .shrc-файл (например, .bashrc, в моём случае это .zshrc):
```bash
echo "fortune delphic" >> ~/.zshrc
```


## MacOS/iTerm2

Отключаем сообщение "Last login from ..." для iTerm2:
```bash
touch ~/.hushlogin
```

Ставим fortune:
```bash
brew install fortune
```

Читаем __man fortune__, и видим захардкоженную директорию __/usr/local/Cellar/fortune/9708/share/games/fortunes/__, в которой fortune ожидает увидеть dat-файлы. Штош:

```bash
mv delphic /usr/local/Cellar/fortune/9708/share/games/fortunes/
strfile /usr/local/Cellar/fortune/9708/share/games/fortunes/delphic
fortune delphic
```

Добавляем в свой .shrc-файл (.bashrc, в моём случае .zshrc):
```bash
echo "fortune delphic" >> ~/.zshrc
```

Открываем новую вкладку, и видим что-то вроде такого:
![Fortune example](/img/fortune-macos.png)

Норм совет, кстати.
