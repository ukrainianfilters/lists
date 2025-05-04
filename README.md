# Ukrainian Filters

Ukrainian Filters (Українські фільтри) — це вебфільтри, які автоматично видаляють небажаний контент з українських сайтів, включно з рекламою, дратівливими елементами, відстежувачами та шкідливими скриптами.

Ця колекція фільтрів була створена та підтримується з 2023 року. Спочатку було створено [Ukrainian Security Filter](https://github.com/braveinnovators/ukrainian-security-filter) (Український безпековий фільтр), робота над рештою фільтрів розпочалася в [лютому 2024 року](https://github.com/serhiyguryev/ukrainian-filters).

Правила фільтрації створюються індивідуально для кожного вебресурсу, що належить до української частини інтернету. Водночас, ми не женемося за кількістю, проте дбаємо про те, щоби наші фільтри працювали максимально ефективно на популярних сайтах, особливо новинних.

Дізнатися більше про проєкт, його особливості та переваги можна [тут](https://mastodon.online/@myroslavandriychuk/112880678611736243).

## Фільтри

### 🛡️ Ukrainian Filters (uBlock Origin Combined List)

Об'єднаний список фільтрів для [uBlock Origin](https://ublockorigin.com/) (Ads + Privacy + Security), призначений для видалення реклами, блокування відстежувачів, шкідливих скриптів та небезпечних вебресурсів (фішинг, онлайн-шахрайство, дропшопінг, шкідливе програмне забезпечення тощо). Розділ `SECURITY FILTERS` містить правила фільтрації, імпортовані з [Українського безпекового фільтра](https://github.com/braveinnovators/ukrainian-security-filter).

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/combined/uBO/uBO.txt
```

### 🚫 Ukrainian Ad Filter

Фільтр для видалення реклами на українських вебсайтах.

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/ads/ads.txt
```

### 🔒 Ukrainian Privacy Filter
Фільтр для блокування відстежувачів та шкідливих скриптів, зменшуючи можливість третіх сторін збирати дані про вашу поведінку в інтернеті

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/privacy/privacy.txt
```

### 🍪 Ukrainian Annoyance Filter

Фільтр для блокування дратівливих елементів (повідомлень про файли cookie, спливні вікна та банери тощо).

```
https://raw.githubusercontent.com/ukrainianfilters/lists/main/annoyances/annoyances.txt
```

### 🚨 Ukrainian Security Filter

Фільтр для блокування шкідливих вебресурсів (фішинг, онлайн-шахрайство, дропшопінг, шкідливе програмне забезпечення тощо). Докладніше [тут](https://github.com/braveinnovators/ukrainian-security-filter).

## Сумісність із розширеннями та браузерами

Наші фільтри (`Ukrainian Ad Filter`, `Ukrainian Annoyance Filter` та `Ukrainian Privacy Filter`) було створено з використанням [синтаксису uBO](https://github.com/gorhill/uBlock/wiki/Static-filter-syntax). Рекомендуємо використовувати [uBlock Origin](https://ublockorigin.com/) із [Firefox](https://www.mozilla.org/uk/firefox/) на персональних комп'ютерах та пристроях із операційною системою Android.

| Браузер/Розширення       | Сумісність | Примітки                                                                                                                                                                                             |
| :----------------------- | :--------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **[uBlock Origin](https://ublockorigin.com/), **[uBlock Origin Lite](https://ublockorigin.com/)**** | ✅ Повна   | Фільтри `Ukrainian Ad Filter`, `Ukrainian Privacy Filter`, та `Ukrainian Security Filter` вже вбудовано в ці розширення.                                                                                                    |
| **[Brave](https://brave.com/uk/)** | ✅ Повна   | Має власний блокувальник реклами з підтримуванням синтаксису uBO.                                                                                                      |
| **[Adblock](https://getadblock.com/uk/), [Adblock Plus](https://adblockplus.org/)**| ❌ Відсутня| Не підтримують блокування вебсторінок (strict blocking) з версії 0.5.                                                                                                                                |
| **[AdGuard](https://adguard.com/uk/welcome.html)** | ❌ Відсутня| Має проблеми з обробкою правил фільтрації ([Issue #2760](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2760)). Має російське коріння.                                                                       |
| **[Google Chrome](https://www.google.com/intl/uk/chrome/)** | ⚠️ Обмежена| З 2025 року розширення без підтримування Manifest V3 (як uBO) не функціонуватимуть повноцінно. Рекомендуємо альтернативи на основі [Chromium](https://uk.wikipedia.org/wiki/Chromium) із підтримуванням Manifest V2 або [Firefox](https://www.mozilla.org/uk/firefox/).                     |

## Як імпортувати фільтри

> [!NOTE]
> Якщо програмне забезпечення для фільтрування контенту підтримує автооновлення імпортованих списків, фільтри будуть оновлюватися автоматично кожні 2 дні (у разі необхідності, списки також можна оновлювати вручну). Вийнятком є розширення `uBlock Origin Lite`, оскільки всі фільтри (включно з оновленнями) додаються до нього його розробниками вручну. Після цього створюється нова версія розширення, яка щоразу перевіряється в Chrome Web Store. Цей процес може тривати від 5 днів і більше.

### uBlock Origin

#### Увімкнення вбудованих фільтрів (Ads + Privacy + Security)

1. Відкрийте налаштування розширення
2. Перейдіть до вкладки `Filter lists` (`Списки фільтрів`)
3. Знайдіть розділ `Regions, languages` (`Регіони, мови`)
4. Оберіть наш фільтр `🇺🇦 ua: Ukrainian Filters`

#### Імпортування інших фільтрів

1. Відкрийте налаштування розширення
2. Перейдіть до вкладки `Filter lists` (`Списки фільтрів`)
3. Знайдіть розділ `Import...` (`Імпорт...`)
4. У поле вводу вставте покликання на фільтр(и)
5. Натисніть кнопку `Apply changes` (`Застосувати зміни`)

### uBlock Origin Lite

> [!NOTE]
> На жаль, підтримування інших фільтрів недоступно через обмеження Manifest V3

#### Увімкнення вбудованих фільтрів (Ads + Privacy + Security)

1. Відкрийте налаштування розширення
2. Перейдіть до вкладки `Filter lists` (`Списки фільтрів`)
3. Знайдіть розділ `Regions, languages` (`Регіони, мови`)
4. Оберіть наш фільтр `🇺🇦 ua: Ukrainian Filters`

### Brave

<details>
<summary>🖥️ Windows, macOS та Linux</summary>

1. Відкрийте налаштування браузера
2. Перейдіть до вкладки `Shields`
3. Змініть налаштування `Trackers & ads blocking` на `Aggressive`
4. Відкрийте розділ `Content filtering`
5. Натисніть `Add custom filter lists`
6. У поле вводу вставте покликання на фільтр(и)
</details>

<details>
<summary>📱 Android та iOS</summary>

1. Відкрийте налаштування браузера
2. Перейдіть до розділу `Brave Shields & privacy`
3. Змініть налаштування `Block trackers & ads` на `Aggressive`
4. Відкрийте `Content filtering`
5. Натисніть `Add custom filter list`
6. У поле вводу вставте покликання на фільтр(и)
7. Збережіть зміни, натиснувши кнопку `Add`
</details>

## Зворотний зв'язок

Якщо ви виявили вебсайти, для яких немає правил фільтрації (наприклад, на яких є реклама, дратівливі елементи, відстежувачі тощо) або на яких наші правила фільтрації не працюють належним чином — [повідомте](https://github.com/ukrainianfilters/lists/issues/new/choose) нас про це.

## Співпраця

Якщо ви створили власні правила фільтрації та бажаєте додати їх до наших списків, виконайте наступні кроки:
1. Ознайомтеся з [вимогами до правил фільтрації та порядком роботи з пісочницею
](https://github.com/ukrainianfilters/lists/blob/main/CONTRIBUTING.md)
2. Якщо ваші правила стосуються **безпеки** (для розділу `SECURITY FILTERS`), їх потрібно додавати безпосередньо до GitHub репозиторію [Ukrainian Security Filter](https://github.com/braveinnovators/ukrainian-security-filter), оскільки це окремий проєкт, звідки ми імпортуємо ці правила.

## Підтримати проєкт

Ви можете підтримати подальший розвиток цього проєкту, обравши зручний для вас спосіб пожертвування:

* **Bitcoin (BTC)**: `bc1q6qtnwc2pdktvl48mr9hf0qmhaxfm7xseftp78a`
* **Ether (ETH)**: `0x185e4FB1f662223B011dedbBd42A444891b094f5`

## Ліцензія

Ukrainian Filters (Українські фільтри) поширюються за умовами ліцензії [GNU General Public License v3.0](https://github.com/ukrainianfilters/lists/blob/main/LICENSE)
