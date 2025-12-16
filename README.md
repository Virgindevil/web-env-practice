# web-env-practice
**Инструкция:**

*I.	Установка ПО*
1.	Установите Visual Studio Code.

2.	Установите Node.js (LTS). После установки выполните в терминале:

`node --version`
(в моём случае после сообщения было так:
C:\Users\user> node --version
v22.19.0  )

`npm --version`
(в моём случае после сообщения было так:
PS C:\Users\user> npm --version
11.6.4  )

4.	Установите Git. Проверьте: 

`git --version`
(в моём случае после сообщения было так:
C:\Users\user> git --version
git version 2.52.0.windows.1  )

ㅤ

*II.	Настройка Git*
1.	Настройте глобально имя и email: 

`git config --global user.name "Ваше Имя"`

`git config --global user.email "email@example.com"`

(Это не запрос, так что на эти строки ответов нет )

2.	Создайте папку проекта и инициализируйте репозиторий: 

`mkdir web-env-practice && cd web-env-practice`
либо если вы используете PowerShell, то команды надо выполнять по-отдельности

`mkdir web-env-practice`
(создаёт папку с названием "web-env-practice")

`cd web-env-practice`
(входит в созданную папку, чтобы дальнейшие действия производились в этой папке)

`git init`
(инициализация репозитория git на локальном компьютере)

ㅤ

*III.	Создание проекта*
1.	Внутри папки web-env-practice создайте папку project и создайте в ней файлы: 

index.html

css/style.css

js/script.js

(В случае с Windows проще и быстрее руками создать)

2.	Создайте базовый HTML (см. пример ниже) и свяжите style.css и script.js.

Пример содержимого index.html:
```bash
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Первая страница</title>
  <link rel="stylesheet" href="css/style.css" />
</head>
<body>
  <h1>Привет, мир!</h1>
  <button id="btn">Нажать</button>
  <script src="js/script.js"></script>
</body>
</html>
Пример style.css:
body { font-family: Arial, sans-serif; padding: 20px; }
h1 { color: #2b6cb0; }
Пример script.js:
document.getElementById('btn').addEventListener('click', () => {
  alert('Кнопка нажата');
});
```

ㅤ

*IV. Запуск локального сервера*

•	Вариант A (рекомендованный): 

Установите расширение Live Server в VS Code и запустите сервер (клик правой кнопкой по index.html → Open with Live Server). 

Запишите URL и убедитесь, что страница открывается.

Пояснения к работе с VS Code:

1.	Откройте проект в VS Code.

2.	Установите и включите полезные расширения: Live Server, Prettier — Code formatter, ESLint (опционально).

3.	Настройте форматирование (Prettier) как формат по сохранению (Format on Save).

•	Вариант B: Инициализируйте npm и установите http-server: 

**ВАЖНО ДЕЛАТЬ ВСЁ ЧЁТКО ПО ПОРЯДКУ!**

`npm init -y`

`npm install --save-dev http-server`

В package.json добавьте скрипт в тело scripts: "start": "http-server ./project -c-1"

Запустите: 

`npm run start`

Откройте в браузере http://localhost:8080 (или адрес, указанный в терминале).


ㅤ

*V. Фиксация результата в Git*

1.	Добавьте файлы, сделайте коммит: 

`git add .`

`git commit -m "Initial project and environment setup"`

2.	Создайте удалённый репозиторий на GitHub
Если вы создаёте репозиторий руками, а не командой, то для того, чтобы связать репозиторий с локального компьютера и на Gitub 
используете:

`git remote add origin "АДРЕС РЕПОЗИТОРИЯ GITHUB"`

3. Если нет проблем с файлами (один из репозиториев полностью пустой или они не имеют разных файлов) то, 
используем:

`git branch -M main`

`git push -u origin main`

4. если файлы всё же конфликтуют, то используем:

`git pull origin main --allow-unrelated-histories`

после чего файлы на локальном компьютеры поддтянут недостающие файлы из репозитория GitHub после чего можно сделать предыдущие шаг (3) по пушу ветки в GitHub
