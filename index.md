---

layout: yandex2

style: |
    /* собственные стили можно писать здесь!! */


---

# ![](themes/yandex2/images/logo-{{ site.presentation.lang }}.svg){:.logo}

## {{ site.presentation.title }}
{:.title}

### ![](themes/yandex2/images/title-logo-{{ site.presentation.lang }}.svg){{ site.presentation.service }}

{% if site.presentation.nda %}
![](themes/yandex2/images/title-nda.svg)
{:.nda}
{% endif %}

<div class="authors">
{% if site.author %}
<p>{{ site.author.name }}{% if site.author.position %}, {{ site.author.position }}{% endif %}</p>
{% endif %}

{% if site.author2 %}
<p>{{ site.author2.name }}{% if site.author2.position %}, {{ site.author2.position }}{% endif %}</p>
{% endif %}

</div>

## Tensorflow и другие

{:images}
![](pictures/logos.png)

## Tensorflow vs all
{:images}
![](pictures/why-tf.png)

Хороший реп, хороший код, богатая инфраструктура.

## Вычислительные графы
{:.section}

## Основы Tensorflow
{:.section}

## Tensorflow -- это просто

![](pictures/graph.png)
{:.image-left}

1. Собрать граф

```python
x = tf.placeholder(tf.float32)
y = tf.placeholder(tf.float32)
z = (x * y) + (x + y)
```

## Tensorflow -- это просто

![](pictures/graph_executed.png)
{:.image-left}

1. Собрать граф

```python
x = tf.placeholder(tf.float32)
y = tf.placeholder(tf.float32)
z = (x * y) + (x + y)
```

2. Использовать его

```python
with tf.Session() as sess:
    sess.run(z, feed_dict={x: 1, y: -2})
    # -3
```

## Tensorflow -- это просто
### Чуть сложнее

![](pictures/counter-how.png)
{:.image-left}

Как сделать счетчик?

```python
counter = tf.Variable(0)
```

## Tensorflow -- это просто
### Чуть сложнее

![](pictures/counter.png)
{:.image-left}

Как сделать счетчик?

```python
counter = tf.Variable(0)
incremented = counter + 1

# state <- new_value
update_op = tf.assign(counter, incremented)
```


## From Keras to Tensorflow
{:.section}

## From Keras

```python
model = Sequential()
model.add(Dense(units=64, activation='relu', input_dim=100))
model.add(Dense(units=10, activation='softmax'))
model.compile(loss='categorical_crossentropy',
              optimizer='sgd',
              metrics=['accuracy'])
model.fit(x_train, y_train, epochs=5, batch_size=32)
loss_and_metrics = model.evaluate(x_test, y_test, batch_size=128)
```



## to Tensorflow
### Tensorflow model

```python
model = ...
```

## to Tensorflow
### Tensorflow train_op

```python
train_op = ...
```

## to Tensorflow
### Tensorflow train loop

```python
with tf.Session() as sess:
    sess.run(init_op)
    for x, y in X, Y:
        sess.run(train_op, feed_dict={input_x: x, input_y: y})
    val = []
    for x, y in vX,  vY:
        val.append(sess.run(metric, feed_dict={input_x: x, input_y: y}))
```

## to Tensorflow
### Подводные камни

1.
2.
3.

## Dataset API
{:.section}

## Dataset API
### Работа с данными

1. Список семплов (картинок, файлов, строчек, ....)
2. Загрузка
3. Предобработка
4. Аугментация
5. Асинхронная подгрузка

## Dataset API
### Dataset API

```python
from_generator
map()
shuffle
repeat
batch
```


## Estimator API
{:.section}

## Estimator API
### Estimator API

Основные пожелания
- несколько версий графа (train, eval, inference)
- сохранение и продолжение тренировки
- переключение режимов train/eval
- корректное сохранение логов для tensorboard
- модульность кода

## Estimator API
### Estimator API. Пример

Here will be code

## Estimator API
### Estimator API. Что внутри

Here will be code

## Estimator API
### Estimator API. Интересные вещи

- как менять LR
- прочие интересности

## Выводы

- читайте исходники
- dataset API
- estimator API


## Название раздела
{:.section}

### Верхний колонтитул

## Длинная цитата переносится на несколько строк
{:.blockquote}

### Источник

## Заголовок

Основной текст

**Ключевая мысль**

- Маркированный список
- Маркированный список

1. Нумерованный список
2. Нумерованный список

### Источник

## Заголовок

Элементы появляются по очереди

1. {:.next}Нумерованный список
2. {:.next}Нумерованный список
3. {:.next}Нумерованный список
4. {:.next}Нумерованный список


### Источник

## Заголовок
{:.images}

![](themes/yandex2/images/images-one.svg)

### Источник

## Заголовок
{:.images .two}

![](themes/yandex2/images/images-two.svg)
*Текст*

![](themes/yandex2/images/images-two.svg)
*Текст*

### Источник

## Заголовок
{:.images .three}

![](themes/yandex2/images/images-three.svg)
*Текст*

![](themes/yandex2/images/images-three.svg)
*Текст*

![](themes/yandex2/images/images-three.svg)
*Текст*

### Источник

## Заголовок

![](themes/yandex2/images/image-right.svg)
{:.image-right}

Основной текст

**Ключевая мысль**

- Маркированный список
- Маркированный список

1. Нумерованный список
2. Нумерованный список

### Источник

## Заголовок

<!-- библиотека пиктограмм https://patterns.yandex-team.ru/presentations?typeIn=icons -->

![](themes/yandex2/images/icons.svg)
{:.icon-left}

Основной текст

**Ключевая мысль**

- Маркированный список
- Маркированный список

1. Нумерованный список
2. Нумерованный список

### Источник

## Заголовок
{:.icons}

<!-- библиотека пиктограмм https://patterns.yandex-team.ru/presentations?typeIn=icons -->

![](themes/yandex2/images/icons.svg)
*Текст*

![](themes/yandex2/images/icons.svg)
*Текст*

![](themes/yandex2/images/icons.svg)
*Текст*

### Источник

## Заголовок
{:.icons .four}

<!-- библиотека пиктограмм https://patterns.yandex-team.ru/presentations?typeIn=icons -->

![](themes/yandex2/images/icons.svg)
*Текст*

![](themes/yandex2/images/icons.svg)
*Текст*

![](themes/yandex2/images/icons.svg)
*Текст*

![](themes/yandex2/images/icons.svg)
*Текст*

### Источник

## Заголовок
{:.icons .five}

<!-- библиотека пиктограмм https://patterns.yandex-team.ru/presentations?typeIn=icons -->

![](themes/yandex2/images/icons.svg)
*Текст*

![](themes/yandex2/images/icons.svg)
*Текст*

![](themes/yandex2/images/icons.svg)
*Текст*

![](themes/yandex2/images/icons.svg)
*Текст*

![](themes/yandex2/images/icons.svg)
*Текст*

### Источник

## Заголовок будет скрыт
{:.fullscreen}

![](themes/yandex2/images/images-fullscreen.svg)

## Заголовок будет скрыт
{:.fullscreen}

![](themes/yandex2/images/images-fullscreen.svg)

<figure markdown="1">
Текст
</figure>

## Таблица

|  Locavore     |  Umami       |  Helvetica |  Vegan     |
+---------------|--------------|------------|------------+
|  Fingerstache<br/>The second line |  Kale        |  Chips     |  Keytar    |
|  Sriracha     |  Gluten-free |  Ennui     |  Keffiyeh  |
|  Thundercats  |  Jean        |  Shorts    |  Biodiesel |
|* Terry        |* Richardson  |* Swag      |* Blog      |

Текст

### Источник

## Исходный код (html)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Shower</title> <!--Comment-->
    <link rel="stylesheet" href="screen.css">
</head>
<body>Hello!</body>
</html>
```

## Исходный код (js)

Пояснение для кода.

```js
var i, j, over, data = new Array(2, 34.12, 4.7, 0, 234, 5);
var test = false;

for (i = 1; i < data.length; i++) {
    over = data[i]; 
    for (j = i - 1; j >= 0 && data[j] > over; j--) {
        data[j + 1] = data[j];
    }
    data[j + 1] = over;
}
alert(data.join(','));
```

## Исходный код (css)

```css
.head {
    background-color: yellow;
}

.head__logo {
    background-image: url(images/logo.svg);
}

#test, body {
    font-weight: bold;
}

```

## Этот заголовок будет скрыт
{:.fullscreen}

```js
// исходный код (на весь экран)

var x = 10;
for (var i = 0; i < x; i++) {
    console.log('hello!');
}
```

## Контакты 
{:.contacts}

{% if site.author %}

<figure markdown="1">

### {{ site.author.name }}

{% if site.author.position %}
{{ site.author.position }}
{% endif %}

</figure>

{% endif %}

{% if site.author2 %}

<figure markdown="1">

### {{ site.author2.name }}

{% if site.author2.position %}
{{ site.author2.position }}
{% endif %}

</figure>

{% endif %}

<!-- разделитель контактов -->
-------

<!-- left -->
- {:.mail}m12sl@yandex-team.ru
- {:.github}m12sl

<!-- right -->
- {:.telegram}m12sl
- {:.vk}@m12sl

<!-- 

- {:.mail}author@yandex-team.ru
- {:.phone}+7-999-888-7766
- {:.github}author
- {:.bitbucket}author
- {:.twitter}@author

- {:.skype}author
- {:.instagram}author
- {:.facebook}author
- {:.ok}@author

-->
