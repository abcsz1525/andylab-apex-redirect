# andylab-apex-redirect

GitHub Pages-сайт, который ловит запросы к голому apex-домену `andylab.studio` (без `www`) и 301/JS-редиректит на `https://www.andylab.studio/`. Нужен потому, что reg.ru DNS не поддерживает CNAME на корне зоны.

## Как это работает

- DNS reg.ru: 4 A-записи на `@` указывают на IP GitHub Pages.
- GitHub Pages читает `CNAME` → знает, что обслуживает `andylab.studio`, выпускает Let's Encrypt-сертификат.
- index.html и 404.html содержат `meta refresh` + JS `location.replace` — пользователь моментально попадает на `https://www.andylab.studio/`.
