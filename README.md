# Ukrainian Filters

Ukrainian Filters (Українські фільтри) — це веб-фільтри, які автоматично видаляють небажаний контент з українських сайтів, включно з рекламою, дратівливими елементами, трекерами та шкідливими скриптами.

Правила фільтрації створюються індивідуально для кожного веб-ресурсу, що належить до українського сегменту інтернету. Для нас важливіша якість, ніж кількість, тому ми дбаємо про те, щоб наші фільтри працювали максимально ефективно на популярних сайтах, особливо новинних.

Дізнатися більше про проєкт, його особливості та переваги можна [тут](https://mastodon.online/@myroslavandriychuk/112880678611736243).

## Фільтри

###  Ukrainian Filters (Combined List)

Об'єднаний список фільтрів (Реклама + Приватність + Безпека), призначений для видалення реклами з українських сайтів, блокування трекерів, шкідливих скриптів та небезпечних веб-ресурсів (фішинг, онлайн-шахрайство, дропшопінг, шкідливе програмне забезпечення тощо). Розділ `SECURITY FILTERS` містить правила фільтрації, що імпортовані з [Українського безпекового фільтра](https://github.com/braveinnovators/ukrainian-security-filter).

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/combined/combined.txt
```

### Ukrainian Annoyance Filter

Фільтр блокує дратівливі елементи (повідомлення про файли cookie, спливаючі вікна, банери тощо).

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/annoyances/annoyances.txt
```

## Сумісність з розширеннями та браузерами


| Розширення / Браузер    | Сумісність | Примітки |
| :---------------------- | :--------- | :------- |
| [Ghostery (Privacy Ad Blocker)](https://www.ghostery.com/ghostery-ad-blocker) | Повна | Рекомендуємо ознайомитися з умовами користування та відключити опцію надсилання інформації про використання розширення на етапі його активації |
| uBlock Origin, uBlock Origin Lite | Повна | 04.05.2025 Raymond Hill, головний розробник uBlock Origin, без жодних пояснень [видалив наші фільтри](https://github.com/gorhill/uBlock/commit/3cd04c3806faed1b4dc840b05a2b75a352ccefef) з розділу регіональних. Жодних критичних нарікань на якість фільтрів з боку українських користувачів не було, виявлені проблеми виправлялися оперативно. Проте, нікому з розробників uBlock Origin, схоже, це не цікаво. Нас також обурює позиція розробників щодо [політично вмотивованих блокувань](https://github.com/uBlockOrigin/uBlock-issues/issues/2692#issuecomment-2848742489) з боку московитських розробників фільтрів. Тому наша команда більше не розглядає це розширення у якості базового для наших фільтрів |
| Adblock, Adblock Plus | Відсутня | Відсутність функції блокування веб-сторінок ([strict blocking](https://web.archive.org/web/20111206122411/http://adblockplus.org/en/faq_features#siteblock)) |
| AdGuard | Відсутня | Московитське походження, проблеми з обробкою правил фільтрації ([Issue #2760](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2760)) |
| [Brave](https://brave.com/uk/) | Повна | Має власний модуль фільтрації контенту |
| [Google Chrome](https://www.google.com/intl/uk/chrome/) | Обмежена | У 2025 році розширення, які не підтримують [Manifest V3](https://blog.chromium.org/2024/05/manifest-v2-phase-out-begins.html), більше не функціонуватимуть у Google Chrome. Це означає, що жоден блокувальник реклами [не зможе повноцінно працювати](https://www.theverge.com/2024/5/30/24168057/google-chrome-extension-change-manifest-v3-ad-blockers) з цим браузером. Альтернативою може стати або Firefox, або браузери на основі [Chromium](https://uk.wikipedia.org/wiki/Chromium), які продовжать підтримувати Manifest V2 та сторонні блокувальники реклами |


## Як імпортувати фільтри

### Ghostery (Privacy Ad Blocker)

<details>
<summary>Windows, macOS та Linux</summary>

1. У розділі `Privacy protection` увімкнути опцію навпроти `Custom Filters` та перейти у цей розділ

2. Скопіювати вміст об'єднаного списку фільтрів у текстове поле:

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/combined/combined.txt
```
</details>

### Brave

Браузер [Brave](https://brave.com/) заснований на [Chromium](https://uk.wikipedia.org/wiki/Chromium), має власний модуль фільтрації контенту з підтримкою [синтаксису фільтрації](https://support.brave.com/hc/en-us/articles/6449369961741-How-do-I-manage-Ad-Block-filters-in-Brave) розширення uBlock Origin. Цей браузер [продовжить підтримувати Manifest V2](https://brave.com/blog/brave-shields-manifest-v3/) та сторонні розширення-блокувальники реклами.

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
> Якщо програмне забезпечення фільтрації контенту підтримує функцію автооновлення імпортованих списків, списки фільтрів будуть оновлюватися автоматично кожні 2 дні (у разі необхідності списки також можна оновлювати вручну).

## Зворотний зв'язок

Якщо ви виявили сайти, для яких відсутні правила фільтрації (ви бачите рекламу, дратівливі елементи, трекери), або на яких наші правила фільтрації не працюють належним чином — [повідомте](https://github.com/ukrainianfilters/lists/issues/new/choose) нас про це.

## Співпраця

Якщо ви створили правила фільтрації та бажаєте, щоб вони були додані до списків з відповідними фільтрами, будь ласка, ознайомтеся зі [стандартами упорядкування](https://github.com/ukrainianfilters/lists/blob/main/CONTRIBUTING.md) списків та порядком роботи з пісочницею проєкту. Щоб додати правила фільтрації до розділу `SECURITY FILTERS`, необхідно перейти до репозиторію [Ukrainian Security Filter](https://github.com/braveinnovators/ukrainian-security-filter) (це окремий проєкт, ми лише імпортуємо звідти правила фільтрації).

## Підтримати проєкт

Ви можете підтримати подальший розвиток цього проєкту, обравши зручний для вас спосіб пожертвування:

* **Bitcoin (BTC)**: `bc1q6qtnwc2pdktvl48mr9hf0qmhaxfm7xseftp78a`
* **Ether (ETH)**: `0x185e4FB1f662223B011dedbBd42A444891b094f5`

## Ліцензія

Ukrainian Filters (Українські фільтри) поширюються за умовами ліцензії [GNU General Public License v3.0](https://github.com/ukrainianfilters/lists/blob/main/LICENSE)
