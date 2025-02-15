---
id: 587d7fb6367417b2b2512c07
title: Створити модель
challengeType: 2
forumTopicId: 301535
dashedName: create-a-model
---

# --description--

**C**RUD Частина І - Створення

First of all, we need a Schema. Кожна схема пов'язана з колекцією MongoDB. Вона визначає форму документів у цій колекції. Schemas are building blocks for Models. They can be nested to create complex models, but in this case, we'll keep things simple. Модель дозволяє створювати екземпляри ваших об’єктів, які називаються документами.

Replit is a real server, and in real servers, the interactions with the database happen in handler functions. Ці функції виконуються, коли трапляється якась подія (наприклад, хтось попадає на кінцеву точку вашого API). Ми будемо дотримуватись того самого підходу в цих вправах. Функція `done()` - це зворотний виклик, який повідомляє нас про те, що ми можемо продовжувати після завершення асинхронної операції, такої як вставка, оновлення чи видалення. Він відповідає конвенції Node і повинен називатися `done(null, data)` on success, or `done(err)` в разі помилки.

Увага! Помилки можуть виникнути при взаємодії з віддаленими службами!

```js
/* Example */

const someFunc = function(done) {
  //... do something (risky) ...
  if (error) return done(error);
  done(null, result);
};
```

# --instructions--

Створіть особисту схему під назвою `personSchema`, яка має такий прототип:

```markup
- Person Prototype -
--------------------
name : string [required]
age :  number
favoriteFoods : array of strings (*)
```

Використовуйте основні типи схем Mongoose. Якщо ви хочете, то також можете додати більше полів, використовувати прості валідатори, такі як обов’язкові або унікальні, і встановити значення за замовчуванням. See our <a href="https://www.freecodecamp.org/news/introduction-to-mongoose-for-mongodb-d2a7aa593c57/" target="_blank" rel="noopener noreferrer nofollow">Mongoose article</a>.

Тепер створіть модель під назвою `Person` from the `personSchema`.

# --hints--

Створення екземпляру зі схеми Mongoose повинно пройти успішно

```js
(getUserInput) =>
  $.post(getUserInput('url') + '/_api/mongoose-model', {
    name: 'Mike',
    age: 28,
    favoriteFoods: ['pizza', 'cheese']
  }).then(
    (data) => {
      assert.equal(data.name, 'Mike', '"model.name" is not what expected');
      assert.equal(data.age, '28', '"model.age" is not what expected');
      assert.isArray(
        data.favoriteFoods,
        '"model.favoriteFoods" is not an Array'
      );
      assert.include(
        data.favoriteFoods,
        'pizza',
        '"model.favoriteFoods" does not include the expected items'
      );
      assert.include(
        data.favoriteFoods,
        'cheese',
        '"model.favoriteFoods" does not include the expected items'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

# --solutions--

```js
/**
  Backend challenges don't need solutions, 
  because they would need to be tested against a full working project. 
  Please check our contributing guidelines to learn more.
*/
```
