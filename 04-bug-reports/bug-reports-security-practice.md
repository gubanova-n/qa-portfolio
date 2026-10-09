# 🐞 Баг-репорты — Security Practice

<table>
  <tr>
    <td><strong>Заголовок</strong></td>
    <td>XSS уязвимость в поле ввода "What are you thinking"</td>
  </tr>
  <tr>
    <td><strong>Описание</strong></td>
    <td>При вводе специального XSS-кода в поле ввода "What are you thinking", введенный JavaScript выполняется в браузере.</td>
  </tr>
  <tr>
    <td><strong>Приоритет</strong></td>
    <td>Срочный</td>
  </tr>
  <tr>
    <td><strong>Серьезность</strong></td>
    <td>Критическая</td>
  </tr>
  <tr>
    <td><strong>Предусловия</strong></td>
    <td>Открыт сайт https://devtools.sedtest-tools.ru/checkout/index.html</td>
  </tr>
  <tr>
    <td><strong>Шаги воспроизведения</strong></td>
    <td>
      1. Открыть страницу http://api-qa.skillbox.ru/xss-practice/#<br>
      2. В поле ввода ввести XSS-код из исходного баг-репорта<br>
      3. Нажать «Поделиться»
    </td>
  </tr>
  <tr>
    <td><strong>Ожидаемый результат</strong></td>
    <td>Введенная строка должна отображаться в поле ввода как обычный текст, а не выполняться как код.</td>
  </tr>
  <tr>
    <td><strong>Фактический результат</strong></td>
    <td>Появляется всплывающее окно</td>
  </tr>
</table>

<br>

<table>
  <tr>
    <td><strong>Заголовок</strong></td>
    <td>SQL уязвимость в форме обратной связи в поле Email</td>
  </tr>
  <tr>
    <td><strong>Описание</strong></td>
    <td>В поле Email формы обратной связи отсутствует корректная валидация ввода, что позволяет выполнить SQL-инъекцию</td>
  </tr>
  <tr>
    <td><strong>Приоритет</strong></td>
    <td>Немедленный</td>
  </tr>
  <tr>
    <td><strong>Серьезность</strong></td>
    <td>Критическая</td>
  </tr>
  <tr>
    <td><strong>Предусловия</strong></td>
    <td>Открыт сайт http://api-qa.skillbox.cc/practicesqli/index.php</td>
  </tr>
  <tr>
    <td><strong>Шаги воспроизведения</strong></td>
    <td>
      1. Нажать "Написать нам"<br>
      2. Открыть в DesTools вкладку Network<br>
      3. В поле "Имя" ввести Наталья<br>
      4. В поле Email ввести test@test.ru' OR SLEEP (5)--<br>
      5. В поле "Заголовок сообщения" ввести Заголовок<br>
      6. В поле "Сообщение" ввести Сообщение<br>
      7. Нажать Отправить
    </td>
  </tr>
  <tr>
    <td><strong>Ожидаемый результат</strong></td>
    <td>Введенный текст должен рассматриваться как обычный текст, без выполнения SQL-запросов</td>
  </tr>
  <tr>
    <td><strong>Фактический результат</strong></td>
    <td>Таймаут задержка 5 секунд</td>
  </tr>
</table>

<br>

<table>
  <tr>
    <td><strong>Заголовок</strong></td>
    <td>SQL уязвимость в форме авторизации в поле "Имя пользователя"</td>
  </tr>
  <tr>
    <td><strong>Описание</strong></td>
    <td>В поле "Имя пользователя" формы обратной связи отсутствует корректная валидация ввода, что позволяет выполнить SQL-инъекцию</td>
  </tr>
  <tr>
    <td><strong>Приоритет</strong></td>
    <td>Срочный</td>
  </tr>
  <tr>
    <td><strong>Серьезность</strong></td>
    <td>Критическая</td>
  </tr>
  <tr>
    <td><strong>Предусловия</strong></td>
    <td>Открыт сайт http://api-qa.skillbox.cc/practicesqli/auth.php</td>
  </tr>
  <tr>
    <td><strong>Шаги воспроизведения</strong></td>
    <td>
      1. Открыть в DesTools вкладку Network<br>
      2. В поле Имя пользователя ввести test<br>
      3. В поле Пароль ввести 5s1rgNTs<br>
      4. Нажать Войти<br>
      5. Из вкладки Network скопировать файл auth.php (Copy as cURL (bash))<br>
      6. Импортировать этот файл в Postman<br>
      7. Во вкладке x-www-form-urlencoded у поля username ввести значение test' OR SLEEP (2)--<br>
      8. Нажать Send
    </td>
  </tr>
  <tr>
    <td><strong>Ожидаемый результат</strong></td>
    <td>Введенный текст должен рассматриваться как обычный текст, без выполнения SQL-запросов</td>
  </tr>
  <tr>
    <td><strong>Фактический результат</strong></td>
    <td>Таймаут задержка 2 секунды</td>
  </tr>
</table>
