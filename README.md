### Проект "YaMDb"

### Описание:
Проект YaMDb собирает отзывы (Review) пользователей о произведениях (Titles). 

### О проекте:
Сами произведения в YaMDb не хранятся, 
здесь нельзя посмотреть фильм или послушать музыку.

Произведения делятся на категории (Category). 
Например: «Книги», «Фильмы», «Музыка». 
Список категорий  может быть расширен администратором.

Произведению может быть присвоен жанр (Genre) из списка предустановленных. 
Например, «Сказка», «Рок» или «Артхаус». 
Новые жанры может создавать только администратор.

Благодарные или возмущённые пользователи оставляют 
к произведениям текстовые отзывы (Review) и 
ставят произведению оценку в диапазоне 
от одного до десяти (целое число).

Из пользовательских оценок формируется усреднённая оценка произведения 
— рейтинг (целое число). 

На одно произведение пользователь может оставить только один отзыв.

Для аутентификации используются JWT-токены.
У неаутентифицированных пользователей доступ к API только на чтение. 
Аутентифицированным пользователям разрешено создание, изменение и удаление своего отзыва; 
в остальных случаях доступ предоставляется только для чтения.

### Технологии:
django==2.2.16
djangorestframework==3.12.4
pytest==6.2.4
pytest-django==4.4.0
pytest-pythonpath==0.7.3
djangorestframework-simplejwt==4.8.0
django-filter==21.1

Модели: User, Category, Genre, Title, Review, Comment

### Как запустить проект:
Клонировать репозиторий и перейти в него в командной строке:

```
git clone ...прописываем путь...
```

```
cd infra
```

Разверните проект:

```
docker-compose up -d --build
```

```
docker-compose exec web python manage.py migrate
```

```
docker-compose exec web python manage.py collectstatic --no-input 
```

Заполните базу данных фикстурами:

```
docker-compose exec web python manage.py loaddata fixtures.json
```




### Примеры. Некоторые примеры запросов к API.

Запрос на получение списка категорий:

```
http://api/v1/categories/
```

Запрос на получение списка жанров
```
http://api/v1/genres/
```
### Об Авторах

Авторы проекта студенты backend-факультета Яндекс.Практикум:

Карагодин Сергей

Мальгин Игорь

Ансарова Арапат

![example workflow](https://github.com/patridon87/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)