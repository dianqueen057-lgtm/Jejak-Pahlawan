#Jejak Sang Pahlawan
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Jejak Sang Pahlawan - Flipbook 5D SD Kelas 6</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    :root {
      --primary-color: #d9534f;
      --secondary-color: #f39c12;
      --bg-gradient: linear-gradient(135deg, #1a2a6c 0%, #b21f1f 50%, #fdbb2d 100%);
      --card-bg: #ffffff;
      --text-color: #2c3e50;
      --shadow-5d: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
    }

    [data-theme="dark"] {
      --bg-gradient: linear-gradient(135deg, #0f2027 0%, #203a43 50%, #2c5364 100%);
      --card-bg: #1e272e;
      --text-color: #f1f2f6;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Comic Sans MS', 'Fredoka', 'Poppins', sans-serif;
    }

    body {
      background: var(--bg-gradient);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      color: var(--text-color);
      overflow-x: hidden;
      padding: 20px;
    }

    /* Floating Toolbar Header */
    .top-toolbar {
      position: fixed;
      top: 15px;
      display: flex;
      gap: 10px;
      background: rgba(255, 255, 255, 0.25);
      backdrop-filter: blur(12px);
      padding: 10px 20px;
      border-radius: 30px;
      box-shadow: 0 8px 25px rgba(0,0,0,0.3);
      z-index: 1000;
      flex-wrap: wrap;
      justify-content: center;
    }

    .tool-btn {
      background: #ffffff;
      border: none;
      padding: 8px 16px;
      border-radius: 20px;
      cursor: pointer;
      font-weight: bold;
      color: var(--primary-color);
      display: flex;
      align-items: center;
      gap: 6px;
      transition: all 0.3s ease;
      font-size: 0.85rem;
    }

    .tool-btn:hover {
      transform: translateY(-3px) scale(1.05);
      box-shadow: 0 5px 15px rgba(0,0,0,0.2);
    }

    /* 5D Perspective Book Container */
    .viewport-3d {
      perspective: 2000px;
      width: 100%;
      max-width: 950px;
      height: 650px;
      display: flex;
      justify-content: center;
      align-items: center;
      margin-top: 50px;
    }

    .book {
      width: 100%;
      height: 100%;
      position: relative;
      transform-style: preserve-3d;
      transition: transform 0.8s cubic-bezier(0.25, 1, 0.5, 1);
      box-shadow: var(--shadow-5d);
      border-radius: 20px;
    }

    .page {
      position: absolute;
      width: 100%;
      height: 100%;
      background-color: var(--card-bg);
      border-radius: 20px;
      padding: 25px 35px;
      display: none;
      flex-direction: column;
      justify-content: space-between;
      backface-visibility: hidden;
      border: 4px solid #f1c40f;
      overflow-y: auto;
      transform-origin: left center;
      animation: flipIn 0.6s ease-out forwards;
    }

    .page.active {
      display: flex;
    }

    @keyframes flipIn {
      from { transform: rotateY(-20deg) scale(0.95); opacity: 0; }
      to { transform: rotateY(0deg) scale(1); opacity: 1; }
    }

    h1, h2 {
      text-align: center;
      color: var(--primary-color);
      text-shadow: 1px 2px 4px rgba(0,0,0,0.1);
      margin-bottom: 12px;
    }

    .grid-2 {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 15px;
      margin-top: 10px;
    }

    .card-ppt {
      background: rgba(217, 83, 79, 0.08);
      border-left: 5px solid var(--primary-color);
      padding: 12px;
      border-radius: 10px;
      font-size: 0.9rem;
      line-height: 1.4;
    }

    /* Layout LKPD Seperti PDF */
    .lkpd-canvas {
      display: grid;
      grid-template-columns: 240px 1fr;
      gap: 20px;
      background: #fff8e7;
      border: 3px dashed #d9534f;
      border-radius: 15px;
      padding: 15px;
      color: #333;
    }

    .hero-avatar-box {
      background: #ffffff;
      border: 2px solid #f39c12;
      border-radius: 12px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 10px;
      text-align: center;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }

    .hero-avatar-box svg {
      width: 160px;
      height: 180px;
    }

    .hero-name-badge {
      background: #d9534f;
      color: white;
      padding: 6px 12px;
      border-radius: 15px;
      font-weight: bold;
      font-size: 0.85rem;
      margin-top: 8px;
      width: 100%;
    }

    .lkpd-form {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .field-box {
      background: #ffffff;
      border: 1px solid #e0e0e0;
      border-radius: 8px;
      padding: 8px 12px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.05);
    }

    .field-box label {
      display: block;
      font-size: 0.8rem;
      font-weight: bold;
      color: #d9534f;
      margin-bottom: 4px;
    }

    .field-box input, .field-box textarea {
      width: 100%;
      border: 1px solid #ccc;
      border-radius: 6px;
      padding: 6px 10px;
      font-size: 0.85rem;
      font-family: inherit;
    }

    /* Controls */
    .controls {
      display: flex;
      align-items: center;
      gap: 20px;
      margin-top: 15px;
      background: rgba(255, 255, 255, 0.95);
      padding: 10px 25px;
      border-radius: 25px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    }

    .nav-btn {
      background: var(--primary-color);
      color: white;
      border: none;
      padding: 8px 18px;
      border-radius: 20px;
      cursor: pointer;
      font-weight: bold;
      transition: background 0.3s;
    }

    .nav-btn:disabled {
      background: #ccc;
      cursor: not-allowed;
    }

    .random-btn {
      background: #27ae60;
      color: white;
      border: none;
      padding: 8px 15px;
      border-radius: 20px;
      cursor: pointer;
      font-weight: bold;
      font-size: 0.85rem;
      margin-top: 10px;
      transition: transform 0.2s;
    }

    .random-btn:hover {
      transform: scale(1.05);
    }

    @media print {
      .top-toolbar, .controls, .nav-btn, .random-btn { display: none !important; }
      .viewport-3d, .book, .page { height: auto !important; position: static !important; display: block !important; border: none !important; }
    }
  </style>
</head>
<body>

  <!-- Floating Top Toolbar -->
  <div class="top-toolbar">
    <button class="tool-btn" onclick="toggleTheme()"><i class="fas fa-moon"></i> Tema</button>
    <button class="tool-btn" onclick="speakCurrentPage()"><i class="fas fa-volume-up"></i> Baca Materi</button>
    <button class="tool-btn" onclick="zoomBook()"><i class="fas fa-search-plus"></i> Zoom 5D</button>
    <button class="tool-btn" onclick="cetakLKPD()"><i class="fas fa-print"></i> Cetak/Simpan PDF</button>
  </div>

  <!-- Main 5D Flipbook Container -->
  <div class="viewport-3d" id="viewport">
    <div class="book" id="book">
      
      <!-- COVER PAGE -->
      <div class="page active">
        <div style="text-align: center; padding: 20px; background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 100%); border-radius: 15px; color: #333;">
          <i class="fas fa-award fa-4x" style="color: #f1c40f; margin-bottom: 10px;"></i>
          <h1>JEJAK SANG PAHLAWAN</h1>
          <p><strong>Media Belajar Digital Interaktif Flipbook 5D</strong></p>
          <p>Khusus Kelas 6 Sekolah Dasar</p>
        </div>
        <div style="text-align: center; margin-top: 20px;">
          <p>Mari menelusuri sejarah perjuangan para pahlawan bangsa dan isi LKPD digital secara mandiri!</p>
          <br>
          <button class="nav-btn" onclick="nextPage()">Buka Flipbook <i class="fas fa-arrow-right"></i></button>
        </div>
        <p style="text-align: center; font-size: 0.8rem; color: #888;">Gunakan navigasi di bawah untuk memilih halaman</p>
      </div>

      <!-- PAGE 1: Materi Ringkas PPT Part 1 -->
      <div class="page">
        <h2><i class="fas fa-book-open"></i> Ringkasan Materi (Part 1)</h2>
        <div class="grid-2">
          <div class="card-ppt">
            <h3><i class="fas fa-flag" style="color:#f39c12"></i> 1. Pengertian Pahlawan</h3>
            <p>Pahlawan adalah sosok yang berjasa memperjuangkan kemerdekaan dengan keberanian, semangat, pengorbanan, dan cinta tanah air.</p>
          </div>
          <div class="card-ppt">
            <h3><i class="fas fa-history" style="color:#f39c12"></i> 2. Latar Belakang Perjuangan</h3>
            <p>Penjajahan menyebabkan rakyat menderita dan kehilangan kebebasan. Hal ini menggerakkan pahlawan untuk bersatu melawan musuh.</p>
          </div>
        </div>
        <div class="card-ppt" style="margin-top: 15px;">
          <h3><i class="fas fa-search-location" style="color:#f39c12"></i> 3. Cara Menelusuri Sejarah</h3>
          <p>Kisah pahlawan dapat dipelajari dari buku sejarah, gambar, museum, cerita rakyat, dan media digital terpercaya.</p>
        </div>
        <div style="text-align: right; font-size: 0.8rem; color:#888;">Halaman 1 dari 3</div>
      </div>

      <!-- PAGE 2: Materi Ringkas PPT Part 2 -->
      <div class="page">
        <h2><i class="fas fa-star"></i> Nilai-Nilai Perjuangan</h2>
        <p style="font-size: 0.9rem; margin-bottom: 10px; text-align:center;">Sikap teladan pahlawan yang wajib diterapkan sehari-hari:</p>
        
        <div class="grid-2">
          <div class="card-ppt"><strong>Cinta Tanah Air:</strong> Bangga & peduli terhadap bangsa Indonesia.</div>
          <div class="card-ppt"><strong>Keberanian:</strong> Berani menghadapi kesulitan & membela kebenaran.</div>
          <div class="card-ppt"><strong>Pantang Menyerah:</strong> Tetap berusaha meskipun ada hambatan.</div>
          <div class="card-ppt"><strong>Persatuan:</strong> Bekerja sama dan menjaga kerukunan.</div>
        </div>
        <div style="text-align: right; font-size: 0.8rem; color:#888; margin-top: 20px;">Halaman 2 dari 3</div>
      </div>

      <!-- PAGE 3: LKPD Digital Canvas (Desain Persis PDF) -->
      <div class="page">
        <h2><i class="fas fa-pen-nib"></i> LKPD Interaktif Siswa</h2>
        
        <div class="lkpd-canvas">
          <!-- Sisi Kiri: Gambar Kartun & Nama Pahlawan -->
          <div class="hero-avatar-box">
            <div id="hero-svg-container">
              <!-- Default SVG Kartun Imam Bonjol (Sesuai PDF) -->
              <svg viewBox="0 0 200 220">
                <circle cx="100" cy="110" r="90" fill="#fcf3cf" />
                <!-- Sorban Putih -->
                <path d="M 40 80 Q 100 10 160 80 Q 100 60 40 80 Z" fill="#ffffff" stroke="#333" stroke-width="3"/>
                <path d="M 45 75 Q 100 40 155 75" fill="none" stroke="#ccc" stroke-width="2"/>
                <!-- Muka -->
                <ellipse cx="100" cy="115" rx="45" ry="50" fill="#f5cba7" stroke="#333" stroke-width="2"/>
                <!-- Mata & Alis -->
                <circle cx="85" cy="110" r="4" fill="#333"/>
                <circle cx="115" cy="110" r="4" fill="#333"/>
                <!-- Janggut Hitam -->
                <path d="M 85 145 Q 100 180 115 145 Z" fill="#2c3e50"/>
                <!-- Baju Gamis Putih -->
                <path d="M 50 165 L 150 165 L 160 210 L 40 210 Z" fill="#ffffff" stroke="#333" stroke-width="2"/>
              </svg>
            </div>
            <div class="hero-name-badge" id="display-hero-name">TUANKU IMAM BONJOL</div>
            <button class="random-btn" onclick="acakPahlawan()"><i class="fas fa-dice"></i> 🎲 Acak Pahlawan</button>
          </div>

          <!-- Sisi Kanan: Form Isian LKPD (Kosong Siap Diisi) -->
          <div class="lkpd-form">
            <div class="field-box">
              <label>1. Tempat & Tanggal Lahir:</label>
              <input type="text" id="input-ttl" placeholder="Ketik tempat & tanggal lahir pahlawan di sini...">
            </div>
            <div class="field-box">
              <label>2. Tahun Perlawanan:</label>
              <input type="text" id="input-tahun" placeholder="Ketik tahun masa perjuangan...">
            </div>
            <div class="field-box">
              <label>3. Latar Belakang Perlawanan:</label>
              <textarea id="input-latar" rows="2" placeholder="Tuliskan latar belakang perlawanan..."></textarea>
            </div>
            <div class="field-box">
              <label>4. Cerita Perlawanan:</label>
              <textarea id="input-cerita" rows="3" placeholder="Ceritakan kisah perlawanannya..."></textarea>
            </div>
          </div>
        </div>

        <div style="text-align: center; margin-top: 10px;">
          <button class="nav-btn" style="background:#27ae60;" onclick="simpanJawaban()"><i class="fas fa-save"></i> Simpan Hasil LKPD</button>
        </div>
        <div style="text-align: right; font-size: 0.8rem; color:#888;">Halaman 3 dari 3</div>
      </div>

    </div>
  </div>

  <!-- Bottom Page Navigation Controls -->
  <div class="controls">
    <button class="nav-btn" id="prevBtn" onclick="prevPage()"><i class="fas fa-chevron-left"></i> SEBELUMNYA</button>
    <span id="pageIndicator" style="font-weight: bold;">Halaman 1 / 4</span>
    <button class="nav-btn" id="nextBtn" onclick="nextPage()">SELANJUTNYA <i class="fas fa-chevron-right"></i></button>
  </div>

  <script>
    let currentPage = 0;
    const pages = document.querySelectorAll('.page');
    const pageIndicator = document.getElementById('pageIndicator');
    const book = document.getElementById('book');
    let isZoomed = false;

    // Daftar Pahlawan Kartun (Termasuk Imam Bonjol & Bung Tomo sesuai PDF)
    const listPahlawan = [
      {
        nama: "TUANKU IMAM BONJOL",
        svg: `<svg viewBox="0 0 200 220">
                <circle cx="100" cy="110" r="90" fill="#fcf3cf" />
                <path d="M 40 80 Q 100 10 160 80 Q 100 60 40 80 Z" fill="#ffffff" stroke="#333" stroke-width="3"/>
                <ellipse cx="100" cy="115" rx="45" ry="50" fill="#f5cba7" stroke="#333" stroke-width="2"/>
                <circle cx="85" cy="110" r="4" fill="#333"/><circle cx="115" cy="110" r="4" fill="#333"/>
                <path d="M 85 145 Q 100 180 115 145 Z" fill="#2c3e50"/>
                <path d="M 50 165 L 150 165 L 160 210 L 40 210 Z" fill="#ffffff" stroke="#333" stroke-width="2"/>
              </svg>`
      },
      {
        nama: "BUNG TOMO",
        svg: `<svg viewBox="0 0 200 220">
                <circle cx="100" cy="110" r="90" fill="#d5f5e3" />
                <!-- Peci / Topi Hijau Veteran -->
                <path d="M 50 70 L 150 70 L 140 40 L 60 40 Z" fill="#1e8449" stroke="#333" stroke-width="2"/>
                <ellipse cx="100" cy="115" rx="45" ry="50" fill="#f5cba7" stroke="#333" stroke-width="2"/>
                <circle cx="85" cy="110" r="4" fill="#333"/><circle cx="115" cy="110" r="4" fill="#333"/>
                <!-- Tangan Menunjuk -->
                <path d="M 140 120 L 170 80 L 180 90 Z" fill="#f5cba7" stroke="#333" stroke-width="2"/>
                <!-- Seragam Hijau -->
                <path d="M 40 165 L 160 165 L 170 210 L 30 210 Z" fill="#27ae60" stroke="#333" stroke-width="2"/>
              </svg>`
      },
      {
        nama: "PANGERAN DIPONEGORO",
        svg: `<svg viewBox="0 0 200 220">
                <circle cx="100" cy="110" r="90" fill="#ebdef0" />
                <path d="M 30 85 Q 100 20 170 85 Z" fill="#8e44ad" stroke="#333" stroke-width="2"/>
                <ellipse cx="100" cy="115" rx="45" ry="50" fill="#f5cba7" stroke="#333" stroke-width="2"/>
                <circle cx="85" cy="110" r="4" fill="#333"/><circle cx="115" cy="110" r="4" fill="#333"/>
                <path d="M 40 165 L 160 165 L 160 210 L 40 210 Z" fill="#8e44ad" stroke="#333" stroke-width="2"/>
              </svg>`
      },
      {
        nama: "R.A. KARTINI",
        svg: `<svg viewBox="0 0 200 220">
                <circle cx="100" cy="110" r="90" fill="#fdebd0" />
                <!-- Sanggul -->
                <circle cx="100" cy="60" r="35" fill="#2c3e50" />
                <ellipse cx="100" cy="115" rx="42" ry="48" fill="#f5cba7" stroke="#333" stroke-width="2"/>
                <circle cx="85" cy="110" r="4" fill="#333"/><circle cx="115" cy="110" r="4" fill="#333"/>
                <!-- Kebaya -->
                <path d="M 45 160 L 155 160 L 165 210 L 35 210 Z" fill="#e74c3c" stroke="#333" stroke-width="2"/>
              </svg>`
      }
    ];

    function updatePages() {
      pages.forEach((page, index) => {
        if (index === currentPage) {
          page.classList.add('active');
        } else {
          page.classList.remove('active');
        }
      });
      pageIndicator.innerText = `Halaman ${currentPage + 1} / ${pages.length}`;
      document.getElementById('prevBtn').disabled = (currentPage === 0);
      document.getElementById('nextBtn').disabled = (currentPage === pages.length - 1);
    }

    function nextPage() {
      if (currentPage < pages.length - 1) {
        currentPage++;
        updatePages();
      }
    }

    function prevPage() {
      if (currentPage > 0) {
        currentPage--;
        updatePages();
      }
    }

    // Fungsi Acak Pahlawan: Mengganti Gambar & Nama, serta Menolak Kosongkan Isian LKPD
    function acakPahlawan() {
      const randomIndex = Math.floor(Math.random() * listPahlawan.length);
      const selected = listPahlawan[randomIndex];

      // Update Gambar Kartun & Nama Pahlawan
      document.getElementById('hero-svg-container').innerHTML = selected.svg;
      document.getElementById('display-hero-name').innerText = selected.nama;

      // Kosongkan seluruh form LKPD agar siswa mengisinya sendiri
      document.getElementById('input-ttl').value = '';
      document.getElementById('input-tahun').value = '';
      document.getElementById('input-latar').value = '';
      document.getElementById('input-cerita').value = '';
    }

    function simpanJawaban() {
      const ttl = document.getElementById('input-ttl').value;
      if (!ttl) {
        alert("Silakan isi dulu kolom LKPD sebelum menyimpan!");
        return;
      }
      alert("Jawaban LKPD berhasil disimpan!");
    }

    function speakCurrentPage() {
      const text = pages[currentPage].innerText;
      const utterance = new SpeechSynthesisUtterance(text);
      utterance.lang = 'id-ID';
      speechSynthesis.speak(utterance);
    }

    function toggleTheme() {
      if (document.body.getAttribute('data-theme') === 'dark') {
        document.body.removeAttribute('data-theme');
      } else {
        document.body.setAttribute('data-theme', 'dark');
      }
    }

    function zoomBook() {
      if (!isZoomed) {
        book.style.transform = 'scale(1.15)';
        isZoomed = true;
      } else {
        book.style.transform = 'scale(1)';
        isZoomed = false;
      }
    }

    function cetakLKPD() {
      window.print();
    }

    // Initialize
    updatePages();
  </script>
</body>
</html>
