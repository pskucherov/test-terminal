
Выбираем html файлы, в которых внутри тега title есть слово ШРИ. Заменяем весь заголовок на ШРИ %)

ack-grep '<title>.*ШРИ.*<\/title>' --type=html ./ -l | \

xargs perl -i -pe "s/<title>[\s\S]*КИТ[\s\S]*<\/title>/<title>ШРИ<\/title>/g;"



