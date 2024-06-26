Предусловие: пользователи должны быть авторизованы

**#1 Продажа товара с Авито доставкой**

***1.1 Товар "б/у" из хорошо изученной категории "Книги". Покупатель забирает себе товар.*** 

Предусловие: счетчики изначально сброшены в 0.
1) Продавец размещает объявление о продаже б/у товара из категории хорошо изученной категории "Книги" .
2) Покупатель нажимает на кнопку "Купить с доставкой"
3) Покупатель выбирает пункт выдачи или курьерскую службу. Указывает адрес.
4) Покупатель оплачивает товар.
5) Покупатель получает товар от курьера или забирает в пункте выдачи.

Ожидаемый результат: 
У покупателя и продавца - счетчики экологического вклада увеличиваются. 
Счетчик воды = 50 литров;
счетчик энергии =  14 кВт*ч;
счетчик CO2 =  2,1 кг.

***1.1.1 Удаление из архива товара, по которому был посчитан экологический вклад***
1) Запоминаем начальное состояние счетчиков. start_CO2, start_water, start_energy
2) Мои объявления -> Архив. Находим товар, добавленный в тест кейсе 1.1.
3) К товару нажимаем ... (троеточие). В выпадающем меню выбираем "Удалить". (либо запросом через БД)

![1404](https://github.com/Natalia-Semushina/avitoTestQA/assets/69298168/f9531459-25da-44f2-91c7-1d7c2744bf8d)

4) Получаем состояние счетчиков end_CO2, end_water, end_energy
5) Вычисляем разницу shift_СО2 = end_CO2 - start_CO2, shift_water = end_water - start_water, shift_energy = end_energy - start_energy

Ожидаемый результат: shift_СО2 = 0, shift_water = 0, shift_energy = 0

***1.2 Товар "Новый" из хорошо изученной категории "Книги". Покупатель забирает себе товар.*** 

Предусловие: запоминаем текущее состояние счетчиков. start_CO2, start_water, start_energy
1) Продавец размещает объявление о продаже "Нового" товара из категории хорошо изученной категории "Книги" .
2) Покупатель нажимает на кнопку "Купить с доставкой"
3) Покупатель выбирает пункт выдачи или курьерскую службу. Указывает адрес.
4) Покупатель оплачивает товар.
5) Покупатель получает товар от курьера или забирает в пункте выдачи.
6) Проверяем текущее состояние счетчиков end_CO2, end_water, end_energy
7) Вычисляем разницу shift_СО2 = end_CO2 - start_CO2, shift_water = end_water - start_water, shift_energy = end_energy - start_energy

Ожидаемый результат: 
У покупателя и продавца - счетчики экологического вклада не изменятся. shift_СО2 = 0, shift_water = 0, shift_energy = 0 

***1.3 Товар из любой хорошо изученной категории. Покупатель отказывается от товара при получении.***
1) Запомнили начально состояние счетчиков у покупателя и продавца. start_CO2, start_water, start_energy
2) Продавец размещает объявление о продаже товара из категории хорошо изученной категории.
3) Покупатель нажимает на кнопку "Купить с доставкой"
4) Покупатель выбирает пункт выдачи или курьерскую службу. Указывает адрес.
5) Покупатель оплачивает товар.
6) Покупатель отказывается от товара в пункте выдачи или при доставке курьером.
7) Получаем текущее состояние счетчиков end_CO2, end_water, end_energy
8) Вычисляем разницу между конечными и начальными показателями счетчиков. shift_СО2 = end_CO2 - start_CO2, shift_water = end_water - start_water, shift_energy = end_energy - start_energy

Ожидаемый результат: у покупателя и продавца - счетчики экологического вклада не изменяются;
shift_СО2 = 0, shift_water = 0, shift_energy = 0

   
***1.4 Товар из плохо изученной категории***
1)  Запомнили начальное состояние счетчиков у покупателя и продавца. start_CO2, start_water, start_energy
1) Продавец размещает объявление о продаже товара из плохо изученной категории Готовый бизнес и оборудование -> Оборудование для бизнеса.
2) Покупатель нажимает на кнопку "Купить с доставкой"
3) Покупатель выбирает пункт выдачи или курьерскую службу. Указывает адрес.
4) Покупатель оплачивает товар.
5) Покупатель получает товар от курьера или забирает в пункте выдачи.
6) Получаем текущее состояние счетчиков end_CO2, end_water, end_energy
7) Вычисляем разницу между конечными и начальными показателями счетчиков у покупателя и у продавца. shift_СО2 = end_CO2 - start_CO2, shift_water = end_water - start_water, shift_energy = end_energy - start_energy
   
Ожидаемый результат: покупатель - у покупателя и продавца - счетчики экологического вклада не изменяются;
shift_СО2 = 0, shift_water = 0, shift_energy = 0.

**#2 Продажа товара без Авито доставки**

***2.1 Товар "Б/У" из хорошо изученной категории "Легковой автомобиль". Перевод единиц измерения. Продал на Авито***
1) Запомнили начальноесостояние счетчиков. start_CO2, start_water, start_energy
2) Продавец размещает объявление о продаже товара из хорошо изученной категории Легковой автомобиль.
3) Продавец переходит в раздел Мои объявления -> Выбирает объявление продажи автомобиля -> Нажимает ... -> Нажимает "Снять с публикации"
4) Продавец в появившемся диалоговом окне выбирает пункт "Продал на Авито"
5) Получили конечное состояние счетчиков end_CO2, end_water, end_energy
6) shift_СО2 = end_CO2 - start_CO2, shift_water = end_water - start_water, shift_energy = end_energy - start_energy

Ожидаемый результат: У продавца счетчики экологического вклада увеличились. Полученные изменения счетчиков попадают в диапазоны 
4 800 <= shift_СО2 <= 9 100 кг,  30 000 <= shift_water <= 58 000 литров,  19 200 <= shift_energy <= 36 400 кВт*ч;
счетчик CO2 - кг перевелись в тонны;
счетчик воды - литры перевелись в метры кубические;
счетчик энергии - кВт*ч перевелось в тыс. кВт*ч.

***2.2 Товар  "Б/У" из хорошо изученной категории "Легковой автомобиль". Продал где-то еще***
1) Запомнили начальноесостояние счетчиков. start_CO2, start_water, start_energy
2) Продавец размещает объявление о продаже товара из хорошо изученной категории Легковой автомобиль.
3) Продавец переходит в раздел Мои объявления -> Выбирает объявление продажи автомобиля -> Нажимает ... -> Нажимает "Снять с публикации"
4) Продавец в появившемся диалоговом окне выбирает пункт "Продал где-то еще"
5) Получили конечное состояние счетчиков end_CO2, end_water, end_energy
6) shift_СО2 = end_CO2 - start_CO2, shift_water = end_water - start_water, shift_energy = end_energy - start_energy

Ожидаемый результат: У продавца счетчики экологического вклада увеличились. Полученные изменения счетчиков попадают в диапазоны 
4 800 <= shift_СО2 <= 9 100 кг,  30 000 <= shift_water <= 58 000 литров,  19 200 <= shift_energy <= 36 400 кВт*ч.


***2.3 Товар "Б/У" из хорошо изученной категории "Легковой автомобиль". Другая причина продажи.***
1) Запомнили начальноесостояние счетчиков. start_CO2, start_water, start_energy
2) Продавец размещает объявление о продаже товара из хорошо изученной категории Легковой автомобиль.
3) Продавец переходит в раздел Мои объявления -> Выбирает объявление продажи автомобиля -> Нажимает ... -> Нажимает "Снять с публикации"
4) Продавец в появившемся диалоговом окне выбирает пункт "Другая причина"
5) Получили конечное состояние счетчиков end_CO2, end_water, end_energy
6) shift_СО2 = end_CO2 - start_CO2, shift_water = end_water - start_water, shift_energy = end_energy - start_energy

Ожидаемый результат: У продавца счетчики экологического вклада не изменились. shift_СО2 = 0, shift_water = 0, shift_energy = 0.




