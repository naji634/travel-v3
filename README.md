<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>北海道観光ガイド | Hokkaido Travel Guide</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    :root {
      --bg-light: linear-gradient(135deg, #fefcea, #f1da36);
      --bg-dark: linear-gradient(135deg, #001f3f, #0074D9);
      --text-light: #000;
      --text-dark: #fff;
    }

    body {
      margin: 0;
      font-family: 'Helvetica Neue', sans-serif;
      transition: background 0.5s, color 0.5s;
      background: var(--bg-light);
      color: var(--text-light);
    }

    body.dark-mode {
      background: var(--bg-dark);
      color: var(--text-dark);
    }

    header {
      padding: 1rem;
      text-align: center;
      background: rgba(255,255,255,0.2);
      backdrop-filter: blur(10px);
    }

    h1 {
      font-size: 2rem;
      margin: 0;
    }

    .lang-switcher, .mode-switcher {
      margin: 1rem;
      text-align: center;
    }

    select, button {
      padding: 0.5rem;
      margin: 0.5rem;
      font-size: 1rem;
    }

    .season-section {
      text-align: center;
      padding: 2rem;
    }

    .cards {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1rem;
    }

    .card {
      width: 260px;
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      background-color: rgba(255, 255, 255, 0.8);
      transition: transform 0.3s;
    }

    .card img {
      width: 100%;
      height: 160px;
      object-fit: cover;
    }

    .card:hover {
      transform: scale(1.03);
    }

    .card-content {
      padding: 1rem;
    }

    footer {
      text-align: center;
      padding: 1rem;
      background: rgba(0,0,0,0.05);
      font-size: 0.9rem;
    }

    /* Animation spray effect */
    body::before {
      content: "";
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: radial-gradient(circle at top left, #ff9a9e 0%, transparent 40%),
                  radial-gradient(circle at bottom right, #a1c4fd 0%, transparent 40%);
      opacity: 0.4;
      z-index: -1;
      animation: spray 10s linear infinite alternate;
    }

    @keyframes spray {
      0% {
        transform: scale(1) rotate(0deg);
      }
      100% {
        transform: scale(1.1) rotate(1deg);
      }
    }

    .hidden {
      display: none;
    }
  </style>
</head>
<body>

<header>
  <h1 id="title">北海道観光ガイド</h1>
  <p id="subtitle">季節ごとのおすすめスポット</p>
</header>

<div class="lang-switcher">
  <label for="language" id="lang-label">言語：</label>
  <select id="language">
    <option value="ja">日本語</option>
    <option value="en">English</option>
    <option value="zh">中文</option>
    <option value="fr">Français</option>
    <option value="ru">Русский</option>
  </select>
</div>

<div class="mode-switcher">
  <button onclick="toggleMode()">ライト / ダークモード切替</button>
</div>

<section class="season-section">
  <h2 id="spring">🌸 春のおすすめ</h2>
  <div class="cards">
    <div class="card">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Sapporo_TV_Tower_and_Odori_Park.jpg/800px-Sapporo_TV_Tower_and_Odori_Park.jpg" alt="Sapporo TV Tower">
      <div class="card-content">
        <h3>札幌テレビ塔</h3>
        <p>大通公園から望む春の絶景</p>
      </div>
    </div>
    <div class="card">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1f/Otaru_canal.jpg/800px-Otaru_canal.jpg" alt="Otaru Canal">
      <div class="card-content">
        <h3>小樽運河</h3>
        <p>桜並木とレトロな街並み</p>
      </div>
    </div>
    <div class="card">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a6/Goryokaku_Sakura.jpg/800px-Goryokaku_Sakura.jpg" alt="Goryokaku">
      <div class="card-content">
        <h3>五稜郭</h3>
        <p>桜の名所、星形の要塞公園</p>
      </div>
    </div>
  </div>
</section>

<section class="season-section">
  <h2 id="summer">🌻 夏のおすすめ</h2>
  <div class="cards">
    <div class="card">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Niseko_Summer.jpg/800px-Niseko_Summer.jpg" alt="Niseko Summer">
      <div class="card-content">
        <h3>ニセコの高原</h3>
        <p>避暑地でのアクティビティが充実</p>
      </div>
    </div>
    <div class="card">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8c/Kushiro_Wetland.jpg/800px-Kushiro_Wetland.jpg" alt="Kushiro Wetlands">
      <div class="card-content">
        <h3>釧路湿原</h3>
        <p>夏の自然と野生動物観察</p>
      </div>
    </div>
  </div>
</section>

<footer>
  &copy; 2025 Hokkaido Travel Guide
</footer>

<script>
  const translations = {
    ja: {
      title: "北海道観光ガイド",
      subtitle: "季節ごとのおすすめスポット",
      "lang-label": "言語：",
      spring: "🌸 春のおすすめ",
      summer: "🌻 夏のおすすめ"
    },
    en: {
      title: "Hokkaido Travel Guide",
      subtitle: "Seasonal Recommended Spots",
      "lang-label": "Language:",
      spring: "🌸 Spring Highlights",
      summer: "🌻 Summer Highlights"
    },
    zh: {
      title: "北海道旅游指南",
      subtitle: "四季推荐景点",
      "lang-label": "语言：",
      spring: "🌸 春季推荐",
      summer: "🌻 夏季推荐"
    },
    fr: {
      title: "Guide touristique de Hokkaido",
      subtitle: "Lieux recommandés par saison",
      "lang-label": "Langue :",
      spring: "🌸 Recommandations pour le printemps",
      summer: "🌻 Recommandations pour l'été"
    },
    ru: {
      title: "Путеводитель по Хоккайдо",
      subtitle: "Рекомендованные места по сезонам",
      "lang-label": "Язык:",
      spring: "🌸 Весенние рекомендации",
      summer: "🌻 Летние рекомендации"
    }
  };

  const langSelect = document.getElementById("language");

  langSelect.addEventListener("change", () => {
    const selected = langSelect.value;
    const dict = translations[selected];
    document.getElementById("title").textContent = dict.title;
    document.getElementById("subtitle").textContent = dict.subtitle;
    document.getElementById("lang-label").textContent = dict["lang-label"];
    document.getElementById("spring").textContent = dict.spring;
    document.getElementById("summer").textContent = dict.summer;
  });

  function toggleMode() {
    document.body.classList.toggle("dark-mode");
  }
</script>

</body>
</html>
