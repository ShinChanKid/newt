# newt
При взаимодействии с программой игроку предоставляется возможность управлять игровым процессом с помощью мыши и клавиатуры, и нельзя сказать, что что-то из них главенствует. При клике на кнопку левой кнопкой мыши открывается соответствующая клетка игрового поля. 
При левом клике мыши, как и при прожатии пробела игрок перелистывает диалог или выбирает вариант пробела. Это позволяет игроку использовать предпочитаемый способ взаимодействия с игрой.
Игра также предоставляет возможность сохранения прогресса, перезапуска, изменение скорости воспроизведения текста и многое другое.
Интерфейс программы реализован с использованием RenPy, предоставляющей графические элементы для создания пользовательского интерфейса.

2.2 Техническая документация
Схема алгоритма решения:

Начало
|--> Сцена: Порог
|    |--> Диалог: "Вы стучите в дверь."
|    |--> Диалог: "Пока вы дожидайтесь ответа..."
|    |--> Показать персонажа: Ньют A
|    |--> Диалог: Ньют "Ох, здравствуй..."
|    |
|--> Сцена: Коридор (с эффектом затухания)
|    |--> Диалог: Ньют "Вы ведь по моей заявке..."
|    |--> Диалог: "Вы киваете."
|    |--> Скрыть персонажа: Ньют A
|    |--> Показать персонажа: Ньют B
|    |--> Диалог: Ньют "Насколько вы помните..."
|    |--> Скрыть персонажа: Ньют B
|    |--> Показать персонажа: Ньют A
|    |--> Диалог: Ньют "Как я и писал..."
|    |--> Диалог: Ньют "Насколько много вы знаете..."
|    |--> Выбор: "Не слишком много."
|    |--> Скрыть персонажа: Ньют A
|    |--> Показать персонажа: Ньют B
|    |--> Диалог: Ньют "Ну, чтож, я всë вам объясню..."
|    |--> Скрыть персонажа: Ньют B
|    |--> Показать персонажа: Ньют A
|    |--> Диалог: "Вы приходите по коридору..."
|    |--> Диалог: Ньют "У меня много зверей..."
|    |--> Диалог: Ньют "Мы с вами также будем тренироваться..."
|    |--> Диалог: Ньют "Первое, что вам стоит узнать..."
|    |--> Скрыть персонажа: Ньют A
|    |--> Показать персонажа: Ньют B
|    |--> Диалог: Ньют "Сначала тебе нужно познакомиться..."
|    |--> Скрыть персонажа: Ньют B
|    |--> Показать персонажа: Ньют A
|    |--> Диалог: Ньют "Демимаска – это мирное травоядное животное..."
|    |--> Диалог: Ньют "Дуглас часто оставался за старшего..."
|    |--> Диалог: Ньют "Тебе стоит медленно к нему подходить."
|    |--> Скрыть персонажа: Ньют A
|    |--> Показать персонажа: Ньют B
|    |--> Диалог: Ньют "Держи."
|    |--> Диалог: "Вы получили свежие ягоды."
|    |--> Скрыть персонажа: Ньют B
|    |--> Показать персонажа: Ньют A
|    |--> Диалог: Ньют "Вытяни руку и по-тихоньку начинай к нему подходить."
|    |--> Скрыть персонажа: Ньют A
|    |
|--> Сцена: Дугал (с эффектом затухания)
|    |--> Показать персонажа: Дугал
|    |--> Диалог: "Сейчас вы должны успевать попадать в зелëную область..."
|    |--> Диалог: "Если всë плохо, игра начнëтся сначала."
|    |--> Скрыть окно
|    |--> Переход к мини-игре: start_minigame
|    |
|--> Сцена: Конец
|    |--> Показать окно
|    |--> Скрыть персонажа: Дугал
|    |--> Показать персонажа: Ньют B
|    |--> Диалог: Ньют "Молодец, у тебя получилось подружиться с Дугласом."
|    |--> Диалог: Ньют "В дальнейшем тебе придëтся подружиться ещё с многими зверьками..."
|    |--> Скрыть персонажа: Ньют B
|    |--> Показать персонажа: Ньют A
|    |--> Диалог: Ньют "Дальше мы пойдëм осмотрим твоë основное рабочее место"
|    |--> Скрыть персонажа: Ньют A
|    |--> Показать персонажа: Ньют D
|    |--> Диалог: Ньют "Секунду, мне не кажется...?"
|    |--> Диалог: "Вы услышали бегание вдалеке."
|    |--> Скрыть персонажа: Ньют D
|    |--> Показать персонажа: Ньют C
|    |--> Диалог: Ньют "Ох, борода Мерлина... Нюхли опять разбежались."
|    |--> Диалог: "Слышится падение чего-то большого."
|    |--> Диалог: Ньют "Не поможете мне поймать всех Нюхлей?"
|    |--> Диалог: Ньют "Вы возьмёте одну комнату, а я другую."
|    |--> Скрыть окно
|    |--> Инициализация Python: res = False
|    |--> Сцена: Комната
|    |--> Игра: Инициализация
|    |--> Игра: Старт
|    |--> Проверка результатов игры
|    |--> Сцена: Коридор
|    |--> Показать персонажа: Ньют C
|    |--> Диалог: Ньют "Нюхли - те ещё проныры..."
|    |--> Скрыть персонажа: Ньют C
|    |--> Показать персонажа: Ньют A
|    |--> Диалог: Ньют "Нюхли — обитают в Британии..."
|    |--> Сцена: Лестница
|    |--> Скрыть персонажа: Ньют A
|    |--> Диалог: "Бесконечные небеса вольера..."
|    |--> Сцена: Алхимия
|    |--> Показать персонажа: Ньют A
|    |--> Диалог: Ньют "Все маги проходили зельеварение..."
|    |--> Скрыть персонажа: Ньют A
|    |--> Показать персонажа: Ньют B
|    |--> Диалог: Ньют "Постарайтесь запомнить как можно больше ингридиентов..."
|    |--> Скрыть персонажа: Ньют B
|    |--> Выборы
|    |--> Тест
|    |--> Конец
Конец
	
	Алгоритм мини-игры на попадание в область.
Инициализация переменных: fable_minigame_bar устанавливается в 90, что является начальным положением индикатора в мини-игре, fable_minigame_score и fable_you_press_button инициализируются как 0, что представляет счёт игрока и флаг нажатия кнопки соответственно, трансформация fable_point_move: определяет движение точки (или индикатора) в мини-игре, который будет вращаться вокруг оси.
Экран fable_2_minigame: отображает фоновое изображение и движущуюся точку, показывает счёт игрока и текущее значение индикатора. Если значение индикатора находится в диапазоне от -14 до 14, нажатие пробела увеличивает счёт, если игрок не нажимал кнопку ранее.
Экраны таймеров fable_timer_left и fable_timer_right: управляют движением индикатора влево и вправо соответственно, когда индикатор достигает крайних точек (-90 или 90), он меняет направление.
Экраны you_press_button_good и you_press_button_bad: отображают сообщения об успехе или неудаче в зависимости от того, была ли нажата кнопка в нужный момент.
Трансформации fable_move_good и fable_move_bad: определяют анимацию для сообщений об успехе или неудаче.
Метки start_minigame и end_minigame: start_minigame запускает мини-игру, показывая экран с таймером и игровой экран, end_minigame завершает мини-игру и продолжает основную игру.
В целом, игрок должен нажимать пробел, когда индикатор находится в центре, чтобы набрать очки. Если игрок нажимает пробел вне центра, счёт обнуляется. Игра продолжается до тех пор, пока игрок не наберёт достаточное количество очков. При ошибке всё начинается сначала.

Алгоритм мини-игры на поиск нюхлей.
	Инициализация игры: устанавливается окно по центру экрана, автоматически объявляются спрайты, инициализируются переменные для хранения координат предметов (oXY), имен предметов (oN), количества найденных предметов (oLen), общего количества предметов (maxLen), фона (oBg), времени (oTime и oMaxTime), и других параметров.
Функция InitGame: принимает фон игры, время и массивы координат и имен предметов, устанавливает начальные значения и размещает предметы на экране.
Функция StartGame: запускает игру и отображает экран игры, если таймер активен и время истекло, игра завершается.
Функция GameAsBG: показывает экран игры как неактивный фон, где уже найденные предметы не отображаются. 
Обработчик клика o_click: при клике по предмету, предмет исчезает, и увеличивается счетчик найденных предметов, если таймер не нужен и все предметы найдены, игра завершается с успехом.
Экран игры screen game: отображает фон и активные предметы для поиска, если таймер активен, отображается таймер обратного отсчета, при клике по предмету вызывается обработчик o_click.
Этот код представляет собой мини-игру, где игрок должен найти и кликнуть по скрытым предметам на экране в течение ограниченного времени. Предметы исчезают при клике, и игра продолжается до тех пор, пока не будут найдены все предметы или пока не истечет время. Если все предметы найдены до истечения времени, игра считается успешно пройденной.
Функции:
Конечно, вот описание функций с добавленными описаниями принимаемых аргументов:
В программе реализовано несколько функций и переменных, каждая из которых выполняет определенную задачу в игре "Новелла". Вот их описание:
	GameAsBg() – показывает экран игры в качестве фона
	InItGame() – заполняет экран игры объектами
	StartGame() – запуск мини-игры
label имя_метки — место в коде, к которому впоследствии можно перейти при помощи команды jump имя_метки. 
scene — команда загрузки фонового изображения из папки images созданного проекта. show — отображение картинки (чаще всего — персонажа) поверх существующего фона. 
say — фраза, произносимая персонажем. 
menu — выбор игрока, в зависимости от которого происходит выполнение соответствующего кода. 
RenPy предоставляет мощный и удобный инструментарий для создания графических пользовательских интерфейсов в приложениях Python. Ее простота в использовании и гибкость делают ее предпочтительным выбором для множества проектов. Разработчики могут легко создавать интерфейсы с помощью разнообразных виджетов и управлять ими с помощью широкого спектра методов и функций, предоставляемых библиотекой.
