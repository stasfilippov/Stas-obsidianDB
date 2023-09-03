# SetTimeOut, setInterval

Изучено: No

**Отличие setInterval от setTimeOut**

- ему безразлично сколько длится функция, вызванная **setInterval**. При каждом истечение времени он будет вызывать еще одну функция, несмотря на состояние функции, вызванной перед этим. Для решения данной проблемы используют
    - рекурсивный вызов **setTimeout**
    
    ```jsx
    let id = setTimeout(function log() {
        console.log('Hello');
        id = setTimeout (log, 500);
    }, timeout);
    ```