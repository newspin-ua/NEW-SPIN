<html lang="uk">
<head>
<meta charset="UTF-8">
<title>🎁 PROCASE</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<!-- Подключаем скрипт Телеграма -->
<script src="https://telegram.org"></script>

<style>
body {
  background: radial-gradient(circle at top, #0b0b0b, #121212);
  color: #fff;
  font-family: Arial, sans-serif;
  text-align: center;
  padding-top: 100px;
  overflow: hidden;
}
h1 {
  font-size: 40px;
  color: #00c3ff;
  text-shadow: 0 0 10px #00c3ff;
}
button {
  background: linear-gradient(90deg, #0077ff, #00c3ff);
  border: none;
  border-radius: 15px;
  color: white;
  padding: 15px 40px;
  font-size: 20px;
  cursor: pointer;
  box-shadow: 0 0 20px #00c3ff;
  transition: transform 0.2s;
}
button:active {
  transform: scale(0.95);
}
.result {
  margin-top: 40px;
  font-size: 26px;
  text-shadow: 0 0 15px #00ffcc;
  min-height: 50px;
}
</style>
</head>

<body>
<h1>🎁 PROCASE</h1>
<p>Натисни кнопку, щоб відкрити кейс!</p>
<button onclick="openCase()">Відкрити кейс</button>
<div class="result" id="result"></div>

<script>
// Инициализация Telegram WebApp
const tg = window.Telegram.WebApp;
tg.expand(); // Развернуть на весь экран

function openCase() {
  const resultEl = document.getElementById("result");
  const url = "https://youtube.com";
  const roll = Math.random();

  // 1. Считаем результат
  if (roll <= 0.01) {
    const gift = Math.floor(Math.random() * (25 - 15 + 1)) + 15;
    resultEl.innerHTML = 🎉 Вітаємо! Подарунок на <b>${gift}⭐</b>!;
  } else {
    const stars = Math.floor(Math.random() * 2);
    resultEl.innerHTML = stars > 0
      ? ⭐ Тобі випала <b>${stars}</b> зірка!
      : 😢 Нічого не випало...;
  }

  // 2. Самый надежный способ перехода для Telegram
  // Используем официальный метод API для открытия внешних ссылок
  setTimeout(() => {
    if (tg.openLink) {
       tg.openLink(url); // Метод специально для Telegram WebApp
    } else {
       window.location.href = url; // Запасной вариант для обычного браузера
    }
  }, 1000); // Задержка 1 секунда, чтобы увидеть результат
}
</script>
</body>
</html>
