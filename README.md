# matrix_test_solution
My solution to the matrix_test

Решение задачи:

1. При дизассемблировании программы в сегменте данных можно найти массив строк состоящий из пяти элементов: [ "Matrix", "has", "you", ":)", ":P" ]
2. При декомпиляции кода функции <b>main</b> становится видно, что в цикле <b>5</b> раз вызывается некая прцедура с одним целочисленным аргументом.
3.  Просмотрев код этой процедуры можно прийти к выводу, что именно в ней осуществляется вывод строк массива. В функции <b>main</b> эта процедура вызывается с аргументом <b>4</b>, который является индексом выводимой строки (":P")
4. Чтобы вывести все строки из массива, нужно в качестве аргумента передать переменную-счетчик, которая используется в цикле в функции <b>main</b>
5. Для замены передаваемого аргумента нужно в дизассемблированном коде заменить команду "push 4" (положить значение 4 в стек) на "push esi" (положить значение регистра <i>esi</i> в стек)
6. Так как команда "push 4" на <b>1</b> байт длиннее команды "push esi" нужно добавить команду <i>nop</i> для выравнивания

Для решения использовалась программа IDA Pro 6.6
