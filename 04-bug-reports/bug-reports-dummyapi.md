# 🐞 Баг-репорты — DummyAPI

## BR-11. Нет возможности создать нового пользователя с именем и фамилией больше 30 символов

<table>
  <tr>
    <th>Заголовок</th>
    <td>Нет возможности создать нового пользователя с именем и фамилией больше 30 символов</td>
  </tr>
  <tr>
    <th>Приоритет</th>
    <td>Нормальный</td>
  </tr>
  <tr>
    <th>Серьезность</th>
    <td>Незначительная</td>
  </tr>
  <tr>
    <th>Описание</th>
    <td>Согласно документации, нового пользователя можно создать с именем и фамилией из 2–50 символов</td>
  </tr>
  <tr>
    <th>Предусловия</th>
    <td>https://dummyapi.io/data/v1/user/create</td>
  </tr>
  <tr>
    <th>Шаги воспроизведения</th>
    <td>
      1. В Body ввести данные пользователя с именем и фамилией больше 30 символов<br>
      2. Нажать Send
    </td>
  </tr>
  <tr>
    <th>Ожидаемый результат</th>
    <td>Пользователь создан. 200 OK</td>
  </tr>
  <tr>
    <th>Фактический результат</th>
    <td>
      "firstName": "Path `firstName` is longer than the maximum allowed length (30)."<br>
      "lastName": "Path `lastName` is longer than the maximum allowed length (30)."<br>
      400 Bad Request
    </td>
  </tr>
</table>
