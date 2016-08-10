# Деплоимся в Heroku за 16 попыток — Йорселфер
Именно так можно озаглавить путь от боли и ручного перетаскивания файлов по sftp до деплоя одной кнопкой с линтером и автотестами.

## Результат
### https://yourselfr.herokuapp.com
На 23:30 August 10, 2016 — всё работает.
<img src='https://pp.vk.me/c636119/v636119043/1c55d/ERFZaxjKvpE.jpg' width='300'/>

### Как раньше выглядела боль
<img src='https://pp.vk.me/c636119/v636119043/1c50c/PU3kWs3KsG8.jpg' />
За основу задания был взят 

**NodeJS API Server** — (https://github.com/fletcherist/Yourselfr)

**React Client** — (https://github.com/fletcherist/yourselfr-api)


### Проблемы и их решения
Как я уже упомянул в заголовке работы — путь до деплоя одной кнопкой занял у меня 16 попыток.

На первой же я словил:
<img src='https://pp.vk.me/c636119/v636119043/1c54c/wOqlIotthdE.jpg' />

Ключевое слово здесь — Dev Dependencies. Heroku deploy скрипт на удивление отлично подхватывает нужные проекту зависимости, но он, к сожалению, забыл установить dev зависимости. Решение есть следующая строка, которую надо скормить Heroku в терминале:

<img src='https://pp.vk.me/c636119/v636119043/1c566/bY51-vi95qE.jpg' />

Ещё на сервере с API пришлось прокинуть 

Деплой на Heroku теперь по `gp` — спасибо Travis CI за это.
<img src='https://pp.vk.me/c636119/v636119043/1c542/yBa86hSu-WA.jpg' width='400'/>

<img src='https://pp.vk.me/c636119/v636119043/1c538/Ltcu2-kh8cM.jpg' width='400'/>

<img src='https://pp.vk.me/c636119/v636119043/1c516/sa7hozXbQwc.jpg' />