# Stepik_ML_contest 

Практическим проектом будет анализ активности студентов онлайн курса Введение в анализ данных в R, спасибо команде stepik, что предоставили анонимизированные данные.

В этом модуле, мы разберемся с задачей, начнем исследовать данные!

# Описание данных:

[events_train.csv](https://stepik.org/media/attachments/course/4852/event_data_train.zip) - данные о действиях, которые совершают студенты со стэпами

1. **step_id** - id стэпа  
2. **user_id** - анонимизированный id юзера  
3. **timestamp** - время наступления события в формате unix date  
4. **action** - событие, возможные значения:  
    + *discovered* - пользователь перешел на стэп
    + *viewed* - просмотр шага,
    + *started_attempt* - начало попытки решить шаг, ранее нужно было явно нажать на кнопку - начать решение, перед тем как приступить к решению практического шага
    + *passed* - удачное решение практического шага  

[submissions_train.csv](https://stepik.org/media/attachments/course/4852/submissions_data_train.zip) - данные о времени и статусах сабмитов к практическим заданиям

1. **step_id** - id стэпа  
2. **timestamp** - время отправки решения в формате unix date  
3. **submission_status** - статус решения  
4. **user_id** - анонимизированный id юзера  

# Структура проекта 

notebooks - каталог с блокнотами решений и создания признаков для обученя моделей 
libs - папка с кодом для генерации датасетов, признаков и вспомогательными модулями  
data_iter1.py - признаки для модели(baseline) основанных на том что давали в курсе  
data_iter_auto.py - признаки сгенерированные автоматически  
data_iter_final.py - признаки для финальной модели в соревновании  
**data** - папка с данными  
**event_data_train.zip** - данные о действиях, которые совершают студенты со стэпами. Используются для обучения.  
**submissions_data_train.zip** - данные о времени и статусах сабмитов к практическим заданиям. Используются для обучения.  
**events_data_test.zip** - данные о действиях, которые совершают студенты со стэпами. Используются для прогноза.  
**submission_data_test.zip** - данные о времени и статусах сабмитов к практическим заданиям. Используются для прогноза.  
**submission_example.csv** - пример файла с предсказаниями.  
**course_data.json** - дополнительный датасет с информацией о курсе Анализ данных в R. Содержит информацию о step-аx(доступна gо ключу steps), а также других сущностях курса.  
**hb_course_info.csv** - дополнительный датасет c важной информацией о курсе, собранный в таблицу на основе данных из course_data.json. Удалены незначительные, на мой взгляд, признаки.  
**reports** - в этой папке размещаются файлы с прогнозом.  
