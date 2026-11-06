# Custom Subscription Page

<p align="center">
  <img src="logo.png" alt="Custom subscription page logo" width="180">
</p>

<p align="center">
  A standalone, responsive subscription page template for 3x-ui.
</p>

<p align="center">
  <a href="#english">English</a> · <a href="#русский">Русский</a>
</p>

---

## English

An alternative public page for 3x-ui subscribers. It brings subscription status, traffic usage, import links, apps, and individual configuration links together in one compact page.

### Highlights

| Area | What it provides |
| --- | --- |
| **Subscription identity** | Configured subscription title, subscription ID, client email, and custom logo |
| **Usage overview** | Circular usage indicator, used/remaining traffic, and unlimited-plan display |
| **Appearance** | Light and dark themes, saved in the browser; animated Vanta globe background |
| **Languages** | English and Russian interface, with the selected language saved in the browser |
| **Subscription link** | JSON subscription link with copy, raw JSON open, and QR code |
| **App setup** | Android/iOS selector and one-tap Happ and Incy import links |
| **Configurations** | Individual links with protocol and transport/security labels, copy-one/copy-all, and QR dialog |
| **Panel information** | Optional announcement, automatic update interval, and support link |
| **Small screens** | Responsive card, tabs, and app list for mobile screens |

### Compared with the built-in subscription page

The built-in page is a React frontend shipped as part of 3x-ui. This project is a separate, self-contained HTML template intended to be installed through the panel's **Sub Theme Directory** setting. It has its own visual identity, logo, animated globe background, and independent English/Russian language selector. It keeps the core subscriber tasks—checking usage, importing a subscription, and copying or scanning configuration links—on a single responsive page.

The template uses the same subscription data and links provided by 3x-ui. It does not replace the panel or subscription server, and it does not generate or change client configurations.

### Install in 3x-ui

1. Copy this folder to the server running 3x-ui. For example:

   ```text
   /etc/3x-ui/custom_sub_page/
   ```

2. In the panel, open **Settings → Subscription → Information**.
3. Set **Sub Theme Directory** to the absolute path of this folder, for example:

   ```text
   /etc/3x-ui/custom_sub_page/
   ```

4. Save the settings and open a subscriber's subscription page to see the template.

The directory must contain `index.html`. Keep `logo.png` beside it; the template refers to the logo using a relative path. The page uses Go's `html/template` variables supplied by 3x-ui, such as `.subTitle`, `.subUrl`, `.subJsonUrl`, `.links`, `.emails`, `.announce`, and `.subSupportUrl`.

> [!NOTE]
> The page expects the subscription fields used by the 3x-ui custom-template renderer. If you host `index.html` as a regular static HTML page, the Go template expressions will not be rendered.

### Files

| File | Purpose |
| --- | --- |
| `index.html` | Complete HTML template, styles, translations, and page behavior |
| `logo.png` | Page branding shown in the header |
| `LICENSE` | License for this custom page |
| `QRCODE-LICENSE.txt` | Third-party QRCode library license notice |
| `THREE-LICENSE.txt` | Three.js license notice |
| `VANTA-LICENSE.txt` | Vanta license notice |

### Privacy and dependencies

- Theme and language choices are stored in browser `localStorage` on the visitor's device.
- Subscription links and QR codes contain access credentials. Treat them as private; anyone who obtains a link may be able to use the subscription.
- The QRCode, Three.js, and Vanta code is bundled in `index.html`; the page does not need a build step or separate JavaScript files.

### License

This custom page is provided under the [MIT License](LICENSE). Third-party notices are included in the `*-LICENSE.txt` files.

---

## Русский

Самостоятельный адаптивный шаблон публичной страницы подписки для пользователей 3x-ui. На одной странице собраны состояние подписки, расход трафика, ссылки для импорта, приложения и конфигурации.

### Возможности

| Раздел | Что доступно |
| --- | --- |
| **Данные подписки** | Настроенное название, ID подписки, email клиента и собственный логотип |
| **Расход трафика** | Круговой индикатор, использованный и оставшийся трафик, отображение безлимитного тарифа |
| **Оформление** | Светлая и тёмная темы; выбор сохраняется в браузере. Анимированный фон Vanta Globe |
| **Языки** | Интерфейс на английском и русском; выбранный язык сохраняется в браузере |
| **Ссылка подписки** | Ссылка JSON с копированием, открытием исходного JSON и QR-кодом |
| **Приложения** | Выбор Android/iOS и быстрый импорт в Happ и Incy |
| **Конфигурации** | Ссылки с обозначениями протокола, транспорта и защиты; копирование одной или всех ссылок и QR-диалог |
| **Информация панели** | Необязательное объявление, интервал автообновления и ссылка поддержки |
| **Мобильная версия** | Адаптивная карточка, вкладки и список приложений для небольших экранов |

### Отличия от встроенной страницы подписки

Встроенная страница — это React-интерфейс, который поставляется вместе с 3x-ui. Этот проект — отдельный HTML-шаблон, который подключается через настройку панели **Sub Theme Directory**. У него собственный логотип и оформление, анимированный фон Vanta Globe и независимый переключатель английского и русского языков. Основные действия пользователя — проверить трафик, импортировать подписку, скопировать или отсканировать ссылку конфигурации — собраны на одной адаптивной странице.

Шаблон использует данные и ссылки подписки, которые предоставляет 3x-ui. Он не заменяет панель или сервер подписок и не создаёт и не изменяет конфигурации клиентов.

### Установка в 3x-ui

1. Скопируйте эту папку на сервер с 3x-ui. Например:

   ```text
   /etc/3x-ui/custom_sub_page/
   ```

2. В панели откройте **Settings → Subscription → Information**.
3. Укажите абсолютный путь к папке в поле **Sub Theme Directory**, например:

   ```text
   /etc/3x-ui/custom_sub_page/
   ```

4. Сохраните настройки и откройте страницу подписки клиента.

В папке должен находиться файл `index.html`. Не перемещайте `logo.png`: шаблон ищет его по относительному пути рядом с HTML-файлом. В `index.html` используются переменные Go-шаблонов, которые передаёт 3x-ui, например `.subTitle`, `.subUrl`, `.subJsonUrl`, `.links`, `.emails`, `.announce` и `.subSupportUrl`.

> [!NOTE]
> Страница рассчитана на поля, которые передаёт обработчик пользовательских шаблонов 3x-ui. Если открыть `index.html` как обычный статический файл, выражения Go-шаблонов не будут обработаны.

### Файлы

| Файл | Назначение |
| --- | --- |
| `index.html` | HTML-шаблон, стили, переводы и логика страницы |
| `logo.png` | Логотип в заголовке страницы |
| `LICENSE` | Лицензия этого шаблона |
| `QRCODE-LICENSE.txt` | Уведомление о лицензии сторонней QRCode-библиотеки |
| `THREE-LICENSE.txt` | Уведомление о лицензии Three.js |
| `VANTA-LICENSE.txt` | Уведомление о лицензии Vanta |

### Конфиденциальность и зависимости

- Выбор темы и языка сохраняется в `localStorage` браузера пользователя.
- Ссылки подписки и QR-коды содержат данные доступа. Храните их в секрете: любой обладатель ссылки может получить доступ к подписке.
- Код QRCode, Three.js и Vanta включён в `index.html`; сборка и отдельные файлы JavaScript не требуются.

### Лицензия

Этот шаблон распространяется по [лицензии MIT](LICENSE). Уведомления о сторонних компонентах находятся в файлах `*-LICENSE.txt`.
