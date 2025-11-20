📘 Agenda 2026

Agenda 2026 is a simple and smart weekly planner written in Python. It allows you to add, edit, and review activities for each day of the week using an interactive, multilingual interface. At the end, you can see your entire weekly schedule in one organized view.

✨ Features

Add an activity for any day of the week

Update existing activities

Review all your activities for the whole week

Multilingual support (30+ languages)

Clear, user-friendly console flow

🚀 How to Run

Install Python 3

Download the program file

Run it in your terminal:



import unicodedata


LANGS = {
    "en": {
        "name": ["English", "Eng", "EN", "english", "eng","en","ENG","Engl","engl","Anglais","anglais","Ang","ANG","ang","Eng.","eng.","En","En.","ENg","eNg","enG","en"],
        "days": ["Monday","Tuesday","Wednesday","Thursday","Friday","Saturday","Sunday"],
        "header_week": "\nYour weekly schedule ",
        "line_week": "🔴{day} → {act} at {place}",
        "ask_day": "\nEnter a day to view/update (or 'exit' to finish): ",
        "show_day": "On {day} you will do {act} at {place}.",
        "ask_change": "Do you want to change {day}'s activity? (y/n): ",
        "ask_new_act": "Enter the new activity for {day}: ",
        "ask_new_place": "Enter the new place for {day}: ",
        "updated": "✅ {day} updated: now {act} at {place}.\n",
        "no_change": "No changes for {day}.",
        "invalid_day": "Invalid day. Please enter a valid weekday.",
        "confirm_exit": "Are you sure you want to exit? (y/n): ",
        "yes": {"y", "yes"},
        "chose_day": "Which day would you like to update? ",
        "Activity_question": "What activity will you do on {day}?",
        "location_question": "Where will you do the activity on {day}?",
        "no_plan": "You don't have planned activities for this week.",
        "prompt_add": "Do you want to add them now? (y/n): ",
        "nothing_planned": "Nothing planned yet.",
        "another_activity": "Do you want to register another activity? (y/n): ",
        "next_time": "OK, maybe next time ",
        "Ambiguous_day": "The day you entered is ambiguous. Please be more specific.",
        "welcome": "Welcome, ",
        "Welcome_2": "! Let's plan your week! 🗓️✨",
        "introduce_name": "Please enter your name: ",
        "occupied_day": "You already have an activity planned for {day} at {place}. Do you want to change it? (y/n): ",
    },
    "es": {
        "name": ["Español", "Castellano","ES", "español", "castellano", "es","spanish","sp","esp","Esp","ESP","Es","es.","Espanol.","ESPAÑOL","espanol","Espanol","Spain","spain","SPAIN","Castellano.","castellano.","CASTELLANO","esp.","ESP."],
        "days": ["Lunes","Martes","Miércoles","Jueves","Viernes","Sábado","Domingo"],
        "header_week": "\nTu horario semanal ",
        "line_week": "🔴{day} → {act} en {place}",
        "ask_day": "\nIngresa un día para ver/actualizar (o 'salir' para terminar): ",
        "show_day": "El {day} harás {act} en {place}.",
        "ask_change": "¿Quieres cambiar la actividad del {day}? (s/n): ",
        "ask_new_act": "Introduce la nueva actividad para el {day}: ",
        "ask_new_place": "Introduce el nuevo lugar para el {day}: ",
        "updated": "✅ {day} actualizado: ahora {act} en {place}.\n",
        "no_change": "No se realizaron cambios para {day}.",
        "invalid_day": "Día no válido. Ingresa un día de la semana.",
        "confirm_exit": "¿Seguro que quieres salir? (s/n): ",
        "yes": {"s", "sí", "si"},
        "chose_day": "¿Cuál día te gustaría actualizar? ",
        "Activity_question": "¿Qué actividad harás el {day}?",
        "location_question": "¿Dónde harás la actividad el {day}?",
        "no_plan": "No tienes actividades planificadas para esta semana.",
        "prompt_add": "¿Quieres agregarlas ahora? (s/n): ",
        "nothing_planned": "Nada planificado aún.",
        "another_activity": "¿Quieres registrar otra actividad? (s/n): ",
        "next_time": "OK, tal vez la próxima vez ",
        "Ambiguous_day": "El día que ingresaste es ambiguo. Por favor, sé más específico.",
        "welcome": "¡Bienvenido, ",
        "Welcome_2": "! ¡Vamos a planear tu semana! 🗓️✨",
        "introduce_name": "Por favor, ingresa tu nombre: ",
        "occupied_day": "Ya tienes una actividad planificada para {day} en {place}. ¿Quieres cambiarla? (s/n): ",
    },
    "hr": {
        "name": ["Hrvatski", "Naše", "HR", "hrvatski", "hr", "Hrv", "HRV", "Hrv.", "hrv.", "Croatian", "croatian", "Cro", "CRO", "cro","Bosanski","bosanski","BOS","bos","bih","BIH","BiH","crnogorski","Crnogorski","CRN","crn","BA","MN","ba","mn","Mne","ME","me"],
        "days": ["Ponedjeljak","Utorak","Srijeda","Četvrtak","Petak","Subota","Nedjelja"],
        "header_week": "\nTvoj tjedni raspored ",
        "line_week": "🔴{day} → {act} u {place}",
        "ask_day": "\nUnesi dan za pregled/izmjenu (ili 'kraj' za završetak): ",
        "show_day": "{day} radiš {act} u {place}.",
        "ask_change": "Želiš li promijeniti aktivnost za {day}? (d/n): ",
        "ask_new_act": "Unesi novu aktivnost za {day}: ",
        "ask_new_place": "Unesi novo mjesto za {day}: ",
        "updated": "✅ {day} ažuriran: sada {act} u {place}.\n",
        "no_change": "Nema promjena za {day}.",
        "invalid_day": "Neispravan dan. Unesi valjani dan u tjednu.",
        "confirm_exit": "Jesi li siguran/na da želiš izaći? (d/n): ",
        "yes": {"d", "da"},
        "chose_day": "Koji dan želiš ažurirati? ",
        "Activity_question": "Što ćeš raditi u {day}?",
        "location_question": "Gdje ćeš raditi aktivnost u {day}?",
        "no_plan": "Nemaš planiranih aktivnosti za ovaj tjedan.",
        "prompt_add": "Želiš li ih sada dodati? (d/n): ",
        "nothing_planned": "Još ništa nije planirano.",
        "another_activity": "Želiš li unijeti još jednu aktivnost? (d/n): ",
        "next_time": "OK, možda drugi put ",
        "Ambiguous_day": "Dan koji si unio/la je nejasan. Molimo budi precizniji/ja.",
        "welcome": "Dobrodošao/la, ",
        "Welcome_2": "! Planirajmo tvoj tjedan! 🗓️✨",
        "introduce_name": "Molimo unesi svoje ime: ",
        "occupied_day": "Već imaš planiranu aktivnost za {day} u {place}. Želiš li je promijeniti? (d/n): ",
    },
    "lv": {
        "name": ["Latviešu", "Latviski","LV", "latviešu", "latviski", "lv","Latvian","latvian","Lat","LAT","lat","Lv","LVA","lva","lva.","LVA."],
        "days": ["Pirmdiena","Otrdiena","Trešdiena","Ceturtdiena","Piektdiena","Sestdiena","Svētdiena"],
        "header_week": "\nTava nedēļas programma ",
        "line_week": "🔴{day} → {act} vietā {place}",
        "ask_day": "\nIevadi dienu, lai skatītu/rediģētu (vai 'iziet' lai beigtu): ",
        "show_day": "{day} tu darīsi {act} vietā {place}.",
        "ask_change": "Vai vēlies mainīt {day} aktivitāti? (j/n): ",
        "ask_new_act": "Ievadi jauno aktivitāti {day}: ",
        "ask_new_place": "Ievadi jauno vietu {day}: ",
        "updated": "✅ {day} atjaunināts: tagad {act} vietā {place}.\n",
        "no_change": "Izmaiņu nav {day}.",
        "invalid_day": "Nederīga diena. Lūdzu, ievadi derīgu nedēļas dienu.",
        "confirm_exit": "Vai tiešām vēlies iziet? (j/n): ",
        "yes": {"j", "ja"},
        "chose_day": "Kuru dienu vēlies atjaunināt? ",
        "Activity_question": "Kāda aktivitāte tev būs {day}?",
        "location_question": "Kur tu veiksi aktivitāti {day}?",
        "no_plan": "Tev nav plānotu aktivitāšu šai nedēļai.",
        "prompt_add": "Vai vēlies tās pievienot tagad? (j/n): ",
        "nothing_planned": "Vēl nekas nav plānots.",
        "another_activity": "Vai vēlies reģistrēt vēl vienu aktivitāti? (j/n): ",
        "next_time": "Labi, varbūt nākamreiz ",
        "Ambiguous_day": "Ievadītā diena ir neskaidra. Lūdzu, esi precīzāks/a.",
        "welcome": "Laipni lūdzam, ",
        "Welcome_2": "! Plānosim tavu nedēļu! 🗓️✨",
        "introduce_name": "Lūdzu, ievadi savu vārdu: ",
        "occupied_day": "Tev jau ir plānota aktivitāte {day} vietā {place}. Vai vēlies to mainīt? (j/n): ",
    },
    "nl": {  # Dutch
        "name": ["Nederlands", "Dutch", "NL", "nl", "Hollands", "Vlaams","Nl","nL","NL","dutch","Dutch","DUTCH","Dut","dut","DUT","Nederlands.","nederlands.","NEDERLANDS","Netherlands","netherlands","NETHERLANDS","Holland","holland","HOLLAND","nl."],
        "days": ["Maandag","Dinsdag","Woensdag","Donderdag","Vrijdag","Zaterdag","Zondag"],
        "header_week": "\nJouw weekschema ",
        "line_week": "🔴{day} → {act} in {place}",
        "ask_day": "\nVoer een dag in om te bekijken/aan te passen (of 'stop' om te beëindigen): ",
        "show_day": "Op {day} ga je {act} in {place} doen.",
        "ask_change": "Wil je de activiteit van {day} wijzigen? (j/n): ",
        "ask_new_act": "Voer de nieuwe activiteit voor {day} in: ",
        "ask_new_place": "Voer de nieuwe locatie voor {day} in: ",
        "updated": "✅ {day} bijgewerkt: nu {act} in {place}.\n",
        "no_change": "Geen wijzigingen voor {day}.",
        "invalid_day": "Ongeldige dag. Voer een geldige weekdag in.",
        "confirm_exit": "Weet je zeker dat je wilt afsluiten? (j/n): ",
        "yes": {"j", "ja"},
        "chose_day": "Welke dag wil je bijwerken? ",
        "Activity_question": "Welke activiteit ga je doen op {day}?",
        "location_question": "Waar ga je de activiteit doen op {day}?",
        "no_plan": "Je hebt geen geplande activiteiten voor deze week.",
        "prompt_add": "Wil je ze nu toevoegen? (j/n): ",
        "nothing_planned": "Nog niets gepland.",
        "another_activity": "Wil je nog een activiteit registreren? (j/n): ",
        "next_time": "Oké, misschien de volgende keer ",
        "Ambiguous_day": "De dag die je hebt ingevoerd is dubbelzinnig. Wees alsjeblieft specifieker.",
        "welcome": "Welkom, ",
        "Welcome_2": "! Laten we je week plannen! 🗓️✨",
        "introduce_name": "Voer alsjeblieft je naam in: ",
        "occupied_day": "Je hebt al een activiteit gepland voor {day} in {place}. Wil je deze wijzigen? (j/n): ",
    },
    "de": {  # German
        "name": ["Deutsch", "German", "DE", "de","german","Deutsch.","deutsch.","De","De.","DEu","dEu","deU","GERMAN","german","German","Germany","germany","GERMANY"],
        "days": ["Montag","Dienstag","Mittwoch","Donnerstag","Freitag","Samstag","Sonntag"],
        "header_week": "\nDein Wochenplan ",
        "line_week": "🔴{day} → {act} in {place}",
        "ask_day": "\nGib einen Tag ein zum Anzeigen/Ändern (oder 'ende' zum Beenden): ",
        "show_day": "Am {day} machst du {act} in {place}.",
        "ask_change": "Möchtest du die Aktivität am {day} ändern? (j/n): ",
        "ask_new_act": "Neue Aktivität für {day} eingeben: ",
        "ask_new_place": "Neuen Ort für {day} eingeben: ",
        "updated": "✅ {day} aktualisiert: jetzt {act} in {place}.\n",
        "no_change": "Keine Änderungen für {day}.",
        "invalid_day": "Ungültiger Tag. Bitte einen gültigen Wochentag eingeben.",
        "confirm_exit": "Möchtest du wirklich beenden? (j/n): ",
        "yes": {"j", "ja"},
        "chose_day": "Welchen Tag möchtest du aktualisieren? ",
        "Activity_question": "Welche Aktivität machst du am {day}?",
        "location_question": "Wo machst du die Aktivität am {day}?",
        "no_plan": "Du hast keine geplanten Aktivitäten für diese Woche.",
        "prompt_add": "Möchtest du sie jetzt hinzufügen? (j/n): ",
        "nothing_planned": "Noch nichts geplant.",
        "another_activity": "Möchtest du eine weitere Aktivität registrieren? (j/n): ",
        "next_time": "Okay, vielleicht nächstes Mal ",
        "Ambiguous_day": "Der eingegebene Tag ist mehrdeutig. Bitte sei spezifischer.",
        "welcome": "Willkommen, ",
        "Welcome_2": "! Lass uns deine Woche planen! 🗓️✨",
        "introduce_name": "Bitte gib deinen Namen ein: ",
        "occupied_day": "Du hast bereits eine Aktivität für {day} in {place} geplant. Möchtest du sie ändern? (j/n): ",
    },
    "fr": {  # French
        "name": ["Français", "French", "FR", "fr","fr."],
        "days": ["Lundi","Mardi","Mercredi","Jeudi","Vendredi","Samedi","Dimanche"],
        "header_week": "\nTon planning hebdomadaire ",
        "line_week": "🔴{day} → {act} à {place}",
        "ask_day": "\nEntre un jour pour voir/modifier (ou 'quitter' pour terminer) : ",
        "show_day": "Le {day}, tu feras {act} à {place}.",
        "ask_change": "Veux-tu changer l'activité du {day} ? (o/n) : ",
        "ask_new_act": "Entre la nouvelle activité pour {day} : ",
        "ask_new_place": "Entre le nouveau lieu pour {day} : ",
        "updated": "✅ {day} mis à jour : maintenant {act} à {place}.\n",
        "no_change": "Aucun changement pour {day}.",
        "invalid_day": "Jour invalide. Entre un jour valide de la semaine.",
        "confirm_exit": "Es-tu sûr(e) de vouloir quitter ? (o/n) : ",
        "yes": {"o", "oui"},
        "chose_day": "Quel jour souhaites-tu mettre à jour ? ",
        "Activity_question": "Quelle activité feras-tu le {day}?",
        "location_question": "Où feras-tu l'activité le {day}?",
        "no_plan": "Tu n'as pas d'activités prévues pour cette semaine.",
        "prompt_add": "Veux-tu les ajouter maintenant ? (o/n) : ",
        "nothing_planned": "Rien de prévu pour l'instant.",
        "another_activity": "Veux-tu enregistrer une autre activité ? (o/n) : ",
        "next_time": "D'accord, peut-être la prochaine fois ",
        "Ambiguous_day": "Le jour que tu as entré est ambigu. Sois plus précis(e), s'il te plaît.",
        "welcome": "Bienvenue, ",
        "Welcome_2": "! Planifions ta semaine ! 🗓️✨"   ,
        "introduce_name": "Veuillez entrer votre nom : ",
        "occupied_day": "Tu as déjà une activité prévue pour {day} à {place}. Veux-tu la changer ? (o/n) : ",
    },
    "pt": {  # Portuguese (PT/BR neutral)
        "name": ["Português", "Portuguese", "PT", "pt", "BR", "br","Br","bR","PORTUGUES","portugues","Portugues","Brasil","brasil","BRASIL","Brazil","brazil","BRAZIL","Pt","pt.","br."],
        "days": ["Segunda-feira","Terça-feira","Quarta-feira","Quinta-feira","Sexta-feira","Sábado","Domingo"],
        "header_week": "\nSeu cronograma semanal ",
        "line_week": "🔴{day} → {act} em {place}",
        "ask_day": "\nDigite um dia para ver/atualizar (ou 'sair' para finalizar): ",
        "show_day": "Na {day} você fará {act} em {place}.",
        "ask_change": "Deseja alterar a atividade de {day}? (s/n): ",
        "ask_new_act": "Digite a nova atividade para {day}: ",
        "ask_new_place": "Digite o novo local para {day}: ",
        "updated": "✅ {day} atualizado: agora {act} em {place}.\n",
        "no_change": "Nenhuma alteração para {day}.",
        "invalid_day": "Dia inválido. Digite um dia válido da semana.",
        "confirm_exit": "Tem certeza que deseja sair? (s/n): ",
        "yes": {"s", "sim"},
        "chose_day": "Qual dia você gostaria de atualizar? ",
        "Activity_question": "Que atividade você fará na {day}?",
        "location_question": "Onde você fará a atividade na {day}?",
        "no_plan": "Você não tem atividades planejadas para esta semana.",
        "prompt_add": "Deseja adicioná-las agora? (s/n): ",
        "nothing_planned": "Nada planejado ainda.",
        "another_activity": "Deseja registrar outra atividade? (s/n): ",
        "next_time": "OK, talvez na próxima vez ",
        "Ambiguous_day": "O dia que você digitou é ambíguo. Por favor, seja mais específico.",
        "welcome": "Bem-vindo, ",
        "Welcome_2": "! Vamos planejar sua semana! 🗓️✨",
        "introduce_name": "Por favor, insira seu nome: ",
        "occupied_day": "Você já tem uma atividade planejada para {day} em {place}. Deseja alterá-la? (s/n): ",
    },
    "tr": {  # Turkish
        "name": ["Türkçe", "Turkish", "TR", "tr","turkce","Turkce","TURKCE","Turk","TURK","turk","Turk.","turk.","Turkey","turkey","TURKEY","Turkiye","turkiye","TURKIYE","Turkiyē","turkiyē"],
        "days": ["Pazartesi","Salı","Çarşamba","Perşembe","Cuma","Cumartesi","Pazar"],
        "header_week": "\nHaftalık programın ",
        "line_week": "🔴{day} → {act} {place}'de",
        "ask_day": "\nGörüntülemek/güncellemek için bir gün gir (veya 'çık' bitirmek için): ",
        "show_day": "{day} günü {place}'de {act} yapacaksın.",
        "ask_change": "{day} etkinliğini değiştirmek ister misin? (e/h): ",
        "ask_new_act": "{day} için yeni etkinliği gir: ",
        "ask_new_place": "{day} için yeni mekanı gir: ",
        "updated": "✅ {day} güncellendi: artık {place}'de {act}.\n",
        "no_change": "{day} için değişiklik yok.",
        "invalid_day": "Geçersiz gün. Lütfen geçerli bir haftalık gün gir.",
        "confirm_exit": "Çıkmak istediğine emin misin? (e/h): ",
        "yes": {"e", "evet"},
        "chose_day":" Hangi günü güncellemek istersin? ",
        "Activity_question": "{day} günü hangi etkinliği yapacaksın {day}?",
        "location_question": "Etkinliği nerede yapacaksın {day}?",
        "no_plan": "Bu hafta için planlanmış etkinliğin yok.",
        "prompt_add": "Şimdi eklemek ister misin? (e/h): ",
        "nothing_planned": "Henüz planlanmış bir şey yok.",
        "another_activity": "Başka bir etkinlik kaydetmek ister misin? (e/h): ",
        "next_time": "Tamam, belki başka zaman ",
        "Ambiguous_day": "Girdiğin gün belirsiz. Lütfen daha spesifik ol.",
        "welcome": "Hoş geldin, ",
        "Welcome_2": "! Haydi haftanı planlayalım! 🗓️✨",
        "introduce_name": "Lütfen adınızı girin: ",
        "occupied_day": "Zaten {day} günü {place}'de planlanmış bir etkinliğin var. Değiştirmek ister misin? (e/h): ",
    },
    "uk": {  # Ukrainian
        "name": ["Українська", "Ukrainian", "UK", "uk", "українська","Ukraine","ukraine","Ukr","UKR","ukr","Ukr.","ukr.","UA","ua","Ua","ykp","ukrainiska","UKRAINISKA","Ukrainiskā","ukrainiskā","UKRAINISKĀ"],
        "days": ["Понеділок","Вівторок","Середа","Четвер","П’ятниця","Субота","Неділя"],
        "header_week": "\nТвій тижневий розклад ",
        "line_week": "🔴{day} → {act} у {place}",
        "ask_day": "\nВведи день для перегляду/зміни (або 'вийти' щоб завершити): ",
        "show_day": "У {day} ти робитимеш {act} у {place}.",
        "ask_change": "Хочеш змінити активність на {day}? (т/н): ",
        "ask_new_act": "Введи нову активність для {day}: ",
        "ask_new_place": "Введи нове місце для {day}: ",
        "updated": "✅ {day} оновлено: тепер {act} у {place}.\n",
        "no_change": "Без змін для {day}.",
        "invalid_day": "Некоректний день. Введи правильний день тижня.",
        "confirm_exit": "Точно хочеш вийти? (т/н): ",
        "yes": {"т", "так"},
        "chose_day": "Який день ти хочеш оновити? ",
        "Activity_question": "Яку активність ти матимеш у {day}?",
        "location_question": "Де ти виконуватимеш активність у {day}?",
        "no_plan": "У тебе немає запланованих активностей на цей тиждень.",
        "prompt_add": "Хочеш додати їх зараз? (т/н): ",
        "nothing_planned": "Ще нічого не заплановано.",
        "another_activity": "Хочеш зареєструвати ще одну активність? (т/н): ",
        "next_time": "Добре, можливо наступного разу ",
        "Ambiguous_day": "Введений день є неоднозначним. Будь ласка, будь конкретнішим.",
        "welcome": "Ласкаво просимо, ",
        "Welcome_2": "! Давай сплануємо твій тиждень! 🗓️✨",
        "introduce_name": "Будь ласка, введи своє ім'я: ",
        "occupied_day": "У тебе вже запланована активність на {day} у {place}. Хочеш її змінити? (т/н): ",
    },
    "az": {  # Azerbaijani
        "name": ["Azərbaycan", "Azerbaijani", "AZ", "az","azerbaijani","Azerbaijani","Azerbaijan","azerbaijan","AZERBAIJAN","Azerbaycan","azerbaycan","AZERBAYCAN","Azerbaycan.","azerbaycan.","Az","az.","AZ."],
        "days": ["Bazar ertəsi","Çərşənbə axşamı","Çərşənbə","Cümə axşamı","Cümə","Şənbə","Bazar"],
        "header_week": "\nHəftəlik cədvəlin ",
        "line_week": "🔴{day} → {act} {place}-də",
        "ask_day": "\nBaxmaq/yeniləmək üçün bir gün daxil et (və ya 'çıx' bitirmək üçün): ",
        "show_day": "{day} günü {place}-də {act} edəcəksən.",
        "ask_change": "{day} fəaliyyətini dəyişmək istəyirsən? (b/x): ",
        "ask_new_act": "{day} üçün yeni fəaliyyəti daxil et: ",
        "ask_new_place": "{day} üçün yeni yeri daxil et: ",
        "updated": "✅ {day} yeniləndi: indi {place}-də {act}.\n",
        "no_change": "{day} üçün dəyişiklik yoxdur.",
        "invalid_day": "Yanlış gün. Zəhmət olmasa, düzgün həftə günü daxil et.",
        "confirm_exit": "Çıxmaq istədiyinə əminsən? (b/x): ",
        "yes": {"b", "bəli"},
        "chose_day":" Hansı günü yeniləmək istərdiniz? ",
        "Activity_question": "günü hansı fəaliyyəti edəcəksən {day}?",
        "location_question": "Fəaliyyəti harada edəcəksən {day}?",
        "no_plan": "Bu həftə üçün planlaşdırılmış fəaliyyətin yoxdur.",
        "prompt_add": "Nəsə əlavə etmək istəyirsən? (b/x): ",
        "nothing_planned": "Hələ heç nə planlaşdırılmayıb.",
        "another_activity": "Başqa bir fəaliyyət qeyd etmək istəyirsən? (b/x): ",
        "next_time": "Yaxşı, bəlkə başqa vaxt ",
        "Ambiguous_day": "Daxil etdiyiniz gün qeyri-müəyyəndir. Zəhmət olmasa, daha dəqiq olun.",
        "welcome": "Xoş gəlmisiniz, ",
        "Welcome_2": "! Gəlin həftənizi planlaşdıraq! 🗓️✨",
        "introduce_name": "Zəhmət olmasa, adınızı daxil edin: ",
        "occupied_day": "{day} günü {place}-də artıq planlaşdırılmış fəaliyyətiniz var. Onu dəyişmək istəyirsiniz? (b/x): ",
    },
    "pl": {
        "name": ["Polski","Polish","PL","pl","polski","pol","POL","Pol","pol.","POL.","Pl","POLSKI"],
        "days": ["Poniedziałek","Wtorek","Środa","Czwartek","Piątek","Sobota","Niedziela"],
        "header_week": "\nTwój tygodniowy plan ",
        "line_week": "🔴{day} → {act} w {place}",
        "ask_day": "\nWpisz dzień, aby zobaczyć/zmienić (lub 'koniec' aby zakończyć): ",
        "show_day": "W {day} będziesz robić {act} w {place}.",
        "ask_change": "Czy chcesz zmienić aktywność w {day}? (t/n): ",
        "ask_new_act": "Wpisz nową aktywność na {day}: ",
        "ask_new_place": "Wpisz nowe miejsce na {day}: ",
        "updated": "✅ {day} zaktualizowano: teraz {act} w {place}.\n",
        "no_change": "Brak zmian dla {day}.",
        "invalid_day": "Niepoprawny dzień. Wprowadź poprawny dzień tygodnia.",
        "confirm_exit": "Na pewno chcesz wyjść? (t/n): ",
        "yes": {"t","tak"},
        "chose_day": "Który dzień chcesz zaktualizować? ",
        "Activity_question": "Jaką aktywność masz w {day}?",
        "location_question": "Gdzie wykonasz aktywność w {day}?",
        "no_plan": "Nie masz zaplanowanych aktywności na ten tydzień.",
        "prompt_add": "Czy chcesz dodać je teraz? (t/n): ",
        "nothing_planned": "Nic jeszcze nie zaplanowano.",
        "another_activity": "Czy chcesz dodać kolejną aktywność? (t/n): ",
        "next_time": "OK, może następnym razem ",
        "Ambiguous_day": "Podany dzień jest niejednoznaczny. Podaj dokładniejszą nazwę.",
        "welcome": "Witaj, ",
        "Welcome_2": "! Zaplanujmy twój tydzień! 🗓️✨",
        "introduce_name": "Podaj swoje imię: ",
        "occupied_day": "Masz już aktywność w {day} w {place}. Chcesz ją zmienić? (t/n): "
    },
    "it": {
        "name": ["Italiano","Italian","IT","it","italiano","ITA","ita","Ital","ital.","ITALIANO","It"],
        "days": ["Lunedì","Martedì","Mercoledì","Giovedì","Venerdì","Sabato","Domenica"],
        "header_week": "\nIl tuo programma settimanale ",
        "line_week": "🔴{day} → {act} a {place}",
        "ask_day": "\nInserisci un giorno per visualizzare/aggiornare (o 'fine' per terminare): ",
        "show_day": "Il {day} farai {act} a {place}.",
        "ask_change": "Vuoi cambiare l’attività di {day}? (s/n): ",
        "ask_new_act": "Inserisci la nuova attività per {day}: ",
        "ask_new_place": "Inserisci il nuovo luogo per {day}: ",
        "updated": "✅ {day} aggiornato: ora {act} a {place}.\n",
        "no_change": "Nessuna modifica per {day}.",
        "invalid_day": "Giorno non valido. Inserisci un giorno corretto della settimana.",
        "confirm_exit": "Sei sicuro di voler uscire? (s/n): ",
        "yes": {"s","si","sì"},
        "chose_day": "Quale giorno vuoi aggiornare? ",
        "Activity_question": "Quale attività farai il {day}?",
        "location_question": "Dove farai l’attività il {day}?",
        "no_plan": "Non hai attività pianificate per questa settimana.",
        "prompt_add": "Vuoi aggiungerle ora? (s/n): ",
        "nothing_planned": "Niente ancora pianificato.",
        "another_activity": "Vuoi registrare un’altra attività? (s/n): ",
        "next_time": "OK, forse la prossima volta ",
        "Ambiguous_day": "Il giorno inserito è ambiguo. Per favore sii più preciso.",
        "welcome": "Benvenuto, ",
        "Welcome_2": "! Pianifichiamo la tua settimana! 🗓️✨",
        "introduce_name": "Per favore inserisci il tuo nome: ",
        "occupied_day": "Hai già un’attività pianificata per {day} a {place}. Vuoi cambiarla? (s/n): "
    },
    "he": {
        "name": ["עברית","Hebrew","HE","he","ivrit","עברית.","He","עבר","IL","il","Il"],
        "days": ["יום שני","יום שלישי","יום רביעי","יום חמישי","יום שישי","שבת","יום ראשון"],
        "header_week": "\nלוח השבוע שלך ",
        "line_week": "🔴{day} → {act} ב{place}",
        "ask_day": "\nהכנס יום לצפייה/עדכון (או 'יציאה' לסיום): ",
        "show_day": "ביום {day} תעשה {act} ב{place}.",
        "ask_change": "האם תרצה לשנות את הפעילות ביום {day}? (כ/ל): ",
        "ask_new_act": "הכנס את הפעילות החדשה ל{day}: ",
        "ask_new_place": "הכנס את המקום החדש ל{day}: ",
        "updated": "✅ {day} עודכן: כעת {act} ב{place}.\n",
        "no_change": "אין שינויים עבור {day}.",
        "invalid_day": "יום לא תקין. אנא הזן יום תקני.",
        "confirm_exit": "האם אתה בטוח שברצונך לצאת? (כ/ל): ",
        "yes": {"כ","כן"},
        "chose_day": "איזה יום תרצה לעדכן? ",
        "Activity_question": "איזו פעילות תעשה ביום {day}?",
        "location_question": "איפה תבצע את הפעילות ביום {day}?",
        "no_plan": "אין לך פעילויות מתוכננות לשבוע זה.",
        "prompt_add": "האם תרצה להוסיף אותן עכשיו? (כ/ל): ",
        "nothing_planned": "אין שום תכנון עדיין.",
        "another_activity": "האם תרצה לרשום פעילות נוספת? (כ/ל): ",
        "next_time": "אולי בפעם הבאה ",
        "Ambiguous_day": "היום שהוזן אינו ברור. אנא היה מדויק יותר.",
        "welcome": "ברוך הבא, ",
        "Welcome_2": "! בוא נתכנן את השבוע שלך! 🗓️✨",
        "introduce_name": "אנא הכנס את שמך: ",
        "occupied_day": "כבר יש לך פעילות מתוכננת ל{day} ב{place}. האם תרצה לשנות אותה? (כ/ל): "
    },
    "sv": {
        "name": ["Svenska","Swedish","SV","sv","svenska","SWE","swe","SVENSKA","SE","se","Se","Swe"],
        "days": ["Måndag","Tisdag","Onsdag","Torsdag","Fredag","Lördag","Söndag"],
        "header_week": "\nDitt veckoschema ",
        "line_week": "🔴{day} → {act} i {place}",
        "ask_day": "\nAnge en dag för att visa/ändra (eller 'avsluta' för att sluta): ",
        "show_day": "På {day} gör du {act} i {place}.",
        "ask_change": "Vill du ändra aktiviteten på {day}? (j/n): ",
        "ask_new_act": "Skriv in den nya aktiviteten för {day}: ",
        "ask_new_place": "Skriv in den nya platsen för {day}: ",
        "updated": "✅ {day} uppdaterad: nu {act} i {place}.\n",
        "no_change": "Inga ändringar för {day}.",
        "invalid_day": "Ogiltig dag. Ange en giltig veckodag.",
        "confirm_exit": "Är du säker på att du vill avsluta? (j/n): ",
        "yes": {"j","ja"},
        "chose_day": "Vilken dag vill du uppdatera? ",
        "Activity_question": "Vilken aktivitet gör du på {day}?",
        "location_question": "Var gör du aktiviteten på {day}?",
        "no_plan": "Du har inga planerade aktiviteter denna vecka.",
        "prompt_add": "Vill du lägga till dem nu? (j/n): ",
        "nothing_planned": "Inget planerat ännu.",
        "another_activity": "Vill du registrera en aktivitet till? (j/n): ",
        "next_time": "Okej, kanske nästa gång ",
        "Ambiguous_day": "Dagen du angav är tvetydig. Var mer specifik.",
        "welcome": "Välkommen, ",
        "Welcome_2": "! Låt oss planera din vecka! 🗓️✨",
        "introduce_name": "Ange ditt namn: ",
        "occupied_day": "Du har redan en aktivitet planerad på {day} i {place}. Vill du ändra den? (j/n): "
    },
    "fi": {
        "name": ["Suomi","Finnish","FI","fi","suomi","Fin","FIN","fin","SUOMI","Fin","Suomi","fn","FN","Fn"],
        "days": ["Maanantai","Tiistai","Keskiviikko","Torstai","Perjantai","Lauantai","Sunnuntai"],
        "header_week": "\nViikkoaikataulusi ",
        "line_week": "🔴{day} → {act} paikassa {place}",
        "ask_day": "\nAnna päivä katsoaksesi/muokataksesi (tai 'loppu' lopettaaksesi): ",
        "show_day": "{day} teet {act} paikassa {place}.",
        "ask_change": "Haluatko muuttaa {day} toimintaa? (k/e): ",
        "ask_new_act": "Anna uusi toiminta päivälle {day}: ",
        "ask_new_place": "Anna uusi paikka päivälle {day}: ",
        "updated": "✅ {day} päivitetty: nyt {act} paikassa {place}.\n",
        "no_change": "Ei muutoksia päivälle {day}.",
        "invalid_day": "Virheellinen päivä. Anna viikonpäivä.",
        "confirm_exit": "Oletko varma, että haluat lopettaa? (k/e): ",
        "yes": {"k","kyllä"},
        "chose_day": "Mitä päivää haluat muokata? ",
        "Activity_question": "Mitä toimintaa teet {day}?",
        "location_question": "Missä teet toiminnan {day}?",
        "no_plan": "Sinulla ei ole suunniteltuja toimintoja tälle viikolle.",
        "prompt_add": "Haluatko lisätä ne nyt? (k/e): ",
        "nothing_planned": "Ei vielä suunnitelmia.",
        "another_activity": "Haluatko lisätä toisen toiminnan? (k/e): ",
        "next_time": "Ehkä ensi kerralla ",
        "Ambiguous_day": "Antamasi päivä on epäselvä. Ole tarkempi.",
        "welcome": "Tervetuloa, ",
        "Welcome_2": "! Suunnitellaan viikkosi! 🗓️✨",
        "introduce_name": "Anna nimesi: ",
        "occupied_day": "Sinulla on jo toiminta {day} paikassa {place}. Haluatko muuttaa sitä? (k/e): "
},
    "da": {
        "name": ["Dansk","Danish","DA","da","dansk","DAN","dan","DK","DANSK","dk","Dk"],
        "days": ["Mandag","Tirsdag","Onsdag","Torsdag","Fredag","Lørdag","Søndag"],
        "header_week": "\nDin ugentlige plan ",
        "line_week": "🔴{day} → {act} i {place}",
        "ask_day": "\nIndtast en dag for at se/ændre (eller 'slut' for at afslutte): ",
        "show_day": "Om {day} laver du {act} i {place}.",
        "ask_change": "Vil du ændre aktiviteten for {day}? (j/n): ",
        "ask_new_act": "Indtast den nye aktivitet for {day}: ",
        "ask_new_place": "Indtast det nye sted for {day}: ",
        "updated": "✅ {day} opdateret: nu {act} i {place}.\n",
        "no_change": "Ingen ændringer for {day}.",
        "invalid_day": "Ugyldig dag. Indtast en gyldig ugedag.",
        "confirm_exit": "Er du sikker på, at du vil afslutte? (j/n): ",
        "yes": {"j","ja"},
        "chose_day": "Hvilken dag vil du opdatere? ",
        "Activity_question": "Hvilken aktivitet laver du om {day}?",
        "location_question": "Hvor laver du aktiviteten om {day}?",
        "no_plan": "Du har ingen planlagte aktiviteter for denne uge.",
        "prompt_add": "Vil du tilføje dem nu? (j/n): ",
        "nothing_planned": "Intet planlagt endnu.",
        "another_activity": "Vil du registrere en anden aktivitet? (j/n): ",
        "next_time": "Okay, måske næste gang ",
        "Ambiguous_day": "Dagen du indtastede er tvetydig. Vær mere specifik.",
        "welcome": "Velkommen, ",
        "Welcome_2": "! Lad os planlægge din uge! 🗓️✨",
        "introduce_name": "Indtast dit navn: ",
        "occupied_day": "Du har allerede en aktivitet planlagt for {day} i {place}. Vil du ændre den? (j/n): "
    },
    "no": {
        "name": ["Norsk","Norwegian","NO","no","norsk","NOR","nor","NORSK"],
        "days": ["Mandag","Tirsdag","Onsdag","Torsdag","Fredag","Lørdag","Søndag"],
        "header_week": "\nDin ukentlige plan ",
        "line_week": "🔴{day} → {act} i {place}",
        "ask_day": "\nSkriv en dag for å vise/endre (eller 'slutt' for å avslutte): ",
        "show_day": "På {day} skal du gjøre {act} i {place}.",
        "ask_change": "Vil du endre aktiviteten på {day}? (j/n): ",
        "ask_new_act": "Skriv inn den nye aktiviteten for {day}: ",
        "ask_new_place": "Skriv inn det nye stedet for {day}: ",
        "updated": "✅ {day} oppdatert: nå {act} i {place}.\n",
        "no_change": "Ingen endringer for {day}.",
        "invalid_day": "Ugyldig dag. Oppgi en gyldig ukedag.",
        "confirm_exit": "Er du sikker på at du vil avslutte? (j/n): ",
        "yes": {"j","ja"},
        "chose_day": "Hvilken dag vil du oppdatere? ",
        "Activity_question": "Hvilken aktivitet gjør du på {day}?",
        "location_question": "Hvor gjør du aktiviteten på {day}?",
        "no_plan": "Du har ingen planlagte aktiviteter denne uken.",
        "prompt_add": "Vil du legge dem til nå? (j/n): ",
        "nothing_planned": "Ingenting planlagt ennå.",
        "another_activity": "Vil du registrere en aktivitet til? (j/n): ",
        "next_time": "Ok, kanskje neste gang ",
        "Ambiguous_day": "Dagen du skrev inn er tvetydig. Vær mer spesifikk.",
        "welcome": "Velkommen, ",
        "Welcome_2": "! La oss planlegge uken din! 🗓️✨",
        "introduce_name": "Skriv inn navnet ditt: ",
        "occupied_day": "Du har allerede en aktivitet planlagt for {day} i {place}. Vil du endre den? (j/n): "
    },
    "is": {
        "name": ["Íslenska","Icelandic","IS","is","islenska","ÍSLENSKA","iceland","Is","Islenska","ISLENSKA","ÍSLENSKA","ISL","Isl","isl","ICE"],
        "days": ["Mánudagur","Þriðjudagur","Miðvikudagur","Fimmtudagur","Föstudagur","Laugardagur","Sunnudagur"],
        "header_week": "\nVikuleg áætlun þín ",
        "line_week": "🔴{day} → {act} í {place}",
        "ask_day": "\nSláðu inn dag til að skoða/breyta (eða 'hætta' til að ljúka): ",
        "show_day": "Á {day} munt þú gera {act} í {place}.",
        "ask_change": "Viltu breyta verkefninu á {day}? (j/n): ",
        "ask_new_act": "Sláðu inn nýtt verkefni fyrir {day}: ",
        "ask_new_place": "Sláðu inn nýjan stað fyrir {day}: ",
        "updated": "✅ {day} uppfærður: nú {act} í {place}.\n",
        "no_change": "Engar breytingar fyrir {day}.",
        "invalid_day": "Ógildur dagur. Sláðu inn gildan vikudag.",
        "confirm_exit": "Ertu viss um að þú viljir hætta? (j/n): ",
        "yes": {"j","já"},
        "chose_day": "Hvaða dag viltu uppfæra? ",
        "Activity_question": "Hvaða verkefni munt þú gera á {day}?",
        "location_question": "Hvar munt þú gera verkefnið á {day}?",
        "no_plan": "Engar áætlanir fyrir þessa viku.",
        "prompt_add": "Viltu bæta þeim við núna? (j/n): ",
        "nothing_planned": "Ekkert áætlað enn.",
        "another_activity": "Viltu skrá annað verkefni? (j/n): ",
        "next_time": "Kannski næst ",
        "Ambiguous_day": "Dagurinn sem þú slóst inn er óljós. Vertu nákvæmari.",
        "welcome": "Velkomin, ",
        "Welcome_2": "! Við skulum skipuleggja vikuna þína! 🗓️✨",
        "introduce_name": "Sláðu inn nafnið þitt: ",
        "occupied_day": "Þú ert nú þegar með verkefni á {day} í {place}. Viltu breyta því? (j/n): "
    },
    "lt": {
        "name": ["Lietuvių","Lithuanian","LT","lt","lietuviu","LIETUVIŲ","Lt","LIETUVIU","Lietuviu","lietuviu","lietuvių"],
        "days": ["Pirmadienis","Antradienis","Trečiadienis","Ketvirtadienis","Penktadienis","Šeštadienis","Sekmadienis"],
        "header_week": "\nTavo savaitės planas ",
        "line_week": "🔴{day} → {act} vietoje {place}",
        "ask_day": "\nĮvesk dieną, kad peržiūrėtum/atnaujintum (arba 'pabaiga' baigti): ",
        "show_day": "{day} darysi {act} vietoje {place}.",
        "ask_change": "Ar nori pakeisti veiklą {day}? (t/n): ",
        "ask_new_act": "Įvesk naują veiklą {day}: ",
        "ask_new_place": "Įvesk naują vietą {day}: ",
        "updated": "✅ {day} atnaujinta: dabar {act} vietoje {place}.\n",
        "no_change": "Jokių pakeitimų {day}.",
        "invalid_day": "Neteisinga diena. Įvesk galiojančią savaitės dieną.",
        "confirm_exit": "Ar tikrai nori išeiti? (t/n): ",
        "yes": {"t","taip"},
        "chose_day": "Kurią dieną nori atnaujinti? ",
        "Activity_question": "Kokią veiklą darysi {day}?",
        "location_question": "Kur darysi veiklą {day}?",
        "no_plan": "Neturi suplanuotų veiklų šiai savaitei.",
        "prompt_add": "Ar nori jas pridėti dabar? (t/n): ",
        "nothing_planned": "Dar nieko neplanuota.",
        "another_activity": "Ar nori registruoti dar vieną veiklą? (t/n): ",
        "next_time": "Gal kitą kartą ",
        "Ambiguous_day": "Įvesta diena neaiški. Būk tikslesnis.",
        "welcome": "Sveikas, ",
        "Welcome_2": "! Suplanuokime tavo savaitę! 🗓️✨",
        "introduce_name": "Įvesk savo vardą: ",
        "occupied_day": "Jau turi suplanuotą veiklą {day} vietoje {place}. Ar nori ją pakeisti? (t/n): "
    },
    "et": {
        "name": ["Eesti","Estonian","ET","et","eesti","EST","ee","EE","Ee","EESTI"],
        "days": ["Esmaspäev","Teisipäev","Kolmapäev","Neljapäev","Reede","Laupäev","Pühapäev"],
        "header_week": "\nSinu nädalaplaan ",
        "line_week": "🔴{day} → {act} kohas {place}",
        "ask_day": "\nSisesta päev vaatamiseks/muutmiseks (või 'lõpp' lõpetamiseks): ",
        "show_day": "{day} teed {act} kohas {place}.",
        "ask_change": "Kas soovid muuta tegevust {day}? (j/e): ",
        "ask_new_act": "Sisesta uus tegevus {day}: ",
        "ask_new_place": "Sisesta uus koht {day}: ",
        "updated": "✅ {day} uuendatud: nüüd {act} kohas {place}.\n",
        "no_change": "Muudatusi pole {day}.",
        "invalid_day": "Vale päev. Palun sisesta korrektne nädalapäev.",
        "confirm_exit": "Kas oled kindel, et soovid lõpetada? (j/e): ",
        "yes": {"j","jah"},
        "chose_day": "Millist päeva soovid uuendada? ",
        "Activity_question": "Millist tegevust teed {day}?",
        "location_question": "Kus teed tegevust {day}?",
        "no_plan": "Sul pole selleks nädalaks tegevusi planeeritud.",
        "prompt_add": "Kas soovid need nüüd lisada? (j/e): ",
        "nothing_planned": "Veel pole midagi planeeritud.",
        "another_activity": "Kas soovid lisada veel ühe tegevuse? (j/e): ",
        "next_time": "Võib-olla järgmisel korral ",
        "Ambiguous_day": "Sisestatud päev on ebaselge. Ole täpsem.",
        "welcome": "Tere tulemast, ",
        "Welcome_2": "! Planeerime sinu nädala! 🗓️✨",
        "introduce_name": "Sisesta oma nimi: ",
        "occupied_day": "Sul on juba tegevus planeeritud {day} kohas {place}. Kas soovid seda muuta? (j/e): "
    },
    "ro": {
        "name": ["Română","Romanian","RO","ro","română","ROM"],
        "days": ["Luni","Marți","Miercuri","Joi","Vineri","Sâmbătă","Duminică"],
        "header_week": "\nProgramul tău săptămânal ",
        "line_week": "🔴{day} → {act} la {place}",
        "ask_day": "\nIntrodu o zi pentru a vedea/modifica (sau 'stop' pentru a încheia): ",
        "show_day": "În {day} vei face {act} la {place}.",
        "ask_change": "Vrei să schimbi activitatea pentru {day}? (d/n): ",
        "ask_new_act": "Introdu noua activitate pentru {day}: ",
        "ask_new_place": "Introdu noul loc pentru {day}: ",
        "updated": "✅ {day} actualizat: acum {act} la {place}.\n",
        "no_change": "Nicio schimbare pentru {day}.",
        "invalid_day": "Zi invalidă. Introdu o zi validă.",
        "confirm_exit": "Ești sigur că vrei să ieși? (d/n): ",
        "yes": {"d","da"},
        "chose_day": "Ce zi dorești să actualizezi? ",
        "Activity_question": "Ce activitate vei face în {day}?",
        "location_question": "Unde vei face activitatea în {day}?",
        "no_plan": "Nu ai activități planificate pentru această săptămână.",
        "prompt_add": "Vrei să le adaugi acum? (d/n): ",
        "nothing_planned": "Nimic planificat încă.",
        "another_activity": "Vrei să înregistrezi o altă activitate? (d/n): ",
        "next_time": "Poate data viitoare ",
        "Ambiguous_day": "Ziua introdusă este ambiguă. Te rog fii mai specific.",
        "welcome": "Bun venit, ",
        "Welcome_2": "! Să îți planificăm săptămâna! 🗓️✨",
        "introduce_name": "Te rog introdu numele tău: ",
        "occupied_day": "Ai deja o activitate planificată în {day} la {place}. Vrei să o schimbi? (d/n): "
    },
    "sk": {
        "name": ["Slovensky","Slovak","SK","sk","slovak","slovenský","SLOVENSKY","SLOVENSKÝ","Slovenský","SLOVAK"],
        "days": ["Pondelok","Utorok","Streda","Štvrtok","Piatok","Sobota","Nedeľa"],
        "header_week": "\nTvoj týždenný plán ",
        "line_week": "🔴{day} → {act} v {place}",
        "ask_day": "\nZadaj deň na zobrazenie/úpravu (alebo 'koniec' pre ukončenie): ",
        "show_day": "V {day} budeš robiť {act} v {place}.",
        "ask_change": "Chceš zmeniť aktivitu v {day}? (a/n): ",
        "ask_new_act": "Zadaj novú aktivitu pre {day}: ",
        "ask_new_place": "Zadaj nové miesto pre {day}: ",
        "updated": "✅ {day} aktualizovaný: teraz {act} v {place}.\n",
        "no_change": "Žiadne zmeny pre {day}.",
        "invalid_day": "Neplatný deň. Zadaj platný deň v týždni.",
        "confirm_exit": "Naozaj chceš skončiť? (a/n): ",
        "yes": {"a","áno"},
        "chose_day": "Ktorý deň chceš aktualizovať? ",
        "Activity_question": "Akú aktivitu budeš robiť v {day}?",
        "location_question": "Kde budeš robiť aktivitu v {day}?",
        "no_plan": "Nemáš naplánované žiadne aktivity na tento týždeň.",
        "prompt_add": "Chceš ich pridať teraz? (a/n): ",
        "nothing_planned": "Zatiaľ nič nie je naplánované.",
        "another_activity": "Chceš pridať ďalšiu aktivitu? (a/n): ",
        "next_time": "Možno nabudúce ",
        "Ambiguous_day": "Zadaný deň je nejasný. Prosím, upresni ho.",
        "welcome": "Vitaj, ",
        "Welcome_2": "! Poďme naplánovať tvoj týždeň! 🗓️✨",
        "introduce_name": "Zadaj svoje meno: ",
        "occupied_day": "Už máš naplánovanú aktivitu v {day} v {place}. Chceš ju zmeniť? (a/n): "
    },
    "cs": {
        "name": ["Čeština","Czech","CZ","cz","czech","česky","CESTINA","CESKY","ČSŠKY","ČEŠTINA","čeština","Česky"],
        "days": ["Pondělí","Úterý","Středa","Čtvrtek","Pátek","Sobota","Neděle"],
        "header_week": "\nTvůj týdenní plán ",
        "line_week": "🔴{day} → {act} v {place}",
        "ask_day": "\nZadej den pro zobrazení/úpravu (nebo 'konec' pro ukončení): ",
        "show_day": "V {day} budeš dělat {act} v {place}.",
        "ask_change": "Chceš změnit aktivitu pro {day}? (a/n): ",
        "ask_new_act": "Zadej novou aktivitu pro {day}: ",
        "ask_new_place": "Zadej nové místo pro {day}: ",
        "updated": "✅ {day} aktualizováno: nyní {act} v {place}.\n",
        "no_change": "Žádné změny pro {day}.",
        "invalid_day": "Neplatný den. Zadej platný den v týdnu.",
        "confirm_exit": "Opravdu chceš skončit? (a/n): ",
        "yes": {"a","ano"},
        "chose_day": "Který den chceš aktualizovat? ",
        "Activity_question": "Jakou aktivitu budeš dělat v {day}?",
        "location_question": "Kde budeš dělat aktivitu v {day}?",
        "no_plan": "Nemáš naplánované žádné aktivity pro tento týden.",
        "prompt_add": "Chceš je přidat nyní? (a/n): ",
        "nothing_planned": "Zatím nic naplánováno.",
        "another_activity": "Chceš přidat další aktivitu? (a/n): ",
        "next_time": "Možná příště ",
        "Ambiguous_day": "Zadaný den je nejednoznačný. Buď prosím konkrétnější.",
        "welcome": "Vítej, ",
        "Welcome_2": "! Naplánujme tvůj týden! 🗓️✨",
        "introduce_name": "Zadej své jméno: ",
        "occupied_day": "Už máš aktivitu naplánovanou v {day} v {place}. Chceš ji změnit? (a/n): "
    },
    "bg": {
        "name": ["Български","Bulgarian","BG","bg","bulgarian","български","Bg","6r","Бъ","Бъл","Бълг","бъ","бъл","бълг"],
        "days": ["Понеделник","Вторник","Сряда","Четвъртък","Петък","Събота","Неделя"],
        "header_week": "\nТвоят седмичен график ",
        "line_week": "🔴{day} → {act} в {place}",
        "ask_day": "\nВъведи ден за преглед/промяна (или 'край' за изход): ",
        "show_day": "В {day} ще правиш {act} в {place}.",
        "ask_change": "Искаш ли да промениш дейността за {day}? (д/н): ",
        "ask_new_act": "Въведи новата дейност за {day}: ",
        "ask_new_place": "Въведи новото място за {day}: ",
        "updated": "✅ {day} актуализиран: сега {act} в {place}.\n",
        "no_change": "Няма промени за {day}.",
        "invalid_day": "Невалиден ден. Въведи валиден ден от седмицата.",
        "confirm_exit": "Сигурен ли си, че искаш да излезеш? (д/н): ",
        "yes": {"д","да"},
        "chose_day": "Кой ден искаш да актуализираш? ",
        "Activity_question": "Каква дейност ще правиш в {day}?",
        "location_question": "Къде ще правиш дейността в {day}?",
        "no_plan": "Нямаш планирани дейности за тази седмица.",
        "prompt_add": "Искаш ли да ги добавиш сега? (д/н): ",
        "nothing_planned": "Все още няма нищо планирано.",
        "another_activity": "Искаш ли да добавиш още една дейност? (д/н): ",
        "next_time": "Може би следващия път ",
        "Ambiguous_day": "Въведеният ден е неясен. Моля, бъди по-конкретен.",
        "welcome": "Добре дошъл, ",
        "Welcome_2": "! Нека планираме седмицата ти! 🗓️✨",
        "introduce_name": "Моля, въведи името си: ",
        "occupied_day": "Вече имаш планирана дейност за {day} в {place}. Искаш ли да я промениш? (д/н): "
    },
    "el": {
        "name": ["Ελληνικά","Greek","EL","el","greek","ΕΛΛΗΝΙΚΑ","GR","gr","Gr"],
        "days": ["Δευτέρα","Τρίτη","Τετάρτη","Πέμπτη","Παρασκευή","Σάββατο","Κυριακή"],
        "header_week": "\nΤο εβδομαδιαίο πρόγραμμά σου ",
        "line_week": "🔴{day} → {act} στο {place}",
        "ask_day": "\nΕισάγετε ημέρα για προβολή/αλλαγή (ή 'τέλος' για έξοδο): ",
        "show_day": "Τη {day} θα κάνεις {act} στο {place}.",
        "ask_change": "Θέλεις να αλλάξεις τη δραστηριότητα της {day}; (ν/ο): ",
        "ask_new_act": "Εισάγετε τη νέα δραστηριότητα για τη {day}: ",
        "ask_new_place": "Εισάγετε το νέο μέρος για τη {day}: ",
        "updated": "✅ {day} ενημερώθηκε: τώρα {act} στο {place}.\n",
        "no_change": "Καμία αλλαγή για τη {day}.",
        "invalid_day": "Μη έγκυρη ημέρα. Εισάγετε έγκυρη ημέρα εβδομάδας.",
        "confirm_exit": "Είσαι σίγουρος ότι θέλεις να βγεις; (ν/ο): ",
        "yes": {"ν","ναι"},
        "chose_day": "Ποια ημέρα θέλεις να ενημερώσεις; ",
        "Activity_question": "Τι δραστηριότητα θα κάνεις τη {day};",
        "location_question": "Πού θα γίνει η δραστηριότητα τη {day};",
        "no_plan": "Δεν έχεις προγραμματισμένες δραστηριότητες για αυτή την εβδομάδα.",
        "prompt_add": "Θέλεις να τις προσθέσεις τώρα; (ν/ο): ",
        "nothing_planned": "Τίποτα δεν έχει προγραμματιστεί ακόμα.",
        "another_activity": "Θέλεις να καταχωρήσεις άλλη μία δραστηριότητα; (ν/ο): ",
        "next_time": "Ίσως την επόμενη φορά ",
        "Ambiguous_day": "Η ημέρα που εισήχθη είναι ασαφής. Παρακαλώ γίνε πιο συγκεκριμένος.",
        "welcome": "Καλώς ήρθες, ",
        "Welcome_2": "! Ας προγραμματίσουμε την εβδομάδα σου! 🗓️✨",
        "introduce_name": "Παρακαλώ εισήγαγε το όνομά σου: ",
        "occupied_day": "Έχεις ήδη μια δραστηριότητα για τη {day} στο {place}. Θέλεις να τη αλλάξεις; (ν/ο): "
    },
    "sq": {
        "name": ["Shqip","Albanian","AL","al","shqip","ALB","alb","SHQIP"],
        "days": ["E Hënë","E Martë","E Mërkurë","E Enjte","E Premte","E Shtunë","E Diel"],
        "header_week": "\nPlani yt javor ",
        "line_week": "🔴{day} → {act} në {place}",
        "ask_day": "\nShkruaj një ditë për të parë/ndryshuar (ose 'fund' për të mbaruar): ",
        "show_day": "Në {day} do të bësh {act} në {place}.",
        "ask_change": "Dëshiron të ndryshosh aktivitetin e {day}? (p/j): ",
        "ask_new_act": "Shkruaj aktivitetin e ri për {day}: ",
        "ask_new_place": "Shkruaj vendin e ri për {day}: ",
        "updated": "✅ {day} u përditësua: tani {act} në {place}.\n",
        "no_change": "Nuk ka ndryshime për {day}.",
        "invalid_day": "Ditë e pavlefshme. Shkruaj një ditë të vlefshme të javës.",
        "confirm_exit": "Je i sigurt që dëshiron të dalësh? (p/j): ",
        "yes": {"p","po"},
        "chose_day": "Cilën ditë dëshiron të përditësosh? ",
        "Activity_question": "Çfarë aktiviteti do të bësh në {day}?",
        "location_question": "Ku do ta bësh aktivitetin në {day}?",
        "no_plan": "Nuk ke aktivitete të planifikuara për këtë javë.",
        "prompt_add": "Dëshiron t’i shtosh tani? (p/j): ",
        "nothing_planned": "Asgjë nuk është planifikuar ende.",
        "another_activity": "Dëshiron të regjistrosh një aktivitet tjetër? (p/j): ",
        "next_time": "Ndoshta herën tjetër ",
        "Ambiguous_day": "Dita që shkrove është e paqartë. Ju lutem, jep më shumë detaje.",
        "welcome": "Mirë se erdhe, ",
        "Welcome_2": "! Le të planifikojmë javën tënde! 🗓️✨",
        "introduce_name": "Shkruaj emrin tënd: ",
        "occupied_day": "Tashmë ke një aktivitet të planifikuar për {day} në {place}. Dëshiron ta ndryshosh? (p/j): "
    },
    "sl": {
        "name": ["Slovenščina","Slovensko","Slovenian","SI","si","Si","slo","SLO","slovenscina","slovenščina","SLOVENŠČINA","Slovenski","SLOVENSKI","SLOVENSCINA"],
        "days": ["Ponedeljek","Torek","Sreda","Četrtek","Petek","Sobota","Nedelja"],
        "header_week": "\nTvoj tedenski urnik ",
        "line_week": "🔴{day} → {act} v {place}",
        "ask_day": "\nVnesi dan za pregled/posodobitev (ali 'konec' za zaključek): ",
        "show_day": "{day} boš delal/a {act} v {place}.",
        "ask_change": "Želiš spremeniti aktivnost za {day}? (d/n): ",
        "ask_new_act": "Vnesi novo aktivnost za {day}: ",
        "ask_new_place": "Vnesi novo lokacijo za {day}: ",
        "updated": "✅ {day} posodobljen: zdaj {act} v {place}.\n",
        "no_change": "Ni sprememb za {day}.",
        "invalid_day": "Neveljaven dan. Vnesi veljaven dan v tednu.",
        "confirm_exit": "Si prepričan/na, da želiš zaključiti? (d/n): ",
        "yes": {"d","da"},
        "chose_day": "Kateri dan želiš posodobiti? ",
        "Activity_question": "Katero aktivnost boš imel/a {day}?",
        "location_question": "Kje boš izvajal/a aktivnost {day}?",
        "no_plan": "Za ta teden nimaš načrtovanih aktivnosti.",
        "prompt_add": "Želiš dodati aktivnosti zdaj? (d/n): ",
        "nothing_planned": "Ni še nič načrtovano.",
        "another_activity": "Želiš dodati še eno aktivnost? (d/n): ",
        "next_time": "OK, mogoče naslednjič ",
        "Ambiguous_day": "Vneseni dan je nejasen. Prosim, bodi bolj natančen/na.",
        "welcome": "Dobrodošel/a, ",
        "Welcome_2": "! Planirajva tvoj teden! 🗓️✨",
        "introduce_name": "Prosim, vnesi svoje ime: ",
        "occupied_day": "Za {day} imaš že načrtovano aktivnost v {place}. Jo želiš spremeniti? (d/n): "
    },
    "sr": {
        "name": ["Српски","Srpski","Serbian","SR","sr","srpski","СРПСКИ","Cp6","Rs","RS","PC","pc","Pc","српски","SRPSKI"],
        "days": ["Понедељак","Уторак","Среда","Четвртак","Петак","Субота","Недеља"],
        "header_week": "\nТвој недељни распоред ",
        "line_week": "🔴{day} → {act} у {place}",
        "ask_day": "\nУнеси дан за приказ/измену (или 'крај' за завршетак): ",
        "show_day": "У {day} радићеш {act} у {place}.",
        "ask_change": "Да ли желиш да промениш активност за {day}? (д/н): ",
        "ask_new_act": "Унеси нову активност за {day}: ",
        "ask_new_place": "Унеси ново место за {day}: ",
        "updated": "✅ {day} ажуриран: сада {act} у {place}.\n",
        "no_change": "Нема промена за {day}.",
        "invalid_day": "Неважећи дан. Унеси важећи дан у недељи.",
        "confirm_exit": "Да ли си сигуран/сигурна да желиш да изађеш? (д/н): ",
        "yes": {"д","да"},
        "chose_day": "Који дан желиш да ажурираш? ",
        "Activity_question": "Коју активност ћеш радити у {day}?",
        "location_question": "Где ћеш радити активност у {day}?",
        "no_plan": "Немаш планираних активности за ову недељу.",
        "prompt_add": "Да ли желиш да их додаш сада? (д/н): ",
        "nothing_planned": "Још увек ништа није планирано.",
        "another_activity": "Да ли желиш да региструјеш још једну активност? (д/н): ",
        "next_time": "Добро, можда следећи пут ",
        "Ambiguous_day": "Дан који си uneo/la је нејасан. Молим те, буди прецизнији/ја.",
        "welcome": "Добродошао/Добродошла, ",
        "Welcome_2": "! Хајде да испланирамо твоју недељу! 🗓️✨",
        "introduce_name": "Молим те, унеси своје име: ",
        "occupied_day": "Већ имаш планирану активност за {day} у {place}. Да ли желиш да је промениш? (д/н): "
    },
    "mt": {
        "name": ["Malti","Maltese","MT","mt","malti","MALTI"],
        "days": ["It-Tnejn","It-Tlieta","L-Erbgħa","Il-Ħamis","Il-Ġimgħa","Is-Sibt","Il-Ħadd"],
        "header_week": "\nIl-pjan ta’ ġimgħek ",
        "line_week": "🔴{day} → {act} f’{place}",
        "ask_day": "\nDaħħal jum biex tara/aġġorna (jew 'tmiem' biex tispiċċa): ",
        "show_day": "Nhari {day} se tagħmel {act} f’{place}.",
        "ask_change": "Trid tbiddel l-attività ta’ {day}? (i/l): ",
        "ask_new_act": "Daħħal l-attività l-ġdida għal {day}: ",
        "ask_new_place": "Daħħal il-post il-ġdid għal {day}: ",
        "updated": "✅ {day} aġġornat: issa {act} f’{place}.\n",
        "no_change": "L-ebda tibdil għal {day}.",
        "invalid_day": "Jum invalidu. Daħħal jum validu tal-ġimgħa.",
        "confirm_exit": "Żgur li trid toħroġ? (i/l): ",
        "yes": {"i","iva"},
        "chose_day": "Liema jum tixtieq taġġorna? ",
        "Activity_question": "X’attività se tagħmel nhar {day}?",
        "location_question": "Fejn se ssir l-attività nhar {day}?",
        "no_plan": "M’għandekx attivitajiet ippjanati għal din il-ġimgħa.",
        "prompt_add": "Trid iżżidhom issa? (i/l): ",
        "nothing_planned": "Xejn ippjanat s’issa.",
        "another_activity": "Trid tirreġistra attività oħra? (i/l): ",
        "next_time": "Tajjeb, forsi darb’oħra ",
        "Ambiguous_day": "Il-jum li daħħalt mhux ċar. Jekk jogħġbok kun aktar speċifiku/a.",
        "welcome": "Merħba, ",
        "Welcome_2": "! Ejjew nippjanaw il-ġimgħa tiegħek! 🗓️✨",
        "introduce_name": "Daħħal ismek jekk jogħġbok: ",
        "occupied_day": "Diġà għandek attività ppjanata nhar {day} f’{place}. Trid tbiddilha? (i/l): "
    },
    "fo": {
        "name": ["Føroyskt","Faroese","FO","fo","foroyar","Føroyar","FØROYAR"],
        "days": ["Mánadagur","Týsdagur","Mikudagur","Hósdagur","Fríggjadagur","Leygardagur","Sunnudagur"],
        "header_week": "\nTín vikuskrá ",
        "line_week": "🔴{day} → {act} í {place}",
        "ask_day": "\nSkriva ein dag fyri at vísa/broyt(a) (ella 'enda' fyri at steðga): ",
        "show_day": "{day} fert tú at gera {act} í {place}.",
        "ask_change": "Vil tú broyta aktivitetin {day}? (j/n): ",
        "ask_new_act": "Skriva nýggjan aktivitet fyri {day}: ",
        "ask_new_place": "Skriva nýtt stað fyri {day}: ",
        "updated": "✅ {day} dagførdur: nú {act} í {place}.\n",
        "no_change": "Ongar broytingar fyri {day}.",
        "invalid_day": "Ógildigur dagur. Vinarliga skriva ein gildugan vikudag.",
        "confirm_exit": "Er tú viss/ur í, at tú vilt steðga? (j/n): ",
        "yes": {"j","ja"},
        "chose_day": "Hvønn dag vilt tú dagføra? ",
        "Activity_question": "Hvat skalt tú gera {day}?",
        "location_question": "Hvar skalt tú gera aktivitetin {day}?",
        "no_plan": "Tú hevur ongar aktivitetir skrásettar hesa vikuna.",
        "prompt_add": "Vilt tú leggja teir afturat nú? (j/n): ",
        "nothing_planned": "Einki er fyribils skrásett.",
        "another_activity": "Vilt tú skráseta ein annan aktivitet? (j/n): ",
        "next_time": "Kanska næstu ferð ",
        "Ambiguous_day": "Dagurin, tú skrivaði, er ógreiður. Vinarliga verið meir nágrein(ur).",
        "welcome": "Vælkomin, ",
        "Welcome_2": "! Lat okkum leggja vikuna tína til rættis! 🗓️✨",
        "introduce_name": "Vinarliga skriva navnið títt: ",
        "occupied_day": "Tú hevur longu ein aktivitet {day} í {place}. Vilt tú broyta hann? (j/n): "
    },
    "mk": {
        "name": ["Македонски","Macedonian","MK","mk","makedonski","македонски","MKD","mkd","Мак","мак"],
        "days": ["Понеделник","Вторник","Среда","Четврток","Петок","Сабота","Недела"],
        "header_week": "\nТвојот неделен распоред ",
        "line_week": "🔴{day} → {act} во {place}",
        "ask_day": "\nВнеси ден за преглед/измени (или 'крај' за завршување): ",
        "show_day": "Во {day} ќе правиш {act} во {place}.",
        "ask_change": "Дали сакаш да ја смениш активноста за {day}? (д/н): ",
        "ask_new_act": "Внеси нова активност за {day}: ",
        "ask_new_place": "Внеси ново место за {day}: ",
        "updated": "✅ {day} ажуриран: сега {act} во {place}.\n",
        "no_change": "Нема промени за {day}.",
        "invalid_day": "Невалиден ден. Внеси важечки ден во неделата.",
        "confirm_exit": "Дали си сигурен/сигурна дека сакаш да излезеш? (д/н): ",
        "yes": {"д","да"},
        "chose_day": "Кој ден сакаш да го ажурираш? ",
        "Activity_question": "Која активност ќе ја правиш во {day}?",
        "location_question": "Каде ќе ја правиш активноста во {day}?",
        "no_plan": "Немаш планирано активности за оваа недела.",
        "prompt_add": "Дали сакаш да ги додадеш сега? (д/н): ",
        "nothing_planned": "Ништо уште не е планирано.",
        "another_activity": "Дали сакаш да внесеш уште една активност? (д/н): ",
        "next_time": "Добро, можеби следниот пат ",
        "Ambiguous_day": "Денот што го внесовте е нејасен. Ве молиме бидете попрецизни.",
        "welcome": "Добредојде, ",
        "Welcome_2": "! Ајде да ја испланираме твојата недела! 🗓️✨",
        "introduce_name": "Ве молиме внесете го вашето име: ",
        "occupied_day": "Веќе имаш планирано активност за {day} во {place}. Дали сакаш да ја смениш? (д/н): "
    },

}

def choose_lang():
    print(
        "🌍 Choose your language / Elige idioma / Odaberi jezik / Izvēlies valodu:\n"
        "1. 🇬🇧 English\n"
        "2. 🇪🇸 Español\n"
        "3. 🇭🇷 Hrvatski\n"
        "4. 🇱🇻 Latviešu\n"
        "5. 🇳🇱 Nederlands\n"
        "6. 🇩🇪 Deutsch\n"
        "7. 🇫🇷 Français\n"
        "8. 🇵🇹 Português\n"
        "9. 🇹🇷 Türkçe\n"
        "10. 🇺🇦 Українська\n"
        "11. 🇦🇿 Azərbaycan\n"
        "12. 🇵🇱 Polski\n"
        "13. 🇮🇹 Italiano\n"
        "14. 🇮🇱 עברית\n"
        "15. 🇸🇪 Svenska\n"
        "16. 🇫🇮 Suomi\n"
        "17. 🇩🇰 Dansk\n"
        "18. 🇳🇴 Norsk\n"
        "19. 🇮🇸 Íslenska\n"
        "20. 🇱🇹 Lietuvių\n"
        "21. 🇪🇪 Eesti\n"
        "22. 🇷🇴 Română\n"
        "23. 🇸🇰 Slovensky\n"
        "24. 🇨🇿 Čeština\n"
        "25. 🇧🇬 Български\n"
        "26. 🇬🇷 Ελληνικά\n"
        "27. 🇦🇱 Shqip\n"
        "28. 🇸🇮 Slovenščina\n"
        "29. 🇷🇸 Српски\n"
        "30. 🇲🇹 Malti\n"
        "31. 🇫🇴 Føroyskt\n"
        "32. 🇲🇰 Македонски\n"
    
    )

    lang_codes = ["en", "es", "hr", "lv", "nl", "de", "fr", "pt", "tr", "uk", "az","pl", "it", "he", "sv", "fi", "da", "no", "is", "lt", "et", "ro", "sk", "cs", "bg", "el", "sq", "sl", "sr", "mt", "fo", "mk"]

    while True:
        choice = input("> ").strip().lower()

        # If user types a number
        if choice.isdigit() and 1 <= int(choice) <= len(lang_codes):
            lang = lang_codes[int(choice) - 1]
            print(f"\n✅ Language selected: {LANGS[lang]['name'][0]}\n")
            return lang

        # Or any matching text / code
        for code, data in LANGS.items():
            if choice in [x.lower() for x in data["name"]] or choice == code:
                print(f"\n✅ Language selected: {data['name'][0]}\n")
                return code

        print("❌ Invalid choice. Please try again.\n")



 #--- helper functions -------------------------------------------------------

def t(L, key, **kw):
    """Translate + format from the active language dict."""
    return L[key].format(**kw)

def normalize(s: str) -> str:
    s = s.strip().casefold()  # lowercase, remove surrounding spaces
    return ''.join(
        c for c in unicodedata.normalize("NFD", s)
        if unicodedata.category(c) != "Mn"  # Mn = Nonspacing_Mark (accents)
    )


def build_day_index(days):
    """Map acceptable tokens to their day index (supports full name + 3-letter abbr)."""
    idx = {}
    for i, d in enumerate(days):
        tok = normalize(d)
        idx[tok] = i
        idx[tok[:3]] = i  # e.g., Mon / Lun / Pon / Pır / Пон
    return idx

def ask_for_name(L):
    nombre = input(t(L, "introduce_name")).strip().capitalize()
    print("\n")
    print(f"{t(L,'welcome')}{nombre}{t(L, 'Welcome_2')}")
    print("\n")
    return nombre
    

def ask_for_day(L, days):
    """Return index 0..6 for a chosen day."""
    norm_days = [normalize(d) for d in days]

    while True:
        raw = input(t(L, "chose_day")).strip()

        # numbers 1–7
        if raw.isdigit() and 1 <= int(raw) <= 7:
            return int(raw) - 1

        s = normalize(raw)

        # short 1-character inputs are too vague – force at least 2 chars
        if len(s) < 2:
            print("❌ " + L["invalid_day"])
            continue

        # exact match first
        for i, nd in enumerate(norm_days):
            if s == nd:
                return i

        # prefix matches
        candidates = [i for i, nd in enumerate(norm_days) if nd.startswith(s)]

        if len(candidates) == 0:
            print("❌ " + L["invalid_day"])
            continue

        if len(candidates) == 1:
            return candidates[0]

        # ambiguous – show menu (like we discussed)
        # --- ambiguous case ---
        print(t(L, "Ambiguous_day"))

        # display options
        for i, idx in enumerate(candidates, start=1):
            print(f"{i}) {days[idx]}")

        while True:
            choice = input("> ").strip()

        # 1) Accept a number (1..n)
            if choice.isdigit():
                num = int(choice)
                if 1 <= num <= len(candidates):
                    return candidates[num - 1]   # return index
                else:
                    print("❌ " + t(L, "invalid_day"))
                    continue

        # 2) Accept an exact full day name
            choice_norm = normalize(choice)
            for idx in candidates:
                if normalize(days[idx]) == choice_norm:
                    return idx

        # 3) Otherwise keep asking
            print("❌ " + t(L, "invalid_day"))



# --- main flow -------------------------------------------------------------
def main():
    # 1) Choose language once
    lang = choose_lang()
    L = LANGS[lang]
    days = L["days"]
    # canonical yes set (use everywhere)
    yes_set = {x.casefold() for x in L["yes"]}

    # 2) Empty “database”
    activity = [""] * 7
    place    = [""] * 7

    # 2.5) Scan user's name
    nombre = ask_for_name(L)

    # 3) Tell user there’s nothing planned
    print(t(L, "no_plan"))

    # 4) Ask if they want to start adding activities
    if normalize(input(t(L, "prompt_add"))) not in L["yes"]:
        print(f"\n{L['next_time']} {nombre}!")
        return

    # 5) LOOP: each time we pick a day, then ask activity + place
    while True:
        # Ask which day (this uses your ask_for_day function)
        day_idx  = ask_for_day(L, days)   # 0..6
        day_name = days[day_idx]
# 🔴 NEW PART: warn if day already has an activity
        if activity[day_idx] or place[day_idx]:
            warning = t(
                L,
                "occupied_day",
                day=day_name,
                place=place[day_idx] or L["nothing_planned"]
            )
            answer = input(warning).strip()

            # if user does NOT want to change it
            if normalize(answer) not in yes_set:
                print(t(L, "no_change", day=day_name))

                # ask if they want to add another activity instead
                another = input(t(L, "another_activity")).strip()
                if normalize(another) in yes_set:
                    continue  # go back to choose another day
                else:
                    break     # exit main loop

        # Ask activity + place for THAT day
        a = ""
        p = ""
        while not a:
            a = input(t(L, "Activity_question", day=day_name)).strip()
        while not p:
            p = input(t(L, "location_question", day=day_name)).strip()

        activity[day_idx] = a
        place[day_idx]    = p

        # Show current schedule
        print(L["header_week"])
        for d, act, pl in zip(days, activity, place):
            if act:
                print(t(L, "line_week", day=d, act=act, place=pl))
            else:
                print(f"✅{d} → {L['nothing_planned']}")

        # Ask if user wants another activity
        another = input(t(L, "another_activity")).strip()

        if normalize(another) not in yes_set:
            
            break   # leave the while True loop

    # 6) Final schedule
    print("\n" + L["header_week"] + nombre + "!\n")
    for d, act, pl in zip(days, activity, place):
        if act:
            print(t(L, "line_week", day=d, act=act, place=pl,))
        else:
            print(f"⬛{d} → {L['nothing_planned']}")

# run
if __name__ == "__main__":
    main()


🌍 Supported Languages

English, Spanish, Croatian, Latvian, Dutch, German, French, Portuguese, Turkish, Ukrainian, Azerbaijani, Polish, Italian, Hebrew, Swedish, Finnish, Danish, Norwegian, Icelandic, Lithuanian, Estonian, Romanian, Slovak, Czech, Bulgarian, Greek, Albanian, Slovenian, Serbian, Maltese, Faroese, Macedonian.

🧑‍💻 Author

Created by Petar Hrgetić Vitols. 
https://www.linkedin.com/in/petarhrgetic/
