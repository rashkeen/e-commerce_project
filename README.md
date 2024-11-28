# Проект e-commerce
### Цель: Провести анализ данных заказов электронного магазина, включая Ad-hoc анализ, для выявления когорты с наивысшим уровнем удержания на третий месяц, а также осуществить RFM сегментацию.
### Стэк: Python, Pandas, Matplotlib
### Выполненные задачи:
1. Обработка данных и общая характеристика. Все колонки времени приведены к единому формату.
2. Выполнен Ad-hoc анализ для ответа на такие вопросы как  
   - Кол-во пользователей, которые совершили покупку только один раз  
     90557, что равно 96% всех пользователей 

   - Среднее число заказов в месяц, которое не доставляется по разным причинам
   
   | order_status | fail_orders | fail_orders_by_month |
   |-------------:|------------:|----------------------|
   |     canceled |         625 |                25.00 |
   |  unavailable |         609 |                24.36 |

   - По каждому товару определить, в какой день недели товар чаще всего покупается
   
   |       |                       product_id | day_of_week | quantity |
   |------:|---------------------------------:|------------:|----------|
   | 15898 | 422879e10f46682990de24d770e7f83d |   Wednesday |       93 |
   | 36512 | 99a4788cb24856965c36a24e339b6058 |      Monday |       92 |
   | 41044 | aca2eb7d00ea1a7b8ebd4e68314663af |    Thursday |       89 |
   | 20123 | 53b36df67ebb7c41585e8d54d6772e08 |     Tuesday |       76 |
   | 13536 | 389d119b48cf3043d311335e499d9c6b |    Thursday |       67 |
   |   ... |                              ... |         ... |      ... |

 - Сколько у каждого из пользователей в среднем покупок в неделю
   
   |               customer_unique_id |                avg_orders_per_week |
   |---------------------------------:|-----------------------------------:|
   | 0000366f3b9a7992bf8c76cfdf3221e2 |                               0.23 |
   | 0000b849f77a49e4a4ce2b2a4ca5be3f |                               0.23 |
   | 0000f46a3911fa3c0805444483337064 |                               0.23 |
   | 0000f6ccb0745a6a4b88665a16c9f078 |                               0.23 |
   | 0004aac84e0df4da2b147fca70cf8255 |                               0.23 |
   |                              ... |                                ... |

3. Проведен когортный анализ пользователей. Определена когорта с наивысшим retention на 3-й месяц: 2017-05

   |  cohort |   1  |   2  |   3  |   4  |   5  |   6  |   7  |   8  |   9  |   10  |   11  |   12  |   13  |   14  |   15  |   16  |   17  |   18  |   19  |
   |--------:|-----:|-----:|-----:|-----:|-----:|-----:|-----:|-----:|-----:|------:|------:|------:|------:|------:|------:|------:|------:|------:|------:|
   | 2017-01 | 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.27% | 0.41% | 0.14% |
   | 2017-02 | 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.06% | 0.24% |       |
   | 2017-03 | 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.08% | 0.16% |       |
   | 2017-04 | 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.13% |       |       |
   | 2017-05 | 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% |       |       |       |
   | 2017-06 | 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% |       |       |       |
   | 2017-07 | 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% |       |       |       |
   | 2017-08 | 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% |       |       |       |
   | 2017-09 | 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% |       |       |       |
   | 2017-10 | 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% |       |       |       |
   | 2017-11 | 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% |       |       |       |
   | 2017-12 | 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41%| 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% | 0.41% |       |       |       |
     
5. RFM сегментация пользователей
   Выполнил сегментацию пользователей по квантилям с использованием метрик Recency,	Frequency,	Monetary по стандартной семантике.  
   В результате выявлено, что подавляющее кол-во пользователей относятся к группе "Спящих". Магазину требуется повести мероприятия для увеличения активности пользователей: разработка РК, промоакции, улучшение системы предложений и т.д.  
   Кроме этого, приведен вариант разделения пользователей с помощью метода k-средних.
