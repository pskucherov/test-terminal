
Выбираем html файлы, в которых внутри тега title есть слово ШРИ. Заменяем весь заголовок на ШРИ %)

cp -ri ./ ../backup && \

ack-grep '[&lt;title>.*ШРИ.*|.*ШРИ.*&lt;\/title>]' --type=html ./ -l \

xargs perl -i -pe 's/КИТ/ШРИ/g while m/title>/ && m/КИТ/;'


Восстановить: 

cp -ri ../backup/* ./




