# Async, defer, динамические скрипты

Изучено: Yes

**Defer**

- прописываем как обычный HTML - атрибут в тег script
- дает продолжать загружать HTML-документ, при этом script - загружается в фоновом режиме → запустить этот скрипт, когда он загрузиться и когда DOM - дерево будут готово
- не блокирует загрузку страницу!!!
- При наличии двух скриптов с defer - будут загружаться последовательно → дает загружать сначала полезный скрипт (библиотеки - jQuery), а потом только наш - который зависит от предыдущей

**Async**

1. Страница не ждет асинхронный код, она сама загружается и обрабатывается
2. DOMContentLoaded и асинхронный скрипт — не ждут друг друга
3. Скрипт начнется загружаться как только до него дойдет страницы и сразу же запуститься. Скрипты с async являются самостоятельными в плане обработки и отображения
- будем использовать для скриптов неподвязанных к каким-либо DOM структурам (метрики и счетчики)