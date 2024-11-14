# Бот-книга

# Чтобы что?

Чтобы можно было читать книгу прямо в телеграм-боте и попрактиковаться в работе с инлайн-кнопками

# Что бот должен уметь?

Загружать страницы книги из хранилища и присылать их в чат в виде сообщений с кнопками

Сохранять страницу, на которой остановился пользователь и загружать книгу на этом месте

Переходить в начало книги

# Дополнительный функционал

Сохранять закладки - страницы книги, которые пользователь пожелал сохранить

Редактировать закладки (удалять ненужные)

# Описание взаимодействия с ботом

Пользователь отправляет команду /start боту (или стартует его, найдя в поиске)

Бот приветствует пользователя, сообщает, что пользователь может прочитать книгу прямо в чате с ботом, а также предлагает пользователю посмотреть список доступных команд, отправив команду /help

На этом этапе пользователь может совершить 5 действий:

1. Отправить в чат команду /help

2. Отправить в чат команду /beginning

3. Отправить в чат команду /continue

4. Отправить в чат команду /bookmarks

5. Отправить в чат любое другое сообщение
   
Пользователь отправляет в чат команду /help:

Бот присылает пользователю список доступных команд, сообщает о том, что можно сохранять страницы книги в закладки и желает приятного чтения


Пользователь отправляет в чат команду /beginning:

Бот отправляет в чат первую страницу книги и 3 инлайн-кнопки (назад, текущий номер страницы и вперед)


Соответственно, при взаимодействии с сообщением-книгой пользователь может:

1. Нажать на кнопку "Вперед" и тогда бот загрузит следующую страницу книги, если текущая страница не последняя. Номер текущей страницы на кнопке увеличится на 1. А если текущая страница последняя в книге, то ничего не изменится.

2. Нажать на кнопку с текущим номером страницы и тогда бот сохранит эту страницу в закладки, сообщив пользователю об этом

3. Нажать на кнопку "Назад" и тогда бот загрузит предыдущую страницу книги, если текущая страница не первая. Номер текущей страницы на кнопке уменьшится на 1. А если текущая страница первая, то ничего не изменится


Пользователь отправляет в чат команду /continue:

1. Бот отправляет в чат страницу книги, на которой пользователь остановил чтение во время последнего взаимодействия с сообщением-книгой.

2. Если пользователь еще не начинал читать книгу - бот отправляет сообщение с первой страницей книги

Пользователь отправляет в чат команду /bookmarks:

1. Если пользователь сохранял закладки ранее, то бот отправляет в чат список сохраненных закладок в виде инлайн-кнопок, а также инлайн-кнопки "Редактировать" и "Отменить"

2. Если пользователь нажимает на кнопку с закладкой - бот отправляет сообщение с книгой на той странице, куда указывала закладка

3. Если пользователь нажимает на кнопку "Отменить", то бот убирает список закладок и отправляет сообщение с предложением продолжить чтение, отправив команду /continue

4. Если пользователь нажимает на кнопку "Редактировать", то бот отправляет список сохраненных закладок в виде инлайн-кнопок с пометкой на удаление, а также инлайн-кнопку "Отменить"

5. Если пользователь нажимает на закладку с пометкой на удаление - она пропадает из списка редактируемых закладок

6. Если список содержит хотя бы одну закладку и пользователь нажимает "Отменить" - бот убирает сообщение со списком редактируемых закладок и меняет его на сообщение с предложением продолжить чтение, отправив команду /continue

7. Если в списке, после очередного удаления закладки, не остается ни одной закладки - бот сообщает пользователю, что у него нет ни одной закладки и предлагает продолжить чтение книги, отправив команду /continue


Пользователь отправляет в чат любое другое сообщение:

Бот как-то реагирует на такое сообщение, например, эхом
