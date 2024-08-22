# Ukrainian Filters

Ukrainian Filters (Українські фільтри) — це веб-фільтри, які автоматично видаляють небажаний контент з українських сайтів, включно з рекламою, дратівливими елементами, трекерами та шкідливими скриптами.

Ця колекція фільтрів створена та підтримується з 2023 року. Першим було створено [Ukrainian Security Filter](https://github.com/braveinnovators/ukrainian-security-filter) (Український безпековий фільтр), робота над рештою фільтрів розпочалася у [лютому](https://github.com/serhiyguryev/ukrainian-filters) 2024 року.

Правила фільтрації створюються індивідуально для кожного веб-ресурсу, що відноситься до українського сегменту Інтернет. При цьому, ми не женемося за кількістю, але водночас дбаємо про те, щоб наші фільтри працювали максимально ефективно на популярних сайтах, особливо новинних.

Дізнатися більше про проєкт, його особливості та переваги можна [тут](https://mastodon.online/@myroslavandriychuk/112880678611736243).

## Фільтри

### Ukrainian Ad Filter

Фільтр видаляє рекламу з українських сайтів.

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/ads/ads.txt
```

### Ukrainian Annoyance Filter

Фільтр блокує дратівливі елементи (повідомлення про файли cookie, спливаючі вікна, банери тощо).

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/annoyances/annoyances.txt
```

### Ukrainian Privacy Filter

Фільтр блокує трекери та шкідливі скрипти, зменшує можливість третіх сторін збирати дані про вашу поведінку в Інтернеті (зокрема, видаляються скрипти систем коментування Disqus, Facebook Comments Plugin тощо).

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/privacy/privacy.txt
```

### Ukrainian Security Filter (Український безпековий фільтр)

Це [фільтр шкідливих веб-ресурсів](https://github.com/braveinnovators/ukrainian-security-filter) (фішинг, онлайн-шахрайство, шкідливе програмне забезпечення тощо), що орієнтовані на громадян України (розробка: [@braveinnovators](https://github.com/braveinnovators))

```
https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/lists/adblock.txt
```

Додаткові формати списків: [domain-based blocklist](https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/lists/domains.txt), [hosts-based blocklist](https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/lists/hosts.txt), [dnsmasq](https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/lists/dnsmasq.txt).

## Сумісність з браузерами та розширеннями

Фільтри `Ukrainian Ad Filter`, `Ukrainian Annoyance Filter` та `Ukrainian Privacy Filter` створені з використанням синтаксису фільтрації розширення [uBlock Origin](https://ublockorigin.com/) (uBO).

Користувачам персональних комп'ютерів та мобільних пристроїв на базі ОС Android ми рекомендуємо використовувати розширення [uBlock Origin](https://ublockorigin.com/) разом з браузером [Firefox](https://www.mozilla.org/firefox/).

Якщо ви використовуєте браузер Google Chrome, майте на увазі, що, починаючи з червня 2024 року, цей браузер почне поступово деактивувати розширення, які не підтримують [Manifest V3](https://blog.chromium.org/2024/05/manifest-v2-phase-out-begins.html). Це означає, що жодне розширення-блокувальник реклами більше [не зможе повноцінно працювати](https://www.theverge.com/2024/5/30/24168057/google-chrome-extension-change-manifest-v3-ad-blockers) з цим браузером. Альтернативою може стати або Firefox, або браузери на основі [Chromium](https://uk.wikipedia.org/wiki/Chromium), які продовжать підтримувати Manifest V2 та сторонні блокувальники реклами, включно з uBlock Origin.

> [!WARNING]
> Починаючи з версії 0.5, розробники розширення **Adblock** [вирішили прибрати](https://web.archive.org/web/20111206122411/http://adblockplus.org/en/faq_features#siteblock) функцію блокування веб-сторінок (strict blocking). Це означає, що ані **Adblock**, ані **Adblock Plus** не можуть блокувати доступ до веб-ресурсів на рівні доменного ім'я. Розширення **AdGuard** так само має проблеми з обробкою правил фільтрації ([Issue #2760](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2760)), навіть тих, що прописані в документації цього розширення. Відповідно, ці розширення не є сумісними з нашими фільтрами.

## Як імпортувати фільтри

### uBlock Origin

[uBlock Origin](https://ublockorigin.com/) (uBO) — платформонезалежне розширення фільтрації контенту для Firefox та інших браузерів, що засновані на [Chromium](https://uk.wikipedia.org/wiki/Chromium) (зокрема, Google Chrome, Opera, Microsoft Edge, Brave). Переваги цього розширення: вільне програмне забезпечення з відкритим кодом, ефективне використання процесора та пам'яті, об'єктивно найкращий вибір з точки зору функціональних можливостей та гнучкості налаштувань.

<details>
<summary>Windows, macOS, Linux та Android</summary>

1. Відкрити меню `Preferences` розширення uBlock Origin, клацнути мишею на вкладку `Filter lists` і прокрутити до розділу `Custom`
2. Клацнути мишею на `Import...` і у поле вводу вставити скопійовані адреси необхідних фільтрів, зберігши зміни.

Додаткова інструкція доступна за адресою: [https://github.com/gorhill/uBlock/wiki/Filter-lists-from-around-the-web](https://github.com/gorhill/uBlock/wiki/Filter-lists-from-around-the-web)
</details>

### Brave

Браузер [Brave](https://brave.com/) заснований на [Chromium](https://uk.wikipedia.org/wiki/Chromium), має власний модуль фільтрації контенту з підтримкою [синтаксису фільтрації](https://support.brave.com/hc/en-us/articles/6449369961741-How-do-I-manage-Ad-Block-filters-in-Brave) розширення uBlock Origin. Цей браузер [продовжить підтримувати Manifest V2](https://brave.com/blog/brave-shields-manifest-v3/) та сторонні розширення-блокувальники реклами, включно з uBlock Origin.

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

> [!NOTE]
> Якщо програмне забезпечення фільтрації контенту підтримує функцію автооновлення імпортованих списків, списки фільтрів будуть оновлюватися автоматично кожні 2 дні. У разі необхідності списки також можна оновлювати вручну.

## Співпраця

Якщо ви створили правила фільтрації та бажаєте, щоб вони були додані до списків з відповідними фільтрами, будь ласка, ознайомтеся зі [стандартами упорядкування](https://github.com/ukrainianfilters/lists/blob/main/CONTRIBUTING.md) списків та порядком роботи з пісочницею проєкту.

Якщо ви виявили сайти, для яких відсутні правила фільтрації (ви бачите рекламу, дратівливі елементи), або на яких наші правила фільтрації працюють некоректно — [повідомте](https://github.com/ukrainianfilters/lists/issues/new/choose) нам про це.

## Підтримати проєкт

Ви можете підтримати подальший розвиток цього проєкту, обравши зручний для вас спосіб перерахування донатів:

* **Bitcoin (BTC)**: bc1q6qtnwc2pdktvl48mr9hf0qmhaxfm7xseftp78a
* **Ether (ETH)**: 0x185e4FB1f662223B011dedbBd42A444891b094f5

## Ліцензія

На Ukrainian Filters (Українські фільтри) поширюються умови ліцензії [GNU General Public License v3.0](https://github.com/ukrainianfilters/lists/blob/main/LICENSE)
