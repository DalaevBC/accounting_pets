# Учет питомцев
## Описание
REST API для ведения учета питомцев (собак и кошек). Позволяет добовлять питомцев и фотографии к ним, получать список питомцев и удалять питомцев по списку. Реализована возможность выгрузить список питомцев в json через командную строку


## Запуск проекта
Инструкция подразумевает что на виртуальной машине уже установлен doker, git pip

Вариант 1(Docker):

* Клонируем репозиторий
 `git clone https://github.com/DalaevBC/accounting_pets.git`
* B проекте создаем файл .env, заполняя данными, по образу и подобию .env.template
* В консоли пишем
`docker-compose up`
* Проект запущен!!!

Вариант 2(напрямую):
* Клонируем репозиторий
 `git clone https://github.com/DalaevBC/accounting_pets.git`
* B проекте создаем файл .env, заполняя данными, по образу и подобию .env.template
* В консоли пишем

`pip install -r requirements.txt`

`python manage.py migrate`

`python manage.py runserver`

* Проект запущен!!!

## Инструкция
Аутентификация реализована на основе API Key Authentication.
Все запросы должны содержать header X-API-KEY, 
значение которого должно соответствовать ключу API_KEY в настройках проекта.
1. POST /pets              -----> Создать питомц
2. POST /pets/{id}/photo   -----> Загрузить фотографию питомца
3. GET /pets               -----> Получить список питомцев
4. DELETE /pets            -----> Удалить питомцев
