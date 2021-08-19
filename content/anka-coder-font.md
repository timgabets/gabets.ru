+++
title = "Шрифт Anka Coder"
date = 2021-08-19
+++

Вот уже наверное лет пять я пользуюсь шрифтом [Anka Coder](https://fontlibrary.org/ru/font/anka-coder), и могу с уверенностью сказать, что это лучший моноширинный шрифт с поддержкой кириллицы (и с великолепным нулём):

![Anka Coder font](/img/anka_coder.png)

Этот шрифт я ставлю по умолчанию всюду - и в консоль, и в текстовый редактор, и в свой блог здесь на сайте. Ниже - короткий мануал по установке шрифта в MacOS:

## Установка в MacOS

1. Качаем шрифт (например, [отсюда](https://fontlibrary.org/ru/font/anka-coder))
2. Устанавливаем его с помощью [Font Book](https://support.apple.com/guide/font-book/install-and-validate-fonts-fntbk1000/mac)

### Sublime
Шрифт в Sublime настраивается элементами font_face и font_size в Preferences->Settings:

```json
{
	"find_selected_text": true,
	"font_face": "Anka/Coder",
	"font_size": 16,
	"rulers":
	[
		120
	],
	"theme": "gruvbox.sublime-theme",
	"ui_scale": 1.0,
}
```

### Терминал

Напомню, что дефолтный терминал в MacOS не совсем удобен для использования, [iTerm2](https://iterm2.com/) во много раз лучше. Настройки шрифтов в iTerm2 доступны на вкладке Preferences->Profiles->Default:

![iTerm2 font setup](/img/iterm2_font.png)
