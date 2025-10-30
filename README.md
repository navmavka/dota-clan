<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Мавка из Нави</title>
  <style>
      @import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@500;600&family=Manrope:wght@400;600&display=swap');

      /* --- Общие стили --- */
      body {
          margin: 0;
          font-family: 'Manrope', sans-serif;
          background: radial-gradient(circle at center, #0b0b0b 0%, #1a1a1a 100%);
          color: #dcdcdc;
          overflow-x: hidden;
          position: relative;
      }

      .fog {
          position: fixed;
          top: 0;
          left: 0;
          width: 200%;
          height: 200%;
          background: radial-gradient(circle at 30% 50%, rgba(255,255,255,0.05), transparent 70%),
          radial-gradient(circle at 70% 60%, rgba(255,255,255,0.03), transparent 80%);
          animation: fogMove 60s linear infinite;
          z-index: 0;
      }

      @keyframes fogMove {
          from { transform: translate(0, 0); }
          to { transform: translate(-50%, -50%); }
      }

      header {
          text-align: center;
          padding: 80px 20px 40px;
          position: relative;
          z-index: 1;
      }

      header h1 {
          font-family: 'Cormorant Garamond', serif;
          font-size: 3.5rem;
          color: #bdb8a3;
          letter-spacing: 1px;
          text-shadow: 0 0 20px rgba(200,200,200,0.15);
          animation: flicker 3s infinite;
      }

      @keyframes flicker {
          0%, 19%, 21%, 23%, 25%, 54%, 56%, 100% {
              opacity: 1;
              text-shadow: 0 0 20px rgba(200,200,200,0.15), 0 0 40px rgba(189,184,163,0.15);
          }
          20%, 24%, 55% {
              opacity: 0.8;
              text-shadow: 0 0 5px rgba(189,184,163,0.1);
          }
      }

      header p {
          font-style: italic;
          color: #9d9d9d;
          max-width: 600px;
          margin: 15px auto 0;
          font-size: 1rem;
      }

      section {
          position: relative;
          z-index: 1;
      }

      .about {
          text-align: center;
          max-width: 800px;
          margin: 60px auto;
          padding: 0 20px;
          line-height: 1.8;
          color: #bfbfbf;
          font-size: 1.05rem;
      }

      .about strong {
          color: #bdb8a3;
          font-family: 'Cormorant Garamond', serif;
          font-weight: 600;
      }

      /* --- Карточки игроков --- */
      .cards {
          display: grid;
          grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
          gap: 24px;
          max-width: 1000px;
          margin: 0 auto 100px;
          padding: 0 20px;
      }

      .card {
          background: rgba(30, 30, 30, 0.85);
          border: 1px solid rgba(255,255,255,0.05);
          border-radius: 16px;
          padding: 24px;
          text-align: center;
          transition: transform 0.3s, box-shadow 0.3s;
          backdrop-filter: blur(5px);
      }

      .card:hover {
          transform: translateY(-6px);
          box-shadow: 0 0 20px rgba(189,184,163,0.2);
      }

      .avatar {
          width: 100px;
          height: 100px;
          border-radius: 50%;
          background: #222;
          margin: 0 auto 18px;
          display: flex;
          align-items: center;
          justify-content: center;
          font-size: 2rem;
          color: #bdb8a3;
          border: 1px solid rgba(255,255,255,0.08);
      }

      .card h3 {
          font-family: 'Cormorant Garamond', serif;
          margin: 10px 0 5px;
          color: #e2e2e2;
          font-size: 1.4rem;
      }

      .role {
          font-size: 0.9rem;
          color: #999;
          margin-bottom: 12px;
      }

      .quote {
          font-style: italic;
          color: #888;
          font-size: 0.9rem;
      }

      /* --- Новый раздел: Летопись --- */
      .chronicles {
          background: rgba(15,15,15,0.5);
          padding: 80px 20px;
          border-top: 1px solid rgba(255,255,255,0.05);
          border-bottom: 1px solid rgba(255,255,255,0.05);
      }

      .chronicles h2 {
          text-align: center;
          font-family: 'Cormorant Garamond', serif;
          font-size: 2.5rem;
          color: #bdb8a3;
          margin-bottom: 50px;
          text-shadow: 0 0 10px rgba(189,184,163,0.15);
      }

      .stories {
          display: grid;
          grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
          gap: 30px;
          max-width: 1000px;
          margin: 0 auto;
      }

      .story {
          background: rgba(35,35,35,0.85);
          border-radius: 12px;
          padding: 28px;
          border: 1px solid rgba(255,255,255,0.05);
          box-shadow: inset 0 0 10px rgba(0,0,0,0.3);
          transition: transform 0.3s, box-shadow 0.3s;
          font-size: 0.95rem;
          color: #c8c8c8;
      }

      .story:hover {
          transform: translateY(-5px);
          box-shadow: 0 0 25px rgba(189,184,163,0.15);
      }

      .story h4 {
          font-family: 'Cormorant Garamond', serif;
          color: #d2ccae;
          font-size: 1.3rem;
          margin-bottom: 8px;
      }

      .story p {
          line-height: 1.6;
          font-style: italic;
          color: #a7a7a7;
      }

      footer {
          text-align: center;
          padding: 30px;
          color: #777;
          font-size: 0.9rem;
          border-top: 1px solid rgba(255,255,255,0.05);
          letter-spacing: 0.5px;
          position: relative;
          z-index: 1;
      }

      footer span {
          color: #bdb8a3;
          font-family: 'Cormorant Garamond', serif;
      }

      .legends {
          text-align: center;
          padding: 80px 20px;
          position: relative;
          z-index: 1;
      }

      .legends h2 {
          font-family: 'Cormorant Garamond', serif;
          font-size: 2.4rem;
          color: #bdb8a3;
          margin-bottom: 50px;
          letter-spacing: 1px;
          text-shadow: 0 0 20px rgba(200,200,200,0.1);
          animation: flicker 3s infinite ease-in-out;
      }

      .legend-cards {
          display: grid;
          grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
          gap: 30px;
          max-width: 900px;
          margin: 0 auto;
      }

      .legend-card {
          background: rgba(25, 25, 25, 0.8);
          border: 1px solid rgba(255,255,255,0.05);
          border-radius: 16px;
          padding: 28px 20px;
          text-align: left;
          color: #ccc;
          transition: transform 0.3s ease, box-shadow 0.3s ease;
          backdrop-filter: blur(4px);
          position: relative;
      }

      .legend-card:hover {
          transform: translateY(-6px);
          box-shadow: 0 0 25px rgba(189,184,163,0.2);
      }

      .legend-card .icon {
          font-size: 2rem;
          margin-bottom: 10px;
          color: #bdb8a3;
      }

      .legend-card h3 {
          font-family: 'Cormorant Garamond', serif;
          color: #e2e2e2;
          margin: 10px 0;
          font-size: 1.4rem;
      }

      .legend-card p {
          font-size: 0.95rem;
          line-height: 1.6;
          color: #a6a6a6;
      }
  </style>
</head>
<body>
<div class="fog"></div>

<header>
  <h1>Мавка из Нави</h1>
  <p>Мёртв, но не забыт. Навь зовёт — и мы идём в мид.</p>
</header>

<section class="about">
  <p>
    <strong>Мавка</strong> — дитя, умершее без крещения или от рук матери.
    <strong>Навь</strong> — мир мёртвых, где отдыхают те, кто не успел нафармить БКБ.
    <br><br>
    Наш клан создан не ради побед — а ради рофлов, душ и вечных камбеков на 80-й минуте.
    <br>Мавка не фидит — <strong>Мавка уводит душу саппорта</strong>.
  </p>
</section>

<section class="cards">
  <div class="card">
    <div class="avatar">🕯️</div>
    <h3>Na'Вий Мертвец</h3>
    <div class="role">Капитан / Позиция 5</div>
    <p class="quote">“Я не мёртв, я просто на кд.”</p>
  </div>

  <div class="card">
    <div class="avatar">👻</div>
    <h3>Маленькая Мавка</h3>
    <div class="role">Керри / Душегуб</div>
    <p class="quote">“Кричи ‘мисс’, пока можешь.”</p>
  </div>

  <div class="card">
    <div class="avatar">💀</div>
    <h3>Батя из Нави</h3>
    <div class="role">Оффлейн / Отца нет</div>
    <p class="quote">“Фармлю, не мешай — я на кладбище.”</p>
  </div>

  <div class="card">
    <div class="avatar">🪦</div>
    <h3>Тень Мида</h3>
    <div class="role">Мидер / Призрак</div>
    <p class="quote">“Если я пропал — значит, в смоке.”</p>
  </div>

  <div class="card">
    <div class="avatar">🦴</div>
    <h3>Саппорт Нави</h3>
    <div class="role">Позиция 4 / Живёт на вардах</div>
    <p class="quote">“Моё богатство — вижен.”</p>
  </div>

  <div class="card">
    <div class="avatar">🩸</div>
    <h3>Древняя Мавка</h3>
    <div class="role">Аналитик / Отвлекает смерть</div>
    <p class="quote">“Если не выиграли — значит, не время.”</p>
  </div>
</section>

<section class="chronicles">
  <h2>Летопись Нави</h2>
  <div class="stories">
    <div class="story">
      <h4>Падение и Воскрешение</h4>
      <p>Когда Мавка впервые пошла в мид, сервер завис. С тех пор нас боятся даже на паблике. Говорят, в тот день упал Dota+.</p>
    </div>
    <div class="story">
      <h4>Рошан, что не успел</h4>
      <p>На 67-й минуте Батя из Нави пошёл соло на Рошана. Никто не знает, кто умер первым. Но обоих нашли без аегиса.</p>
    </div>
    <div class="story">
      <h4>Камбек из Нави</h4>
      <p>Проигрывая 60 тысяч нетворса, мы выиграли на морали и рофлах. Враг просто ливнул, не выдержав духовного давления.</p>
    </div>
  </div>
</section>

<section class="legends">
  <h2>Легенды Нави</h2>
  <div class="legend-cards">
    <div class="legend-card">
      <div class="icon">🔥</div>
      <h3>Проклятие 322</h3>
      <p>
        Говорят, один керри однажды продал катку ради бутылки манго.
        С тех пор его дух бродит по миду, шепча: <em>“ещё один фид — и всё сначала...”</em>
      </p>
    </div>

    <div class="legend-card">
      <div class="icon">🌑</div>
      <h3>Туман на Рошане</h3>
      <p>
        Когда пятеро входят в яму, но выходит только один — знай, Навь приняла жертву.
        И Рошан доволен.
      </p>
    </div>

    <div class="legend-card">
      <div class="icon">🕯️</div>
      <h3>Свеча саппорта</h3>
      <p>
        Пока горит его вижен — команда жива.
        Но когда последний вард гаснет, даже древний начинает плакать.
      </p>
    </div>
  </div>
</section>


<footer>
  © 2025 <span>Мавка из Нави</span>. Все души сохранены.
</footer>
</body>
</html>
