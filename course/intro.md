# Java Базовый Курс

## Занятие 1

## Введение

Прежде чем начать изучение языка программирования `Java`, надо ответить на вопрос: Почему именно `Java`?

Выбор языка - важная часть вашего обучения и развития карьеры.

Итак, почему именно `Java`?

> Ниже я изложу свое субъективное мнение.
>
> Если вы нашли для себя что-то еще - это замечательно.

Одним из немаловажных плюсов `Java` является кроссплатформенность.

Это значит, что вы можете запустить `Java` код везде, где есть `Java` машина - `JVM`.
То, что вы не завязываетесь на платформу при разработке приложения, является неоспоримым плюсом.
Так как сегодня вы пишете приложение для заказчика и запускаете его на операционной системе `Windows`, а завтра спокойно и без каких-либо дополнительных действий сможете запустить его на `Unix`.

За счет чего `Java` является кроссплатформенным языком?

Как уже было сказано выше, достигается это благодаря [JVM](https://ru.wikipedia.org/wiki/Java_Virtual_Machine) - `Java Virtual Machine`.
`JVM` является ключевым компонентом платформы Java.

Исходный код `Java` с помощью компилятора преобразуется в [байт-код](https://ru.wikipedia.org/wiki/%D0%91%D0%B0%D0%B9%D1%82-%D0%BA%D0%BE%D0%B4_Java), а уже после этого выполняется виртуальной машиной. Таким образом, не важно где и на какой платформе было написано и собрано ваше приложение, - главное, чтобы была доступна `JVM`.

Отсюда идет и один из лозунгов `Java`: `WORA`.

> Write once, run anywhere

Каждый файл исходного кода имеет расширение `.java` и компилируется в `.class`. Так как ваше приложение после компиляции будет представлять некоторый набор `.class` файлов, то логично для удобства собрать их в один архив и распространять уже скопом. Такие архивы называются `jar`-архивами или "jar-никами".

Отсюда следует еще один плюс - это простота подключения сторонних библиотек.

Если каждая библиотека или приложение - это просто `jar`-архив, то для его использования вы должны просто добавить его в место, где ваше приложение будет искать скомпилированные файлы. Такое место называется `classpath`.

Благодаря тому, что обмениваться библиотеками и использовать их в `Java` невероятно просто, то существует огромное количество написанного кода, который легко переиспользовать.

Помимо этого, `JVM` платформа дает нам еще один гиганский плюс.
Это автоматическое управление памятью.

Некоторые языки программирования, такие как `C` или `C++`, дают возможность ручного управления памятью.

Но за такую гибкость приходится платить, и обратной стороной монеты является то, что теперь программист обязан освобождать память.

Для кого-то это не является большим минусом, но взглянем правде в глаза: многие проблемы программ, написанных на таких языках, связаны с несовершенным управлением памятью.
Человеку присуще делать ошибки, что-то забывать и пропускать. И по отношению к памяти такие вещи крайне опасны и губительны.

И `JVM` освобождает разработчиков от ручного управления памятью, забирая эту ответственность себе.
Благодаря чему, `Java`-разработчик больше сконцентрирован на бизнес задаче.

Как устроена работа по освобождению памяти мы поговорим [вот здесь](../other/garbage_collector.md).

> Может показаться, что я негативно отношусь к языкам программирования с ручным управлением памятью.
> Это совершенно не так.
>
> Эти языки позволяют делать очень и очень крутые вещи.
> Но для многих современных задач, с современными компьютерами и мощностями, это не дает тех плюсов, ради которых можно отказаться от перекладки этой рутинной работы на кого-то еще, например, на `JVM`.
>
> Скажем так, для многих задач это будет скорее рутинная работа, чем явный плюс и помощь.
> Когда вам нужно нарезать хлеб и порезать овощи, вам будет удобнее использовать хороший нож, нежели боевую катану.

Добавим сюда еще и то, что на `Java` решается невероятно огромный круг задач. Здесь и `Desktop`-разработка, и `Big Data`, и [BI](https://ru.wikipedia.org/wiki/Business_Intelligence), и серверная разработка, и веб-разработка, и т.д!

На момент написания этого текста `Java` занимает 1-е место в рейтинге языков программирования [TIOBE](https://www.tiobe.com/tiobe-index/).

Понятно, что `Java` далеко - и очень далеко - не идеальный язык программирования.

Но это очень мощный инструмент, на котором действительно можно творить.

## Типизация

Языки программирования по типизации принято делить на два лагеря — `типизированные` и `нетипизированные`.

В свою очередь, `типизированные` языки делятся на несколько категорий:

* Статическая/Динамическая типизация.
* Сильная/Слабая или Строгая/Нестрогая типизация.
* Явная/Неявная типизация.

### Статическая/Динамическая

Статическая типизация определяется тем, что конечные типы переменных и функций устанавливаются на этапе компиляции. Каждая переменная и каждое выражение имеют тип, который известен на этапе компиляции.

В то время как при динамической типизации все типы выясняются во время выполнения программы.

### Сильная/Слабая

Сильная типизация выделяется тем, что язык не позволяет смешивать в выражениях различные типы и не выполняет автоматические неявные преобразования, например нельзя вычесть из строки множество.

Языки со слабой типизацией выполняют множество неявных преобразований автоматически, даже если может произойти потеря точности или преобразование неоднозначно/неявное.

### Явная/Неявная

Явно-типизированные языки отличаются тем, что тип новых переменных или функций и их аргументов нужно задавать явно.

Языки с неявной типизацией перекладывают эту задачу на компилятор/интерпретатор.

> Об этом отлично написано [здесь](https://habr.com/post/161205/) и [здесь](https://habr.com/post/308484/).

Соответственно, `Java` - это язык программирования со статической, строгой и явной типизацией.

Я лично склонен относить типизацию `Java` к ее плюсам. Особенно, статическую.
Так как это дает нам гарантию того, что каждый параметр имеет именно тот тип, который мы ожидаем. Таким образом, это снимает с нас довольно большую область ответственности за контроль над тем, что мы используем и передаем в методы, например.

Хоть и не в восторге от явной типизации.

## Привет, Мир

`Java` - это объектно-ориентированный язык программирования. Это значит, что здесь мы будем оперировать классами и объектами.

Чуть позже мы поговорим об этом более подробно, но для начала необходимо дать определения классу и объекту, постараемся максимально просто описать эти понятия.

Если говорить простым языком, то можно сказать так: класс - это как техническое описание прибора, купленного вами в электронном дискаунтере.
То, каким он должен быть: материал, форма, список составляющих и т.д.

А объект - это уже непосредственно сам прибор, сделанный **по** техническому описанию, со своим уникальным набором свойств.

Для того, чтобы объявить класс используется, барабанная дробь, ключевое слово `class`, после него уже идет имя класса.

В `Java` имена классов начинаются с заглавной буквы. В целом, язык позволяет называть классы и не с заглавной буквы, но так не принято и смотреть на вас будут косо.
Относитесь к этому как к джентльменскому соглашению.

Для примера приведем описание класса `Box`, этот класс не содержит никаких свойств и поведения, он демонстрирует только сам процесс объявления:

```java
public class Box {

}
```

> `public` - это так называемый модификатор доступа.
> О них мы также поговорим чуть позднее, но, чтобы не было недопониманий, считайте, что таким образом мы делаем наш класс "публичным", т.е доступным из любой точки программы.

Так уж сложилось, что в начале изучения любого языка программирования обычно пишут программу, печатающую "Hello World".

Кто мы такие, чтобы не соблюдать традиции?

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

Запустим данный пример и убедимся, что на экран вывелось то, что мы хотим.

Теперь давайте разберем пример выше чуть более подробно.

Мы создали класс с именем `HelloWorld`, внутри которого поместили только один метод с названием `main`.

Такой метод в `Java` является точкой входа в программу. Это то, откуда исполнение вашей программы начнется при запуске.

---

**Вопрос**:

Сколько таких точек входа в вашей программе может быть?
Может ли у меня быть несколько классов с таким методом?

**Ответ**:

Может!

Представьте вашу программу в виде здания. Каждая дверь в это здание - это наш метод `main`.
В здании может быть несколько дверей, а может быть одна. Но **войти** в здание можно только через одну дверь.

При этом **как** войти и через какую дверь - это уже решаете вы, все как и в жизни.

Под термином **как войти** я подразумеваю, какие параметры мы передаем программе при запуске.

---

Еще раз, точка входа в программу - это некоторый класс с методом, который имеет вид:

```java
public static void main(String[] args)
```

Этот метод принимает в качестве аргумента массив строк, ничего не возвращает(так как тип возвращаемого значений `void`) и имеет модификатор `static`.

Этот массив строк, который принимает точка входа - это аргументы программы, которые передаются при запуске.

Метод ничего не возвращает, поэтому имеет тип `void`.

Теперь пришла пора поговорить про модификатор `static`.

### Static

Мы уже имеем некоторое представление о классах и объектах.

Выше был приведен пример с описанием прибора и самим объектом прибора, как объектом конкретного класса.

Класс **описывает** свойства и методы, принадлежащие объекту. И для каждого объекта эти свойства свои собственные, они уникальные для каждого объекта.

Т.е если у вас есть класс `Car`, у которого есть, например, цвет и год выпуска, то для каждого **объекта** будут свои цвета и модели.

Мимо вас может проехать и красная, и синяя машина, разных годов выпуска. Эти свойства **принадлежат** объекту.

Так вот модификатор `static` говорит о том, что свойство или метод принадлежит **классу**, а не объекту.

Классу, Карл!

Это значит, что для обращения к таким полями и методам вам не нужен объект, так как поле/метод к объекту не относится.

> Забегая вперед можно сказать, что класс `Car` - этот такой же объект в `Java`, как и `instance`, объект `Car`.
>
> Т.е классы - это такие же объекты класса `Class`, который имеет свои поля и методы, хранящие некоторую информацию о вашем классе.

Именно поэтому точка входа объявляется как `static`, так как на момент старта вашей программы просто еще не существует никаких объектов, `instance`-ов нашего класса `HelloWorld`.

Но сам класс загружен, сам класс существует на момент загрузки. Поэтому `Java` спокойно запускает наш метод `main` и все.

Если вы хотите более подробно разобрать эту тему, то можете прочесть [полную заметку](../start/static_java.md) об этом.

Теперь поговорим о том, как создать объект(сущность) нашего класса `Box`.

### Instance

Чтобы создать `instance` или объект использьуется ключевое слово `new`:

```java
public class Test {
    public static void main(String[] args) {
        Box box = new Box();
    }
}
```

Обратим внимание на оператор присваивания `=`.

Здесь стоит запомнить, что все, что находится справа от `=` - это объект. В то время как все, что находится слева - это **ссылка**.
Ссылка на объект.

> Это так, если мы не оперируем примитивными типами данных, о которых речь пойдет буквально в следующем параграфе.

Ссылка имеет тип и имя, в нашем примере выше у нас объявляется ссылка с именем `box`, имеющая тип `Box`.

Теперь через ссылку вы можете работать с вашим объектом, вызывая у него методы и получая доступ до свойств.

По джентльменскому соглашению, которое никто не видел, но все знают, имена ссылок, если это не константа, начинаются с строчной буквы и придерживаются стиля [CamelCase](https://ru.wikipedia.org/wiki/CamelCase).

Вообще по оформлению посмотрите [эту заметку](../start/code_style.md)

### Типы данных

В `Java` существует разделение на ссылочные и примитивные типы данных.

Примитивных типов в `Java` всего 8: `byte`, `short`, `char`, `int`, `long`, `float`, `double`, `boolean`.

Все остальное - это ссылочные типы.

```java
public class Test {
    public static void main(String[] args) {
        int a = 14;
        double b = 22;
    }
}
```

> Когда мы работаем с примитивными типами данных все, что справа от `=` - это значение, все что слева - это переменная.
>
> У переменной также есть тип и имя.
>
> В данном случае `int` - это типа переменной с именем `a`, значение в переменной равно `14`.

Примитивные типы имеют фиксированный размер, например, `int` занимает `4 байта` и может принимать значения от `-2147483648` до `2147483647`.

Каждый примитив имеет объектный аналог.

|  Примитивный тип   | Объект         |
|:-------------------|:--------------:|
|      byte          |     Byte       |
|      short         |     Short      |
|      char          |     Char       |
|      int           |     Integer    |
|      long          |     Long       |
|      float         |     Float      |
|      double        |     Double     |
|      boolean       |     Boolean    |

Объектные аналоги примитивов обычно называют классами-обертками или просто обертками.

Каждый такой класс внутри себя содержит поле, в котором хранит примитив, и дополнен большим количеством вспомогательных методов.
Отсюда и название - обертка.

Примитивные типы хранятся на стеке, поэтому работа с ними будет происходить быстрее, чем с объектным аналогом.

> Если вы не совсем поняли смысл последнего предложения, не пугайтесь, мы об этом еще поговорим.
> Просто имейте в виду, что операции с примитивами будут происходить несколько быстрее.

Для работы с целочисленными значениями примитивов существуют ряд операторов типа `+`, `-` и так далее.

Еще стоит добавить, что все классы-обертки, а также класс `java.lang.String` являются `неизменяемыми` или `immutable` классами.
Это значит, что при любых действиях, изменяющих объект, будет создан **новый** объект.

---

**Вопрос**:

Рассмотрим следующую строчку кода:

```java
String s1 = "Greeting";
String s = "hello" + "world" + s1;
```

Как вы думаете сколько объектов будет создано?

**Ответ**:

Здесь мы пытаемся сделать `конкатенацию` или сложение строк.
Учитывая, что cтроки являются неизменяемым объектом, то при любой операции, изменяющей объект, будет создан новый объект -результат операции.

Давайте считать. Понятно, что будет создан объект строки, содержащий "Greeting", это раз.
Далее будет создан "hello", это два, и "world", это три. Результатом их сложения будет новая строка "helloworld", это четыре.
После этого мы прибавим еще то, что возьмем по ссылке `s1` - это пять.

Будет создано: 5 строк.

---

Существует еще также специальный тип `null`. Пустая ссылка `null` может быть единственным возможным значением выражения типа `null`.

Любому ссылочному типу можно присвоить `null`, это является специальной заглушкой, обозначающей, что значения ссылки не инициализировано еще.

```java
String a = null;
```

### Массивы

В начале разговора мы вскользь затронули тему массивов.
Давайте поговорим о них подробнее.

Массив - это объект, хранящий в себе фиксированное количество значений одного типа, с последовательными(непрерывными) адресами в памяти.
Другими словами, массив — это нумерованный набор переменных, идущих в памяти подряд.

Если вам для понимания надо как-то представить это, то представьте себе шкаф для обуви.
В каждую ячейку можно положить только одну пару обуви, а так как шкаф у нас заранее для обуви, то и положить мы туда можем только обувь.
Шкаф всегда ограниченного размера - количество ячеек заранее определено.

Если в какой-то момент количество пар обуви у вас становится больше, чем размер шкафа, то вы заказываете новый шкаф.
При этом, если вы экономны, вы старый шкаф сдадите/продадите, а на его месте поставите как раз шкаф нужного размера.

Точно то же самое и в нашем случае с массивами. За исключеним того, что `Java` берет на себя заботу об утилизации вашего старого шкафа.

Пример объявления массива:

```java
int[] array = new int[5];
```

Здесь `array` - это ссылка на массив `int`-ов, размер которого равен 5 элементам.

Массив является ссылочными типом данных, так как это объект.
Благодаря этому в нем хранится много полезной информации, например, размер массива.

Пример создания двумерного массива:

```java
int [][] d = new int [5][];
for (int i = 0; i < d.length; i++) {
    d[i] = new int[i];
}
```

Здесь создается матрица 5 на 5, каждый элемент которой это `int`.

Если вы знакомы с языком программирования `C` или `C++` у вас не возникнет проблем.

Очень важным моментом является еще и то, что массив может работать не только с примитивными типами данных, но и с ссылочными.
В случае, когда вы создаете массив для ссылочного типа, например, строк, такой массив будет содержать в себе **ссылки** на объекты.

```java
String[] args = {"Hello", "World"};
```

Массив, содержащий две ссылки на объекты строк.

Но мы к этому еще вернемся.

Большое количество полезных методов для работы с массивами содержится в стандартном классе `java.util.Arrays`.

### Циклы

`Java`, как и практически любой язык программирования, умеет работать с циклами.

В `Java` вы можете использовать следующие виды циклов:

* `for`
* `while`
* `do while`

Я не думаю, что надо делать полный обзор работы циклов, так как тут все так же, как и везде.
Примеров использования очень много, да и вы сами, я думаю, писали код, использующий циклы.

Можно отметить разве что разницу между `while` и `do while`.
Разница эта состоит только в том, что `do while` гарантирует вам **хотя бы одну** итерацию цикла, в то время как `while` не гарантирует этого.

### Логические операторы

`Java` поддерживает логические операторы `if`/`else` и тернарный оператор.

Тернарный оператор доступен не во всех языках программирования, так как многие считают, что он делает код менее читабельным и советуют его не использовать.

Лично у меня нет каких-то претензий к бедолаге, поэтому я иногда, хоть и редко, использую его.

Выглядит тернарный оператор как:

```java
логическоеУсловие ? выражение1 : выражение2
```

Опять же, примеров по этой теме чуть более, чем очень много, поэтому акцент на этом делать не будем и перейдем к паре практических задач.

## Практика

Сразу стоит сказать, что эти задачи довольно просты и направлены только на то, чтобы вы ближе познакомились с синтаксисом и привыкли к нему.

### FizzBuzz

Напишите программу, которая выводит на экран числа от 1 до 100.

При этом вместо чисел, кратных трем, программа должна выводить слово "Fizz", а вместо чисел, кратных пяти — слово "Buzz". Если число кратно и 3, и 5, то программа должна выводить слово "FizzBuzz".

Оформить решение надо в отдельный класс `FizzBuzzGame`, содержащий метод с сигнатурой `public void startGame(int start, int end)`.
Здесь `start` и `end` - это диапазон чисел, в котором будет произведен поиск, проверка и вывод чисел.

### Числа Фибоначчи

Здесь вам надо создать класс `FibonacсiPrinter` и реализовать в нем метод вычисления и распечатки N чисел фибоначи.

Я предлагаю объявить метод с сигнатурой `public void print(int n)`.

### Вычисление факториала числа

Снова объявляем класс `Factorial`, в нем метод, вычисляющий факториал числа.

В качестве усложнения вы можете создать несколько методов, реализующих разные алгоритмы вычисления, например, рекурсивный и с кешированием значения.

### Порядок должен быть

Напишите класс `Math` в котором объявите метод, принимающий массив, и делающий вывод - идут ли числа в массиве в порядке возрастания.

Предлагаю этот метод объявить в виде: `public boolean isAscOrder(int[] array)`

### Двоичная система

В том же классе `Math` создайте еще метод, который будет переводить обычный `int` в двоичную систему исчисления и возвращать результат в виде строки.

Предлагаю этот метод объявить в виде: `public String toBinary(int number)`

### Цензура

Давайте создадим метод, который принимает на вход строку и убирает слово паразит `блин`:

Предлагаю этот метод объявить в виде: `public String censored(String line)`.

Т.е мы передаем методу строку вида "Блин я устал", а вернется нам "я устал".
