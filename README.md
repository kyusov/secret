# secret
## Алгоритмы для машины Тьюринга
С помощью этих задач Вы можете проверить свои навыки в построении алгоритмов с помощью машины Тьюринга
## Состояния и условия
Состояния машины Тьюринга обозначаются как <b>q</b>

В данных задачах условие начала работы алгоритма:
  1. Машина должна начинать работу с пустого символа (в данной реализации обозначается символом <b>B</b>)
  2. Машина должна начинать работу из состояния <b>s</b>
  3. Машина успешно завершит работу, когда получит состояние <b>STOP</b>
## Дополнения
Приветствуется дополнение репозитория новыми задачами

## Пример задачи
#### Задача
Постройте детерминированную машину Тьюринга, вычисляющую функцию f(n) = n + 2 в унарной системе счисления
#### Условия
Машина должна начинать работу в конфигурации (s, B1...1) и заканчивать работу в конфигурации (STOP, B1...1)

Пусть n = 2, что соответствует 11 в унарной системе. Опишем команды для работы алгоритма:
  1. <b>Bs->Bq2R</b>
  
     Машина начинает работу в состоянии <b>s</b> и ожидает на вход пустой символ. Если она получила пустой символ, то машина перейдет в состояние <b>q2</b>, при этом оставит на месте пустой символ и сдвинется на одну ячейку вправо
  2. <b>1q2->1q2R</b>
  
     Если машина получает на вход 1, то она оставляет на этом месте 1 и двигается дальше вправо
  3. <b>Bq2->1q3R</b>
  
     Если машина получила пустой символ(пробел), то есть прошла все единички, то она переходит в состояние <b>q3</b> и меняет содержание этой ячейки на 1
  4. <b>Bq3->1q4L</b>
  
     Повтор шага 3, только после вставки единицы на место пустого символа, машина идет влево (символ <b>L</b>)
  5. <b>1q4->1q4L</b>
  
     Машина идет влево до момента пока не встретит символ отличный от 1
  6. <b>Bq4->BSTOP</b>
  
     Если машине встретился пустой символ, то мы оставляем эту ячеку неизменённой и останавливаем машину
     
  <b>Пример:</b>
     
     n = 4
     
     В унарной системе: 1111
     
     Прибавляем 2 => 1111 + 11
     
     Машина должна остановить свою работу когда прибавит к нашему числу (1111) двойку (11)
     
     Подаем на вход: B1111
     
     Получаем на выходе: B111111
     
## Проверка работы алгоритма
[Интерактивный тренажер](http://domic.isu.ru/res/sim/tm.html)
