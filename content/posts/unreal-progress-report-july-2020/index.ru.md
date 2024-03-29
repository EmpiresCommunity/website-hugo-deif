---
title: Ежемесячный отчёт о разработке Empires UE4  - Июль 2020
author: RoyAwesome
date: "2020-08-04"
tags: [ "UNREALENGINE" ]
post_type: UE4
---

# Обновление проекта
## Roy Awesome

Всем Привет! Еще один месяц в позади для UEpires, и мы действительно кое в чём преуспели. Мы достигли важной задачи в этом месяце, мы провели **несколько** игровых тестов! Да, теперь мы в состоянии играть в этот шедевр и получить общий цикл геймплея. Мы даже нашли сбой во время тестирования!

{{< image-resize img1.jpg >}}

<video controls>
  <source src="https://cdn.discordapp.com/attachments/698655659193008208/734615702643671070/2020-07-19_20-37-32.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video> 



Это большой успех, потому благодаря ему мы чувствуем, что проект становится реальным. Это также самый дальний путь, который когда-либо мы проделывали над ремейками Empires, так что мы очень рады этому.

Тем не менее, у нас все еще есть тонна работы. Приведение игры в состояние, в котором мы могли бы протестировать игру, заняло немного больше времени, чем ожидалось, и это включало в себя большую часть работы, которую мы сделали в этом месяце. Мы добились некоторого прогресса в направлении теста, но не закончили его в этом месяце, как надеялись.

Тем не менее, у нас есть довольно много потрясающего прогресса для показа его в Июле.

# Руководство по стилю проекта
## f1r3w4rr10r

Мы начали следовать этому [руководству по стилю](https://github.com/Allar/ue4-style-guide) о том, как выложить наш контент в каталог Unreal project. Как и большинство руководств по стилю, он очень самоуверен, но помогает поддерживать последовательность вещей. Это позволит вам легче понимать вещи и держать их организованными в целом.

В основном я был занят этим в течение последнего месяца, когда я вообще мог работать над Empires. Две другие мои статьи в этом обновлении относятся к вещам, которые уже были сделаны, просто у меня не было времени писать об этом до сих пор.


# Программирование геймплея
## Roy Awesome

Для геймплея в этом месяце я сделал много низкоуровневых вещей, которые на самом деле не достойны скриншотов. В первую очередь я был сосредоточен на том, чтобы заставить браузер Steam Server работать с выделенными серверами. Это был действительно долгий и трудный процесс, в котором не было бы никаких ошибок, но сервер просто не появлялся в steam. Я обновил версию движка steamworks до 1.49, очистил код сеанса, чтобы разместить правильные теги, и настроил выделенный сервер, чтобы использовать правильный steam appid. Однако работа была не напрасной, так как теперь мы можем запустить сборку на нашем сервере Jenkins, она автоматически публикуется в steam, а затем мы просто обновляем наши игры и играем. Сейчас этот процесс проходит быстро и легко, и в будущем его не нужно будет менять. Важно иметь хорошую инфраструктуру, но это не приводит к интересным обновлениям.

Кроме того, у меня заработало табло. Я немного экспериментирую с дизайном и хотел бы услышать все ваши отзывы. Я удалил “Убийства” и “Смерти” и вместо этого использую “Счет” и "Использованные билеты". Убийства - интересная метрика для Empires, но она не совсем передает все то, что хорошо делать в Empires. Исцеление, строительство, нанесение урона... все это действия, которые пополняют счет, и самый крутой игрок часто является лучшим, даже если он не убивает врагов пачками. Замена смерти на используемые билеты - это просто очевидное изменение, как будто вы возрождены, ваша смерть на самом деле не имеет значения.  

{{< image-resize scoreboard.jpg >}}

Я также добавил анимацию к игровым способностям, то есть такие события, как стрельба, перезарядка и тому подобное, есть уже прямо сейчас! Я использую некоторые анимации заполнителей, так что они выглядят довольно плохо. Теперь я настроил все это так, чтобы художники и аниматоры могли добавлять новые анимации без какой-либо поддержки кода, что, несомненно, принесет пользу долгосрочному развитию этого порта.

# Перерисовка сетки Игрока
## f1r3w4rr10r

Привет, возможно, вы помните, что несколько обновлений назад PYA попробовала портировать старые сетки плееров с помощью ретаргетинга анимации. (По сути, отображение костей от одного скелета к другому, чтобы иметь возможность воспроизводить одни и те же анимации на обоих из них.) Это дало нам некоторые смешанные результаты, особенно вокруг скручивания костей, например, на запястьях.

Теперь я попробовал другой подход, но просто использовал скелет манекена UE4 и перекинул сетки игрока на этот скелет. Этот способ несколько труднее, но у него есть огромное преимущество, дающее нам немного больше контроля над движением сетки вместе со скелетом.

Основная причина использования манекена UE4 заключается в том, что Unreal marketplace битком набит готовыми анимационными пакетами для этого скелета. Это означает, что мы получаем базовую анимацию общего назначения бесплатно. Если нам понадобится что-то более индивидуальное, мы все равно сможем сами создать эти анимации.

У меня уже было несколько попыток заставить Blender работать с остальной частью экосистемы 3D-игр, но здесь мне снова пришлось немного повозиться, чтобы найти что-то, что работает. Если вы хотите узнать больше об этом, прочтите мою статью "Совместимость 3D программного обеспечения" ниже в этом отчёте.

Но в конце концов мне удалось запихнуть в движок вполне приличную на вид текстуру солдата Бреноди. Я все еще должен сделать солдата Северных фракций. Для представления от первого лица мы хотели бы использовать несколько иной подход, и для этого мы могли бы просто создать совершенно новые сетки.

<div class="video-container">
  <iframe src="https://www.youtube.com/embed/z-6JpPQRjcs" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>


# Совместимость 3D программного обеспечения

Так как я вообще смог запихнуть в Blender настоящий скелет? Короткий ответ: Я не смог. \
Вы можете экспортировать ассеты из редактора Unreal. Большинство видов 3D-данных будут экспортированы в формате FBX. У Blender действительно есть экспортер/импортер FBX, но поскольку библиотека FBX является проприетарным программным обеспечением Autodesk, ребята, которые делают Blender, должны были перепроектировать формат файла, чтобы заставить этот импортер/экспортер работать. Добавьте к этому, что формат файла является двоичным и что Autodesk любит изменять произвольные вещи в нем от версии к версии, просто чтобы помешать таким попыткам обратного проектирования.

В любом случае, Blender имеет работающий экспортер, который поддерживает большинство, но не все вещи в формате файла. Далее, в зависимости от того, с чем вы хотите взаимодействовать (в нашем случае с Unreal Engine/Editor), вы должны правильно настроить параметры импорта/экспорта. Далее, Если вы импортируете скелет из Unreal в Blender, кости имеют неправильную ориентацию.


![][mannequin]


Это не ошибка импортера или неправильные настройки, это на самом деле то, как скелет был написан в Maya и импортирован в Unreal. Проблема в том, что Blender на самом деле заботится о базовой ориентации костей, а Maya и Unreal - нет. наличие правильной ориентации костей в Blender делает многие вещи намного проще. А именно: установка ограничений и, следовательно, ригинг, автоматическое обшивание сеток на каркас с помощью оболочек и т. д.

Я также не могу просто вращать эти кости так, как мне хотелось бы, потому что они сломаются, как только я реимпортирую их в Unreal.

Посмотрев вокруг, я нашел этот удобный плагин для Blender'а: [Mr. Mannequins Tools](https://gumroad.com/l/MrMannequinsTools)

Это избавляет меня от тонны работы. Не только потому, что он дает мне правильный скелет, но и потому, что он идёт виесте с довольно хорошей системой ригинга!. (Я еще не совсем уверен, сколько всего того, что он делает, импортируется из готовых файлов и сколько генерируется кодом.)

{{< image-resize rigging.png >}}

Теперь это позволяет мне тестировать мои сетки в Blender, а также создавать новые анимации и экспортировать их в движок.

# Ремастер карты Glycencity
## thomasfn

Я работал над портированием / ремастерингом glycencity из Sourcepires(Empires на Source). Мне нравится идея и эстетика заснеженного города. Есть также интересные потенциальные последствия геймплея для проверки их позже, например, плотный снегопад, который ограничивает видимость, фонари/фары, освещающие снегопад и освещая позиции и т. д. А пока я останусь верен оригиналу, в духе проекта Unrealpires.

Первый шаг - импортировать карту из Sourcepires в движок, чтобы у меня был что-то для сравнения, что можно легко включать и выключать в редакторе. Я сделал это с помощью моего плагина [HL2 asset importer](https://github.com/thomasfn/HL2UE4AssetImporter), над которым я начал работать задолго до того, как проект Unrealpires зародился. Мне нужно было сделать несколько модификаций, чтобы импортированные ассеты не зависели от плагина, что было бы раздражающим для других разработчиков, у которых он не установлен.

{{< image-resize glycen1.jpg >}}


Все материалы и модели вышли в нужном масштабе. Есть несколько недостающих кистей, нормали на смещениях завинчены, и ни одна из надписей не прошла (некоторые здания используют надписи для окон), но это достаточно для справки. После завершения ремастера импортированная карта и ресурсы будут удалены, чтобы гарантировать, что они случайно не попадут в сборку.

Большая часть рельефа карты состоит из ландшафта, причем здания сделаны из кистей. Рельеф в UE4 лучше всего достигается с помощью ландшафтов, поэтому я решил преобразовать смещения в один большой ландшафт. Здесь вы можете увидеть импортированную карту только с геометрией смещения.


{{< image-resize glycen2.png >}}


Есть много отверстий, где размещаются здания, но покрытие, как правило, довольно хорошее, и случаи наслоения редки (смещения поверх других смещений). Я решил написать скрипт, который будет проходить через каждую точку ландшафта и пробовать делать смещения, чтобы вычислить правильную высоту.

{{< image-resize glycen3.jpg >}}


Первая версия скрипта вышла довольно хорошо. Вы можете видеть, что это отлично работает для областей, покрытых ландшафтом, но есть некоторые огромные ямы, генерируемые там, где есть отверстия, так как не удалось ничего проследить и высота образца 0 вернулась. Поэтому я изменил скрипт, чтобы выбрать ближайшую допустимую высоту для точек, где он ничего не смог проследить.

{{< image-resize glycen4.png >}}

Гораздо лучше, хотя вы все еще можете видеть резкие капли на внешней стороне карты, поэтому я снова включил геометрию кисти для справки и приступил к очистке краев. Это было в значительной степени достигнуто с помощью инструмента ramp для создания пандусов от вершин кромок до плоских областей и сглаживания всего этого с помощью инструмента smooth. Я также обошел по периметру игровую территорию и добавил еще несколько более высоких холмов, чтобы придать фону большую глубину. Я не потратил на это слишком много времени, так как пока не знаю, сколько еще зданий я хочу добавить к горизонту, и любые мелкие детали, вероятно, будут зависеть от используемого материала.

{{< image-resize glycen5.png >}}


Я пока не слишком беспокоюсь о том, что игроки попадут в затекстурье - это можно решить позже. Уточнение ландшафта, скорее всего, будет постоянной задачей, поскольку я добавляю здания и больше деталей на карту.

Затем я хотел добавить материал к ландшафту, что является самым быстрым способом оживления уровня. Текстуры, используемые Sourcepires, имеют низкое разрешение и не являются PBR, поэтому я зашёл на [freepbr](https://freepbr.com/) взял пару снежных и ледяных текстуры. Есть вероятность, что поменяю их позже, или, может быть, мы сможем сделать некоторые получше для домов, но сейчас они проявляют себя хорошо. Немного импорта и материалов позже, и у нас есть снежный пейзаж.

{{< image-resize glycen6.png >}}

Сразу же вы заметите тайлы. Тайлы были проблемой в играх с тех пор, как текстуры впервые были использованы в 3D-графике, и вы не найдёте игру в настоящее время, которая не имеет текстуры тайлов где-то или в другом месте (хотя к их чести текстуры Sourcepires на самом деле довольно хороши для тайлов, по крайней мере те, которые видны на этой карте). С современным оборудованием у нас больше вычислительной мощности, поэтому я решил попробовать наложить текстуру несколько раз в несколько разных масштабах и поворотах, используя более крупную текстуру шума, чтобы смешаться между ними.

{{< image-resize glycen7.jpg >}}

Как вы можете видеть, это выглядит намного лучше на расстоянии. Вы все еще можете видеть некоторые повторяющиеся паттерны здесь и там, но они гораздо более разбиты и не должны быть слишком заметны, как только у нас будет больше наземных деталей. Эффект исчезает до обычной текстуры тайла, когда вы находитесь вблизи, чтобы сохранить четкость более мелких деталей.

Следующий шаг - блокировать здания и другие объекты, важные для игрового процесса, такие как стены и препятствия для укрытия. Для этого я создал гигантские нетекстурированные кубы вокруг всей импортированной геометрии. Цель блокировки карты - как можно скорее перейти в воспроизводимое состояние, даже если это самая фиговая вещь, которую вы когда-либо видели, так что лучше заблокировать масштаб карты, чем тратить слишком много времени на детализацию.

{{< image-resize glycen8.jpg >}}

Здесь вы можете увидеть, что первый блокирующий проход завершен. Там все еще есть по крайней мере несколько зданий, которые я забыл добавить, и нет никаких сомнений в том, что есть проблемы с масштабированием и невозможностью пролезть через двери или вещи, которые кажутся слишком большими/маленькими, но, по крайней мере, теперь у нас есть не импортированная точка отсчета для работы. Следующие шаги для меня будут заключаться в том, чтобы перейти к воспроизводимой демо-версии, которая будет включать в себя настройку всех точек возрождения, флагов и т. д. и добавление блокирующих величин, чтобы предотвратить побег игрока в страну затекстурья.



# Звук и музыка
## KGBEATS

Привет всем! Немного более спокойный месяц на музыкальном фронте... Постоянные изменения в моей рабочей ситуации с пандемией держали меня довольно занятым.

Мне удалось создать одну полную мелодию, которую я представляю себе как начала раунда, где есть эта 1-2-минутная атмосфера, прежде чем вы вступите в контакт с вражеской командой. Следовательно, именно поэтому трек относительно короткий, просто нужно чем-то заполнить это время. Послушайте!

<audio
        controls
        src="./OfftoBattle.mp3">
            Your browser does not support the
            <code>audio</code> element.
</audio>


Как я уже обсуждал с RoyAwesome, одна из вещей, которые, как мне кажется, было бы интересно попробывать для этого нового ремейка, состояла бы в том, чтобы включить несколько различных музыкальных стилей/жанров/вкусов, а не только строго оркестровые. Таким образом, в этом месяце я начал работать над другим треком, который, хотя и основан на оркестровом стиле, также немного исследует хард-рок сторону. Этот трек я представляю себе играющим, когда вступаю в контакт с врагом, возможно, в первый раз. Я вижу, что создаю другие треки, которые более ориентированы на рок/экшн для этого саундтрека, так что это хорошая отправная точка для естественного перехода/включения обоих стилей и изучения моего голоса в этом жанре.

Опять же, этот трек НЕ ЗАКОНЧЕН, далеко от этого на самом деле. Это также всего лишь небольшой образец первой части трека. Хотя я редко демонстрирую незавершенные проекты, я подумал, что было бы неплохо поделиться этим, поскольку это то, что, я думаю, может привнести много прохладного аромата в новый саундтрек. Я надеюсь, что полный трек будет сделан к следующему месяцу.

<audio
        controls
        src="./BraveFirefightDemo.mp3">
            Your browser does not support the
            <code>audio</code> element.
</audio>



# Портирование сайта Hugo
## Tama "Bob2" McGlinn

В качестве прощального подарка недавно созданной команде Unreal я портировал веб-сайт empiresmod с установки hakyll, которую мы использовали для Hugo. Главное преимущество заключается в том, что hugo имеет гораздо большую поддержку - его действительно легко настроить на новой машине, поэтому, вероятно, не будет никаких проблем с запуском сервера непрерывной интеграции, так что Pull-запросы могут приходить с предварительным просмотром, а одобрение PR на github будет всем, что необходимо команде для внесения изменений на веб-сайт. У старой установки был CI, но он сломался, а hakyll такая сложная штука - мы не смогли ее исправить. Так что уже почти год моя машина была единственной, кто мог создать сайт и продвигать изменения. \
\
Новый сайт должен выглядеть идентично текущему, однако страница команды, очевидно, будет нуждаться в большом обновлении. Hugo также принесет некоторые новые функции, такие как возможность фильтровать по тегам и авторам, но это зависит от новой команды, а именно будут ли они использовать это. 

[mannequin]: ./mannequin.gif