# 🐞 Баг-репорты — DummyAPI

<table>
  <tr>
    <td><strong>Заголовок</strong></td>
    <td>Нет возможности создать нового пользователя с именем и фамилией больше 30 символов</td>
  </tr>
  <tr>
    <td><strong>Описание</strong></td>
    <td>Согласно документации, нового пользователя можно создать с именем и фамилией из 2-50 символов</td>
  </tr>
  <tr>
    <td><strong>Приоритет</strong></td>
    <td>Нормальный</td>
  </tr>
  <tr>
    <td><strong>Серьезность</strong></td>
    <td>Незначительная</td>
  </tr>
  <tr>
    <td><strong>Предусловия</strong></td>
    <td>
      URL: https://dummyapi.io/data/v1/user/create<br>
      Метод: POST
    </td>
  </tr>
  <tr>
    <td><strong>Шаги воспроизведения</strong></td>
    <td>
      1. В Body ввести данные пользователя с именем и фамилией больше 30 символов<br>
      2. Нажать Send
    </td>
  </tr>
  <tr>
    <td><strong>Ожидаемый результат</strong></td>
    <td>Пользователь создан. 200 OK</td>
  </tr>
  <tr>
    <td><strong>Фактический результат</strong></td>
    <td>
      "firstName": "Path `firstName` is longer than the maximum allowed length (30)."<br>
      "lastName": "Path `lastName` is longer than the maximum allowed length (30)."<br>
      400 Bad Request
    </td>
  </tr>
</table>
