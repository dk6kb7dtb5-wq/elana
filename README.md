[index-zahida.html](https://github.com/user-attachments/files/28552511/index-zahida.html)
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Для Захиды 💌</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300;1,400&family=Montserrat:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --rose: #c8506a;
    --rose-light: #f2c4ce;
    --rose-dark: #8b2a3e;
    --cream: #fdf6f0;
    --gold: #c9a96e;
    --gold-light: #f0ddb0;
    --dark: #2a1a1f;
    --text: #4a2a35;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Montserrat', sans-serif;
    background: var(--cream);
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Floating petals */
  .petals {
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    pointer-events: none;
    z-index: 0;
    overflow: hidden;
  }

  .petal {
    position: absolute;
    top: -40px;
    font-size: 18px;
    opacity: 0.5;
    animation: fall linear infinite;
  }

  @keyframes fall {
    0%   { transform: translateY(-40px) rotate(0deg) translateX(0); opacity: 0.6; }
    50%  { transform: translateY(50vh) rotate(180deg) translateX(30px); }
    100% { transform: translateY(110vh) rotate(360deg) translateX(-20px); opacity: 0; }
  }

  /* Main container */
  .container {
    position: relative;
    z-index: 1;
    max-width: 680px;
    margin: 0 auto;
    padding: 40px 24px 80px;
  }

  /* Hero */
  .hero {
    text-align: center;
    padding: 60px 0 40px;
    animation: fadeUp 1s ease both;
  }

  .hero-label {
    font-family: 'Montserrat', sans-serif;
    font-size: 11px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 20px;
  }

  .hero h1 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(48px, 10vw, 80px);
    font-weight: 300;
    line-height: 1.1;
    color: var(--dark);
  }

  .hero h1 em {
    font-style: italic;
    color: var(--rose);
  }

  .hero-sub {
    font-family: 'Cormorant Garamond', serif;
    font-size: 20px;
    font-style: italic;
    color: var(--rose-dark);
    margin-top: 16px;
    opacity: 0.8;
  }

  .divider {
    display: flex;
    align-items: center;
    gap: 16px;
    margin: 36px 0;
  }

  .divider-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(to right, transparent, var(--gold), transparent);
  }

  .divider-icon { color: var(--gold); font-size: 18px; }

  /* Cards */
  .section {
    animation: fadeUp 0.8s ease both;
  }

  .section-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: 28px;
    font-weight: 300;
    color: var(--dark);
    margin-bottom: 6px;
  }

  .section-hint {
    font-size: 12px;
    color: var(--rose);
    letter-spacing: 1px;
    margin-bottom: 20px;
  }

  /* Date picker */
  .dates-grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 10px;
    margin-bottom: 32px;
  }

  @media (max-width: 480px) {
    .dates-grid { grid-template-columns: repeat(4, 1fr); gap: 8px; }
  }

  .date-card {
    background: white;
    border: 1.5px solid var(--rose-light);
    border-radius: 14px;
    padding: 12px 6px;
    text-align: center;
    cursor: pointer;
    transition: all 0.2s ease;
    user-select: none;
  }

  .date-card:hover {
    border-color: var(--rose);
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(200, 80, 106, 0.15);
  }

  .date-card.selected {
    background: var(--rose);
    border-color: var(--rose);
    color: white;
    transform: translateY(-3px);
    box-shadow: 0 8px 24px rgba(200, 80, 106, 0.35);
  }

  .date-day {
    font-size: 11px;
    letter-spacing: 1px;
    text-transform: uppercase;
    opacity: 0.6;
  }

  .date-num {
    font-family: 'Cormorant Garamond', serif;
    font-size: 28px;
    font-weight: 300;
    line-height: 1.1;
  }

  .date-month {
    font-size: 10px;
    opacity: 0.7;
    margin-top: 1px;
  }

  /* Time picker */
  .times-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
    margin-bottom: 32px;
  }

  @media (max-width: 400px) {
    .times-grid { grid-template-columns: repeat(3, 1fr); }
  }

  .time-card {
    background: white;
    border: 1.5px solid var(--rose-light);
    border-radius: 12px;
    padding: 12px 8px;
    text-align: center;
    cursor: pointer;
    transition: all 0.2s ease;
    font-family: 'Cormorant Garamond', serif;
    font-size: 22px;
    user-select: none;
  }

  .time-card:hover {
    border-color: var(--rose);
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(200, 80, 106, 0.15);
  }

  .time-card.selected {
    background: var(--rose);
    border-color: var(--rose);
    color: white;
    transform: translateY(-3px);
    box-shadow: 0 8px 24px rgba(200, 80, 106, 0.35);
  }

  /* Food picker */
  .food-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 12px;
    margin-bottom: 32px;
  }

  .food-card {
    background: white;
    border: 1.5px solid var(--rose-light);
    border-radius: 16px;
    padding: 18px 16px;
    cursor: pointer;
    transition: all 0.2s ease;
    display: flex;
    align-items: center;
    gap: 12px;
    user-select: none;
  }

  .food-card:hover {
    border-color: var(--rose);
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(200, 80, 106, 0.12);
  }

  .food-card.selected {
    background: linear-gradient(135deg, #fff5f7, #ffe8ed);
    border-color: var(--rose);
    box-shadow: 0 6px 20px rgba(200, 80, 106, 0.2);
  }

  .food-emoji { font-size: 28px; line-height: 1; }

  .food-info { flex: 1; }

  .food-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 18px;
    color: var(--dark);
  }

  .food-desc {
    font-size: 11px;
    color: #999;
    margin-top: 2px;
  }

  .food-check {
    width: 22px;
    height: 22px;
    border-radius: 50%;
    border: 2px solid var(--rose-light);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 12px;
    transition: all 0.2s;
    color: white;
    background: transparent;
    flex-shrink: 0;
  }

  .food-card.selected .food-check {
    background: var(--rose);
    border-color: var(--rose);
  }

  /* Wishes */
  .wishes-input {
    width: 100%;
    background: white;
    border: 1.5px solid var(--rose-light);
    border-radius: 16px;
    padding: 16px 18px;
    font-family: 'Montserrat', sans-serif;
    font-size: 14px;
    color: var(--text);
    resize: none;
    outline: none;
    transition: border-color 0.2s;
    min-height: 90px;
    margin-bottom: 32px;
  }

  .wishes-input:focus { border-color: var(--rose); }
  .wishes-input::placeholder { color: #ccc; }

  /* Submit button */
  .submit-btn {
    width: 100%;
    background: linear-gradient(135deg, var(--rose), var(--rose-dark));
    color: white;
    border: none;
    border-radius: 16px;
    padding: 20px;
    font-family: 'Cormorant Garamond', serif;
    font-size: 24px;
    font-style: italic;
    cursor: pointer;
    transition: all 0.3s ease;
    box-shadow: 0 8px 30px rgba(200, 80, 106, 0.4);
    letter-spacing: 1px;
  }

  .submit-btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 14px 40px rgba(200, 80, 106, 0.5);
  }

  .submit-btn:active { transform: translateY(0); }

  .submit-btn:disabled {
    opacity: 0.5;
    cursor: not-allowed;
    transform: none;
  }

  /* Success screen */
  .success {
    display: none;
    text-align: center;
    padding: 60px 20px;
    animation: fadeUp 0.8s ease both;
  }

  .success-heart {
    font-size: 80px;
    animation: pulse 1.5s ease infinite;
  }

  @keyframes pulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.1); }
  }

  .success h2 {
    font-family: 'Cormorant Garamond', serif;
    font-size: 42px;
    font-weight: 300;
    color: var(--dark);
    margin: 20px 0 10px;
  }

  .success p {
    font-size: 15px;
    color: var(--rose-dark);
    opacity: 0.8;
    line-height: 1.6;
  }

  /* Setup banner */
  .setup-banner {
    background: linear-gradient(135deg, #fff9e6, #fff3d0);
    border: 1.5px solid var(--gold-light);
    border-radius: 16px;
    padding: 18px 20px;
    margin-bottom: 32px;
    font-size: 13px;
    line-height: 1.6;
    color: #7a5c20;
  }

  .setup-banner strong { color: #5a3c10; }
  .setup-banner code {
    background: rgba(201,169,110,0.15);
    padding: 2px 6px;
    border-radius: 4px;
    font-size: 12px;
  }

  .setup-steps { margin-top: 10px; padding-left: 16px; }
  .setup-steps li { margin-bottom: 4px; }

  /* Error */
  .error-msg {
    background: #fff0f3;
    border: 1px solid var(--rose-light);
    border-radius: 12px;
    padding: 14px 16px;
    font-size: 13px;
    color: var(--rose-dark);
    margin-bottom: 16px;
    display: none;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .section:nth-child(2) { animation-delay: 0.15s; }
  .section:nth-child(3) { animation-delay: 0.25s; }
  .section:nth-child(4) { animation-delay: 0.35s; }
  .section:nth-child(5) { animation-delay: 0.45s; }
  .section:nth-child(6) { animation-delay: 0.55s; }
</style>
</head>
<body>

<!-- Petals -->
<div class="petals" id="petals"></div>

<div class="container">

  <!-- Setup banner -->
  <div class="setup-banner" id="setupBanner" style="display:none">
    ⚙️ <strong>Настройка Telegram бота (2 минуты):</strong>
    <ol class="setup-steps">
      <li>Напиши <strong>@BotFather</strong> в Telegram → <code>/newbot</code> → дай имя боту</li>
      <li>Скопируй токен вида <code>123456:ABCdef...</code></li>
      <li>Напиши своему боту любое сообщение (чтобы он знал твой chat_id)</li>
      <li>Открой: <code>https://api.telegram.org/bot<b>ТВОЙ_ТОКЕН</b>/getUpdates</code> — найди <code>"id"</code> внутри <code>"from"</code></li>
      <li>Вставь токен и chat_id ниже 👇</li>
    </ol>
    <div style="margin-top:12px; display:flex; gap:8px; flex-wrap:wrap;">
      <input id="inputToken" placeholder="Telegram Bot Token" style="flex:2; min-width:200px; padding:8px 12px; border-radius:8px; border:1.5px solid var(--gold-light); font-size:12px; outline:none;">
      <input id="inputChatId" placeholder="Твой Chat ID" style="flex:1; min-width:110px; padding:8px 12px; border-radius:8px; border:1.5px solid var(--gold-light); font-size:12px; outline:none;">
      <button onclick="saveConfig()" style="padding:8px 16px; background:var(--gold); color:white; border:none; border-radius:8px; cursor:pointer; font-size:12px; white-space:nowrap;">Сохранить</button>
    </div>
    <div id="configStatus" style="margin-top:6px; font-size:12px; display:none;"></div>
  </div>

  <!-- Hero -->
  <div class="hero">
    <div class="hero-label">Для тебя, Захида</div>
    <h1>Пойдём на<br><em>свидание?</em></h1>
    <div class="hero-sub">Выбери всё, как тебе хочется ✨</div>
  </div>

  <div class="divider">
    <div class="divider-line"></div>
    <div class="divider-icon">🌸</div>
    <div class="divider-line"></div>
  </div>

  <!-- Main form -->
  <div id="mainForm">

    <!-- Date -->
    <div class="section">
      <div class="section-title">Когда встретимся?</div>
      <div class="section-hint">ВЫБЕРИ ДАТУ</div>
      <div class="dates-grid" id="datesGrid"></div>
    </div>

    <!-- Time -->
    <div class="section">
      <div class="section-title">Во сколько?</div>
      <div class="section-hint">ВЫБЕРИ ВРЕМЯ</div>
      <div class="times-grid" id="timesGrid">
        <div class="time-card" onclick="selectTime(this)" data-val="14:00">14:00</div>
        <div class="time-card" onclick="selectTime(this)" data-val="16:00">16:00</div>
        <div class="time-card" onclick="selectTime(this)" data-val="18:00">18:00</div>
        <div class="time-card" onclick="selectTime(this)" data-val="19:00">19:00</div>
        <div class="time-card" onclick="selectTime(this)" data-val="19:30">19:30</div>
        <div class="time-card" onclick="selectTime(this)" data-val="20:00">20:00</div>
        <div class="time-card" onclick="selectTime(this)" data-val="20:30">20:30</div>
        <div class="time-card" onclick="selectTime(this)" data-val="21:00">21:00</div>
      </div>
    </div>

    <!-- Food -->
    <div class="section">
      <div class="section-title">Что будем есть?</div>
      <div class="section-hint">МОЖНО ВЫБРАТЬ НЕСКОЛЬКО</div>
      <div class="food-grid">
        <div class="food-card" onclick="toggleFood(this)" data-val="Суши 🍣">
          <div class="food-emoji">🍣</div>
          <div class="food-info"><div class="food-name">Суши</div><div class="food-desc">Японская кухня</div></div>
          <div class="food-check">✓</div>
        </div>
        <div class="food-card" onclick="toggleFood(this)" data-val="Пицца 🍕">
          <div class="food-emoji">🍕</div>
          <div class="food-info"><div class="food-name">Пицца</div><div class="food-desc">Итальянская кухня</div></div>
          <div class="food-check">✓</div>
        </div>
        <div class="food-card" onclick="toggleFood(this)" data-val="Национальная кухня 🫕">
          <div class="food-emoji">🫕</div>
          <div class="food-info"><div class="food-name">Национальная</div><div class="food-desc">Азербайджанская кухня</div></div>
          <div class="food-check">✓</div>
        </div>
        <div class="food-card" onclick="toggleFood(this)" data-val="Бургеры 🍔">
          <div class="food-emoji">🍔</div>
          <div class="food-info"><div class="food-name">Бургеры</div><div class="food-desc">Американская кухня</div></div>
          <div class="food-check">✓</div>
        </div>
        <div class="food-card" onclick="toggleFood(this)" data-val="Паста 🍝">
          <div class="food-emoji">🍝</div>
          <div class="food-info"><div class="food-name">Паста</div><div class="food-desc">Итальянская кухня</div></div>
          <div class="food-check">✓</div>
        </div>
        <div class="food-card" onclick="toggleFood(this)" data-val="Стейк 🥩">
          <div class="food-emoji">🥩</div>
          <div class="food-info"><div class="food-name">Стейк</div><div class="food-desc">Гриль-ресторан</div></div>
          <div class="food-check">✓</div>
        </div>
        <div class="food-card" onclick="toggleFood(this)" data-val="Морепродукты 🦐">
          <div class="food-emoji">🦐</div>
          <div class="food-info"><div class="food-name">Морепродукты</div><div class="food-desc">Рыбный ресторан</div></div>
          <div class="food-check">✓</div>
        </div>
        <div class="food-card" onclick="toggleFood(this)" data-val="Любое 💝">
          <div class="food-emoji">💝</div>
          <div class="food-info"><div class="food-name">Любое</div><div class="food-desc">Пусть он выберет</div></div>
          <div class="food-check">✓</div>
        </div>
      </div>
    </div>

    <!-- Wishes -->
    <div class="section">
      <div class="section-title">Пожелания</div>
      <div class="section-hint">НЕОБЯЗАТЕЛЬНО, НО ПРИЯТНО</div>
      <textarea class="wishes-input" id="wishesInput" placeholder="Например: хочу у моря, или чтобы была живая музыка..."></textarea>
    </div>

    <!-- Error -->
    <div class="error-msg" id="errorMsg"></div>

    <!-- Submit -->
    <div class="section">
      <button class="submit-btn" id="submitBtn" onclick="submitForm()">
        Я иду на свидание! 💌
      </button>
    </div>

  </div>

  <!-- Success -->
  <div class="success" id="successScreen">
    <div class="success-heart">💖</div>
    <h2>Ждём тебя!</h2>
    <p>Захида, всё готово.<br>Он уже знает и готовится<br>к лучшему вечеру для тебя 🌹</p>
  </div>

</div>

<script>
  // ── Config ──────────────────────────────────────────
  let BOT_TOKEN = '8816982062:AAE_BiZJKThGG5QIFaIg5MxDBqBEINEEMfg';
  let CHAT_ID   = '530921101';

  function saveConfig() {
    const t = document.getElementById('inputToken').value.trim();
    const c = document.getElementById('inputChatId').value.trim();
    if (!t || !c) { showConfigStatus('Заполни оба поля', '#c00'); return; }
    BOT_TOKEN = t; CHAT_ID = c;
    localStorage.setItem('tg_token', t);
    localStorage.setItem('tg_chatid', c);
    showConfigStatus('✅ Сохранено!', 'green');
    setTimeout(() => document.getElementById('setupBanner').style.display = 'none', 1200);
  }

  function showConfigStatus(msg, color) {
    const el = document.getElementById('configStatus');
    el.textContent = msg; el.style.color = color; el.style.display = 'block';
  }

  if (BOT_TOKEN && CHAT_ID) {
    document.getElementById('setupBanner').style.display = 'none';
  } else {
    document.getElementById('inputToken').value = BOT_TOKEN;
    document.getElementById('inputChatId').value = CHAT_ID;
  }

  // ── Petals ───────────────────────────────────────────
  const petalsEl = document.getElementById('petals');
  const petalSymbols = ['🌸','🌺','✿','❀','🌷'];
  for (let i = 0; i < 18; i++) {
    const p = document.createElement('span');
    p.className = 'petal';
    p.textContent = petalSymbols[Math.floor(Math.random() * petalSymbols.length)];
    p.style.left = Math.random() * 100 + '%';
    p.style.animationDuration = (8 + Math.random() * 12) + 's';
    p.style.animationDelay = (Math.random() * 10) + 's';
    p.style.fontSize = (12 + Math.random() * 14) + 'px';
    petalsEl.appendChild(p);
  }

  // ── Dates ─────────────────────────────────────────────
  const days = ['Вс','Пн','Вт','Ср','Чт','Пт','Сб'];
  const months = ['Янв','Фев','Мар','Апр','Май','Июн','Июл','Авг','Сен','Окт','Ноя','Дек'];
  const monthsFull = ['января','февраля','марта','апреля','мая','июня','июля','августа','сентября','октября','ноября','декабря'];
  const grid = document.getElementById('datesGrid');

  let selectedDate = null;
  let selectedTime = null;
  const selectedFoods = new Set();

  for (let i = 1; i <= 10; i++) {
    const d = new Date();
    d.setDate(d.getDate() + i);
    const card = document.createElement('div');
    card.className = 'date-card';
    card.innerHTML = `
      <div class="date-day">${days[d.getDay()]}</div>
      <div class="date-num">${d.getDate()}</div>
      <div class="date-month">${months[d.getMonth()]}</div>`;
    card.dataset.val = `${d.getDate()} ${monthsFull[d.getMonth()]}`;
    card.onclick = function() { selectDate(this); };
    grid.appendChild(card);
  }

  function selectDate(el) {
    document.querySelectorAll('.date-card').forEach(c => c.classList.remove('selected'));
    el.classList.add('selected');
    selectedDate = el.dataset.val;
  }

  function selectTime(el) {
    document.querySelectorAll('.time-card').forEach(c => c.classList.remove('selected'));
    el.classList.add('selected');
    selectedTime = el.dataset.val;
  }

  function toggleFood(el) {
    el.classList.toggle('selected');
    const v = el.dataset.val;
    if (selectedFoods.has(v)) selectedFoods.delete(v);
    else selectedFoods.add(v);
  }

  // ── Submit ─────────────────────────────────────────────
  async function submitForm() {
    const errEl = document.getElementById('errorMsg');
    errEl.style.display = 'none';

    if (!selectedDate) { showErr('Выбери дату 📅'); return; }
    if (!selectedTime) { showErr('Выбери время ⏰'); return; }
    if (selectedFoods.size === 0) { showErr('Выбери хотя бы одно блюдо 🍽'); return; }
    if (!BOT_TOKEN || !CHAT_ID) { showErr('Сначала настрой Telegram бот (смотри инструкцию выше) ⚙️'); return; }

    const wishes = document.getElementById('wishesInput').value.trim();
    const foods = [...selectedFoods].join(', ');

    const msg = `💌 *Захида ответила на приглашение!*\n\n📅 Дата: *${selectedDate}*\n🕐 Время: *${selectedTime}*\n🍽 Кухня: *${foods}*${wishes ? `\n💬 Пожелания: _${wishes}_` : ''}\n\n_Готовься к лучшему свиданию! 🌹_`;

    const btn = document.getElementById('submitBtn');
    btn.disabled = true;
    btn.textContent = 'Отправляю... 💌';

    try {
      const params = new URLSearchParams({ chat_id: CHAT_ID, text: msg, parse_mode: 'Markdown' });
      await fetch(`https://api.telegram.org/bot${BOT_TOKEN}/sendMessage`, {
        method: 'POST',
        mode: 'no-cors',
        headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
        body: params
      });
      document.getElementById('mainForm').style.display = 'none';
      document.getElementById('successScreen').style.display = 'block';
      document.getElementById('setupBanner').style.display = 'none';
    } catch (e) {
      showErr('Ошибка сети. Проверь интернет.');
      btn.disabled = false;
      btn.textContent = 'Я иду на свидание! 💌';
    }
  }

  function showErr(msg) {
    const el = document.getElementById('errorMsg');
    el.textContent = msg;
    el.style.display = 'block';
    el.scrollIntoView({ behavior: 'smooth', block: 'center' });
  }
</script>
</body>
</html>
