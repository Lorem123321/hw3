# Домашнее задание:
Дополнить файл с инструкцией по работе с git информацией о работе с удаленными репозиториями и направить pull request в репозиторий преподавателя (сюда).
В системе (на сайте gb.ru) подгрузить скриншот отправленного pull request.

# Совместная работа и обновление проектов
Не так уж много команд в Git требуют сетевого подключения для своей работы, практически все команды оперируют с локальной копией проекта. Когда вы готовы поделиться своими наработками, всего несколько команд помогут вам работать с удалёнными репозиториями.

    git fetch
Команда git fetch связывается с удалённым репозиторием и забирает из него все изменения, которых у вас пока нет и сохраняет их локально.

Мы познакомились с ней в разделе Получение изменений из удалённого репозитория — Fetch и Pull главы 2 и продолжили знакомство в разделе Удалённые ветки главы 3.

Мы использовали эту команду в нескольких примерах из раздела Участие в проекте.

Мы использовали её для скачивания запросов на слияние (pull request) из других репозиториев в разделе Ссылки на запрос слияния главы 6, также мы рассмотрели использование git fetch для работы с упакованными репозиториями в разделе Создание пакетов главы 7.

Мы рассмотрели тонкую настройку git fetch в главе и Спецификации ссылок.

    git pull
Команда git pull работает как комбинация команд git fetch и git merge, т. е. Git вначале забирает изменения из указанного удалённого репозитория, а затем пытается слить их с текущей веткой.

Мы познакомились с ней в разделе Получение изменений из удалённого репозитория — Fetch и Pull главы 2 и показали как узнать, какие изменения будут приняты в случае применения в разделе Просмотр удаленного репозитория главы 2.

Мы также увидели как она может оказаться полезной для разрешения сложностей при перемещении веток в разделе Меняя базу, меняй основание главы 3.

Мы показали как можно использовать только URL удалённого репозитория без сохранения его в списке удалённых репозиториев в разделе Извлечение удалённых веток главы 5.

И наконец мы показали как проверять криптографические подписи полученных коммитов, используя опцию --verify-signatures в разделе Подпись коммитов главы 7.

    git push
Команда git push используется для установления связи с удалённым репозиторием, вычисления локальных изменений отсутствующих в нём, и собственно их передачи в вышеупомянутый репозиторий. Этой команде нужно право на запись в репозиторий, поэтому она использует аутентификацию.

Мы познакомились с этой командой в разделе Отправка изменений в удаленный репозиторий (Push) главы 2. Там мы рассмотрели основы обновления веток в удалённом репозитории. В разделе Отправка изменений главы 3 мы подробнее познакомились с этой командой, а в разделе Отслеживание веток главы 3 мы узнали как настроить отслеживание веток для автоматической передачи на удалённый репозиторий. В разделе Удаление веток на удалённом сервере главы 3 мы использовали флаг --delete для удаления веток на сервере, используя git push.

На протяжении раздела Участие в проекте мы показали несколько примеров использования git push для совместной работы в нескольких удалённых репозиториях одновременно.

В разделе Публикация изменений подмодуля главы 7 мы использовали опцию --recurse-submodules чтобы удостовериться, что все подмодули будут опубликованы перед отправкой на проекта на сервер, что может быть реально полезным при работе с репозиториями, содержащими подмодули.

В разделе Прочие хуки на стороне клиента главы 8 мы поговорили о триггере pre-push, который может быть выполнен перед отправкой данных, чтобы проверить возможность этой отправки.

Наконец, в разделе Спецификации ссылок для отправки данных на сервер главы 10 мы рассмотрели передачу данных с полным указанием передаваемых ссылок, вместо использования распространённых сокращений. Это может быть полезным если вы хотите очень точно указать, какими изменениями хотите поделиться.

    git remote
Команда git remote служит для управления списком удалённых репозиториев. Она позволяет сохранять длинные URL репозиториев в виде понятных коротких строк, например «origin», так что вам не придётся забивать голову всякой ерундой и набирать её каждый раз для связи с сервером. Вы можете использовать несколько удалённых репозиториев для работы и git remote поможет добавлять, изменять и удалять их.

Эта команда детально рассмотрена в разделе Работа с удалёнными репозиториями главы 2, включая вывод списка удалённых репозиториев, добавление новых, удаление или переименование существующих.

Она используется практически в каждой главе, но всегда в одном и том же виде: git remote add <имя> <URL>.

    git archive
Команда git archive используется для упаковки в архив указанных коммитов или всего репозитория.

Мы использовали git archive для создания тарбола (tar.gz файла) всего проекта для передачи по сети в разделе Подготовка релиза главы 5.

    git submodule
Команда git submodule используется для управления вложенными репозиториями. Например, это могут быть библиотеки или другие, используемые не только в этом проекте ресурсы. У команды submodule есть несколько под-команд — add, update, sync и др. — для управления такими репозиториями.