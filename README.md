# FinNet 

Дан анонимизированный граф транзакций между юридическими лицами России. Из него была удалена часть рёбер. Ваша задача восстановить их.<br>
В данном репозитории можно найти baseline решение: https://github.com/finnethackaton/finnet<br><br>
## Формат входных данных
Набор данных доступен по ссылке: https://drive.google.com/drive/folders/1NahA7Aw0CwMIMrS8cjeiaOH8FzxocxHu?usp=sharing <br>
Файл vertices.csv содержит информацию о юридических лицах:<br>
• id — id юридического лица;<br>
• main_okved — основной ОКВЭД юридического лица;<br>
• region_code — код региона юридического лица;<br>
• company_type — тип юридического лица.<br>
Файл edges.csv содержит информацию об обороте между юридическими лицами, прошедшем через счета банка Точка:<br>
• id_1 — id первого юридического лица;<br>
• id_2 — id второго юридического лица;<br>
• value — суммарный оборот между юридическими лицами, к которому применено некоторое монотонное преобразование;<br>
• n_transactions — количество транзакций между юридическими лицами, к которому было применено некоторое монотонное преобразование.<br>
Обратите внимание на то, что рёбра неориентированные! Граф не содержит кратных рёбер, но может содержать петли. Файл edges.csv содержит исключительно не удалённые рёбра.<br>
Файл ids.csv содержит информацию о наиболее крупных юридических лицах, для которых требуется восстановить ребра:<br>
• id — id юридического лица<br><br>
## Формат выходных данных 
Из графа было удалено 100000 рёбер, инцидентных юридическим лицам из файла ids.csv. Ваша задача — восстановить удалённые рёбра и отправить в проверяющую систему .csv файл, который помимо заголовка «id_1,id_2» (без кавычек) содержит 100000 строк в формате id_1,id_2, где:<br>
• id_1 — id первого юридического лица;<br>
• id_2 — id второго юридического лица.<br>
Концы рёбер разрешается выводить в любом порядке. Хотя бы один конец ребра должен содержаться в файле ids.csv. Оба конца ребра должны содержаться в файле vertices.csv. Все рёбра должны быть уникальными (с учётом того, что они неориентированные).<br><br>
## Система оценки
Метрика, по которой будет оцениваться решение — размер пересечения вашего ответа с реальным множеством удалённых рёбер.<br>
Множество удалённых рёбер было разбито на две равные непересекающиеся части по 50000 рёбер. Во время соревнования вы будете видеть результат пересечения с первой частью. После завершения соревнования мы выберем последнее решение, набравшее положительное число баллов, и протестируем на второй части множества удалённых рёбер. Результат такого тестирования будет учитываться в качестве финального результата.<br><br>
## Примечание
После завершения соревнования каждому участнику нужно предоставить организаторам воспроизводимый код последнего решения, используемого в финальном тестировании.
