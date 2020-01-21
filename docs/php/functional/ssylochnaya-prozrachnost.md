---
description: Математические принципы создания функций без сайд эффекта
---

# Ссылочная прозрачность

В функциональном программировании функции рассматриваются с математической точки зрения, как _мэппинг_ типов.

Например:

`f :: A -> B`

Это функция `f`, которая принимает объект `А` и возвращает объект типа `B`. По этому, инкремент записывается:

`increment :: int -> int`

Ссылочно-прозрачные функции всегда могут быть заменены их вычисленным значением, за счет отсутствия в них сайд эффекта:

`add(square(increment(4)), increment(16)) =~ add(square(5), 17) =~ add(25, 17) =~ 25 + 17 =~ 42`

**Функциональное программирование основывается на чистых функциях, а композиция является ключевым элементом, который заставляет систему работать.**