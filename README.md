[![Build status](https://ci.appveyor.com/api/projects/status/urallti0707gnbae?svg=true)](https://ci.appveyor.com/project/AntonKopylov89/web-form-testing)

## Задача №1: заказ карты

Вам необходимо автоматизировать тестирование формы заказа карты:

![](pic/order.png)

Требования к содержимому полей:
1. В поле фамилии и имени разрешены только русские буквы, дефисы и пробелы.
2. В поле телефона — только 11 цифр, символ + на первом месте.
3. Флажок согласия должен быть выставлен.

Тестируемая функциональность: отправка формы.

Условия: если все поля заполнены корректно, то вы получаете сообщение об успешно отправленной заявке:

![](pic/success.jpg)

Вам необходимо самостоятельно изучить элементы на странице, чтобы подобрать правильные селекторы.

<details>
    <summary>Подсказка</summary>

    Смотрите на `data-test-id` и внутри него ищите нужный вам `input` — используйте вложенность для селекторов.
</details>

Проект с автотестами должен быть выполнен на базе Gradle с использованием Selenide или Selenium по выбору студента.

Для запуска тестируемого приложения скачайте JAR-файл из текущего каталога и запускайте его командой:
`java -jar app-order.jar`.

Приложение будет запущено на порту 9999.

Если по каким-то причинам порт 9999 на вашей машине используется другим приложением, используйте:

`java -jar app-order.jar -port=7777`

Убедиться, что приложение работает, вы можете, открыв в браузере страницу: http://localhost:9999.

## Задача №2: проверка валидации (необязательная)

После того как вы протестировали happy path, необходимо протестировать остальные варианты.

Тестируемая функциональность: валидация полей перед отправкой.

Условия: если какое-то поле не заполнено или заполнено неверно, то при нажатии на кнопку «Продолжить» должны появляться сообщения об ошибке. Будет подсвечено только первое неправильно заполненное поле:

![](pic/error.png)

<details>
    <summary>Подсказка</summary>

    У некоторых элементов на странице появится css-класс `input_invalid`.
</details>
