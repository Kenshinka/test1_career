# Карьерный сайт ВсеИнструменты.ру — план реализации

> **Для исполнителя:** план выполняется по шагам, отмечай чекбоксы (`- [ ]`). Каждый шаг — 2–5 минут. Команды копируются как есть.

**Цель:** собрать статический карьерный сайт (HTML+CSS+JS), завести git-репозиторий, опубликовать на GitHub и включить GitHub Pages.

**Архитектура:** один `index.html` с секциями-якорями, отдельные `styles.css` и `script.js`. Без сборщиков и фреймворков. Данные вакансий захардкожены. Отклик — через `mailto:`.

**Стек:** HTML5, CSS3, чистый JS, git, GitHub, GitHub Pages.

> **Замечание для новичка:** шаги, которые делаешь **ты руками в браузере** (создать репозиторий, включить Pages), помечены 👤. Остальное может выполнить ассистент в терминале.

---

## Задача 1: Каркас проекта и git

**Файлы:**
- Создать: `.gitignore`, `README.md`

- [ ] **Шаг 1: Инициализировать git**

```bash
cd /Users/pavelevdokimov/Claude/Project/Test1_career
git init
```
Ожидаемо: `Initialized empty Git repository ...`. Это превращает папку в репозиторий — теперь git отслеживает изменения.

- [ ] **Шаг 2: Проверить имя/почту в git (нужно для коммитов)**

```bash
git config user.name; git config user.email
```
Если пусто — задать:
```bash
git config --global user.name "Pavel Evdokimov"
git config --global user.email "evdokimovpavelepi@gmail.com"
```

- [ ] **Шаг 3: Создать `.gitignore`**

Файл `.gitignore` (что git должен игнорировать — системный мусор macOS):
```gitignore
.DS_Store
Thumbs.db
*.log
```

- [ ] **Шаг 4: Создать `README.md`**

```markdown
# Карьерный сайт ВсеИнструменты.ру

Учебный статический сайт «Работай у нас»: о компании, вакансии, контакты.

## Локальный запуск
Открыть `index.html` в браузере (двойной клик).

## Публикация
Сайт публикуется через GitHub Pages из ветки `main`.
```

- [ ] **Шаг 5: Первый коммит**

```bash
git add .gitignore README.md
git commit -m "chore: каркас проекта (gitignore, readme)"
```
Ожидаемо: `2 files changed`. Коммит — это сохранённый снимок состояния проекта.

---

## Задача 2: Разметка страницы (index.html)

**Файлы:**
- Создать: `index.html`

- [ ] **Шаг 1: Создать `index.html`**

```html
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Работа в ВсеИнструменты.ру</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <header class="topbar">
    <div class="container topbar__inner">
      <a href="#" class="logo">ВсеИнструменты.ру</a>
      <nav class="nav">
        <a href="#about">О компании</a>
        <a href="#jobs">Вакансии</a>
        <a href="#contacts">Контакты</a>
      </nav>
    </div>
  </header>

  <section class="hero">
    <div class="container">
      <h1>Работай в ВсеИнструменты.ру</h1>
      <p>Крупнейший DIY-ритейлер. Расти вместе с нами.</p>
      <a href="#jobs" class="btn">Смотреть вакансии</a>
    </div>
  </section>

  <section id="about" class="section">
    <div class="container">
      <h2>Почему мы</h2>
      <div class="cards">
        <div class="card"><h3>Стабильность</h3><p>Белая зарплата, оформление по ТК с первого дня.</p></div>
        <div class="card"><h3>Развитие</h3><p>Обучение, наставники и карьерный рост внутри компании.</p></div>
        <div class="card"><h3>Команда</h3><p>Дружный коллектив и поддержка на каждом этапе.</p></div>
        <div class="card"><h3>Масштаб</h3><p>Сотни магазинов по стране и современные технологии.</p></div>
      </div>
    </div>
  </section>

  <section id="jobs" class="section section--alt">
    <div class="container">
      <h2>Открытые вакансии</h2>
      <div class="jobs">
        <article class="job">
          <h3>Продавец-консультант</h3>
          <p class="job__meta">Москва · Офлайн · Полный день</p>
          <a class="btn btn--small" href="mailto:hr@vseinstrumenti.ru?subject=Отклик: Продавец-консультант">Откликнуться</a>
        </article>
        <article class="job">
          <h3>Кладовщик</h3>
          <p class="job__meta">Санкт-Петербург · Склад · Сменный график</p>
          <a class="btn btn--small" href="mailto:hr@vseinstrumenti.ru?subject=Отклик: Кладовщик">Откликнуться</a>
        </article>
        <article class="job">
          <h3>Frontend-разработчик</h3>
          <p class="job__meta">Удалённо · IT · Полный день</p>
          <a class="btn btn--small" href="mailto:hr@vseinstrumenti.ru?subject=Отклик: Frontend-разработчик">Откликнуться</a>
        </article>
        <article class="job">
          <h3>Менеджер по логистике</h3>
          <p class="job__meta">Екатеринбург · Офис · Полный день</p>
          <a class="btn btn--small" href="mailto:hr@vseinstrumenti.ru?subject=Отклик: Менеджер по логистике">Откликнуться</a>
        </article>
      </div>
    </div>
  </section>

  <section id="contacts" class="section">
    <div class="container">
      <h2>Контакты и отклик</h2>
      <p>Не нашли подходящую вакансию? Напишите нам — мы ответим.</p>
      <p>HR-отдел: <a href="mailto:hr@vseinstrumenti.ru">hr@vseinstrumenti.ru</a></p>
      <a class="btn" href="mailto:hr@vseinstrumenti.ru?subject=Хочу работать в ВсеИнструменты.ру">Откликнуться</a>
    </div>
  </section>

  <footer class="footer">
    <div class="container">
      <p>© 2026 ВсеИнструменты.ру — учебный проект</p>
    </div>
  </footer>

  <script src="script.js"></script>
</body>
</html>
```

- [ ] **Шаг 2: Проверить в браузере**

Открыть `index.html` двойным кликом. Ожидаемо: видны все секции (пока без стилей, простой текст и ссылки). Якоря в меню прокручивают к секциям.

- [ ] **Шаг 3: Коммит**

```bash
git add index.html
git commit -m "feat: разметка карьерной страницы"
```

---

## Задача 3: Стили (styles.css)

**Файлы:**
- Создать: `styles.css`

- [ ] **Шаг 1: Создать `styles.css`**

```css
:root {
  --brand: #e2231a;
  --dark: #1a1a1a;
  --gray: #f5f5f5;
  --text: #222;
}

* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: -apple-system, "Segoe UI", Roboto, Arial, sans-serif;
  color: var(--text);
  line-height: 1.6;
}

.container { max-width: 1000px; margin: 0 auto; padding: 0 20px; }

.topbar {
  position: sticky; top: 0; background: #fff;
  border-bottom: 1px solid #eee; z-index: 10;
}
.topbar__inner { display: flex; align-items: center; justify-content: space-between; height: 64px; }
.logo { font-weight: 700; color: var(--brand); text-decoration: none; font-size: 18px; }
.nav a { margin-left: 24px; color: var(--text); text-decoration: none; }
.nav a:hover { color: var(--brand); }

.hero {
  background: linear-gradient(135deg, var(--brand), #a5170f);
  color: #fff; padding: 90px 0; text-align: center;
}
.hero h1 { font-size: 40px; margin-bottom: 12px; }
.hero p { font-size: 18px; margin-bottom: 28px; opacity: .95; }

.btn {
  display: inline-block; background: #fff; color: var(--brand);
  padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600;
}
.btn:hover { background: var(--gray); }
.btn--small { padding: 8px 16px; background: var(--brand); color: #fff; }
.btn--small:hover { background: #a5170f; }

.section { padding: 64px 0; }
.section--alt { background: var(--gray); }
.section h2 { font-size: 28px; margin-bottom: 28px; text-align: center; }

.cards { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 20px; }
.card { background: #fff; border: 1px solid #eee; border-radius: 12px; padding: 24px; }
.card h3 { color: var(--brand); margin-bottom: 8px; }

.jobs { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 20px; }
.job {
  background: #fff; border: 1px solid #eee; border-radius: 12px; padding: 24px;
  display: flex; flex-direction: column; gap: 12px; align-items: flex-start;
}
.job__meta { color: #666; font-size: 14px; }

.footer { background: var(--dark); color: #bbb; padding: 32px 0; text-align: center; }
```

- [ ] **Шаг 2: Проверить в браузере**

Обновить страницу (Cmd+R). Ожидаемо: красная шапка-hero, карточки преимуществ сеткой, карточки вакансий, тёмный подвал.

- [ ] **Шаг 3: Коммит**

```bash
git add styles.css
git commit -m "style: оформление страницы"
```

---

## Задача 4: Интерактив (script.js)

**Файлы:**
- Создать: `script.js`

- [ ] **Шаг 1: Создать `script.js`**

```javascript
// Плавная прокрутка по якорям меню
document.querySelectorAll('a[href^="#"]').forEach(function (link) {
  link.addEventListener('click', function (e) {
    var id = this.getAttribute('href');
    if (id.length > 1) {
      var target = document.querySelector(id);
      if (target) {
        e.preventDefault();
        target.scrollIntoView({ behavior: 'smooth' });
      }
    }
  });
});
```

- [ ] **Шаг 2: Проверить в браузере**

Обновить страницу. Клик по пунктам меню → плавная прокрутка к секции.

- [ ] **Шаг 3: Коммит**

```bash
git add script.js
git commit -m "feat: плавная прокрутка по якорям"
```

---

## Задача 5: Публикация на GitHub

**Файлы:** изменений в коде нет — только git/GitHub.

- [ ] **Шаг 1: 👤 Создать пустой репозиторий на GitHub**

Зайти на https://github.com/new и:
- **Repository name:** `Test1_career`
- Видимость: Public (нужно для бесплатного GitHub Pages).
- НЕ ставить галочки «Add README / .gitignore / license» (файлы уже есть локально).
- Нажать **Create repository**.

После создания GitHub покажет адрес репозитория. Скопировать его — он вида
`https://github.com/<твой-логин>/Test1_career.git`.

- [ ] **Шаг 2: Привязать репозиторий и переименовать ветку в main**

Подставить свой логин вместо `<твой-логин>`:
```bash
git branch -M main
git remote add origin https://github.com/<твой-логин>/Test1_career.git
```
Проверка:
```bash
git remote -v
```
Ожидаемо: две строки с origin и твоим URL.

- [ ] **Шаг 3: Запушить код на GitHub**

```bash
git push -u origin main
```
Браузер/терминал может попросить логин GitHub — авторизоваться. Ожидаемо:
ветка `main` появилась на github.com, файлы видны в репозитории.

- [ ] **Шаг 4: 👤 Включить GitHub Pages**

На странице репозитория: **Settings → Pages**. В разделе «Build and
deployment»:
- Source: **Deploy from a branch**
- Branch: **main**, папка **/ (root)** → **Save**.

Через 1–2 минуты вверху появится ссылка вида
`https://<твой-логин>.github.io/Test1_career/`.

- [ ] **Шаг 5: Проверить живой сайт**

Открыть ссылку GitHub Pages. Ожидаемо: тот же сайт, что локально, но в
интернете. Если 404 — подождать пару минут и обновить.

---

## Задача 6: Тренировка веток (ради чего всё затевалось)

**Файлы:** небольшая правка `index.html` для практики.

- [ ] **Шаг 1: Создать новую ветку**

```bash
git checkout -b update-slogan
```
Ожидаемо: `Switched to a new branch 'update-slogan'`. Ветка — отдельная
линия изменений, не трогающая `main`.

- [ ] **Шаг 2: Внести правку**

В `index.html` заменить текст слогана в hero:
```html
<p>Крупнейший DIY-ритейлер России. Тысячи коллег уже с нами.</p>
```

- [ ] **Шаг 3: Закоммитить в ветке**

```bash
git add index.html
git commit -m "copy: обновить слоган на главной"
```

- [ ] **Шаг 4: Запушить ветку**

```bash
git push -u origin update-slogan
```

- [ ] **Шаг 5: 👤 Открыть Pull Request и слить**

На github.com появится кнопка **Compare & pull request** → создать PR →
**Merge pull request**. Так изменения из ветки попадают в `main`, а Pages
обновит сайт.

- [ ] **Шаг 6: Вернуться на main и подтянуть изменения**

```bash
git checkout main
git pull
```
Теперь локальный `main` снова синхронен с GitHub. Цикл «ветка → правки →
push → PR → merge → pull» — основа работы с git.

---

## Самопроверка плана (выполнено автором плана)

- **Покрытие спецификации:** структура файлов (З1–4), все 3 секции +
  hero + подвал (З2), git-инициализация и коммиты (З1), создание репо и
  push (З5), GitHub Pages (З5), ветки/PR (З6), mailto-отклик (З2). Всё
  покрыто.
- **Плейсхолдеры:** отсутствуют, весь код приведён целиком.
- **Согласованность:** имена классов в `index.html` и `styles.css`
  совпадают (`.hero`, `.card`, `.job`, `.btn--small` и т.д.).
