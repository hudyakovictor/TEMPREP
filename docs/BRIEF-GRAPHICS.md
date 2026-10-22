# ТЗ · Иконки и графика Table Tennis Ultimate (уровень AAA+)

> Реестр имён, размеры, бюджет веса и техтребования — здесь. Разделение работы на независимые пакеты (по одному дизайнеру на пакет) и арт-дирекшн — в `BRIEF-PACKAGES.md`. Пасхалки и пародийные бренды — в `BRIEF-EGGS.md`. Названия ассетов и тексты — на английском, термины из глоссария ITTF: аудитория международная.

## 0. Инвентаризация сборки
- Спрайт: **61** `<symbol>` 24×24, `stroke:currentColor`, оптика 1.8, round caps/joins; хелпер `ico(n, cls)`; размеры `.i` 20 + `.i-12/14/16/18/24/28`. **194** вызова, **46** имён идут из полей `icon:` (SHOP, DRILLS, QUESTS, ACHIEVEMENTS, NAV_TABS).
- **52** подложки `.islot`; **44** слота `.art` — пустые градиентные прямоугольники, незанятые витрины. **14** inline-`<svg>`, **0** `<img>`, **0** `<canvas>`; растр один — KEYART jpeg 768×1376, 61 КБ, 6 вставок.
- **124** экрана в 17 группах, **15** попапов; **58** из 177 рендер-блоков стартуют без графики.
- Эмодзи вместо иконок: ₵×80, ◈×45, ✓×9, соперники 🐯🦊🐼🦅🐉+АС, флаг 🇱🇹, реакции 😉😮😅😄👏🎯🔥, ☰ = **155 вхождений**: шрифтозависимы, не темизуются, портят плотную раскладку. Удалить все.
- **Цель:** 288 иконок + 128 детализированных ассетов + 16 FX, ≥90 % экранов с графикой, 0 эмодзи, 0 изображений людей, вес ≤ 420 КБ. Разбивка по производственным партиям — в `BRIEF-ASSETS.md`.

## 1. Стиль (обязателен для всех подрядчиков)
Сетка 24, отступ 2, оптика 1.8 (1.6 для 12–14 px, 2.2 для 28+), радиусы только из токенов. Цвет только `currentColor`; дуотон — второй путь с `opacity:.28`. Состояния: default / `.on` (drop-shadow 8 px `--coral`) / disabled (`saturate(.45)`). Имя `i-<домен>-<объект>[-<состояние>]`, ≤3 путей на symbol, без `<g>`/transform. Запрещены: серые полупрозрачные копии, гибрид fill+stroke, детали неразличимые на 16 px.

## 2. Реестр иконок: 61 есть → 288 (★ — новые)
**Уже в спрайте (61):** home, gear, shop, trophy, user, users, bell, chev-r, chev-d, arrow-l, arrow-r, x, plus, minus, info, check, edit, warn, lock, refresh, logout, eye, wifi, wifi-off, help, flag, shield, play, pause, expand, coin, gem, gift, box, medal, crown, star, paddle, ball, sword, bolt, fire, target, vibe, hand, mouse, chart, clock, map, share, mail, cards, key, cal, motion, contrast, sound, music, tv, lang, paint.
**A. Каркас/навигация, +9.** ★ search, globe, menu, chev-l, chev-u, bookmark, history, layers, filter.
**B. Статус/фидбек, +9.** ★ error-cloud, retry-timer, verified, alert-octagon, dot-online, dot-away, dot-offline, calendar-lock, progress-ring.
**C. Валюты и награды, +14.** ★ coin-stack, gem-cluster, token, keycard, chest-bronze, chest-silver, chest-gold, chest-season, voucher, xp-crystal, stars (замена ₵), orb-blue (замена ◈), ribbon, prize-pouch.
**D. Экипировка, +23.** ★ handle-flare, handle-straight, blade-carbon, blade-arylate, rubber-tackey, rubber-pips, sponge-hu, sponge-mh, glue, blade-thickness, racket-case, shoe, jersey, glove, towel, tension, sweetspot, ball-3star, ball-plastic, ball-celluloid, table-top, table-legs, net-set.
**E. Геймплей и удары, +24.** ★ serve-top, serve-back, serve-no, drive, loop-heavy, loop-side, flick, push-long, push-short, chop, block-on, block-off, smash, counter, lob, footwork, third-ball, receive, rally, spin-curve, speed-kmh, placement, net-clip, edge-ball.
**F. Тренировки и аналитика, +20.** ★ drill-spiral, drill-smash, drill-deception, drill-reaction, drill-footwork, drill-serve, metronome, heartbeat, heat-map, accuracy-pie, stroke-height, timing-bar, fatigue, form-score, replay-strip, camera-angle, slow-mo, whistle, plan-list, goal-flag.
**G. Турниры и лиги, +18.** ★ bracket-tree, bracket-final, group-stage, swiss, bye, seed, div-bronze, div-silver, div-gold, div-pro, div-super, promotion, relegation, live-dot, schedule, rules-scroll, entry-fee, prize-pool.
**H. Соц и клуб, +17.** ★ club-crest, club-chat, club-war, war-siege, invite-link, friend-add, friend-remove, block, report, react-like, react-fire, react-laugh, react-shock, react-wow, team-week, dm-thread, voice.
**I. Магазин и экономика, +17.** ★ cart, price-tag, discount, bundle, cosmetic-set, rarity-common, rarity-rare, rarity-epic, rarity-legend, limited-timer, wishlist, owned-tick, refund, tx-in, tx-out, topup, deal.
**J. Профиль и прогресс, +19.** ★ level-shield, tier-badge, streak-flame, season-pass, track-line, node-dot, ach-cluster, avatar-frame, frame-gold, nameplate, title-royal, win-loss, winrate, match-count, mvp, fair-play, career-map, chapter-gate, cabinet.
**K. Настройки и устройства, +20.** ★ gamepad, keyboard, gesture, tilt, vibration, haptic, audio-mix, sfx, voice-chat, mic-off, notif-group, privacy-shield, data-download, data-erase, cloud-sync, device-session, fps-meter, quality-low, quality-mid, quality-high.
**L. Онбординг и анатомия, +12.** ★ grip-shake, grip-penhold, grip-seytoven, finger-pos, thumb-pressure, wrist-hinge, forearm-axis, stance-open, stance-square, ready-pos, device-phone, device-tablet.
**M. Локации и атмосфера, +12.** ★ arena-indoor, arena-street, arena-club, arena-national, skyline, weather-rain, weather-wind, seats (бывш. crowd: только ряды кресел, людей не рисуем), scoreboard, floor-wood, lighting, sponsor-board.
**N. Карьера и выезды, +13.** ★ plane, hotel, wallet, ticket, contract, hamburger, first-aid, heat, map-pin, handshake, debt, wall, bucket (glue и towel уже есть в D; entry-fee, schedule, career-map, nameplate, cabinet — в G/J).

Итого 61 + 227 = 288. Очередь: **P0** = A+B+C+D+E (79, включая эмодзи-замены stars, orb-blue, 4 chest) · **P1** = F+G+H+I+J+N (104) · **P2** = K+L+M (44).
## 3. Графические тизеры
44 `.art`-слота заполнить тизер-иллюстрацией 2× вместо градиента: 150–230 px: splash, online-entry, matchmaking, recovery, practice-brief, boss-stage, tournament-card, product, club, onb-device, onb-done, season-pass, cosmetic-set, career-story, season-recap, about, widgets · 74–110 px: welcome, offline, maintenance, update-required, session-check, practice-result, tournament-result, purchase-success, chapter-reward, qa-audit · 38–64 px: inventory, bundles, daily-deals, purchase-confirm, practice-list, settings-flags, engine-console (6).
Формула: один объект + один акцент + темовый фон (`color-mix`, `--coral/--sky`); считывается за 300 мс.
Новые точки: баннер сезона 4:1 в хабе под hero-колодой · полоса асценсии в карточке лиги · обложка пропуска 3:4 в season-pass · рампа победы 16:9 в pop-win · лента дропов 1:1 в магазине · превью арены 16:9 над HUD · гербова панель 1:1 в клубе · обложка сезона 4:1 за аватаром · шапка календаря 4:1 · empty-state 120 px с подписью.

## 4. Детализированная графика (128 ассетов)
1. **Key art, 8** — 4 сезонные обложки 9:16 + 4 промо (старт, Суперлига, сундук, Stars); WebP ≤ 80 КБ, 1×/2×, safe-area под топбар.
2. **Рендеры экипировки, 24** — по одному экземпляру на ракетку в одном свете и ракурсе (5 серий), накладки/аксессуары — тем же стилем; стол 16:9 с фактурой сукна, мяч 120 px со следом, PNG alpha ≤ 60 КБ.
2b. **Игровые ассеты матча, 8** — своя ракетка (лицевая/тыльная сторона) и ракетка соперника (2 + 2), мяч (тренировочный / матч / старый), след вращения, точка контакта; купленный скин должен быть виден на поле — задача к моменту подключения геймплея.
3. **Сцены арен, 8** — школьный зал, клубный зал, парк (бетонный стол), университет, склад-конвертер, гостиничный конференц-зал, национальная арена, финальный зал с камерами; 16:9, слоёные (фон / туман / свет / ряды сидений без фигур — людей в кадре нет).
4. **Соперники, 12** — изображений людей нет (0 маскотов, 0 портретов, 0 силуэтов): вымышленные имена, ник-плитка 3 размеров, табличка «кто это» текстом, аватар = типографская плашка с инициалами; заглушки 🐯🐼🦅🐉 убрать. В матче от соперника видна только его ракетка (2b).
5. **Гербы клубов и лиг, 10** — 5 дивизионных эмблем (монохром + цвет) + 5 клубных щитов.
6. **Медали и награды, 10** — 3 метал × 3 состояния, 4 ленты, кубок, MVP.
6b. **Мерч спонсоров, 4** — намеренно кринжовая футболка `Buncho's` в четырёх версиях (базовая / после «обновления брендбука» / заклеенная скотчем в Индии / чемпионская): мультяшная сосиска с ракеткой, взрыв-звезда, три конфликтующих цвета, кривой кернинг, слоган забегаловки, номер телефона, «EST. 1994». Плохая вёрстка должна быть спроектирована аккуратно — это единственная графика в сборке, которая обязана выглядеть дурно; рендер футболки 150×190 PNG alpha ≤ 25 КБ каждая, макет письма-уведомления 3:4 ≤ 30 КБ, бюджет пакета 115 КБ.
7. **Сундуки, 6** — 4 корпуса (бронза / серебро / золото / сезонный) + состояние «открыт» вторым слоем + дымка раскрытия.
8. **Карта карьеры, 3** — панорама глав 1–4 (парк → школа → клуб → национальный тур) 4:1 + 2 узла боссов.
9. **Empty и ошибки, 8** — офлайн, техработы, обновление, сессия, пустой чат/инвентарь, нет друзей/турниров; 120 px, двухцветные.
10. **Онбординг-диаграммы, 6** — без лиц: кисть руки с хватом, стойка ног, предплечье, тесты устройства и управления; разрезы 170×130 со стрелками.
11. **Артефакты карьеры, 12** — наклейка на чехол · гравировка на торце · вымпел · строка журнала тренера с датой · строка на доске почёта · именной мяч · полотенце с номером серии · щуп с отметкой 2,16 мм · сломанная накладка в рамке · предупреждение судьи · башня мячей 3/10/50 · пустое место на полке; 96–140 px, PNG alpha ≤ 18 КБ.
12. **Бумага спонсоров и федераций, 9** — письмо-оффер 3:4 с вложением · протокол инцидента · уведомление о взносе · чек подтверждения · письмо ассоциации о дикой карте · баннер арены 4:1 для пяти брендов (`Buncho's`, `Fixall`, `Nebula`, `Abibas`, `Roplex`); ≤ 30 КБ, типографика важнее иллюстрации.

## 5. Motion/FX, 16
Фонтан монет, россыпь сфер, конфетти победы, рампа, искра контакта мяча, спиральный след подачи, полоса смэша, вспышка critical, дымка сундука, shine по XP-бара, тик календаря, посадка карточки hero-колоды, свет арены, оверлей счётчика, net-clip, свечение `.on` (уже есть). Реализация: атлас 512×512 WebP либо inline-SVG+CSS; 240–420 мс; гашение в `body.rm` / `prefers-reduced-motion`.

## 6. Технические требования
Спрайт — 4 блока (core, game, meta, shop) в `head.part`; `<title>` у смысловых, декоративные `aria-hidden="true"`. Растр WebP/AVIF 1×/2×, q78–84. Бюджет на экран: иконка 0,4 · тизер 24 · иллюстрация 60 · key art 80 · FX-атлас 90 КБ, итого ≤ 420 КБ на экран; весь корпус на диске ≤ 5 МБ, грузится по требованию. Base64 в JS > 8 КБ запрещён — папка `art/`, `<img loading="lazy" width height>` без сдвига layout. Иллюстрации двухслойные: база `currentColor`/`--bg1`, акцент `--coral`/`--sky` — темы без перерендера.

## 7. Этапы, приёмка, метрики, риски
**Э1 (P0):** 79 иконок, 12 тизеров, 2 key-иллюстрации (splash, online-entry), 100 % замена эмодзи. **Э2 (P1):** +104 иконы (включая N «Карьера»), 24 рендера, 8 сцен, 12 ник-плиток соперников, бумага и артефакты. **Э3 (P2):** +44 икона, карта глав, 16 FX, 10 гербов, 8 empty-state.
**DoD экрана:** 0 эмодзи · ≥1 осмысленная графика в первом экране без прокрутки · все `.art` заполнены · 0 сдвига layout · light/dark без правки ассета.
**Метрики:** 288/288 иконок, 128/128 ассетов, ≥90 % экранов с графикой, ≤ 420 КБ на экран и ≤ 5 МБ на диске, LCP splash ≤ 1,2 с, 0 эмодзи, 0 изображений людей.
**Риски:** вес (атласы + двухслойность) · stylistic drift (одна сетка на категорию) · ложная детализация (тест читаемости 16 px) · каскад (CSS только в `extra8.css`).
