# Деплоимся в Heroku за 16 попыток — Йорселфер
Именно так можно озаглавить путь от боли и ручного перетаскивания файлов по sftp до деплоя одной кнопкой.

## Результат
## [yourselfr.herokuapp.com](https://yourselfr.herokuapp.com)
На 23:30 August 10, 2016 — всё работает.

<img src='https://pp.vk.me/c636119/v636119043/1c55d/ERFZaxjKvpE.jpg' width=700/>

### Как раньше выглядела боль
<img src='https://pp.vk.me/c636119/v636119043/1c50c/PU3kWs3KsG8.jpg' />
### Раньше
За основу задания был взят сервис анонимных мнений Йорселфер, который я делаю в свободное время.

Его архитектура на момент прошедший уже представляла собой некоторое количество компонент и решений для CI и CD, но они были, если выражаться как можно точнее, были далеко друг от друга: они были обособлены и не имели ничего общего друг с другом. Это есть огромная проблема для меня, как для человека, ограниченного временем. Поэтому построение грамотной архитектуы должно было стать огромной помощью мне, в первую очередь, как разработчику.

**NodeJS API Server** — (https://github.com/fletcherist/yourselfr-api)

**React Client** — (https://github.com/fletcherist/Yourselfr)


### Проблемы и их решения

Проблема первая: exception при первой попытке раздеплоить приложение.

<img src='https://pp.vk.me/c636119/v636119043/1c570/tiL-KmVM6qU.jpg' width=700/>

Ключевое слово здесь — Dev Dependencies. Heroku deploy скрипт на удивление отлично подхватывает нужные проекту зависимости, но он, к сожалению, забыл установить dev зависимости. Решение есть следующая строка, которую надо скормить Heroku в терминале:

<img src='https://pp.vk.me/c636119/v636119043/1c566/bY51-vi95qE.jpg' width=400/>



### Что ещё
На стороне сервера пришлось внести хостнейм heroku в whitelist, дабы избежать проблем с кроссдоменными запросами.

Деплой на Heroku теперь по `gp` — спасибо Travis CI за это.

<img src='https://pp.vk.me/c636119/v636119043/1c57a/fQyokeNl2nc.jpg' width=700/>
<img src='https://pp.vk.me/c636119/v636119043/1c5a9/ObqqA289W7M.jpg' width=400>

## Послесловие
Да, действительно, с появлением сервисов типа Cloud-As-a-Service **один** человек может комфортно разрабатывать и поддерживать high-load приложения, не испытывая особенно никакого дискомфорта со вторым пунктом (поддержка). Теперь я осознал и это тоже. 

Да, действительно, навык построения хорошей архитектуры и окружения должен цениться среди разработчиков так же, как и умение писать качественный и поддерживаемый код.

Да, действительно, я начну использовать такие сервисы в ближайшем будушем. Какие именно? Мне очень нравится концепция Docker-контейнеров и их окружения. Скорее всего, я попробую что-нибудь из этого. Я действительно хочу перенести Йорселфер с VPS на Ubuntu в что-то легко масштабируемое и легко развёртываемое.

<img src='https://pp.vk.me/c636119/v636119043/1c516/sa7hozXbQwc.jpg' />
