
1. Сохраняем содержимое директории в папку backup

2. Выбираем html файлы, которые содержат в себе открывающийся или закрывающийся теги title + слово КИТ

3. Заменяем слова КИТ, если они стоят после или перед тегом title

cp -ri ./ ../backup && \

ack-grep '[&lt;title>.*КИТ.*|.*КИТ.*&lt;\/title>]' --type=html ./ -l | \

xargs perl -i -pe 's/КИТ/ШРИ/g while m/[&lt;title>.*КИТ.*|.*КИТ.*&lt;\/title>]/g;'


Восстановить файлы из бэкапа: 

cp -ri ../backup/* ./




