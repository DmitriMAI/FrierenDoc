<img src="https://github.com/DmitriMAI/DmitriMAI.github.io/assets/106885046/087ccc17-880c-4f59-96c0-d6db0784745e" width="50%" height="50%">

Документация к языку Friren. Написан на основе языка F#  
Данный язык основан на японском фильме   
"Встреча Фриры в ее бесповоротном пути"  
Вольный перевод от : 葬送のフリーレン  
  
# Авторы проекта  
  
| ФИО | Группа | Вклад  |
|---|---|---|
| Овчинников Дмитрий  | М8О-306Б-21  | Документация, архитектура языка    |
| Лохматов Никита  | М8О-306Б-21  |  Парсер, расширения для vsc, отчёт  |
| Устинов Денис  | М8О-306Б-21  | Интерпретатор  |
| Егор Аббдуллаев  | М8О-306Б-21  | Синтаксическое дерево  |
| Егор Белоусов  | М8О-30*Б-21  |   |

***
Для более удобной работы с языком разработано расширение vs code для подсветки синтаксиса.  
## Порядок установки  
![image](https://github.com/DmitriMAI/DmitriMAI.github.io/assets/106885046/fdfde1cf-3da6-4a6a-9d54-b6513372a0e4)  

В `расширениях/extention` выбрать `...`    
В выпадающем окне выбрать `install from VSIX`  
Файл расширения находится по [ссылке](https://github.com/MAILabs-Edu-2024/fp-compiler-lab-team-3/blob/main/frieren/frieren-0.0.1.vsix)

# Блоки
Абсолютно все конструкции в языке Frieren (кроме комментариев) должны быть обёрнуты в
блоки `()`:

```
~ Возможны несколько вариантов размещения (), выбор зависит от удобства прочтения ~
~ № 1 ~
(
    someFunction
)
~ № 2 ~
(someFunction)
```

# Комментарии 
Не все маги способны запомнить всю информацию.  
Важно оставлять заметки  
>Знания — это сила, но понимание — это еще более глубокая сила.

```
~ Line Comment ~

~

Block Comment

~
```

# Вывод в консоль 
Маги должны уметь применять заклинания. Для этого используется функция `cast`

```
(
    cast "Frieren"
)
```

# Переменные 
Можно использовать `=`, либо `:` для объявления переменной  
`lt` - Link Trinket. Прикрепить волшебный брелок с магической силой внутри.   
(Теперь он будет висеть вместе с нами)

```
(lt NAME = VALUE)
(lt a = 4.0)
(lt b : 5.0)
(lt str = "str")
(lt boolean = true)
```

# Изменения переменных
Помочь с изменением способен `mut`  
Что означает мутацию состояния нашего брелка.

```
(
  mut a = 10
)
```

# Поддержка базовой арифметики
Можно по разному объединять брелки  
Поддерживаются такие операции как :  `+`, `-`, `/`, `*`  

```
(
    cast (+ a b)
)
```

# Префиксная запись
Для успешного освоения языка Frieren вы должны привыкнуть к префиксной записи выражений

```
(
    cast (+ 1 4)   ~ выведет 5 ~
)
```

# Поддержка базовых булевый операций
Особый тип логических брелков.  
Для операций с ним нужны определенные инструменты.   
Доступны такие как: `&` и `|`

```
(
    ~  преобразует к false ~
    cast (& true false)
)
```

# Поддержка операторов сравнения
Естественно некоторые брелки могут обладать большей силой.  
Необходимо сравнивать магическую силу.  
Есть варианты: `>`, `<`, `==`, `>=`, `<=`

```
cast(>= a b)
```

# Поддержка оператора if else  
Маг должен предусмотреть все варианты развития событий. В помощь ему магический разветвлитель
> Будущее формируется выборами, сделанными сегодня
```
(
    if (> a b) =>
        (cast "a > b")
    else =>
        (cast "a < b")
)

/~  if может использоваться в одиночку ~/
(
    if (>= 1 1) =>
        (cast "true")
)
```

# Поддержка цикла for и while
Возможно мы хотим сделать четкий порядок обряда.  
И знаем, что придется повторять несколько действий снова и снова.  
Для таких случаев есть заклинения в помощь нам.  
Убейте цикл с помощью `kill`    
Поддерживайте цикл в рабочем состоянии с помощью `heal`

```
(
    for i [0 .. 3] =>
        (cast i)
)

(
    while true =>
        ((cast "STOP!")
        kill)
)
```

# Cоставление сложных функций
Конечно же из собранных ингредиентов можно подготовить намного более сильное `spell` для следующего приключения.

```
(
    spell printNum {num} =>
        (cast num)
)

~ Можно использовать дальше в коде с помощью ~
(printNum 100)
```

# Поддержка работы с файлами
>Опытные маги всегда знают все наперед. Поэтому у них составлены магические гримуары.  
>Именно те маги, которые ими пользовались, остались жить дольше других.

```
~ Получение выходных данных ~
(cast (readGrim "./tests/input.txt") )

~ Перенаправление вывода ~
(writeGrim "./tests/output.txt" "Wow!")
```

# Самая красивая магия
Создайте поле цветов

```
(flowerField)
```
