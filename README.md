# Ukrainian Filters

Ukrainian Filters (Українські фільтри) — це веб-фільтри, які автоматично видаляють небажаний контент з українських сайтів, включно з рекламою, дратівливими елементами, трекерами та шкідливими скриптами.

Ця колекція фільтрів створена та підтримується з 2023 року. Першим було створено [Ukrainian Security Filter](https://github.com/braveinnovators/ukrainian-security-filter) (Український безпековий фільтр), робота над публічним розвитком решти фільтрів розпочалася у 2024 році ([початковий реліз](https://github.com/serhiyguryev/ukrainian-filters) від 27.02.2024).

Правила фільтрації створюються індивідуально для кожного веб-ресурсу, що відноситься до українського сегменту Інтернет. При цьому, ми не женемося за кількістю, але водночас дбаємо про те, щоб наші фільтри працювали максимально ефективно на популярних сайтах, особливо новинних.

Дізнатися більше про проєкт, його особливості та переваги можна [тут](https://mastodon.online/@myroslavandriychuk/112880678611736243).

## Фільтри

### Ukrainian Ad Filter

Фільтр видаляє рекламу з українських сайтів.

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/ads/ads.txt
```

### Ukrainian Annoyance Filter

Фільтр блокує дратівливі елементи на українських та деяких популярних іноземних сайтах (повідомлення про файли cookie, спливаючі вікна, банери тощо).

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/annoyances/annoyances.txt
```

### Ukrainian Privacy Filter

Фільтр блокує трекери та шкідливі скрипти, зменшує можливість третіх сторін збирати дані про вашу поведінку в Інтернеті. Цей фільтр видаляє скрипти та html-елементи систем коментування (Disqus, Facebook Comments Plugin тощо) на новинних та деяких інших сайтах. Якщо для вас це неприйнятно, не використовуйте цей фільтр.

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/privacy/privacy.txt
```

### Ukrainian Security Filter (Український безпековий фільтр)

Це [фільтр шкідливих веб-ресурсів](https://github.com/braveinnovators/ukrainian-security-filter) (фішинг, онлайн-шахрайство, шкідливе програмне забезпечення тощо), що орієнтовані на громадян України.

```
https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/lists/adblock.txt
```

## Сумісність з браузерами та розширеннями

Фільтри `Ukrainian Ad Filter`, `Ukrainian Annoyance Filter` та `Ukrainian Privacy Filter` створені з використанням специфічного синтаксису фільтрації розширення [uBlock Origin](https://github.com/gorhill/uBlock) (uBO), при цьому, більшість правил фільтрації все ж сумісні як з іншими популярними сторонніми розширеннями, так і з браузерами з вбудованими модулями фільтрації контенту.

Однак, з точки зору ефективності, приватності та безпеки, найбільш оптимальним для користувачів персональних комп'ютерів буде використання розширення [uBlock Origin](https://ublockorigin.com/) разом з браузером [Firefox](https://www.mozilla.org/firefox/) (якщо ви не плануєте змінювати браузер, все одно розгляньте можливість встановлення саме розширення uBlock Origin).

Альтернативою для мобільних пристроїв, що працюють на базі ОС Android та iOS, може стати використання браузера [Brave](https://brave.com/), який має власний модуль фільтрації контенту та підтримує [синтаксис фільтрації](https://support.brave.com/hc/en-us/articles/6449369961741-How-do-I-manage-Ad-Block-filters-in-Brave) розширення uBlock Origin.

> [!WARNING]
> Починаючи з версії 0.5, розробники розширення **Adblock** [вирішили прибрати](https://web.archive.org/web/20111206122411/http://adblockplus.org/en/faq_features#siteblock) функцію блокування веб-сторінок (strict blocking). Це означає, що ані **Adblock**, ані **Adblock Plus** не можуть блокувати доступ до шкідливих веб-ресурсів на рівні доменного ім'я. Розширення **AdGuard** так само має проблеми з обробкою правил фільтрації ([Issue #2760](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2760)), навіть тих, що прямо прописані в документації цього розширення. Відповідно, ці розширення не можуть забезпечити обробку правил фільтрації, що повністю відповідають вимогам сучасних версій синтаксису Adblock, тому вони не є сумісними з фільтром `Ukrainian Security Filter (Український безпековий фільтр)`.

## Як імпортувати фільтри

### uBlock Origin

<details>
<summary>Windows, macOS, Linux та Android</summary>

1. Відкрити меню `Preferences` розширення uBlock Origin, клацнути мишею на вкладку `Filter lists` і прокрутити до розділу `Custom`
2. Клацнути мишею на `Import...` і у поле вводу вставити скопійовані адреси необхідних фільтрів, зберігши зміни.

Додаткова інструкція доступна за адресою: [https://github.com/gorhill/uBlock/wiki/Filter-lists-from-around-the-web](https://github.com/gorhill/uBlock/wiki/Filter-lists-from-around-the-web)
</details>

### Brave

<details>
<summary>Windows, macOS та Linux</summary>

1. У меню `Settings` відкрити вкладку `Shields` й змінити налаштування `Trackers & ads blocking` на `Aggressive`
2. У вкладці `Shields` відкрити розділ `Content filtering` і у розділі `Add custom filter lists` у поле вводу вставити скопійовані адреси необхідних фільтрів.
</details>

<details>
<summary>Android та iOS</summary>

1. У меню `Settings` відкрити розділ меню `Brave Shields & privacy` й змінити налаштування `Block trackers & ads` на `Aggressive`
2. У розділі меню `Brave Shields & privacy` відкрити `Content filtering`, далі `Add custom filter list` і у поле вводу вставити скопійовані адреси необхідних фільтрів, зберігши зміни шляхом натискання на кнопку `Add`.
</details>

## Співпраця

Якщо ви створили правила фільтрації та бажаєте, щоб вони були додані до файлів (списків) з відповідними фільтрами, вам необхідно:

1. Створити [fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/about-forks) репозиторію [пісочниці](https://github.com/ukrainianfilters/sandbox) та додати правила до файлів (списків) з відповідними фільтрами: `ads.txt`, `annoyances.txt` або `privacy.txt`, що містяться в окремих директоріях
2. Створити [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) (після проходження тестування, ваші правила будуть додані безпосередньо мейнтейнерами проєкту із зазначенням авторства)

## Підтримати проєкт

Ви можете підтримати подальший розвиток цього проєкту, обравши зручний для вас спосіб перерахування донатів:

* **Bitcoin (BTC)**: bc1q6qtnwc2pdktvl48mr9hf0qmhaxfm7xseftp78a
* **Ether (ETH)**: 0x185e4FB1f662223B011dedbBd42A444891b094f5

## Ліцензія

На Ukrainian Filters (Українські фільтри) поширюються умови ліцензії [GNU General Public License v3.0](https://github.com/ukrainianfilters/lists/blob/main/LICENSE)
