---
title: Ежемесячный отчёт о разработке Empires UE4  - Август 2020
author: RoyAwesome
date: "2020-09-12"
tags: [ "UNREALENGINE" ]
post_type: UE4
---

# Обновление проекта
## Roy Awesome

Всем привет

В этом месяце я невероятно рад объявить вам, что мы завершили первый этап развития проекта Empires UE4. Это знаковое событие является крупным достижением нашей команды, и теперь это самый успешный ремейк Empires, над которым мы когда-либо работали за эти 15 лет. Хотя у нас есть довольно много способов сделать этот проект играбельным и веселым, я очень горжусь людьми и прогрессом, которого они добились за эти 3 коротких месяца.   

Итак, вот наша путеводная карта прогресса:

Первый Этап (Минимально возможный продукт) (ГОТОВО)


  * Игроки могут присоединиться к игровому серверу и делать пиу-пиу в других игроков. Они распределены на две команды и имеют примитивный выбор точек спавна. Они могут общаться друг с другом и видеть свои результаты на табло. По крайней мере, один класс реализован для каждой команды, с одним пистолетом, одним вторичным и одной гранатой. Игроки должны иметь возможность общаться друг с другом через текстовый чат

Второй Этап (Прототип пехотных сражений) (Мы здесь)


  * Игроки могут разделяться на отряды, и все классы реализованы. Игроки могут выбирать точку спавна (так же спавны могут быть размещены вручную). Многие из простых навыков, утилит и гранат реализованы. Игроки могут бегать и приседать. Игроки могут взаимодействовать с контейнерами боеприпасов, чтобы получить боеприпасы. У команд есть билеты, и когда одна команда исчерпывает свои билеты, игра заканчивается.

Третий Этап (Прототип техники)


  * Временно: игроки могут размещать здания. Все навыки и умения реализованы. Примитивные транспортные средства реализованы, но без турелей и навыков. Захватываемые цели размещаются в уровнях. Карта Emp_Escort или Emp_Glycencity, воспроизведена от начала до конца. Казармы, Оружейная и Завод функционируют. Игроки должны иметь возможность общаться друг с другом через голосовой чат.

Четвёртый Этап (Прототип командира)


  * Все транспортные средства реализованы, хотя их загрузка может быть изменена. Командирская машина реализована, и игрок может перейти в режим RTS и размещать здания. Ресурсы теперь существуют и функционируют. Отряды имеют командные способности и командный счет. Ремонтная станция, радар и нефтеперерабатывающий завод функционируют. Возможно сыграть в классический Empires.

Пятый Этап (Классический Empires)


  * Плагин "Парашюты" должен быть реализован (и опционально). Все карты из Empires должны быть либо импортированы, либо переделаны. Возможность плавания в воде. Члены сообщества Empires должны рассматривать игру как полнофункциональную, как равную Source версии.

Итак, как вы можете видеть, нам осталось еще немного, мы добились серьезного прогресса!

Теперь некоторые из вас могут подумать, что, если нам потребовалось около 3 месяцев, чтобы завершить Первый Этап, нам может потребоваться еще 3 месяца для следующего и так далее, и так далее. Простая экстраполяция позволит доделать эту игру где-то в следующем году. Я не исключаю этого (в конце концов, мы все волонтеры с дневной работой), однако я предвижу, что Второй Этап пройдет гораздо быстрее, чем первый. Довольно много времени, затраченного на Первый Этап, было потрачено на то, чтобы убедиться, что мы стоим на прочном фундаменте с нашим игровым кодом. Сейчас у нас есть очень хороший загрузчик ассетов, который позволяет нам быстро создавать новый контент, у нас есть солидный арт-загрузчик ассетов, который позволяет нам использовать художественные ассеты, и у нас было много трудностей и ньюансов, которые уже решены и устранены на данный момент. К примеру, нам потребовалось 3 недели, чтобы заставить работать выделенные сервера Steam. Такой белеберды во Втором Этапе отроду не будет, так что все должно пойти гораздо быстрее.

_Примечание автора: приношу извинения за позднюю публикацию этого обновления. Из-за того, что это волонтерский проект, публикация этого обновления была отложена из-за моих охрененных рабочих дедлайнов, а затем мой штат буквально вспыхнул._


# Звук и Музыка
## KGBEATS

Привет - с вами KGBEATS.

К сожалению, у меня не было возможности заняться проектом на музыкальном фронте в этом месяце, и это могло бы быть таковым и дальше. Моя реальная работа заняла центральное место в моей жизни, что оставило мало времени для побочных занятий, таких как этот проект. Однако я рассматриваю это лишь как временную неудачу и надеюсь вернуться в русло композирования/продюсирования, когда этот аспект моей жизни более или менее уладится.

Однако вся команда работает безумно усердно ради ремейка. Вам стоит посмотреть на них и похвалить их вклад, ведь они этого больше всего заслуживают! 

# Обновление: Программирование Геймплея
## RoyAwesome

Август выдался на редкость продуктивным! Теперь игра, в основном, работает, просто нужно доделать некоторые функции.

Я потратил довольно много времени, пытаясь интегрировать арты и анимацию в игру. Это, как правило, непривлекательная часть разработки игр, но чрезвычайно важно создать хороший загрузчик ассетов, чтобы художники, аниматоры и дизайнеры геймплея могли взять созданные ими ассеты и ввести их в игру и уже работать с игровыми событиями (такими как стрельба, перезарядка и т. д.). В этом месяце я сел и полностью внёс эти системы в приятный и простой способ написания сценариев таких вещей, как прикрепление оружия к частям тела игрока, анимация смены оружия, перезарядки и тому подобное. Все эти вещи работают как для первого лица (то, что вы видите) так и для третьего лица (то, что вы видите на других игроках). Все они чрезвычайно просты в настройке, поэтому добавление новых артов и анимации для различных видов оружия должно быть легким делом и не должно требовать от программистов настройки этих вещей.

Как только я разобрался с арт-загрузчиком ассетов, я сменил тактику и закончил систему текстового чата. Twusty проделал хорошую работу в начале проекта, создав систему для маршрутизации текстовых сообщений различным игрокам, и я сделал акцент на нее, дабы обобщить ее и создать скриптовые правила для того, как сообщения чата должны доходить до других игроков. Я также обобщил систему правил, чтобы разрешить маршрутизацию любых данных сообщений, и расширил ее для работы с системой сценариев “Toast”. Оно будет использоваться для разделения игровых событий из чата, таких как “Вы были повышены” и уведомления об убийстве, подобные современным шутерам. Даже с искусством постановки эти уведомления об убийстве выглядели и чувствовали себя действительно хорошо и были большим улучшением геймплея. Я также потратил некоторое время на создание универсальной системы маршрутизации для работы с голосовым чатом, поэтому мы также можем написать сценарий, кто может отправлять и кто получает данные голосового чата. В то время как план состоит в том, чтобы иметь командный VOIP, мы можем легко экспериментировать с местным VOIP, отрядным VOIP или с тем, что мы хотим видеть.  

 <video controls>
  <source src="https://cdn.discordapp.com/attachments/704846651252015205/745108375561437225/2020-08-17_19-34-03.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video> 

_Чат, демонстрирующий различные "каналы", которые могут быть созданы с помощью системы чата.  Это показывает командный чат и весь чат._

 <video controls>
  <source src="https://cdn.discordapp.com/attachments/704846651252015205/747703609143066654/2020-08-24_23-26-40.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video> 

_Уведомления убийства.  Когда вы убиваете другого игрока, вы получаете уведомление о том, что вы его убили_

Пока я тестировал различные вещи, я заметил, как трудно было понять, наносите ли вы урон или получаете его, поэтому я провел вечер, создавая уведомления о повреждениях. Они чрезвычайно просты, но заставляют игру чувствовать себя хорошо. Когда вы стреляете в игрока, в центре экрана выскакивает маленький “X”и издаётся небольшой “Звуковой Сигнал”, указывающий на то, что вы нанесли урон. Когда вы получаете урон, на вашем экране мигает красная полоса, указывающая, с какой стороны вы получили урон. Сейчас все очень просто, но это действительно сделало игру лучше и более отзывчивой. 

 <video controls>
  <source src="https://cdn.discordapp.com/attachments/698655659193008208/747276690664718394/2020-08-23_19-10-15.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video> 

_Уведомления о повреждениях.  На главном экране отображается человек, получающий урон, а на меньшем - "X" при нанесении урона._

Наконец, я построил общую систему отдачи. В то время как Source-Empires не имеет отдачи для многих пушек, тяжёлые ручные пулемёты имеют чрезвычайно высокую отдачу стоя, заставляя пользователей приседать или лежать при их использовании. Однако, поскольку большинство игр в наши дни имеют отдачу для каждой пушки, я хотел создать универсальную систему отдачи, которая может делать как чрезвычайно высокую отдачу у пулемётов, так и тонкую, контролируемую отдачу, которую имеют современные шутеры. Итак, с этой целью я создал концепцию “Анимации Отдачи”, которая представляет собой скриптовый объект отдачи, который добавляется к игроку, когда происходит событие отдачи. Он смешивается и исчезает, а также перемещает контрольное вращение игрока, чтобы имитировать движение отдачи. Каждая анимация отдачи может принимать полезную нагрузку данных от генератора событий отдачи, что позволяет нам писать ряд статистических данных, которые управляют такими вещами, как направление отдачи, интенсивность и то, как ствол опускается после стрельбы. В то время как возврата отдачи в настоящее время нет (т. е. без компенсации отдачи оно возвращается в центр), я планирую создать модель отдачи, которая действительно опускает оружие, но если вы переместите мышь, чтобы компенсировать отдачу, она остановится.  

 <video controls>
  <source src="https://cdn.discordapp.com/attachments/698655659193008208/746986249516089394/2020-08-22_23-56-23.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video> 

_Простой пример отдачи.  Оружие будет скакать вверх при стрельбе.  Все это можно записать и настроить, что позволяет дизайнерам создавать любую модель отдачи, которую они хотят_



{{< image-resize scriptablerecoil.png >}}

_Снапшот скриптовой отдачи. Используя простой чертёжный код, мы можем создавать все виды механик с отдачей._

Хотя эта система, безусловно, будет использоваться пулемётами, мне было бы интересно услышать, что люди думают о добавлении отдачи к каждому оружию. Есть ли современные шутеры, в которых, по вашему мнению, реализована хорошая отдача? Может ли отдача помочь сбалансировать снайперки и винтовки? Залетайте к нам в Дискорд канал Empires, нам важно ваше мнение! Есть много споров на эту тему, и поскольку теперь у нас есть скриптовая система отдачи, у нас появилось много направлений, в которых мы можем пойти с ней.  


# Гранаты
## Megafunk

Привет, я Megafunk, и я новичок в Empires. Я присоединился к этому проекту, чтобы улучшить свои навыки в UE4, и в настоящее время я занимаюсь гранатами. До сих пор я делал простые гранаты, которые бросаются и наносят урон. 

# Рескин солдата Северных Фракций
## f1r3w4rr10r

После рескина солдата Бреноди, я также занялся рескином солдата СФ .

 <video controls>
  <source src="./nfsoldier.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video> 

_Солдат СФ в цикле анимации ходьбы на корточках_

Это дает нам, по крайней мере, два различимых персонажа для дальнейшего игрового тестирования.


# Концепт-арт СФ
## Mayama

Привет, я Mayma, если вы давно играете в Empires, то, наверняка, помните мое ник. Я недавно присоединился к команде, и моя главная цель - получить последовательный дизайн и визуальный стиль для обоих фракций Empires. Прямо сейчас я занимаюсь концепт-артом для пехотного оружия СФ, потому что это отличный шанс прочувствовать стиль. Ведь оружие в шутере от первого лица является продолжением игрока в игровом мире и требует большего внимания, чем всё остальное. Имейте в виду, что все показанные здесь картинки являются незавершенными работами и, скорее всего, не будут напоминать ничего из того, что вы увидите в готовой игре.

{{< image-resize NF_art1.jpg >}}

_3D концепт для штурмовой винтовки СФ_

{{< image-resize NF_art3.jpg >}}

_3D концепт для штурмовой винтовки СФ_

{{< image-resize NF_art4.jpg >}}

_3D концепт для штурмовой винтовки СФ_

{{< image-resize NF_art2.jpg >}}

_3D концепт для ручной Мортиры СФ_

{{< image-resize NF_art5.jpg >}}

_3D концепт для ручной Мортиры СФ_

{{< image-resize NF_art6.jpg >}}

_3D концепт для БТРа СФ_

{{< image-resize NF_art7.jpg >}}

_Рендер осколочной гранаты СФ_
