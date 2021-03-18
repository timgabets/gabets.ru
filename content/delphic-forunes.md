+++
title = "Delphic Fortunes"
date = 2021-03-18
+++

Как-то так получилось, что дожив до седых волос, впервые услышал о [Дельфийских Максимах](https://ru.wikipedia.org/wiki/%D0%94%D0%B5%D0%BB%D1%8C%D1%84%D0%B8%D0%B9%D1%81%D0%BA%D0%B8%D0%B5_%D0%BC%D0%B0%D0%BA%D1%81%D0%B8%D0%BC%D1%8B) только сейчас, ближе к 4 десятку. Этот набор афоризмов настолько мне зашёл, что я решил добавить его в [fortune](https://en.wikipedia.org/wiki/Fortune_(Unix)) в терминалах на своих рабочих и домашних машинах.

Специально для зумеров напомню, что fortune это юниксовая программа, которая показывает некие афоризмы/цитаты/анекдоты при логине в юниксовом/линуксовом терминале. Например, так:

![Fortune example](/img/fortune.png)

Создаём текстовый файл, в котором каждый афоризм разделён символом %. Получаем что-то вроде [вот этого](/delphic). 

## Gentoo Linux

Ставим fortune:
```bash
USE="offensive" emerge fortune-mod
```

Смотрим, где находятся файлы для fortune:
```bash
# fortune -f
100.00% /usr/share/fortune
```
Кладём туда наш [delpic файл](/delphic), генерим .dat с помощью strfile:
```bash
mv delphic /usr/share/fortune
strfile /usr/share/fortune/delphic
fortune delphic
```

Добавляем в свой .shrc-файл (.bashrc, в моём случае .zshrc):
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

