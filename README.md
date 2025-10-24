TOC
-------------------------------------------------
- Working Environment
- Tools


Working Environment
-------------------------------------------------

**ТОЛЬКО БЕЗПЛАТНЫЕ/ОПЕНСОРС ПРИЛОЖЕНИЯ**

### Node.js vs NWM (Node Version Manager)
- [nodejs.org](https://nodejs.org){target="_blank"}
- [nvm-windows](https://github.com/coreybutler/nvm-windows){target="_blank"}

Также для дальнейшего удобства нужно установить Node Version Manager - утилита, которая позволяет активировать на компьютере различные версии node.js в зависимости от необходимости. Например нужно сделать правки на старом проекте, и там новая версия node.js не поддерживается. В таком случае можно активировать более старую версию, сделать правки и вернуться обратно на актуальную.

Чтобы установить NVM на windows переходим по этой ссылке - https://github.com/coreybutler/nvm-windows/releases и скачиваем последнюю актуальную версию:


#### NPM Global Packeges
- postcss
- autoprefixer
- webpack

```bash
npm install -g postcss autoprefixer webpack
```

> При переустановке Node.js или изменении версии ноді через NWM, вам понадобиться сделать новую установку глобальных пакетов


Актуальний список глобальных пакетов можна узнать посмотрев секцию `scripts` файла package.json темы.


```json
{
  "dependencies": {
    "foundation-sites": "~6.9.0",
    "sass": "1.93.2" // устанавливаеться локально в каждый проект, глобалььно устанавливать не нужно
  },
  "scripts": {
    "bs": "browser-sync start --config bs-config.js", // если используете -> [browser-sync]
    "watch": "sass -w assets/scss/custom.scss:assets/css/custom.css --source-map --style=compressed",
    "build:css": "sass assets/scss/:assets/css/ --style=compressed && postcss --use autoprefixer -r assets/css/*.css --no-map", // [postcss, autoprefixer]
    "build:fn-js": "webpack --config webpack.config.js" // [webpack]
  },
```


### IDE (VSC)
[https://docs.google.com/document/d/1SLnWugotTuJs8hRQoosxJvcXZVgSytzJuEgYzhbB_Uo/edit?tab=t.0#heading=h.yplh4mo28wq3](https://docs.google.com/document/d/1SLnWugotTuJs8hRQoosxJvcXZVgSytzJuEgYzhbB_Uo/edit?tab=t.0#heading=h.yplh4mo28wq3){target="_blank"}

**VSC Extensions:**
- Auto Rename Tag
- PHP Intelephense
- SFTP

#### SFTP

Для начала вам нужно сгенерировать файл sftp.json. Это можно сделать программно (см. скриншот) или вручную, создав папку .vscode с файлом sftp.json внутри. Начальные настройки SFTP можно получить здесь (необходимо сохранить копию вместе с настройками SFTP).

Файл sftp.json содержит параметры, которые помогут вам подключиться к серверу.


```json
{
    "name": "Project Name",
    "protocol": "sftp",
    "port": 2222,
    "remotePath": "/",
    "uploadOnSave": false,
    "useTempFile": false,
    "openSsh": false,
     "watcher": {
        "files": "assets/dist/**/*.{css,js}",
        "autoUpload": false,
        "autoDelete": false
    },
    "profiles": {
        "dev": {
            "host": "",
            "username": "",
            "password": ""
        }
    },
    "defaultProfile": "dev",
    "ignore": [
        ".vscode",
        ".git",
        ".DS_Store",
        "node_modules"
    ]
}
```

### Other
- [Slack](https://slack.com/downloads/windows){target="_blank"}
- [ShareX](https://getsharex.com){target="_blank"} - удобная скриншотилка
- [Chrom](https://www.google.com/intl/ru/chrome/){target="_blank"}, [Firefox](https://www.firefox.com){target="_blank"}
  - [Chrome Pixel Perfect Extension](https://chromewebstore.google.com/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=ru){target="_blank"}
  - [Firefox Pixel Perfect Extension](https://addons.mozilla.org/en-US/firefox/addon/pixel-perfect-pro/){target="_blank"}
- WEB Services
  - [clockify.me](https://clockify.me){target="_blank"}
  - [clickup.com](https://clickup.com/){target="_blank"}




Introduction to CRR
-------------------------------------------------


Advanced Custom Fields (ACF)
-------------------------------------------------


Gravity Forms
-------------------------------------------------




Coding basic steps & standards
-------------------------------------------------
### Огляд

#### How does production work?

#### Структура проекту та початок розробки / Project structure and starting development


#### Coding basic steps / Lectures


#### General WP functions

`get_header(), get_footer()` - ця функція включає `header.php`, `footer.php` на сайті  
`register_nav_menus()` - функція, за допомогою якої ви можете зареєструвати меню на своєму сайті  
`wp_nav_menu()` - функція, за допомогою якої ви можете вставити це меню на свій сайт  
`register_sidebar()` - функція, за допомогою якої ви можете зареєструвати область, де ви хочете бачити свій віджет, який був доданий в `Панель управління > Зовнішній вигляд > Віджети`  
`dynamic_sidebar()` - функція, за допомогою якої ви можете вставити свою бічну панель, яка була зареєстрована  
`wp_enqueue_script()` - функція, за допомогою якої ви можете включити свої скрипти на сайт  
`wp_enqueue_style()` - функція, за допомогою якої ви можете включити свої стилі на сайт  
`get_stylesheet_directory_uri()` - функція, яка повертає шлях до папки теми (`http://site.org/wp-content/themes/theme_name`)  
`bloginfo()` - повертає інформацію про сайт (посилання на сайт, назва сайту, електронна адреса адміністратора, шлях до теми)  
`add_image_size()` - функція, за допомогою якої можна створити додатковий розмір для зображень  
`add_image_size(“your_size”, width, height, array(“center”,'center'));`  
`the_post_thumbnail('your_size');` - Коли потрібно обрізати зображення  
`wp_oembed_get($url)` - виводить будь-яке вбудоване відео з сторонніх сервісів, таких як YouTube, vimeo тощо.

Більш розширена версія [[слайди]](https://slides.com/wladeveloper/general-wp-functions#/){target="_blank"}


#### Standards realization
- Основні стандарти розробки WLA [[посилання]](https://docs.google.com/spreadsheets/d/1ZK23IRJEU5o4vAiBzZwGq94Dz9_0SbQ89pHkuLGc-fE/edit?usp=sharing){target="_blank"}
  Головне зображення завжди має бути слайдером
- Related posts - Relation field, Latest posts/news - WP_Query
- Gravity Form - потрібно вимкнути всі стилі за замовчуванням
- Усі бічні панелі повинні бути саме бічними панелями з віджетами, а не частиною шаблону
- Включення локальних шрифтів через font-face повинно використовувати ту саму назву сімейства шрифтів та інший стиль шрифту, а також має включати властивість `font-display: swap` [[скріншот]](https://www.screencast.com/t/jFFjdjplV){target="_blank"}
- Коли ми маємо довгий контент з кнопкою «далі», ми повинні використовувати `the_content()` + роздільник `MORE` на сторінці адміністратора. Приклад [[скріншот]](https://app.screencast.com/QiIQdEiGyQ6yA){target="_blank"}
- Не використовуйте зображення на фоні (лише якщо це має бути фонове зображення для якогось розділу), будь ласка, використовуйте цю функцію `wp_get_attachment_image()`
- Стандартні плагіни, які ми повинні використовувати [[посилання]](https://docs.google.com/document/d/1r7zB1pil8OboFynzVM15fhXTsWIVSuju54T3XnF2dfo/edit?tab=t.0#heading=h.961zdy3dxbyg){target="_blank"}
- Розширити випадаючий список форматів TinyMCE, якщо необхідно [[посилання]](https://docs.google.com/document/d/1Di3ntglDTaAzXkqHk0A6dU4UytWxIUlIf_MWLTE_hWY/edit?tab=t.0#heading=h.yvrwjm2aha4r){target="_blank"}
- Розширити селектор кольору тексту TinyMCE основними кольорами теми в `tiny-mce-customizations.php` [[скріншот]](https://app.screencast.com/8wDY9OuX16fH0){target="_blank"}


### Typography
### Using of background images
### How to work with images
### Copyright field
### “Excerpt” / Read More
### Flexbox vs matchHeight
### Section Anchors
### Parallax
### Animations
### Website Migration

Never use!
-------------------------------------------------

Lectures
-------------------------------------------------

Useful links
-------------------------------------------------

- [White Label Agency dev workflow](https://docs.google.com/presentation/d/1uQtlvqYADsAJf_IUQFCOyGAaXCX5kNv2geuS4PczRUA/edit?usp=sharing){target="_blank"}
- [Ready Solution](https://docs.google.com/document/d/1h46Oet1QQhTK2Zp4CzuxLrRlXbK7MDyjfzcq5gh0fRY){target="_blank"}
- [Naming Convention](https://docs.google.com/document/d/1dNDEtXyiFdqvpzEuLZzbyDlZFOWPVaurHZExier8NYY/edit?usp=sharing){target="_blank"}
- [WordPress Codex](https://codex.wordpress.org){target="_blank"}
- [WordPress template hierarchy](http://codex.wordpress.org/images/9/96/wp-template-hierarchy.jpg){target="_blank"}
- [Foundation grid explanation](http://foundation.zurb.com/sites/docs/grid.html){target="_blank"}
- [WLA development plugins](https://drive.google.com/drive/folders/0BzANYn0xDtq2Vmc1Uk1jMjRJeHM?resourcekey=0-wvW82AtTbsHKk5w9ZznsXw&usp=drive_link){target="_blank"}
- [png to ico converter](http://convertico.com/){target="_blank"}
- Gradient generator
- Font generator
- Slick slider documentation
- Online psd viewer
- Font Awesome
- Fancybox 3
