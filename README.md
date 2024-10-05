<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Градієнтний фон з анімацією</title>
    <style>
        body {
            height: 100vh;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(to bottom, #001f3f, #b03060);
            color: white;
            font-size: 2em;
            text-align: center;
            transition: background 0.5s;
            overflow: hidden;
        }

        .emoji {
            position: absolute;
            font-size: 48px;
        }

        #cat {
            top: 10%;
            left: 10%;
            animation: moveCat 3s infinite alternate ease-in-out;
        }

        #hearts {
            bottom: 10%;
            right: 10%;
            animation: moveHearts 3s infinite alternate ease-in-out;
        }

        #heart {
            display: none;
            font-size: 48px;
            position: absolute;
            bottom: 20%;
            left: 50%;
            transform: translateX(-50%);
        }

        @keyframes moveCat {
            from {
                transform: translate(0, 0);
            }
            to {
                transform: translate(50px, 50px);
            }
        }

        @keyframes moveHearts {
            from {
                transform: translate(0, 0);
            }
            to {
                transform: translate(-50px, -50px);
            }
        }
    </style>
</head>
<body>
    <div id="text">Просто нажимай на екран 🤍</div>

    <div id="cat" class="emoji">🐈‍⬛🤍🐈‍⬛🤍🐈‍⬛🤍</div>
    <div id="hearts" class="emoji">🤍🐈‍⬛🤍🐈‍⬛🤍🐈‍⬛</div>
    <div id="heart" class="emoji">❤️</div>

    <script>
        const texts = [
           messages = [
    "Ти колись пробувала малювати кавовими зернами? Ні? Ну, завжди можна почати з чашки міцної кави ☕️",
    "Ти знаєш, що твої малюнки краще за будь-який K-pop альбом? Ну добре, майже краще, але ти точно в топі! 🎨",
    "Я дивлюсь на твої малюнки і думаю: коли ти встигла стати такою геніальною? Щось я проспала цей момент 😜",
    "Якби в мене були твої таланти, я б малювала себе щоранку, щоб пам'ятати, яка я крута 👑",
    "Ти впевнена, що не в Кореї народилася? Твоє захоплення відчувається на рівні ДНК 🇰🇷",
    "Якщо BTS будуть шукати дизайнера для нового альбому, ти будеш їх номер один 🎤",
    "Може, ти могла б намалювати мій ранок? Бо він був настільки хаотичним, що я сама не пам'ятаю, що відбувалося 🤯",
    "Коли я бачу твої роботи, одразу згадую, що у нас в сім'ї є геніальність… і вона точно не моя 😅🎨",
    "Пам’ятаєш ту К-драму, де всі плакали? Я теж ледь не розплакалась, коли не знайшла твій олівець. Ти ж знаєш, він — головна зброя художника! ✏️",
    "Ти що, постійно тренуєшся в малюванні, коли я не дивлюсь? Інакше я не розумію, звідки така майстерність! 🖌️",
    "Якби малюнки могли танцювати, твої точно стали б айдолами на сцені 🕺🎨",
    "Ти коли-небудь пробувала малювати з закритими очима? Я теж ні, але думаю, ти б і це змогла 😎",
    "У тебе виходять такі милі малюнки, що я починаю сумніватися, чи існує в цьому світі щось миліше за тебе! 🐰",
    "Якби у мене була твоя уява, я б малювала так багато, що в мене закінчився б папір. Але не хвилюйся, у мене є запас! 📜",
    "Я завжди знала, що мистецтво в тебе в крові. А ось звідки в тебе така любов до K-драм — це загадка! 🎬",
    "Може, нам варто разом намалювати щось епічне? Ти художник, а я… скажімо, людина з кавою! ☕️",
    "Якщо я колись забуду свій пароль, сподіваюсь, що ти не забудеш свої мистецькі ідеї! 🔑",
    "У світі є дві речі, яких я боюся: не знайти твій малюнок і пропустити нову серію K-драми! 😱",
    "Знаєш, мені здається, що твоя творчість зараз на рівні шедеврів, але в K-pop форматі! 🎶",
    "Коли ти малюєш, в кімнаті ніби відбувається магія. Чесно, як в серіалі з Кореї! ✨",
    "Якщо б я мала такий талант, як у тебе, я б вже відкрила студію і продавала малюнки на всі K-pop концерти! 🎨",
    "Може, ти вже думала над тим, щоб твої малюнки мали свою виставку в Сеулі? Бо я знаю, що там їх чекають! 🖼️",
    "Ти така майстерна, що здається, у тебе є особистий наставник-художник з Кореї. Чи це просто YouTube? 🤔",
    "Як ти встигаєш і малювати, і дивитися K-драми? У тебе якийсь секретний годинник з Кореї? ⏰",
    "Коли я бачу твої нові малюнки, мені хочеться зробити лотерею і розіграти їх серед шанувальників K-pop. Тільки підпишу їх своїм ім'ям 😆🎟️",
    "Ти вже бачила нову серію улюбленої драми? Бо я майже впевнена, що малювала на її основі свій останній шедевр 🎥",
    "Як ти думаєш, якби ти могла малювати під час сну, ти б створювала ще більше класних робіт? 🛏️🎨",
    "Ти коли-небудь думала стати дизайнером корейської косметики? Бо твої малюнки точно можуть стати логотипами 🌸",
    "Може, ми колись разом подивимося всі серії наших улюблених серіалів і створимо малюнок на основі кожної з них? Це був би мистецький марафон! 🏃‍♀️",
    "Я іноді думаю, що ти — це реінкарнація корейського художника. Як інакше пояснити таку любов до Кореї і мистецтва? 🌟",
    "Ти вже знайшла рецепт, як поєднати корейську кухню з українським борщем? Якщо так, чекаю на дегустацію 🍲",
    "Здається, якщо б ти була стравою, то була б кимчи. Гаряча, гостра і надзвичайно унікальна 🔥",
    "Ти що, збираєшся готувати щось сьогодні? Я завжди поруч із ложкою, готова оцінити будь-який шедевр 🍽️",
    "Я думаю, що твої кулінарні здібності можуть спокійно перевершити навіть найкращих шефів на корейському ТВ-шоу 👩‍🍳",
    "Ти впевнена, що не хотіла стати шеф-кухарем? Бо твій суп виглядає так, наче його готував якийсь знаменитий кухар з Сеула 🍜",
    "Якщо сьогодні готуєш щось солодке, не забудь мене покликати. Я ж найкращий дегустатор десертів, ти знаєш 🍰",
    "Твоя страва така смачна, що навіть BTS приїхали б на вечерю, якби знали про неї 🍱",
    "Я от думаю, може, ти б могла відкрити ресторан? Я буду допомагати як головний їдок! І це не обговорюється 😋🍴",
    "Ти коли готуєш, то на кухні починається справжня магія. Майже як у моїй улюбленій К-драмі, але з кращим кінцем 🍳✨",
    "Якщо б ти варила каву так само, як готуєш суп, то всі кав'ярні закрилися б через твою конкуренцію ☕️",
    "Ти коли вирішуєш готувати, навіть хліб намагається бути смачнішим, щоб відповідати твоїм вимогам 🍞",
    "Твоя страва така гарна, що я б її навіть не їла, а поставила в рамочку як витвір мистецтва 🖼️🍲",
    "Якщо ти сьогодні готуєш щось із соусом, то я беру свій великий ніж і виделку. Я ж професіонал у їжі! 🍴",
    "Твої кулінарні здібності такі, що я думаю, скоро побачу тебе в шоу “МайстерШеф”! І я буду кричати за тебе з дивана 📺",
    "Ти коли робиш щось на кухні, здається, що навіть холодильник радіє, що він частина твого мистецтва 🍇",
    "Ти приготувала стільки смакоти, що мені здається, я щойно отримала плюс два кілограми від одних лише запахів 🧁",
    "Я не знаю, що смачніше — твої страви чи твій гумор, але вони точно на одному рівні. І я обожнюю обидва 😆🍛",
    "Ти точно не хочеш відкрити кулінарний блог? Я впевнена, що у тебе буде більше підписників, ніж у будь-якого К-pop айдола 🍜",
    "Якщо б ми з тобою брали участь у корейському кулінарному шоу, я була б твоїм асистентом. Але, чесно кажучи, я б просто їла 🍱",
    "Ти така майстерна на кухні, що навіть сковорідки в твоїх руках стають магічними 🥘",
    "Твої страви так смачно виглядають, що я готова з'їсти навіть те, що не люблю, аби лише це було зроблено тобою 🍽️"
     "Знаєш, мені все одно, що тобі вже 18. Для мене ти завжди залишишся тією малечею в зимовому комбінезоні, яку я обожнюю 💖
     "Тобі може бути хоч 30, але я все одно бачитиму тебе в тому малесенькому комбезі, як у дитинстві. Люблю тебе, моя мала! ❄️ "
     "Люблю тебе 💖💖💖💖💖💖💖💖"
    
        ];

        let index = 0;
        const textElement = document.getElementById('text');
        const heartElement = document.getElementById('heart');

        document.addEventListener('click', () => {
            if (index < texts.length) {
                textElement.innerText = texts[index];
                index++;
            } else {
                textElement.innerText = ""; // Сховати текст
                heartElement.style.display = 'block'; // Показати серце
                index = 0; // Скидаємо index для повторного перегляду
            }
        });
    </script>
</body>
</html>
