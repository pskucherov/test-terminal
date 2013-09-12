
Выбираем html файлы, в которых внутри тега title есть слово ШРИ. Заменяем весь заголовок на ШРИ %)

cp -ri ./ ../backup && \

ack-grep '&lt;title>.*ШРИ.*&lt;\/title>' --type=html ./ -l | \

xargs perl -i -pe "s/&lt;title>[\s\S]*КИТ[\s\S]*<\/title>/&lt;title>ШРИ<\/title>/g;"


Восстановить: 

cp -ri ../backup/* ./




