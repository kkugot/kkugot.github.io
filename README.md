# kkugot.com

Англоязычная стартовая страница экспертного микросайта. Визуальное направление из Design Skills — редакционный минимализм. Крупное имя, исходный портрет с янтарным фоном и две ссылки. Имя, слоган, ссылки и путь к фотографии редактируются в `index.md`. GitHub Pages собирает страницу через Jekyll.

## Опубликовать на GitHub Pages

1. Создайте публичный репозиторий `kkugot/kkugot.github.io`. Если он уже существует, используйте его.
2. Загрузите в корень репозитория `index.md`, `_config.yml`, `README.md` и папки `_layouts/`, `assets/` с их содержимым. В пустом репозитории нажмите **uploading an existing file**, а если в нём уже есть файлы, выберите **Add file → Upload files**. Сохраните изменения в ветке `main`.
3. Откройте **Settings → Pages → Build and deployment**. В **Source** выберите **Deploy from a branch**, затем **main**, **/(root)** и **Save**.
4. Дождитесь успешной сборки во вкладке **Actions** и откройте [kkugot.github.io](https://kkugot.github.io/). [Инструкция GitHub по публикации из ветки](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

## Подключить kkugot.com

1. Откройте [Pages в настройках аккаунта GitHub](https://github.com/settings/pages) и нажмите **Add a domain**. Введите `kkugot.com`. GitHub покажет имя и значение TXT-записи. Добавьте её в DNS и нажмите **Verify**, когда запись станет доступна. Сохраните TXT-запись после проверки. [Подтверждение домена](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages).
2. В репозитории откройте **Settings → Pages → Custom domain**, введите `kkugot.com` и нажмите **Save**. GitHub сам добавит файл `CNAME` в ветку публикации. [Настройка домена в GitHub](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).
3. В кабинете imena.ua откройте **Послуги → kkugot.com → Налаштування домену (DNS та редиректи) → Перейти до налаштування домену**. Если DNS обслуживает другой провайдер, добавьте записи в его панели. [Инструкция imena.ua](https://www.imena.ua/blog/site-on-wordpress-part-1/amp/).
4. Добавьте четыре записи типа **A** для `@` (корень домена, в некоторых панелях поле имени пустое). Если корень уже указывает на другой сайт, удалите старые адресные записи **A** и **AAAA** этого сайта. Почтовые записи MX и TXT сохраните.
   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`
5. Добавьте **CNAME** для хоста `www` со значением `kkugot.github.io`. Уберите конфликтующие адресные записи для `www`. С этими записями GitHub перенаправляет `www.kkugot.com` на `kkugot.com`. [DNS-записи GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#dns-records-for-your-custom-domain).
6. Когда GitHub подтвердит DNS и выпустит сертификат, включите **Enforce HTTPS** в **Settings → Pages**. Проверьте оба адреса в браузере. Обновление DNS может занять до 24 часов.

На macOS записи можно проверить в Терминале.

```sh
dig +short NS kkugot.com
dig +short A kkugot.com
dig +short CNAME www.kkugot.com
```

## Добавить первый кейс

Создайте `projects/index.md` с таким началом. Страница появится по адресу `/projects/`.

```markdown
---
layout: default
title: Projects
---

# Projects

## Название проекта

Задача, ваша роль, что вы сделали и чему научились.
```

Когда появится опубликованный кейс, добавьте ссылку в общий шаблон `_layouts/default.html`.

```html
<a href="{{ '/projects/' | relative_url }}">Projects</a>
```

Таким же способом можно открыть раздел AI-экспериментов и добавлять короткие заметки о проектах. LinkedIn остаётся местом для обсуждения этих материалов.
