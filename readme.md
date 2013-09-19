1. Сохраняем содержимое директории в папку backup

2. Выбираем html файлы, которые содержат в себе открывающийся или закрывающийся теги title + слово КИТ

3. Заменяем слова КИТ, если они стоят после или перед тегом title

cp -ri ./ ../backup && \

ack-grep '[&lt;title>.*КИТ.*|.*КИТ.*&lt;\/title>]' --type=html ./ -l | \

xargs perl -e 's/КИТ/ШРИ/g while m/[&lt;title>.*КИТ.*|.*КИТ.*&lt;\/title>]/g;'


Восстановить файлы из бэкапа: 

cp -ri ../backup/* ./

=====

Другой способ бэкапа (если файл был изменён, создаётся резервная копия "file.ext~"): 

ack-grep '[&lt;title>.*КИТ.*|.*КИТ.*&lt;\/title>]' --type=html ./ -l | \

xargs perl -i~ -e 's/КИТ/ШРИ/g while m/[&lt;title>.*КИТ.*|.*КИТ.*&lt;\/title>]/g;'

=====

Последний вариант с многострочной заменой: 

find . -type f -iname '*.html' -print0 | \ 

xargs -0 perl -i.bak -0777 -npe 's/КИТ/ШРИ/g while /&lt;title>(.*?)&lt;\/title>/gs'
