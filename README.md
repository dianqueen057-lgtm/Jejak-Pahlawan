#Jejak Sang Pahlawan
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Misi Pahlawan - Media Pembelajaran Laptop SD Kelas 6</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Fredoka+One&family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
  
  <style>
    :root {
      --primary: #FF4757;
      --secondary: #FFA502;
      --accent: #2ED573;
      --dark: #2F3542;
      --bg-gradient: linear-gradient(135deg, #0f2027 0%, #203a43 50%, #2c5364 100%);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Poppins', sans-serif;
    }

    body {
      background: var(--bg-gradient);
      min-height: 100vh;
      color: var(--dark);
      display: flex;
      flex-direction: column;
      overflow-x: hidden;
    }

    /* HEADER LAPTOP */
    header {
      background: rgba(255, 255, 255, 0.15);
      backdrop-filter: blur(15px);
      padding: 12px 40px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 2px solid rgba(255, 255, 255, 0.2);
    }

    .logo-title {
      font-family: 'Fredoka One', cursive;
      font-size: 1.8rem;
      color: #FFF;
      text-shadow: 2px 2px 0px var(--primary);
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .btn-game {
      background: var(--secondary);
      color: #fff;
      border: none;
      padding: 10px 22px;
      border-radius: 25px;
      font-weight: 700;
      cursor: pointer;
      box-shadow: 0 4px 0px #d35400;
      transition: all 0.2s ease;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .btn-game:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 0px #d35400;
    }

    /* LAYOUT HORISONTAL KHUSUS LAPTOP (2 KOLOM) */
    .laptop-container {
      display: grid;
      grid-template-columns: 380px 1fr;
      gap: 25px;
      max-width: 1300px;
      width: 95%;
      margin: 20px auto;
      height: calc(100vh - 110px);
    }

    /* PANEL KIRI: ANIMASI PAHLAWAN BERGERAK */
    .left-panel {
      background: rgba(255, 255, 255, 0.95);
      border-radius: 25px;
      padding: 25px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: space-between;
      box-shadow: 0 15px 35px rgba(0,0,0,0.3);
      border: 4px solid #FFF;
      text-align: center;
    }

    .panel-title {
      font-family: 'Fredoka One', cursive;
      color: var(--primary);
      font-size: 1.5rem;
    }

    /* CAROUSEL / CARDS ANIMASI PAHLAWAN */
    .hero-display-box {
      width: 100%;
      background: #FFF8E7;
      border: 3px dashed var(--secondary);
      border-radius: 20px;
      padding: 15px;
      animation: float 4s ease-in-out infinite;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0px) rotate(0deg); }
      50% { transform: translateY(-10px) rotate(1deg); }
    }

    .hero-svg-large {
      width: 100%;
      height: 200px;
    }

    .hero-name-tag {
      font-family: 'Fredoka One', cursive;
      font-size: 1.2rem;
      color: var(--dark);
      margin-top: 10px;
      background: #FFF;
      padding: 6px 15px;
      border-radius: 15px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.05);
    }

    /* PANEL KANAN: KONTEN MATERI & KUIS */
    .right-panel {
      background: rgba(255, 255, 255, 0.95);
      border-radius: 25px;
      padding: 25px 30px;
      box-shadow: 0 15px 35px rgba(0,0,0,0.3);
      border: 4px solid #FFF;
      display: flex;
      flex-direction: column;
      overflow-y: auto;
    }

    .nav-tabs {
      display: flex;
      gap: 15px;
      margin-bottom: 20px;
      border-bottom: 2px solid #E4E7EB;
      padding-bottom: 12px;
    }

    .tab-btn {
      background: #E4E7EB;
      border: none;
      padding: 12px 25px;
      border-radius: 20px;
      font-weight: 700;
      cursor: pointer;
      font-size: 1rem;
      transition: all 0.3s;
    }

    .tab-btn.active {
      background: var(--primary);
      color: #FFF;
      box-shadow: 0 5px 15px rgba(255, 71, 87, 0.4);
    }

    .tab-content {
      display: none;
      height: 100%;
    }

    .tab-content.active {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    /* CARDS MATERI LANSCAPE */
    .ppt-horizontal-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 15px;
    }

    .ppt-card {
      background: #FFF;
      border-radius: 18px;
      padding: 18px;
      border-top: 6px solid var(--primary);
      box-shadow: 0 5px 15px rgba(0,0,0,0.06);
    }

    .ppt-card h3 {
      font-family: 'Fredoka One', cursive;
      color: var(--primary);
      font-size: 1.1rem;
      margin-bottom: 8px;
    }

    .ppt-card p {
      font-size: 0.9rem;
      color: #555;
      line-height: 1.4;
    }

    /* KUIS BOX LAPTOP */
    .quiz-box {
      background: #FFF8E7;
      border: 3px dashed var(--secondary);
      border-radius: 20px;
      padding: 25px;
      flex: 1;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .quiz-question {
      font-size: 1.25rem;
      font-weight: 700;
      color: var(--dark);
      margin-bottom: 15px;
    }

    .options-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }

    .option-btn {
      background: #FFF;
      border: 2px solid #E4E7EB;
      border-radius: 12px;
      padding: 12px 18px;
      font-size: 0.95rem;
      font-weight: 600;
      cursor: pointer;
      text-align: left;
      transition: all 0.2s;
    }

    .option-btn:hover {
      border-color: var(--secondary);
      background: #FFFBF0;
    }

    .option-btn.correct {
      background: #2ED573 !important;
      color: #FFF !important;
      border-color: #26AF5F !important;
    }

    .option-btn.wrong {
      background: #FF4757 !important;
      color: #FFF !important;
      border-color: #D63031 !important;
    }

    @media (max-width: 900px) {
      .laptop-container { grid-template-columns: 1fr; height: auto; }
      .ppt-horizontal-grid { grid-template-columns: 1fr; }
      .options-grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

  <!-- HEADER -->
  <header>
    <div class="logo-title">
      <i class="fas fa-laptop-code"></i> MISI PAHLAWAN (VERSI LAPTOP)
    </div>
    <button class="btn-game" onclick="restartQuiz()"><i class="fas fa-redo"></i> Ulangi Kuis</button>
  </header>

  <!-- CONTAINER TAMPILAN HORISONAL (LAPTOP) -->
  <div class="laptop-container">
    
    <!-- PANEL KIRI: AVATAR PAHLAWAN BERGERAK -->
    <div class="left-panel">
      <h2 class="panel-title">🎮 TOKOH PAHLAWAN</h2>
      
      <div class="hero-display-box" id="hero-display">
        <!-- SVG Imam Bonjol -->
        <svg class="hero-svg-large" viewBox="0 0 200 220">
          <circle cx="100" cy="110" r="85" fill="#FCF3CF" />
          <path d="M 40 80 Q 100 10 160 80 Q 100 60 40 80 Z" fill="#FFFFFF" stroke="#2C3E50" stroke-width="3"/>
          <ellipse cx="100" cy="115" rx="45" ry="50" fill="#F5CBA7" stroke="#2C3E50" stroke-width="2"/>
          <circle cx="85" cy="110" r="4" fill="#2C3E50"/><circle cx="115" cy="110" r="4" fill="#2C3E50"/>
          <path d="M 85 145 Q 100 180 115 145 Z" fill="#2C3E50"/>
          <path d="M 50 165 L 150 165 L 160 210 L 40 210 Z" fill="#FFFFFF" stroke="#2C3E50" stroke-width="2"/>
        </svg>
        <div class="hero-name-tag" id="hero-name">TUANKU IMAM BONJOL</div>
      </div>

      <button class="btn-game" style="background: var(--accent); width: 100%; justify-content: center;" onclick="nextHero()">
        🔄 Ganti Karakter Pahlawan
      </button>
    </div>

    <!-- PANEL KANAN: MATERI & KUIS -->
    <div class="right-panel">
      
      <div class="nav-tabs">
        <button class="tab-btn active" onclick="switchTab('materi')">📖 Ringkasan Materi</button>
        <button class="tab-btn" onclick="switchTab('kuis')">🏆 Kuis Interaktif</button>
      </div>

      <!-- TAB 1: MATERI (3 CARDS HORISONTAL) -->
      <div id="materi-tab" class="tab-content active">
        <div class="ppt-horizontal-grid">
          
          <div class="ppt-card">
            <h3><i class="fas fa-star"></i> Pengertian Pahlawan</h3>
            <p>Pahlawan adalah sosok yang berjasa memperjuangkan kemerdekaan dan membela bangsa dengan keberanian & pengorbanan.</p>
          </div>

          <div class="ppt-card" style="border-top-color: var(--secondary);">
            <h3><i class="fas fa-history"></i> Latar Belakang Perjuangan</h3>
            <p>Penjajahan menyebabkan rakyat menderita. Keadaan ini mendorong para tokoh bersatu melakukan perlawanan membela tanah air.</p>
          </div>

          <div class="ppt-card" style="border-top-color: var(--accent);">
            <h3><i class="fas fa-heart"></i> Nilai-Nilai Teladan</h3>
            <p>Sikap luhur yang wajib diteladani: <strong>Cinta Tanah Air, Keberanian, Pantang Menyerah, dan Persatuan</strong>.</p>
          </div>

        </div>

        <div style="background: #E8F8F5; padding: 15px; border-radius: 15px; margin-top: 15px; border-left: 5px solid var(--accent);">
          <strong>💡 Tips Belajar:</strong> Setelah membaca ketiga poin di atas, klik tab <strong>"🏆 Kuis Interaktif"</strong> di atas untuk menguji pemahamanmu!
        </div>
      </div>

      <!-- TAB 2: KUIS INTERAKTIF -->
      <div id="kuis-tab" class="tab-content">
        <div class="quiz-box" id="quiz-box-content">
          <div>
            <div style="display:flex; justify-content:space-between; margin-bottom:12px; font-weight:bold;">
              <span id="question-number">Soal 1 / 3</span>
              <span id="score-display" style="color: var(--primary);">Skor: 0</span>
            </div>

            <div class="quiz-question" id="question-text">
              Siapakah sosok yang dinamakan Pahlawan?
            </div>
          </div>

          <div class="options-grid" id="options-container">
            <!-- Option buttons rendered via JS -->
          </div>
        </div>
      </div>

    </div>

  </div>

  <script>
    // CAROUSEL PAHLAWAN PANEL KIRI
    const heroesList = [
      {
        nama: "TUANKU IMAM BONJOL",
        svg: `<svg class="hero-svg-large" viewBox="0 0 200 220">
                <circle cx="100" cy="110" r="85" fill="#FCF3CF" />
                <path d="M 40 80 Q 100 10 160 80 Q 100 60 40 80 Z" fill="#FFFFFF" stroke="#2C3E50" stroke-width="3"/>
                <ellipse cx="100" cy="115" rx="45" ry="50" fill="#F5CBA7" stroke="#2C3E50" stroke-width="2"/>
                <circle cx="85" cy="110" r="4" fill="#2C3E50"/><circle cx="115" cy="110" r="4" fill="#2C3E50"/>
                <path d="M 85 145 Q 100 180 115 145 Z" fill="#2C3E50"/>
                <path d="M 50 165 L 150 165 L 160 210 L 40 210 Z" fill="#FFFFFF" stroke="#2C3E50" stroke-width="2"/>
              </svg>`
      },
      {
        nama: "BUNG TOMO",
        svg: `<svg class="hero-svg-large" viewBox="0 0 200 220">
                <circle cx="100" cy="110" r="85" fill="#D5F5E3" />
                <path d="M 50 70 L 150 70 L 140 40 L 60 40 Z" fill="#1E8449" stroke="#2C3E50" stroke-width="2"/>
                <ellipse cx="100" cy="115" rx="45" ry="50" fill="#F5CBA7" stroke="#2C3E50" stroke-width="2"/>
                <circle cx="85" cy="110" r="4" fill="#2C3E50"/><circle cx="115" cy="110" r="4" fill="#2C3E50"/>
                <path d="M 40 165 L 160 165 L 170 210 L 30 210 Z" fill="#27AE60" stroke="#2C3E50" stroke-width="2"/>
              </svg>`
      },
      {
        nama: "CUT NYAK DIEN",
        svg: `<svg class="hero-svg-large" viewBox="0 0 200 220">
                <circle cx="100" cy="110" r="85" fill="#FADBD8" />
                <circle cx="100" cy="65" r="30" fill="#2C3E50" />
                <ellipse cx="100" cy="115" rx="45" ry="50" fill="#F5CBA7" stroke="#2C3E50" stroke-width="2"/>
                <circle cx="85" cy="110" r="4" fill="#2C3E50"/><circle cx="115" cy="110" r="4" fill="#2C3E50"/>
                <path d="M 40 165 L 160 165 L 170 210 L 30 210 Z" fill="#E74C3C" stroke="#2C3E50" stroke-width="2"/>
              </svg>`
      }
    ];

    let currentHeroIndex = 0;

    function nextHero() {
      currentHeroIndex = (currentHeroIndex + 1) % heroesList.length;
      const hero = heroesList[currentHeroIndex];
      document.getElementById('hero-display').innerHTML = hero.svg + `<div class="hero-name-tag" id="hero-name">${hero.nama}</div>`;
    }

    // SWITCH TAB
    function switchTab(tab) {
      document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
      document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));

      if(tab === 'materi') {
        document.querySelectorAll('.tab-btn')[0].classList.add('active');
        document.getElementById('materi-tab').classList.add('active');
      } else {
        document.querySelectorAll('.tab-btn')[1].classList.add('active');
        document.getElementById('kuis-tab').classList.add('active');
      }
    }

    // LOGIKA KUIS
    const questions = [
      {
        q: "Siapakah sosok yang dinamakan Pahlawan?",
        options: ["Orang yang berjasa membela dan memperjuangkan kemerdekaan bangsa", "Orang yang bekerja mencari keuntungan sendiri", "Orang yang tidak peduli dengan lingkungan sekitar", "Orang yang sering berkelahi"],
        answer: 0
      },
      {
        q: "Apa latar belakang utama para pahlawan melakukan perlawanan?",
        options: ["Ingin menjadi terkenal", "Melawan penderitaan rakyat akibat penjajahan", "Ingin menguasai wilayah lain", "Sekadar mengisi waktu luang"],
        answer: 1
      },
      {
        q: "Berikut ini yang merupakan contoh nilai perjuangan pahlawan adalah...",
        options: ["Mudah menyerah jika ada tugas susah", "Sering membeda-bedakan teman", "Keberanian, cinta tanah air, dan pantang menyerah", "Tidak mau bekerja sama"],
        answer: 2
      }
    ];

    let currentQ = 0;
    let score = 0;

    function loadQuestion() {
      const q = questions[currentQ];
      document.getElementById('question-number').innerText = `Soal ${currentQ + 1} / ${questions.length}`;
      document.getElementById('question-text').innerText = q.q;

      const optsContainer = document.getElementById('options-container');
      optsContainer.innerHTML = '';

      q.options.forEach((opt, index) => {
        const btn = document.createElement('button');
        btn.className = 'option-btn';
        btn.innerText = `${String.fromCharCode(65 + index)}. ${opt}`;
        btn.onclick = () => checkAnswer(index, btn);
        optsContainer.appendChild(btn);
      });
    }

    function checkAnswer(selectedIndex, btn) {
      const q = questions[currentQ];
      const allBtns = document.querySelectorAll('.option-btn');
      allBtns.forEach(b => b.disabled = true);

      if(selectedIndex === q.answer) {
        btn.classList.add('correct');
        score += 35;
        document.getElementById('score-display').innerText = `Skor: ${score}`;
      } else {
        btn.classList.add('wrong');
        allBtns[q.answer].classList.add('correct');
      }

      setTimeout(() => {
        currentQ++;
        if(currentQ < questions.length) {
          loadQuestion();
        } else {
          showFinalScore();
        }
      }, 1300);
    }

    function showFinalScore() {
      document.getElementById('quiz-box-content').innerHTML = `
        <div style="text-align:center; padding:30px;">
          <i class="fas fa-trophy fa-4x" style="color:#F1C40F; margin-bottom:10px;"></i>
          <h2 style="font-family:'Fredoka One'; font-size:2rem; color:var(--primary);">KUIS SELESAI!</h2>
          <p style="font-weight:bold; margin-top:10px;">Skor Akhir Kamu:</p>
          <h1 style="font-size:3.5rem; color:var(--primary); font-family:'Fredoka One';">${score}</h1>
          <button class="btn-game" style="margin:15px auto 0;" onclick="restartQuiz()">Main Lagi</button>
        </div>
      `;
    }

    function restartQuiz() {
      currentQ = 0;
      score = 0;
      document.getElementById('score-display').innerText = `Skor: 0`;
      loadQuestion();
    }

    // Init
    loadQuestion();
  </script>
</body>
</html>
