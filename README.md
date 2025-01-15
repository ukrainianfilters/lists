# Ukrainian Filters

Ukrainian Filters (Українські фільтри) — це веб-фільтри, які автоматично видаляють небажаний контент з українських сайтів, включно з рекламою, дратівливими елементами, трекерами та шкідливими скриптами.

Ця колекція фільтрів створена та підтримується з 2023 року. Першим було створено [Ukrainian Security Filter](https://github.com/braveinnovators/ukrainian-security-filter) (Український безпековий фільтр), робота над рештою фільтрів розпочалася у [лютому](https://github.com/serhiyguryev/ukrainian-filters) 2024 року.

Правила фільтрації створюються індивідуально для кожного веб-ресурсу, що відноситься до українського сегменту Інтернет. При цьому, ми не женемося за кількістю, але водночас дбаємо про те, щоб наші фільтри працювали максимально ефективно на популярних сайтах, особливо новинних.

Дізнатися більше про проєкт, його особливості та переваги можна [тут](https://mastodon.online/@myroslavandriychuk/112880678611736243).

## Фільтри

###  Ukrainian Filters (uBlock Origin Combined List)

Список фільтрів (`Ads` + `Privacy` + `Security`), призначений для видалення реклами з українських сайтів, блокування трекерів, шкідливих скриптів та небезпечних веб-ресурсів (фішинг, онлайн-шахрайство, дропшопінг, шкідливе програмне забезпечення тощо). Розділ `SECURITY FILTERS` містить правила фільтрації, що імпортовані з [Українського безпекового фільтра](https://github.com/braveinnovators/ukrainian-security-filter).

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/combined/uBO/uBO.txt
```

### Ukrainian Annoyance Filter

Фільтр блокує дратівливі елементи (повідомлення про файли cookie, спливаючі вікна, банери тощо).

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/annoyances/annoyances.txt
```

## Сумісність з розширеннями та браузерами

### uBlock Origin

Фільтри `Ukrainian Ad Filter`, `Ukrainian Annoyance Filter` та `Ukrainian Privacy Filter` створені з використанням синтаксису фільтрації розширення [uBlock Origin](https://ublockorigin.com/) (uBO).

Користувачам персональних комп'ютерів та мобільних пристроїв на базі ОС Android ми рекомендуємо використовувати розширення [uBlock Origin](https://ublockorigin.com/) разом з браузером [Firefox](https://www.mozilla.org/firefox/).

### Adblock, Adblock Plus, AdGuard

Починаючи з версії 0.5, розробники розширення **Adblock** [вирішили прибрати](https://web.archive.org/web/20111206122411/http://adblockplus.org/en/faq_features#siteblock) функцію блокування веб-сторінок (strict blocking). Це означає, що ані **Adblock**, ані **Adblock Plus** не можуть блокувати доступ до веб-ресурсів на рівні доменного ім'я. Розширення **AdGuard** так само має проблеми з обробкою правил фільтрації ([Issue #2760](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2760)), навіть тих, що прописані в документації цього розширення. Відповідно, ці розширення не є сумісними з нашими фільтрами.

### Google Chrome

У 2025 році розширення, які не підтримують [Manifest V3](https://blog.chromium.org/2024/05/manifest-v2-phase-out-begins.html), більше не функціонуватимуть у Google Chrome. Це означає, що жоден блокувальник реклами [не зможе повноцінно працювати](https://www.theverge.com/2024/5/30/24168057/google-chrome-extension-change-manifest-v3-ad-blockers) з цим браузером. Альтернативою може стати або Firefox, або браузери на основі [Chromium](https://uk.wikipedia.org/wiki/Chromium), які продовжать підтримувати Manifest V2 та сторонні блокувальники реклами, включно з uBlock Origin.

## Як імпортувати фільтри

### uBlock Origin

[uBlock Origin](https://ublockorigin.com/) (uBO) — платформонезалежне розширення фільтрації контенту для Firefox та інших браузерів, що засновані на [Chromium](https://uk.wikipedia.org/wiki/Chromium) (зокрема, Google Chrome, Opera, Microsoft Edge, Brave). Переваги цього розширення: вільне програмне забезпечення з відкритим кодом, ефективне використання процесора та пам'яті, об'єктивно найкращий вибір з точки зору функціональних можливостей та гнучкості налаштувань.

<details>
<summary>Windows, macOS, Linux та Android</summary>

1. Відкрити меню `Preferences` розширення uBlock Origin, клацнути мишею на вкладку `Filter lists` і прокрутити до розділу `Custom`
2. Клацнути мишею на `Import...` і у поле вводу вставити скопійовані адреси необхідних фільтрів, зберігши зміни.

Додаткова інструкція доступна за адресою: [https://github.com/gorhill/uBlock/wiki/Filter-lists-from-around-the-web](https://github.com/gorhill/uBlock/wiki/Filter-lists-from-around-the-web)
</details>

### uBlock Origin Lite

Наші фільтри вже вбудовані у [uBlock Origin Lite](https://github.com/uBlockOrigin/uBOL-home) (вкладка `Filter lists`, розділ `Regions, languages`).

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
> Якщо програмне забезпечення фільтрації контенту підтримує функцію автооновлення імпортованих списків, списки фільтрів будуть оновлюватися автоматично кожні 2 дні (у разі необхідності списки також можна оновлювати вручну). Виключенням є розширення uBlock Origin Lite, оскільки всі фільтри (включно з оновленнями) додаються до нього його розробниками вручну. Після цього створюється нова версія розширення, яка щоразу проходить перевірку в Chrome Web Store. Цей процес може тривати від 5 днів і більше.

## Зворотний зв'язок

Якщо ви виявили сайти, для яких відсутні правила фільтрації (ви бачите рекламу, дратівливі елементи, трекери), або на яких наші правила фільтрації працюють некоректно — [повідомте](https://github.com/ukrainianfilters/lists/issues/new/choose) нам про це.

## Співпраця

Якщо ви створили правила фільтрації та бажаєте, щоб вони були додані до списків з відповідними фільтрами, будь ласка, ознайомтеся зі [стандартами упорядкування](https://github.com/ukrainianfilters/lists/blob/main/CONTRIBUTING.md) списків та порядком роботи з пісочницею проєкту. Щоб додати правила фільтрації до розділу `SECURITY FILTERS`, необхідно перейти до репозиторію [Ukrainian Security Filter](https://github.com/braveinnovators/ukrainian-security-filter) (це окремий проєкт, ми лише імпортуємо звідти правила фільтрації).

## Підтримати проєкт

Ви можете підтримати подальший розвиток цього проєкту, обравши зручний для вас спосіб перерахування донатів:

* **Bitcoin (BTC)**: bc1q6qtnwc2pdktvl48mr9hf0qmhaxfm7xseftp78a
* **Ether (ETH)**: 0x185e4FB1f662223B011dedbBd42A444891b094f5

## Ліцензія

На Ukrainian Filters (Українські фільтри) поширюються умови ліцензії [GNU General Public License v3.0](https://github.com/ukrainianfilters/lists/blob/main/LICENSE)
