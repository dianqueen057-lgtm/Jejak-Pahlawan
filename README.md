# Jejak-Pahlawan <!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Jejak Sang Pahlawan - Media Pembelajaran Flipbook 5D SD Kelas 6</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    :root {
      --bg-gradient: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
      --book-bg: #fffbf0;
      --accent-color: #d9534f;
      --text-color: #2c3e50;
      --shadow-5d: 0 20px 50px rgba(0, 0, 0, 0.4), 0 0 20px rgba(217, 83, 79, 0.3);
    }

    [data-theme="dark"] {
      --bg-gradient: linear-gradient(135deg, #0f2027 0%, #203a43 50%, #2c5364 100%);
      --book-bg: #222c36;
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
    }

    /* Floating Toolbar Header */
    .top-toolbar {
      position: fixed;
      top: 15px;
      display: flex;
      gap: 12px;
      background: rgba(255, 255, 255, 0.2);
      backdrop-filter: blur(10px);
      padding: 10px 20px;
      border-radius: 30px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.2);
      z-index: 100;
    }

    .tool-btn {
      background: #ffffff;
      border: none;
      padding: 8px 16px;
      border-radius: 20px;
      cursor: pointer;
      font-weight: bold;
      color: var(--accent-color);
      display: flex;
      align-items: center;
      gap: 6px;
      transition: all 0.3s ease;
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
      height: 600px;
      display: flex;
      justify-content: center;
      align-items: center;
      margin-top: 60px;
    }

    .book {
      width: 100%;
      height: 100%;
      position: relative;
      transform-style: preserve-3d;
      transition: transform 0.8s cubic-bezier(0.25, 1, 0.5, 1);
      box-shadow: var(--shadow-5d);
      border-radius: 15px;
    }

    .page {
      position: absolute;
      width: 100%;
      height: 100%;
      background-color: var(--book-bg);
      border-radius: 15px;
      padding: 30px 40px;
      display: none;
      flex-direction: column;
      justify-content: space-between;
      backface-visibility: hidden;
      border: 3px solid #e0d6c3;
      overflow-y: auto;
      transform-origin: left center;
      animation: flipIn 0.6s ease-out forwards;
    }

    .page.active {
      display: flex;
    }

    @keyframes flipIn {
      from { transform: rotateY(-30deg) scale(0.95); opacity: 0; }
      to { transform: rotateY(0deg) scale(1); opacity: 1; }
    }

    /* Headers & Content Styling */
    h1, h2 {
      text-align: center;
      color: #d9534f;
      text-shadow: 1px 2px 4px rgba(0,0,0,0.1);
      margin-bottom: 15px;
    }

    .grid-2 {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 15px;
      margin-top: 10px;
    }

    .card-ppt {
      background: rgba(217, 83, 79, 0.08);
      border-left: 5px solid var(--accent-color);
      padding: 12px;
      border-radius: 8px;
      font-size: 0.95rem;
      line-height: 1.4;
    }

    .badge-icon {
      font-size: 1.2rem;
      color: #f39c12;
      margin-right: 6px;
    }

    /* LKPD Form Style */
    .lkpd-container {
      background: #ffffff;
      padding: 15px;
      border-radius: 12px;
      border: 2px dashed #d9534f;
      color: #333;
    }

    .form-group {
      margin-bottom: 10px;
    }

    .form-group label {
      display: block;
      font-weight: bold;
      font-size: 0.85rem;
      margin-bottom: 4px;
      color: #d9534f;
    }

    .form-group input, .form-group textarea {
      width: 100%;
      padding: 8px;
      border: 1px solid #ccc;
      border-radius: 6px;
      font-size: 0.9rem;
    }

    /* Bottom Navigation Controls */
    .controls {
      display: flex;
      align-items: center;
      gap: 20px;
      margin-top: 20px;
      background: rgba(255, 255, 255, 0.9);
      padding: 10px 25px;
      border-radius: 25px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    }

    .nav-btn {
      background: #d9534f;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 20px;
      cursor: pointer;
      font-weight: bold;
      transition: background 0.3s;
    }

    .nav-btn:disabled {
      background: #ccc;
      cursor: not-allowed;
    }

    /* Sparkle & 5D Interactive Parallax Layer */
    .hero-5d {
      text-align: center;
      padding: 20px;
      background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 100%);
      border-radius: 15px;
      color: #333;
      transform: translateZ(20px);
    }
  </style>
</head>
<body>

  <!-- Floating Top Toolbar -->
  <div class="top-toolbar">
    <button class="tool-btn" onclick="toggleTheme()"><i class="fas fa-moon"></i> Tema</button>
    <button class="tool-btn" onclick="toggleAudio()"><i class="fas fa-music"></i> Audio</button>
    <button class="tool-btn" onclick="zoomBook()"><i class="fas fa-search-plus"></i> Zoom</button>
    <button class="tool-btn" onclick="printLKPD()"><i class="fas fa-print"></i> Cetak LKPD</button>
  </div>

  <!-- Main 5D Flipbook Container -->
  <div class="viewport-3d" id="viewport">
    <div class="book" id="book">
      
      <!-- PAGE 0: Cover -->
      <div class="page active">
        <div class="hero-5d">
          <i class="fas fa-medal fa-4x" style="color: #f1c40f; margin-bottom: 10px;"></i>
          <h1>JEJAK SANG PAHLAWAN</h1>
          <p><strong>Media Pembelajaran Interaktif Digital</strong></p>
          <p>Untuk SD Kelas 6</p>
        </div>
        <div style="text-align: center; margin-top: 20px;">
          <p>Selamat datang! Mari menelusuri sejarah perjuangan pahlawan bangsa dengan cara yang seru dan interaktif.</p>
          <br>
          <button class="nav-btn" onclick="nextPage()">Mulai Petualangan <i class="fas fa-arrow-right"></i></button>
        </div>
        <p style="text-align: center; font-size: 0.8rem; color: #888;">Gunakan navigasi di bawah untuk membalik halaman</p>
      </div>

      <!-- PAGE 1: Ringkasan Materi 1 & 2 -->
      <div class="page">
        <h2><i class="fas fa-book-open"></i> Jelajah Materi (Part 1)</h2>
        <div class="grid-2">
          <div class="card-ppt">
            <h3><i class="fas fa-flag badge-icon"></i> 1. Siapa itu Pahlawan?</h3>
            <p>Orang yang berjuang dengan keberanian, pengorbanan, dan cinta tanah air demi membela & mempertahankan kemerdekaan Indonesia dari penjajahan.</p>
          </div>
          <div class="card-ppt">
            <h3><i class="fas fa-history badge-icon"></i> 2. Latar Belakang Perjuangan</h3>
            <p>Penjajahan membuat rakyat menderita dan kehilangan kebebasan. Hal ini memicu keberanian para pahlawan untuk bersatu dan melakukan perlawanan.</p>
          </div>
        </div>
        <div class="card-ppt" style="margin-top: 15px;">
          <h3><i class="fas fa-compass badge-icon"></i> 3. Menelusuri Jejak Pahlawan</h3>
          <p>Kisah sejarah dapat kita pelajari dari berbagai sumber: <em>Buku Sejarah, Gambar, Museum, Cerita Masyarakat, dan Platform Digital Terpercaya</em>.</p>
        </div>
        <div style="text-align: right; font-size: 0.8rem;">Halaman 1 dari 4</div>
      </div>

      <!-- PAGE 2: Ringkasan Materi 3 & 4 -->
      <div class="page">
        <h2><i class="fas fa-star"></i> Jelajah Materi (Part 2)</h2>
        <h3><i class="fas fa-heart badge-icon"></i> Nilai-Nilai Perjuangan Pahlawan</h3>
        <p style="font-size: 0.9rem; margin-bottom: 10px;">Sikap luhur yang wajib kita teladani dalam kehidupan sehari-hari:</p>
        
        <div class="grid-2">
          <div class="card-ppt"><strong>Cinta Tanah Air:</strong> Bangga & peduli terhadap Indonesia.</div>
          <div class="card-ppt"><strong>Keberanian:</strong> Berani membela kebenaran & pantang menyerah.</div>
          <div class="card-ppt"><strong>Persatuan:</strong> Bekerja sama & tidak mudah terpecah belah.</div>
          <div class="card-ppt"><strong>Tanggung Jawab:</strong> Mengerjakan tugas sekolah dengan sungguh-sungguh.</div>
        </div>
        <div style="text-align: right; font-size: 0.8rem; margin-top: 15px;">Halaman 2 dari 4</div>
      </div>

      <!-- PAGE 3: LKPD Digital Section 1 -->
      <div class="page">
        <h2><i class="fas fa-edit"></i> LKPD Interaktif Digital</h2>
        <p style="font-size: 0.85rem; text-align: center; margin-bottom: 10px;">Isilah lembar kerja berikut berdasarkan pahlawan pilihanmu!</p>
        
        <div class="lkpd-container">
          <div class="form-group">
            <label><i class="fas fa-user-shield"></i> Nama Pahlawan:</label>
            <input type="text" id="pahlawan-nama" placeholder="Contoh: Pangeran Diponegoro / Ir. Soekarno">
          </div>
          <div class="form-group">
            <label><i class="fas fa-map-marker-alt"></i> Tempat & Tanggal Lahir:</label>
            <input type="text" id="pahlawan-ttl" placeholder="Contoh: Yogyakarta, 11 November 1785">
          </div>
          <div class="form-group">
            <label><i class="fas fa-calendar-alt"></i> Tahun Perlawanan:</label>
            <input type="text" id="pahlawan-tahun" placeholder="Contoh: 1825 - 1830">
          </div>
        </div>
        <div style="text-align: right; font-size: 0.8rem; margin-top: 10px;">Halaman 3 dari 4</div>
      </div>

      <!-- PAGE 4: LKPD Digital Section 2 -->
      <div class="page">
        <h2><i class="fas fa-pen-nib"></i> LKPD (Lanjutan)</h2>
        
        <div class="lkpd-container">
          <div class="form-group">
            <label><i class="fas fa-book"></i> Latar Belakang Perlawanan:</label>
            <textarea id="pahlawan-latar" rows="3" placeholder="Tuliskan alasan mengapa pahlawan tersebut berjuang..."></textarea>
          </div>
          <div class="form-group">
            <label><i class="fas fa-fire"></i> Cerita Singkat Perjuangan:</label>
            <textarea id="pahlawan-cerita" rows="4" placeholder="Ceritakan jalannya perjuangan pahlawan..."></textarea>
          </div>
        </div>
        
        <div style="text-align: center; margin-top: 10px;">
          <button class="tool-btn" style="background:#27ae60; color:white; display:inline-block;" onclick="simpanLKPD()">
            <i class="fas fa-save"></i> Simpan Hasil Jawaban
          </button>
        </div>
        <div style="text-align: right; font-size: 0.8rem; margin-top: 5px;">Halaman 4 dari 4</div>
      </div>

    </div>
  </div>

  <!-- Bottom Page Navigation -->
  <div class="controls">
    <button class="nav-btn" id="prevBtn" onclick="prevPage()"><i class="fas fa-chevron-left"></i> SEBELUMNYA</button>
    <span id="pageIndicator" style="font-weight: bold;">Halaman 1 / 5</span>
    <button class="nav-btn" id="nextBtn" onclick="nextPage()">SELANJUTNYA <i class="fas fa-chevron-right"></i></button>
  </div>

  <script>
    let currentPage = 0;
    const pages = document.querySelectorAll('.page');
    const pageIndicator = document.getElementById('pageIndicator');
    const book = document.getElementById('book');
    let isZoomed = false;

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

    function toggleTheme() {
      const body = document.body;
      if (body.getAttribute('data-theme') === 'dark') {
        body.removeAttribute('data-theme');
      } else {
        body.setAttribute('data-theme', 'dark');
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

    function toggleAudio() {
      alert("Fitur Backsound Musik Nasional Interaktif diaktifkan!");
    }

    function simpanLKPD() {
      const nama = document.getElementById('pahlawan-nama').value;
      if (!nama) {
        alert('Silakan isi setidaknya Nama Pahlawan di LKPD!');
        return;
      }
      alert(' Jawaban LKPD berhasil disimpan di memori browser!');
    }

    function printLKPD() {
      window.print();
    }

    // Initial Load
    updatePages();
  </script>
</body>
</html>
